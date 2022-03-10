## 軟體理論研究

## Software engineering

1. [Language, Script.](./software-engineering/language_and_script.md)
    + [Folder structure and namespace defined](./software-engineering/folder_structure_and_namespace_defined.md)
    + [Imperative and Declarative](./software-engineering/programming_paradigm_imperative_and_declarative.md)
    + [Reactive programming](./software-engineering/programming_paradigm_reactive_programming.md)
    + [Cross Compiler](./software-engineering/cross_compiler.md)
    + [SOLID (物件導向設計)](https://zh.wikipedia.org/wiki/SOLID_(%E9%9D%A2%E5%90%91%E5%AF%B9%E8%B1%A1%E8%AE%BE%E8%AE%A1))
2. [Software Analysis & Design](./software-engineering/software_analysis_and_design.md)
3. [Design Pattern](./software-engineering/design_pattern.md)
4. [Architecture Pattern](./software-engineering/architecture_pattern.md)
    + [Interactive Architecture](./software-engineering/interactive_architecture.md)
    + [Dataflow Architecture](./software-engineering/dataflow_architecture.md)
    + [Event-driven Architecture](./software-engineering/event_driven_architecture.md)
        - [Event Listener implemented by Observer pattern](./software-engineering/event_listener_implemented_by_observer_pattern.md)
    + [Microservice Architecture](./software-engineering/microservice_architecture.md)
5. [Design Methodologies](./software-engineering/design_methodologies.md)
    + [Clean Architecture](https://blog.cleancoder.com/uncle-bob/2012/08/13/the-clean-architecture.html)
        - [再談Clean Architecture三原則](http://teddy-chen-tw.blogspot.com/2020/08/clean-architecture.html)
    + [Domain-driven design](./software-engineering/domain-driven-design.md)
    + [Aspect-oriented programming](https://en.wikipedia.org/wiki/Aspect-oriented_programming)
        - [來談談 AOP (Aspect-Oriented Programming) 的精神與各種主流實現模式的差異](https://medium.com/cymetrics/aop-caf6a403e07f)

## Development Operations

<center>
    <img src="./development-operations/img/devops-concept.png" alt="devops concept picture" />
</center>

1. [軟體配置管理 ( SCM、Software Configuration Management )](https://zh.wikipedia.org/wiki/%E8%BD%AF%E4%BB%B6%E9%85%8D%E7%BD%AE%E7%AE%A1%E7%90%86)
    + [Git 議題](./development-operations/git-issue.md)
2. [Virtual Machine](https://github.com/eastmoon/research-distributed-computing#virtual-machine)
    + [Vagrant](https://github.com/eastmoon/research-distributed-computing/blob/master/Vagrant/docs)
    + [Docker](https://github.com/eastmoon/research-distributed-computing/blob/master/Docker/docs)
3. [Cross Compile](https://github.com/eastmoon/tutorial-cmake#%E4%BA%A4%E5%8F%89%E7%B7%A8%E8%AD%AF%E5%99%A8--cross-compiler-)
    + [安裝 arm64 套件於 amd64 環境](./development-operations/cross-package-install.md)

## Computer vision

1. [Scale-invariant feature transform](./computer-vision/Scale-invariant_feature_transform.md)
2. [Computer-Mediated Reality](./computer-vision/computer_mediated_reality.md)

## Computer graphics

1. [Concept, Light](./computer-graphics/concept_and_light.md)
    + [Mobile GPU Tile Based Rendering 介紹](https://medium.com/%E4%BA%8C%E6%B5%81%E9%81%8A%E6%88%B2%E9%96%8B%E7%99%BC/796f0eb1bbc)

## Information retrieval

1. [Database](https://zh.wikipedia.org/wiki/%E6%95%B0%E6%8D%AE%E5%BA%93)
    +[RDBMS](https://zh.wikipedia.org/wiki/%E5%85%B3%E7%B3%BB%E6%95%B0%E6%8D%AE%E5%BA%93)
        - [ACID wiki](https://zh.wikipedia.org/wiki/%E6%95%B0%E6%8D%AE%E5%BA%93%E4%BA%8B%E5%8A%A1#ACID%E6%80%A7%E8%B4%A8)
        - [Database Normalization](https://zh.wikipedia.org/wiki/%E6%95%B0%E6%8D%AE%E5%BA%93%E8%A7%84%E8%8C%83%E5%8C%96)
            + [1NF：定義主鍵值 ( primary key或unique key ) 以及剔除重複資料，來打好資料表的基礎](https://progressbar.tw/posts/265)
            + [2NF：符合 1NF，將部分相依的資料另開表格作儲存，確保每一非鍵值欄位必須「完全功能相依」( Functional Dependency ) 於主鍵](https://progressbar.tw/posts/267)
            + [3NF：符合 2NF，且每一個非鍵值欄位都必須不得和其他非鍵值欄位產生相關性；欄位避免由其他欄位計算所得，從而迴避「更新異常」(Modification Anomalies)](https://progressbar.tw/posts/270)
            + [4NF](https://zh.wikipedia.org/wiki/%E7%AC%AC%E5%9B%9B%E6%AD%A3%E8%A6%8F%E5%8C%96)、[5NF](https://zh.wikipedia.org/wiki/%E7%AC%AC%E4%BA%94%E8%8C%83%E5%BC%8F) 需基於在資料面的應用特例，用於加強分離數據
        - [Database Management System、DBMS](https://zh.wikipedia.org/wiki/%E6%95%B0%E6%8D%AE%E5%BA%93%E7%AE%A1%E7%90%86%E7%B3%BB%E7%BB%9F)
            + [MySQL(MariaDB) InnoDB Clustered Index & Secondary Index](https://medium.com/into-the-night/mysql-mariadb-innodb-clustered-index-secondary-index-45dc8335859c)
            + [什麼是 OLTP？什麼是 OLAP？](https://datadrivenai.wordpress.com/2019/11/01/%E4%BB%80%E9%BA%BC%E6%98%AF-oltp%EF%BC%9F%E4%BB%80%E9%BA%BC%E6%98%AF-olap%EF%BC%9F/)
    + [NoSQL](https://zh.wikipedia.org/wiki/NoSQL)
        - [CAP wiki](https://zh.wikipedia.org/wiki/CAP%E5%AE%9A%E7%90%86)
        - [了解NoSQL不可不知的5項觀念](https://www.ithome.com.tw/news/92506)
    + [RDBMS vs NoSQL](https://shininglionking.blogspot.com/2018/04/rdbms-vs-nosql.html)
        - [RDBMS vs. NOSQL | 關聯式資料庫 vs. 非關聯式資料庫](https://medium.com/@eric248655665/1423c9fbb91a)
2. [Data Mining](https://zh.wikipedia.org/wiki/%E6%95%B0%E6%8D%AE%E6%8C%96%E6%8E%98)
    + [Pattern recognition](https://zh.wikipedia.org/wiki/%E6%A8%A1%E5%BC%8F%E8%AF%86%E5%88%AB)
    + [Machine Learning and Deep Learnin : a survey](https://link.springer.com/article/10.1007/s10462-018-09679-z)
        - Machine Learning
            + [infra-weka](https://github.com/eastmoon/infra-weka)
        - [Deep Learning](./information-retrieval/deep_learning.md)

## Distribution & Network

1. [分散運算研究專案](https://github.com/eastmoon/research-distribution-calculation)
2. [異步執行 ( Asynchronous execute )](./distribution-and-network/asynchronous-execute.md)
3. Message Queue
    + AMQP，https://en.wikipedia.org/wiki/Advanced_Message_Queuing_Protocol
4. [OSI](./distribution-and-network/osi-model.md)
    + [TCP vs UDP](https://nordvpn.com/zh-tw/blog/tcp-udp-bijiao/)
        - [Transmission Control Protocol、TCP wiki](https://zh.wikipedia.org/wiki/%E4%BC%A0%E8%BE%93%E6%8E%A7%E5%88%B6%E5%8D%8F%E8%AE%AE)
        - [User Datagram Protocol、UDP wiki](https://zh.wikipedia.org/wiki/%E7%94%A8%E6%88%B7%E6%95%B0%E6%8D%AE%E6%8A%A5%E5%8D%8F%E8%AE%AE)
        - 原則上，TCP 為『可靠通訊』，UDP 為『不可靠通訊』，其差別在 TCP 基於檢查碼有序的傳輸，但 UDP 是以串流封包單向的廣播近網路
    + [Socket vs MQTT](https://www.educba.com/mqtt-vs-websocket/)
        - [Socket wiki](https://zh.wikipedia.org/wiki/%E7%B6%B2%E8%B7%AF%E6%8F%92%E5%BA%A7)；**Websocket is a computer communication protocol. It creates a two-way channel between a web browser and a server.**
        - [MQTT wiki](https://zh.wikipedia.org/wiki/MQTT)；**MQTT (Message Queue Telemetry Transmission) uses the publish/subscribe network protocol, which is used to transport messages between devices directly in the web browser.**
        - Socket 是基於點對點通訊，MQTT 基於訂閱 ( subscribe ) 與發佈 ( publish )；相較通訊上 Socket 是基於 TCP 規則的簡化，而 MQTT 是基於 Socket 設計的簡化，可以說 MQTT 效率高於 Socket 則是因為功能與用途更加明確的精簡設計導致
    + [Socket vs HTTP](https://www.geeksforgeeks.org/what-is-web-socket-and-how-it-is-different-from-the-http/)
        - [HTTP State](./distribution-and-network/http-state.md)
        - [RestAPI](https://zh.wikipedia.org/wiki/%E8%A1%A8%E7%8E%B0%E5%B1%82%E7%8A%B6%E6%80%81%E8%BD%AC%E6%8D%A2)
            + [淺談 REST API 的設計和規劃](https://marco79423.net/articles/%E6%B7%BA%E8%AB%87-rest-api-%E7%9A%84%E8%A8%AD%E8%A8%88%E5%92%8C%E8%A6%8F%E5%8A%83/)
5. [Internet of Things](https://zh.wikipedia.org/wiki/%E7%89%A9%E8%81%94%E7%BD%91)
    + [OOSGA 物聯網定義與趨勢](https://oosga.com/iot/)
    + [SAP 什麼是物聯網（IoT）？](https://www.sap.com/taiwan/insights/what-is-iot-internet-of-things.html)
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

## Reference Document

+ [Record CS knowlegement with XMind](https://github.com/SmartKeyerror/Psyduck)
    - 綜合知識文獻專案
+ [What is the difference between executing a Bash script vs sourcing it?](https://superuser.com/questions/176783)
    - **Sourcing** a script will run the commands in the current shell process. Changes to the environment take effect in the current shell.
    - **Executing** a script will run the commands in a new shell process. Changes to the environment take effect in the new shell and is lost when the script is done and the new shell is terminated.
    - Use source if you want the script to change the environment in your currently running shell. use execute otherwise.
+ [AI Expert Roadmap](https://i.am.ai/roadmap/#deep-learning-roadmap)

## Operating system performance adjustment

+ Windows
    - [連接用户體驗和遙測服務 (Connected User Experiences and Telemetry)](https://snippetinfo.net/media/1880)
    - [微軟兼容性遙測服務 (Microsoft Compatibility Telemetry)](https://tw.easeus.com/partition-manager-tips/fix-windows-10-microsoft-compatibility-telemetry-high-disk-usage.html#3)
