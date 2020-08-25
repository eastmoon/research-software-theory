## Architecture pattern
> 本研究依據 Pattern-Oriented Software Architecture, Volume 1 - A System Of Patterns 為基礎，並從後期延伸發展與實務應用架構進行討論

**『Architecture is a concept.』**
> Pattern is a solution to solve the problem, often recall and reuse on the same problem.

架構是對問題的概念解決方案，樣式是針對問題的可重用解決方案；架構樣式(Architecture pattern)，則是針對概念性問題的可重用解決方案。

不論何種架構樣式，都是對其定義的概念問題提出適合的結決方案；然而，沒有一個樣式能解決所有問題，同樣也無法利用一個概念定義所有軟體用途；因此，找出概念的相似、相異處，並將之結合與混用會是重新尋找架構樣式的途徑。

架構樣式的設計目的：

1. 模組化

模組化目的是透過切割程式碼，將邏輯、內容分離，避免產生冗餘且複雜的程式碼，降低程式間的依賴(耦合)，提高重用性；進而達到避免重工、降低解讀難度、減少錯誤率。

2. 維護性

軟體的維護性，在TDD(Test-driven developer)來說，是指自我檢測或軟體的測試性；自我檢測，其目的是在繁瑣、冗長的錯誤管理(用戶回報、檢錯機制)前，先行進行可預測、可檢測項目進行自我檢測，於問題發生前、後，降低問題檢查點的數量。

3. 重用性

軟體的重用性，在軟體開發中，其著重在於軟體的商業邏輯對用戶的需求反饋。

然而，過度回應用戶需求的軟體開發，則會因此出現過多繁重而不易維護的部分；即使架構的模組化、維護性設計可以降低此問題，仍存有無法避免設計不當問題。

重用性設計，基於模組化、維護性，將模組設計成針對特定問題的解決方案、共通方案，並且讓模組的行為符合測試性；透過重用性模組化，將軟體的基礎邏輯抽象化抽出，並以此降低邏輯與內容的依賴。
> 商業邏輯是指符合軟體商業價值的邏輯，其中包含了大量的針對性邏輯、內容；在抽象化過程，第一步則先將商業邏輯、內容分割、第二步則將基礎邏輯(模組管理、訊息傳遞系統等)、商業邏輯(帳戶登入、登出)分割。


### Interactive

互動 ( Interactive ) 架構，此項分類取自架構樣式中的一項分類，除書中提及的兩個架構外，另外提及兩個著名的延伸架構，此兩架構源自日後基於簡化設計、目標設計後抽象與化約的結果。

+ PAC，Presentation-Abstraction-Control
+ MVC，Model-View-Controller
+ MVVM，Model-View-ViewModel
+ MVP，Model-View-Presenter

#### 參考

+ [淺談MVVM架構](http://www.syscom.com.tw/ePaper_New_Content.aspx?id=498&EPID=219&TableName=sgEPArticle)
+ [MVVM架構的一次實踐](https://read01.com/aQKJBO.html)
+ [UI的設計模式MVP模式 - Passive View](http://blog.sanc.idv.tw/2011/09/uimvp-passive-view.html)
+ [Android 官方 MVP 架構解讀](https://read01.com/KEd4E7.html)
+ [Architecture - MVP, MVC, MVVM](https://dotblogs.com.tw/regionbbs/2011/09/29/compare_to_mvp_mvc_mvvm)

### Dataflow Structure

資料流 ( Dataflow ) 架構，此項分類取自架構樣式中 From Mud to Structure 的分類，除書中提及的三個早期架構外，此外有一個串流系統的架構，一個用於反應式設計的資料流架構；對於資料流架構在書中並未定義，但其內容皆針對資料處理對於『單元』、『流程』、『資料』關係做出定義，因此在此統一歸納為資料流架構，並對此進行研究與說明。

+ Pipe & Filter
+ Layer
+ Blackboard
+ Store Process
+ Progress

### Distributed

分散式 ( Distributed ) 架構，此項分類取自架構樣式中的一項分類

+ Mediator
+ Broker
+ Microkernel
+ Microservices
+ Cloud

### Adaptable

適應式 ( Adaptable ) 架構，此項分類取自架構樣式中的一項分類

+ Reflection
