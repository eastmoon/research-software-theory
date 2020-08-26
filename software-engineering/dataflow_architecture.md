## Dataflow architecture

### Layer

The Layer architectural pattern helps to structure applications that can be decomposed into groups of subtasks in which each group of subtasks is at a particular level of abstraction.

**A large system that requires decomposition**

其主要架構規範如下：

+ 層級的執行順序為同步且依據順序
+ 層級之間為解偶
+ 層級不可直接跨越
+ 層級為抽象的子程序集
+ 層級間的資料來源可為上層的結果亦可為其他資料源
+ 層級應設計適當的接口或應用程序介面

##### § 小結

Layer 架構在網際網路應用程式、企業應用程式中是極為著名的架構，典型的範例更是著名的 OSI 7 Layers；其設計特定並沒有詳細規範，使其靈活性與解釋性更適合不同語言的對於網路應用程式的基礎架構。

在傳統的設計中，單一網際網路語言會涵蓋各個層級，例如 ASP.NET、PHP 的函式庫規範與程式框架建立時對資料夾的定義；然而，在網際網路應用程式規模放大後，採用附載平衡、容器化虛擬機、自動延展主機的設計中，各層級則不會只用單一語言，更加使得『層級為抽象的字程序集』成了一個抽象概念，因為實際執行不但會是不同語言，更會有完全獨立於層中內的架構，而應對這樣的設計下『層級應設計適當的接口或應用程序介面』的規範則更為重要。

##### § 參考

+ [Web-Service的基本架構](http://www.interinfo.com.tw/edoc/ch14/frontline.htm)
+ [三層結構](https://wiki.mbalib.com/zh-tw/%E4%B8%89%E5%B1%82%E7%BB%93%E6%9E%84)
+ [3-Tier Architecture: Everything You Need to Know](https://www.finereport.com/en/product-functions/3-tier-architecture.html)
+ [Multitier architecture wiki](https://en.wikipedia.org/wiki/Multitier_architecture)
    - [Enterprise architecture framework](https://en.wikipedia.org/wiki/Enterprise_architecture_framework)
+ [Software Architecture Patterns — Layered Architecture](https://medium.com/@priyalwalpita/software-architecture-patterns-layered-architecture-a3b89b71a057)
    - [軟體分層架構模式](https://blog.johnwu.cc/article/software-layered-architecture-pattern.html)

### Pipe & Filter

The Pipes and Filters architectural pattern provides a structure for systems that process a stream of data. Each Processing step is encapsulated in a filter component. Data is passed through pipes between adjacent filters. Recombining filters allows you to build families of related systems.

**Processing data streams.**

**Use the Pipes and Filters architectural style to divide a larger processing task into a sequence of smaller, independent processing steps (Filters) that are connected by channels (Pipes).**

其架構主要規範：

+ Pipes 會包含一個以上的 Filters
+ Filter 是封裝後的元件，其處理程序是隱含在元件中
+ Filter 內不可以再次呼叫另外一個 Pipe 作為其處理程序
+ Pipe 與 Filter 是可以重複使用的元件
+ 需處理的資料會在 Filter 間依序傳遞下去
+ 若各 Filter 共用的資料，則應存放於 Store 中，透過 Pipe 或 Data 的介面來取得資料

##### § 小結

Pipes and Filters 架構在處理串流資料，或動態構築處理流程上是一個著名的常用架構，典型的實用指令與軟體就是 Linux Shell 的 Pipe 處理，以及 DirectX Show 用來作影片解碼與播放的。

在文件中提及 Pipes and Filters 架構不適合於互動介面，以及若設計太多 Filter 會導致效能下降，但在階段的資料流處理確實實用此架構是適當的，可為更加適應於互動介面與降低物件複雜度，因此延伸出反應式程式設計 ( Reactive programming )，以宣告式程式設計或函數程式設計，將主要功能與邏輯以函數替代 Filter 物件，更有為了應對互動介面的而將流程固定以增加效能。

但若不是重視效能與閱讀的反應式程式設計外，在階段處理動畫、轉場、資料處理、演算控管仍是一個適當的資料流處理架構。

##### § 參考

+ [Pipes and Filters pattern](https://docs.microsoft.com/zh-tw/azure/architecture/patterns/pipes-and-filters)
+ [Pipes and Filters Pattern – API Architecture for general purpose](https://kudocode.me/2019/04/16/pipes-and-filters-pattern-api-architecture-for-general-purpose/)
+ [Pipes and Filters - Enterprise Integration Patterns](https://www.enterpriseintegrationpatterns.com/patterns/messaging/PipesAndFilters.html)

### Blackboard

The Blackboard architectural pattern is useful for problems for which no deterministic solution strategies are known. In blackboard several specialized subsystems assemble their knowledge to build a possibly partial or approximate solution.

**An immature domain in which no closed approach to a solution is known or feasible.**

其架構主要規範：

+ Control 為控制應執行之資源
+ Knowledge Source 為一個包含複數執行方案物件的群集
+ Knowledge Source 具有重複使用的特性
+ Blackboard 為記錄執行狀態、結果的資料物件
+ Blackboard 未必會有結果，亦即資料在 KS 的檢測及全不通過
+ 系統會從 Control 開始執行，並訊問所有 Knowledge Source 內的方案是否可執行，若可執行才正式啟動動作，並將尋訪與執行結果寫入 Blackboard

##### § 小結

Blackboard 架構是針對未確定解決方案的問題處理，其透過 Knowledge Source 的儲存多個解決方案，在資料匯入時選擇最有可能產生運用的方案來計算近似解；以目前知道的軟體中，最相似的是用於機械學習各類演算法驗算與測試的 [Waka](https://www.cs.waikato.ac.nz/ml/weka/index.html)，但此軟體未必使用到 Blackboard。

在多數介紹文件中有提到，Knowledge Source 本身製作不困難、不易測試、執行效能低，雖然針對未知解決方案的問題，使用窮舉法讓所有複合執行條件的演算法來試驗資料，這是必然做法；但其中對於無法平行處理這點，再隨著時間的演進，利用運算單元容器化的方式或運算內容分散運算，是可以透過系統架構來構築平行運算的可行架構。

##### § 參考

+ [Blackboard (design pattern) wiki](https://en.wikipedia.org/wiki/Blackboard_(design_pattern))
+ [Blackboard architecture pattern PPT](https://www.slideshare.net/aish006/blackboard-architecture-pattern)
+ [Blackboard Architecture PDF](http://users.encs.concordia.ca/~gregb/home/PDF/soen6461_blackboard_arch.pdf)
+ [Two complementary patterns to build multi-expert systems](https://hillside.net/plop/plop97/Proceedings/lalanda.pdf)
+ [Using a Blackboard Architecture in a Web Application ](https://pdfs.semanticscholar.org/b380/19939299661fcf9e81b0ebccdf9097a04aea.pdf)
+ [The Reflective Blackboard Architectural Pattern](https://www.semanticscholar.org/paper/The-Reflective-Blackboard-Architectural-Pattern-Silva-Garcia/7b999b728aecd2842fd919bf131b41c2fb16b9f6)

### Dataflow architecture pattern summary

##### § 小結

##### § 參考
