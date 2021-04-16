## 軟體分析與設計 ( Software Analysis & Design )

軟體分析與設計是基於客戶需求與軟體開發間，對軟體的規模、目的、定義、關係進行規劃的步驟，其可分為兩個階段：

+ [Software Analysis](https://en.wikipedia.org/wiki/Requirements_analysis)

軟體分析也被稱為需求分析，指的是在建立一個新的或改變一個現存的系統或產品時，對軟體需求的技術評估、抽象性規劃、影響範圍定義；在這階段的文件偏向需求側與雛形軟體的規劃，並不是正式對應系統的設計。

+ [Software Design](https://en.wikipedia.org/wiki/Software_design)

軟體設計，是基於需求與軟體分析結過，對既有軟體進行實際設計與規劃；在這階段的文件偏向實務側，並根據實際軟體的架構、框架來制定的實務規範與樣板設計。

## 文件範本

軟體分析文件 ( Software Analysis Document、SAD )、軟體設計文件 ( Software Design Document、SDD ) 是以文字描述功能需求與產品設計技術面規劃，由軟體分析師、設計師負責撰寫，目的是提供軟體開發團隊對於產品架構與設計指引。

+ [Software Design Overview Docuemnt](./software_analysis_and_design_template_overview.md)
+ [Software Design Docuemnt](./software_analysis_and_design_template_ssd.md)

### User story

用戶故事 ( User story ) 是以日常語言或商務用語撰寫句子，是一段簡單的功能表述，以客戶或使用者的觀點撰寫下有價值的功能、引導、框架來與使用者進行互動；對於用戶故事說它是規格文件，不如說它代表客戶的一個需求列項而已，因為實做細節將延後至開發時才會確定。

撰寫用戶故事使用簡單描述，其句型如同英式簡單句：

**As a (role of user), I want (some feature) so that (some business value).**

並以條列方式呈述：

+ 使用者可以用條件搜尋工作，例如地點、薪資範圍、工作職稱、公司名字等
+ 使用者可以瀏覽詳細的工作內容
+ 使用者可以瀏覽詳細的公司資料

需注意，用戶故事的故事粒度往往會對等實務的複雜度，亦可等同開發時程；因此，精確的切割容易明確預估時程，但亦表示冗長討論與衝突排解過程，從而拉長評估時程而減少開發時程，這是在撰寫與規劃時應避免的問題。

### Use Case

使用案例 ( Use Case ) 是 **『使用 ( Use ) 此系統的互動、操作範例 ( Case )』**，亦即對於相同系統，考量不同使用者在此系統會產生的使用案例；案例本身是個使用者與系統的互動行為，其案例描述會包括如下：

+ User Case Name
    - Description
    - Pre-condition、Post-condition
    - Basic flow、Extensions flow

需注意，使用案例的描述是貼近實務面的規範，並不等同程式碼，因此，部分文獻會提到其描述、流程不具順序性，僅有描述性；然而，實際的撰寫方式仍視撰寫者的描述需要而定，若案例的粒度夠細，則其描述性本身就會具有順序性。

### User Story v.s Use Case

調研不同文獻可以注意到，此兩類文件呈述方式皆有其優點與缺點，但兩者本身並不可替換 ( not interchangeable )，但可相互輔助。

+ 用戶故事
    - 重視功能的描述
    - 貼近用戶需求
    - 適用於軟體分析
+ 使用案例
    - 重視互動的描述
    - 貼近實務描述
    - 是用於軟體設計

相較於用戶故事，使用案例會更加細緻的規範，亦可看成用戶故事的實例化內容可以使用案例描述。

## 結論

軟體分析與設計產出的是軟體藍圖，其存在目的是將需求循序漸進的轉換成軟體實務所需的前置資料，實務設計則是基於此藍圖的規範來避免實務結果的二義性 ( ambiguous )，從而降低維護、重構的範圍，並據此留下基礎文件與討論依據。

需注意，相較於軟體開發要遵循依賴的軟體框架，軟體分析與設計本身並沒有依賴來源，雖其內容根源於需求，但並非一致，亦需根據實務面的架構原則、軟體框架來規劃，並適度抽象化其關係令其設計具有足夠的結構性、複用性。

## 參考

+ [Introduction to Software Analysis & Design](http://info.ee.surrey.ac.uk/Teaching/Courses/ee2.sad/s01sad.pdf)
    - [Software Analysis & Design Tools](https://www.tutorialspoint.com/software_engineering/software_analysis_design_tools.htm)
+ Software Analysis
    - [Software Requirements Analysis with Example](https://www.guru99.com/learn-software-requirements-analysis-with-case-study.html)
    - [Requirements Analysis Document](https://www.cs.fsu.edu/~lacher/courses/COP3331/rad.html)
    - [Requirements Analysis Document Guidelines](http://faculty.washington.edu/jtenenbg/courses/360/w02/project/bruegge-rad.html)
+ Software Design
    - [Software Design Document](https://github.com/AdriaticOrg/sdd)
    - [Software Design Document: What, Why and How? (Template Included)](https://blog.bit.ai/software-design-document/)
    - [How To Write Software Design Documents](https://blog.tara.ai/software-design-documents/)
    - [Why Writing Software Design Documents Matters](https://www.toptal.com/freelance/why-design-documents-matter)
+ Document
    - [User Story](https://zh.wikipedia.org/wiki/%E7%94%A8%E6%88%B7%E6%95%85%E4%BA%8B)
        + [什麼是 User Story?](https://ihower.tw/blog/archives/2090)
        + [產品管理流程中，使用者故事（User Story）常見的三種使用情境](https://medium.com/3pm-lab/3-use-cases-for-writing-effective-user-stories-cd42625fef53)
        + [User Story vs Use Case](https://www.visual-paradigm.com/guide/agile-software-development/user-story-vs-use-case/)
    - [Use Case](https://zh.wikipedia.org/wiki/%E7%94%A8%E4%BE%8B)
        + [使用案例關係的UML風格指南](https://www.ithome.com.tw/node/53543)
        + Diagram Case
            - [Use Case Model](https://creately.com/diagram/example/grrj6nrf4)
            - [FrontEnd Use case](https://creately.com/diagram/example/hmx4epbn1)
            - [Backend process](https://creately.com/diagram/example/ijxxcsyz2)
