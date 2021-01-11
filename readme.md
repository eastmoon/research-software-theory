## 軟體理論研究

## Software engineering

1. [Language, Script.](./software-engineering/language_and_script.md)
    + [Folder structure and namespace defined](./software-engineering/folder_structure_and_namespace_defined.md)
    + [Imperative and Declarative](./software-engineering/programming_paradigm_imperative_and_declarative.md)
    + [Reactive programming](./software-engineering/programming_paradigm_reactive_programming.md)
    + [Cross Compiler](./software-engineering/cross_compiler.md)
    + [SOLID (物件導向設計)](https://zh.wikipedia.org/wiki/SOLID_(%E9%9D%A2%E5%90%91%E5%AF%B9%E8%B1%A1%E8%AE%BE%E8%AE%A1))
2. [Design Pattern](./software-engineering/design_pattern.md)
3. [Architecture Pattern](./software-engineering/architecture_pattern.md)
    + [Interactive Architecture](./software-engineering/interactive_architecture.md)
    + [Dataflow Architecture](./software-engineering/dataflow_architecture.md)
    + [Event-driven Architecture](./software-engineering/event_driven_architecture.md)
        - [Event Listener implemented by Observer pattern](./software-engineering/event_listener_implemented_by_observer_pattern.md)
4. [Design Methodologies](./software-engineering/design_methodologies.md)
    + [Clean Architecture](https://blog.cleancoder.com/uncle-bob/2012/08/13/the-clean-architecture.html)
        - [再談Clean Architecture三原則](http://teddy-chen-tw.blogspot.com/2020/08/clean-architecture.html)
    + [Domain-driven design](./software-engineering/domain-driven-design.md)

## Development Operations

<center>
    <img src="./development-operations/img/devops-concept.png" alt="devops concept picture" />
</center>

1. [軟體配置管理 ( SCM、Software Configuration Management )](https://zh.wikipedia.org/wiki/%E8%BD%AF%E4%BB%B6%E9%85%8D%E7%BD%AE%E7%AE%A1%E7%90%86)
    + [Git 議題](./development-operations/git-issue.md)

## Computer vision

1. [Scale-invariant feature transform](./computer-vision/Scale-invariant_feature_transform.md)
2. [Computer-Mediated Reality](./computer-vision/computer_mediated_reality.md)

## Computer graphics

1. [Concept, Light](./computer-graphics/concept_and_light.md)

## Information retrieval

1. [Database Normalization](https://zh.wikipedia.org/wiki/%E6%95%B0%E6%8D%AE%E5%BA%93%E8%A7%84%E8%8C%83%E5%8C%96)
    + [1NF：定義主鍵值 ( primary key或unique key ) 以及剔除重複資料，來打好資料表的基礎](https://progressbar.tw/posts/265)
    + [2NF：符合 1NF，將部分相依的資料另開表格作儲存，確保每一非鍵值欄位必須「完全功能相依」( Functional Dependency ) 於主鍵](https://progressbar.tw/posts/267)
    + [3NF：符合 2NF，且每一個非鍵值欄位都必須不得和其他非鍵值欄位產生相關性；欄位避免由其他欄位計算所得，從而迴避「更新異常」(Modification Anomalies)](https://progressbar.tw/posts/270)
    + [4NF](https://zh.wikipedia.org/wiki/%E7%AC%AC%E5%9B%9B%E6%AD%A3%E8%A6%8F%E5%8C%96)、[5NF](https://zh.wikipedia.org/wiki/%E7%AC%AC%E4%BA%94%E8%8C%83%E5%BC%8F) 需基於在資料面的應用特例，用於加強分離數據
2. [Deep Learning](./information-retrieval/deep_learning.md)

## Distribution & Network

1. [分散運算研究專案](https://github.com/eastmoon/research-distribution-calculation)
2. [異步執行 ( Asynchronous execute )](./distribution-and-network/asynchronous-execute.md)
3. Message Queue
    + AMQP，https://en.wikipedia.org/wiki/Advanced_Message_Queuing_Protocol
4. TCP/IP Protocols
    + UDP
    + TCP
    + Socket
    + HTTP
        - HTTP State
        - RestAPI
5. [Internet of Things](https://zh.wikipedia.org/wiki/%E7%89%A9%E8%81%94%E7%BD%91)
    + [OOSGA 物聯網定義與趨勢](https://oosga.com/iot/)
    + 美國國家標準暨技術研究院（NIST）對於雲端運算的定義：
        - [軟體即服務 ( SaaS、Software as a Service )](https://zh.wikipedia.org/wiki/%E8%BD%AF%E4%BB%B6%E5%8D%B3%E6%9C%8D%E5%8A%A1)
        - [平台即服務 ( PaaS、Platform as a Service )](https://zh.wikipedia.org/wiki/%E5%B9%B3%E5%8F%B0%E5%8D%B3%E6%9C%8D%E5%8A%A1)
        - [基礎設施即服務 ( IaaS、Infrastructure as a Service )](https://zh.wikipedia.org/wiki/%E5%9F%BA%E7%A4%8E%E8%A8%AD%E6%96%BD%E5%8D%B3%E6%9C%8D%E5%8B%99)

## Library research

1. OpenCL
    + https://zh.wikipedia.org/wiki/OpenCL
2. PWA
    + https://developers.google.com/web/ilt/pwa/introduction-to-progressive-web-app-architectures
    + https://www.simicart.com/blog/pwa-vs-electron/
