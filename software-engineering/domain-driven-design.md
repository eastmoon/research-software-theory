## 領域驅動設計 ( Domain-driven design、DDD )

Domain-driven design is predicated on the following goals:

+ placing the project's primary focus on the core domain and domain logic.
> 把專案的主要重點放在核心領域（core domain）和領域邏輯 (domain logic)

+ basing complex designs on a model of the domain.
> 基於領域模型來應對複雜的設計

+ initiating a creative collaboration between technical and domain experts to iteratively refine a conceptual model that addresses particular domain problems.
> 發起一個創意合作在技術和領域專家間疊代完善概念模組，以解決特定領域的問題

Concepts of the DDD include:
> 對於 DDD 觀念與名詞定義，其中包括了英文對特定知識的解釋，這部份用中文未必能完整陳述；但亦可理解對於領域模組的規劃與設計上，很吃重對需求描述的解釋。

+ Context ( 上下文、語境、脈絡 )
> The	setting in which a word or statement appears that determines its meaning. Statements about a model can only be understood in a context.
>
> 依單字與描述的位置來決定其意義；關於模組的描述應從脈絡來了解。

+ Domain ( 領域 )
> A sphere of knowledge, influence, or activity. The subject area to which the user applies a program is the domain of the software.
>
> 一個領域由知識（knowledge），影響 (influence)，或活動 (activity)構成；亦或使用者運用的時機就是該軟體領域的主題區域。

+ Model ( 模組 )
> A system of abstractions that describes selected aspects of a domain and can be used to solve problems related to that domain.
>
> 描述領域中特定方面的抽象系統，並可用於解決領域相關問題。

+ Ubiquitous Language ( 統一語言 )
  > A language structured around the domain model and used by all team members within a bounded context to connect all the activities of the team	with the software.
>
> 一個由領域模組組成的語言，並由團隊成員使用，讓團隊將脈絡邊界 (bounded context) 中所有行為與軟體聯繫起來。

+ Bounded Context ( 脈絡邊界 )
> A description of a boundary ( typically a subsystem, or the work of a particular team ) within which a particular model is defined and applicable.
>
> 對邊界內的描述 ( 通常是指一個子系統或特定團隊的工作 )，包括特定模組的定義與應用。

領域驅動設計 ( Domain-driven design、DDD ) 是一種對領域知識、商業邏輯模組化的方法論，其處理過程類似 OOAD，從領域知識與商業邏輯著手，經過以下步驟來構築：

+ 從領域 ( Domain ) 的脈絡 ( Context ) 中抽出術語 ( Term ) 與描述 ( Statement )
+ 由術語與描述構成統一語言 ( Ubiquitous Language )
+ 經由統一語言來描述問題，並從問題中抽象出對應處理的模組 ( Model )
+ 若模組過度龐大，設定脈絡邊界 ( Bounded Context ) 來切割模組，並避免模組重疊的行為與應用範圍

需要注意，對於問題解析或模組化並沒有一定的步驟，但 DDD 對於模組抽離，並將問題側重在模組的疊代改善，其目的應是『領域模組與軟體技術解耦』，避免『業務邏輯與技術邏輯綁定』從而導致的維護性降低。

另外在使用時機上，在多數的文獻中有提到，DDD 並不適合新創或快速開發的軟體，更適合在需長期維護且開發成熟度高的軟體；這原因是基於前者在商業環境上有其考量，使用 DDD 的方法論會產生的觀念爭論、技術重構將導致開發時程受阻；但也並非不可使用，在初期階段就導入規劃對長期維護是有其幫助，但這必須建立在團隊的觀念統一、技術基礎雄厚，若非如此，考量時程上應避免導入 DDD，直到專案進程有餘裕可進行重構。

## DDD 設計樣式

### Entity

### Value object

### Aggregate

**『Aggregates are the basic element of transfer of data storage — you request to load or save whole aggregates. Transactions should not cross aggregate boundaries.』**

**『1 Aggregate = 1 Repository』**

Aggreate 為領域驅動設計的設計樣式，其主旨在規範一個領域模組的邊界。

誠如 Teddy 在領域驅動設計筆記中所言：

