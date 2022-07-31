# Fundamentals of Software Architecture

書名：軟體架構原理 - 工程方法 ( Fundamentals of Software Architecture - An Engineering Approach )

出版社：O'Reilly

## 失效中的公理 ( Invalidating Axioms )

**公理，一個被視為己被確定、接受或不證自明為真的敘述或主張**

數學以公理為基礎延伸很多應用數學與論點，因為公理的真實性無可爭辯；在軟體設計中，架構就如同公理，一切的設計與應用皆源自於此。

然而，軟體與數學不同之處，是軟體的生態系是動態平衡的狀態，即使在某個時間點市場的技術要求是平衡的，但這其中仍有無數的微小動態在悄然改變著基礎，猶如單機應用程式因網路誕生而出現網際網路應用程式，亦如虛擬機容器化誕生而出現如分散式雲端服務 ( Kubernetes )； 架構師其中一個職責，就是質疑前個世代的公理，並非公理錯誤，只是現今的生態系中是否仍然適用，猶如 MVC ( Model-View-Controller ) 是互動應用程式的常見架構，但應用於現在的生態系其定義與解釋有了新解，亦延伸出如 MVP ( Model-View-Presenter )。

**在軟體架構中沒有正確，只有最適**

如同[The Software Architect Elevator](./the-software-architect-elevator.md)提到，質疑每一件事是架構師的職責，不論是否有必要改變，都有必要去懷疑現況、去思考假設、去探索新知、去重新定義公理，然後取捨公理，最後加以實踐決策後的公理；透過工程的邏輯思維與實務經驗，歷史中堆疊出無數的架構，便是本書所要介紹的主要內容。

**程式撰寫時深信公理，程式除錯時懷疑公理**

看文本書並不會讓人成為架構師，但這書期望的是提供足夠的觀念，給予閱讀者一個思考的切入點，而身為架構師則需如前述一般，在實務時要信任已知的公理，在思考時要懷疑已知的公理。

## 軟體架構

### 架構定義

軟體架構難以定義，不論是 [Pattern-Oriented Software Architecture](../software-engineering/architecture_pattern.md) 或 [The Software Architect Elevator](./the-software-architect-elevator.md) 都有著各自的定義，其原因基於 **『Architecture is a concept.』** 來看可以理解為每個人對於觀念的解釋與看法各自不同，這也能對應 **『架構的定義幾乎與職業的架構師一樣多』** 的解釋；但不論是何種解釋，其中不乏相似且具有統一性的觀點，因此，本書提出了對軟體架構的定義描述：

+ 系統結構，系統元件間關係的說明或圖例
+ 架構決策，系統元件間的關係運作法則與限制
+ 架構特性，系統在此架構下可支援的特性 ( The Software Architect Elevator 一書中的非功能性需求 )
+ 設計原理，系統在此架構下依循的設計理論，亦是當決策衝突時的指導方針

舉例來說，規劃一個負載平衝系統，則其架構定義描述如下：

+ 負載平衝系統結構：from [Load Balancer Definition - Avinetworks](https://avinetworks.com/glossary/load-balancer/)
![load-balancer-system-diagram](avinetworks-load-balancer-system-diagram.png)
+ 結構決策：
    - 負載平衝會基於現有 Application Servers 運作狀態配置 Application Client 的請求
+ 架構特性：
    - 可擴展性，基於此架構可以依據系統需要增減對應設備來擴充處理量
+ 設計原理：
    - [分層式架構 ( Layered Architecture )](https://cs.uwaterloo.ca/~m2nagapp/courses/CS446/1195/Arch_Design_Activity/Layered.pdf)

### 架構思維

### 架構特性

### 模組化

## 架構風格

### Layered

### Pipeline

### Microkernel

### Microservice

### Event-Driven
