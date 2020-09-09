## 領域驅動設計 ( Domain-driven design、DDD )

## DDD 設計樣式

### Repository

**A data persistence abstraction**

**Mediates between the domain and data mapping layers using a collection-like interface for accessing domain objects.**

Repository 為封裝資料實際存取手段的中介物件；在不同的設計細節上，外部程式是透過 Repository 來取得資料，然而取得的資料是源自快取記憶體或雲端資料則取決於被 Repository 封裝的實際存取手段。

![Repository ](https://codewithshadman.com/assets/images/repository-pattern-csharp_structure.png)

+ [P of EAA: Repository](https://martinfowler.com/eaaCatalog/repository.html)
+ [Repository Pattern](https://deviq.com/repository-pattern/)
+ [Repository Pattern C#](https://codewithshadman.com/repository-pattern-csharp/)

### Unit of Work

**Maintains a list of objects affected by a business transaction and coordinates the writing out of changes and the resolution of concurrency problems.**

Unit of Work 為異步資料源存取衝突時，如何維護受存取的列表可正常運作。

```
SimpleExampleUOW UowObj = new SimpleExampleUOW();
UowObj.Add(Customerobj); // record 1 added to inmemory
UowObj.Add(Supplierobj); // record 1 added to inmemory
UowObj.Commit(); // The full inmemory collection is sent for final commit
```
> 最終 Commit 時，會將整理好的 2 筆新增記錄處理完畢後送出

在異步處理的架構中，大量不確定存取時間的資料最終皆需要些入資料庫，然而資料庫的存取是有其極限，若每一筆交易皆直接寫入資料庫，勢必導致死結 ( Deadlock ) 或處理緩慢；因此，Unit of Work 設計一個物件，供不同資料源再透過不同存取路徑進入系統時，可有效的管理應該寫入的資料；此設計亦可視為一個緩衝快取，確保存取存取頻繁時可減少不必要的動作。

但實際需要注意，實際上 Unit of Work 等同將存取判斷與運算快取在記憶體，而非最終資料庫，這樣的情況可能導致快取消耗過多，導致伺服器異常。

在實務上 Unit of Work 和 Repository 會經常混合使用，其常見原因在若複數 Respository 操作同一個資料表，若要確保最終寫入不會互相衝突，則應該透過 UoW 來管理對資料庫的連線、寫入時機。

```
ExampleUoW uow = new ExampleUoW();
uow.repoA.Add(Customerobj);
uow.repoB.Add(Supplierobj);
uow.commit();
```
> 在結構上，UoW 物件會管理對應的 Repository 物件，而 Respository 則透過 UoW 來對表格操作。

+ [P of EAA: Unit of Work](https://martinfowler.com/eaaCatalog/unitOfWork.html)
+ [Unit of Work Design Pattern](https://www.codeproject.com/Articles/581487)
+ Unit of Work & Repository
    - [Using the Repository and Unit Of Work Pattern in .net core](https://garywoodfine.com/generic-repository-pattern-net-core/)
    - [Repository and Unit of Work Pattern](https://www.programmingwithwolfgang.com/repository-and-unit-of-work-pattern/)

### Aggregate

**Aggregates are the basic element of transfer of data storage — you request to load or save whole aggregates. Transactions should not cross aggregate boundaries.**

**1 Aggregate = 1 Repository**

Aggreate 為領域驅動設計的設計樣式，其主旨在規範一個領域模組的邊界。

誠如 Teddy 在領域驅動設計筆記中所言：

**『領域驅動設計（Domain-Driven Design；DDD）有一個重點就是開發人員與領域專家一起討論領域模型，這個領域模型用來解釋與理解問題領域，成為開發團隊和領域專家在溝通時的通用語言。使用領域模型（Domain Model）而不是資料模型（Data Model），這一點一直是物件導向分析與設計以及DDD的核心，但是以資料庫（或是使用者介面）為主的軟體設計思考方式已經深入許多開發人員的骨子裡。就算已經有了物件導向領域模型，在設計功能（use case或user story）時總是免不了寫出一堆CRUD（新增、讀取、修改、刪除）。』**
> 基於[物件關聯對映 ( Object Relational Mapping、ORM )](https://en.wikipedia.org/wiki/Object-relational_mapping)設計的系統，在呈現到資料庫的整體設計就不會脫離表格的框架。

從上述可以理解，領域模型本身並非單純的資料模型，而是構成資料模型的運算式、數值集合，因此領域模型應由複數的物件構成最後應該輸出的數據集；典型的 ORM 系統並不會產生這樣的數據變化，但若數據需經過演算導致數據升降維度，則表示某些欄位實際上不會透過資料源獲得。

+ [Aggregates in Domain Driven Design](https://medium.com/ingeniouslysimple/5aab3ef9901d)
+ [領域驅動設計學習筆記（5）：Aggregate (上)](http://teddy-chen-tw.blogspot.com/2019/06/5aggregate.html)
+ [領域驅動設計學習筆記（7）：Aggregate (下)](http://teddy-chen-tw.blogspot.com/2020/01/7aggregate.html)
+ [Design a microservice domain model](https://docs.microsoft.com/zh-tw/dotnet/architecture/microservices/microservice-ddd-cqrs-patterns/microservice-domain-model)

## 參考

+ [Domain-driven design Wiki](https://en.wikipedia.org/wiki/Domain-driven_design)
+ [Architecture Pattern with Python](https://www.amazon.com/Architecture-Patterns-Python-Domain-Driven-Microservices/dp/1492052205)
    - Create domain-model to support architecture.
        + Repository，封裝資料存取方方法
        + Unit of Work，避免異步資料源導致存取同步衝突
        + Aggreate，封裝與切分領域模型
    - Architecture implemented method.
        + Message Bus，訊息佇列來管理應被驅動的處理程序
        + Command，異步事件驅動應採用命令區隔
        + CQRS，建立讀寫分離機制
        + Dependency Injection，規劃相依注入來達到規劃系統的運作與測試狀態