**『領域驅動設計（Domain-Driven Design；DDD）有一個重點就是開發人員與領域專家一起討論領域模型，這個領域模型用來解釋與理解問題領域，成為開發團隊和領域專家在溝通時的通用語言。使用領域模型（Domain Model）而不是資料模型（Data Model），這一點一直是物件導向分析與設計以及DDD的核心，但是以資料庫（或是使用者介面）為主的軟體設計思考方式已經深入許多開發人員的骨子裡。就算已經有了物件導向領域模型，在設計功能（use case或user story）時總是免不了寫出一堆CRUD（新增、讀取、修改、刪除）。』**
> 基於[物件關聯對映 ( Object Relational Mapping、ORM )](https://en.wikipedia.org/wiki/Object-relational_mapping)設計的系統，在呈現到資料庫的整體設計就不會脫離表格的框架。

從上述可以理解，領域模型本身並非單純的資料模型，而是構成資料模型的運算式、數值集合，因此領域模型應由複數的物件構成最後應該輸出的數據集；典型的 ORM 系統並不會產生這樣的數據變化，但若數據需經過演算導致數據升降維度，則表示某些欄位實際上不會透過資料源獲得。

+ [Aggregates in Domain Driven Design](https://medium.com/ingeniouslysimple/5aab3ef9901d)
+ [領域驅動設計學習筆記（5）：Aggregate (上)](http://teddy-chen-tw.blogspot.com/2019/06/5aggregate.html)
+ [領域驅動設計學習筆記（6）：Aggregate (中)](http://teddy-chen-tw.blogspot.com/2019/07/6aggregate.html)
+ [領域驅動設計學習筆記（7）：Aggregate (下)](http://teddy-chen-tw.blogspot.com/2020/01/7aggregate.html)
+ [Design a microservice domain model](https://docs.microsoft.com/zh-tw/dotnet/architecture/microservices/microservice-ddd-cqrs-patterns/microservice-domain-model)

### Domain Event

### Service

### Repository

**『A data persistence abstraction』**

**『Mediates between the domain and data mapping layers using a collection-like interface for accessing domain objects.』**

Repository 為封裝資料實際存取手段的中介物件；在不同的設計細節上，外部程式是透過 Repository 來取得資料，然而取得的資料是源自快取記憶體或雲端資料則取決於被 Repository 封裝的實際存取手段。

![Repository ](https://codewithshadman.com/assets/images/repository-pattern-csharp_structure.png)

+ [P of EAA: Repository](https://martinfowler.com/eaaCatalog/repository.html)
+ [Repository Pattern](https://deviq.com/repository-pattern/)
+ [Repository Pattern C#](https://codewithshadman.com/repository-pattern-csharp/)

### Unit of Work

**『Maintains a list of objects affected by a business transaction and coordinates the writing out of changes and the resolution of concurrency problems.』**

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
## 參考

+ [Domain-driven design Wiki](https://en.wikipedia.org/wiki/Domain-driven_design)
    - [Domain-driven design community](https://dddcommunity.org/)
    - [Teddy 搞笑談軟功](http://teddy-chen-tw.blogspot.com/)
        + [領域驅動設計學習筆記（1）：學習的切入角度（上）](http://teddy-chen-tw.blogspot.com/2016/08/1.html)
        + [領域驅動設計學習筆記（2）：學習的切入角度（下）](http://teddy-chen-tw.blogspot.com/2016/08/2.html)
        + [如何閱讀模型驅動設計建構區塊的模式語言](http://teddy-chen-tw.blogspot.com/2019/12/blog-post_6.html)
    - [Domain Driven Design 簡介和為什麼你需要DDD](https://medium.com/%E7%A7%91%E6%8A%80%E6%96%B0%E6%83%B3/ddd-6cf4ceed6088)
        + [第一步：了解價值鏈與定義領域模型](https://medium.com/%E7%A7%91%E6%8A%80%E6%96%B0%E6%83%B3/b60bb817f43d)
        + [第二步：Bounded Contexts 和其應用](https://medium.com/%E7%A7%91%E6%8A%80%E6%96%B0%E6%83%B3/75c5780dab49)
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
+ [Domain Driven Design (DDD)in Microservice architecture in a nutshell](https://medium.com/@jpdeffo/19c7c579009a)
+ [MartinFowler tagged by: domain driven design](https://martinfowler.com/tags/domain%20driven%20design.html)
