## 定義語言與腳本 (Defined Language and Script)

### 語言(Language)

+ [Programming language wiki](https://en.wikipedia.org/wiki/Programming_language)
+ [Programming paradigm wiki](https://en.wikipedia.org/wiki/Programming_paradigm)

程式語言，是以命令描述式對電子設備下達實際機械運作指令的描述方式，其描述方式依據不同的規範、解釋法則、輸出結果等，可區分為不同的程式語言。

A programming language is a formal constructed language designed to communicate instructions to a machine, particularly a computer. Programming languages can be used to create programs to control the behavior of a machine or to express algorithms.

程式語言是一種正規建構語言，設計用來傳達指令給機械，特別是電腦；程式語言可以用於建立程序來控制機械行為或做演算法呈現。

The description of a programming language is usually split into the two components of syntax (form) and semantics (meaning). Some languages are defined by a specification document (for example, the C programming language is specified by an ISO Standard), while other languages (such as Perl) have a dominant implementation that is treated as a reference.

程式語言的描述式可分為兩個單元，語法(形式)與語意(意義)；一些語言是由規範文件定義(例如，C語言是由ISO標準文件定義)，其他語言(例如，Perl)則由相應參考文獻實踐而來。

A programming paradigm is a fundamental style of computer programming, serving as a way of building the structure and elements of computer programs. Some programming languages are designed to follow only one paradigm, while others support multiple paradigms.

程式規範是一套程式語言的基本樣式，例如如何在電腦程序中建立架構與元件；一些程式語言的設計只會跟隨一種規範，其餘則會支援多個規範。

Programming paradigms that are often distinguished include imperative, declarative, functional, object-oriented, procedural, logic and symbolic programming.[1][2][3] With different paradigms, programs can be seen and built in different ways; for example, in object-oriented programming, a program is a collection of objects interacting in explicitly defined ways, while in declarative programming the computer is told only what the problem is, not how to actually solve it.

程式規範通常區分為含括命令式(imperative)、宣告式(declarative)、函數式(functional)、物件導向(object-oriented)、程序式(procedural)、邏輯與符號(logic and symbolic)程式。隨著不同的規範，程式會有不同的建立方式，例如，在物件導向程式，程序是物件集合在明確定義下的互動，而在宣告式程式只告知電腦有什麼問題，而不告知明確的解法。

對於程式語言，若詳細區分應採用程式規範的定義(Programming paradigm)，若依據個人認知區分，則分為三大類型：

1. 結構(Structure)，利用不同的結構、演算構築的語言類型，目的在自由度、維護性，控制結構體來設計出各類演算與互動系統。
2. 程序(Procedural)，利用程序、函數構築的語言類型，目的在簡易、快速，效能取向的一次性運行，並以此運用於微型、嵌入式設備。
3. 邏輯(Logic)，利用人類語言、邏輯式來撰寫，以擬人、人工智慧等抽象、不明確議題為主的設計，用於學習式、自適性演算法。

這三類型語言是個人用於解釋當前所學所知語言的用途、設計傾向，並解析其設計目的，便與理解應用時應注意事項。
這類型不同於程式規範的細膩，也不足以完全解釋單一語言的特性，但單一語言亦可能橫跨兩類；不過含括過多程式規範的語言本身就具有其風險，越是涵蓋過多意義的語言，越容易失去應有特性，進而喪失語言的設計目的，亦或說即使能達到目的也劣於專攻於此的語言，至於何優何劣，應用何者，則留待專案分析才可得出結論。

### 腳本(Script)

+ [Scripting language wiki](https://en.wikipedia.org/wiki/Scripting_language)

A scripting or script language is a programming language that supports scripts, programs written for a special run-time environment that automate the execution of tasks that could alternatively be executed one-by-one by a human operator. Scripting languages are often interpreted (rather than compiled). Primitives are usually the elementary tasks or API calls, and the language allows them to be combined into more complex programs. Environments that can be automated through scripting include software applications, web pages within a web browser, the shells of operating systems (OS), embedded systems, as well as numerous games.

腳本語言(Script Language)，是一套對基底程式語言的支援腳本，程序編寫給特定執行中環境，使其可自動執行任務，用以取代人工操作。
基底語言通常對基礎任務提供API(應用程式介面)，而腳本語言則在此基礎上重組複雜的操作程序。
應用程式其本身可能即是提供腳本運行的環境，例如瀏覽器可執行網頁，作業系統、嵌入式可執行Shells，遊戲內的腳本編輯工具。

『針對特定環境的限制型操作語言。』

以下是腳本據有的特色：

1. 針對特定目的運行。
2. 無需編譯，只需解讀即可運行。
3. 執行時需有基底環境，如虛擬機、作業系統。

## 語言與腳本的不同 (Scripting Language vs Programming Language)

+ [Scripting Language vs Programming Language - stackoverflow](http://stackoverflow.com/questions/17253545/scripting-language-vs-programming-language)
+ [Scripting vs. Coding vs. Programming](http://www.naelshawwa.com/scripting-coding-programming/)

『This line is getting more and more blurry since compilation can be so fast with modern hardware and modern compilation techniques. For instance, V8, the JavaScript engine in Google Chrome and used a lot outside of the browser as well, actually compiles the JavaScript code on the fly into machine code, rather than interpreting it. (In fact, V8's an optimizing two-phase compiler.)

Also note that whether a language is a "scripting" language or not can be more about the environment than the language. There's no reason you can't write a C interpreter and use it as a scripting language (and people have). There's also no reason you can't compile JavaScript to machine code and store that in an executable file (and people have). The language Ruby is a good example of this: The original implementation was entirely interpreted (a "scripting" language), but there are now multiple compilers for it.』

程式語言與腳本語言的差別可從下列幾點來說明：

1. 溝通對象
程式語言，溝同於硬體設備或軟體本身。
腳本語言，溝同於基底環境可溝通的硬體設備、軟體。

2. 功能範疇
程式語言與腳本的分界，在於是否以特定語言為基底提供執行環境作轉介。
若環境提供了完整操作的介面，且所有環境皆可解讀同類腳本語言，則該腳本其廣泛應用程度將大於等於基底語言；這亦是當前JavaScript腳本語言的其廣泛性高於特定基礎語言。

3. 語言範疇
腳本語言本身是為符合操作基底環境提供的介面而存在，其中自有的運算式、描述式、宣告式，常會因為簡化於操作這特性，而不符合語言的規範。
亦如早期的JavaScript其弱型態且結構單純，無法完整應用於物件導向的物件互動管理設計。
