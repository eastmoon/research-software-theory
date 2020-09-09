## Event-driven architecture

+ [Event-driven architecture wiki](https://en.wikipedia.org/wiki/Event-driven_architecture)
+ [Event-driven programming wiki](https://en.wikipedia.org/wiki/Event-driven_programming)

事件驅動架構 ( EDA ) 是一種程式設計範式，其設計方法相關於事件的產生 ( production )、檢測 ( detection )、使用 ( consumption )、反應 ( reaction )；若從程式設計來看，從鍵值得邏輯式 ( Switch-Case、Key-Value ) 到各類互動程式框架、反應式程式設計、資訊處裡架構皆會有使用到事件驅動的概念。

### 事件驅動程式設計 ( Event-driven programming )

源自 Windows SDK 的事件驅動程式設計共有兩種要素：

+ 事件名稱
+ 觸發函數

```
{
	do {
		switch(...) {
			case EVENT : {...} break;
		}
	} while(...)
}
```
> 簡易事件驅動程式結構

軟體在宣告要執行的『事件名稱』，從而由軟體執行對應名稱下的『觸發函數』；此外，依據不同的軟體框架下，本來的事件驅動內容會轉由由框架管理，例如 Unity 的顯示物件會固定觸發的 Update 行為，若在 Win32SDK 框架之下則需另外去設計相關的事件名稱與觸發函數；然而，除了透過框架的生命週期管理的事件外，事件驅動亦可用於物件解耦合、互動行為觸發等。

#### DOM Event system

+ [DOM events](https://en.wikipedia.org/wiki/DOM_events)
+ [An Introduction To DOM Events](https://www.smashingmagazine.com/2013/11/an-introduction-to-dom-events/)
+ [Document Object Model (DOM) Level 3 Events Specification](https://www.w3.org/TR/2013/WD-DOM-Level-3-Events-20131105/)

文件物件模型 ( DOM、Document Object Model )，最早可追朔至1990年代，第一次瀏覽器大戰 ( Browser wars )，因為當時賦予瀏覽器的功能，JavaScript、ActiveX，乃至於DHTML的設計方式，進而產生了DOM，並由W3C進行標準化。

現今DOM規範達到Level 4 ( 2015公佈 )，但對於事件系統，有最主要的兩個版本。

##### DOM Level 0

**『Each event can only have one event handler registered.』**

DOM最早的規範中，開發者可經由單行(inline)命令，在HTML標籤內加上要驅動的事件，如onClick，並指定負責的觸發函數；而於JavaScript中，則撰寫觸發函數，等待HTML標籤接受瀏覽器將事件觸發。

但於DOM Level 0中，事件驅動僅能一對一，亦即單一事件僅能觸發單一函數，若要多重觸發、跨層即改寫資訊，皆必須由開發者自行處理。

##### DOM Level 2

**『Bubbling structure and Event-listener, and multiple event handlers can be registered for the same event.』**

於2000年，DOM Level 2規範的事件系統，增加泡沫事件系統、單一事件多重觸發，並且不在限定事件來源；亦即開發者可自定是建規格，這規範從而影響了後期的軟體與語言規範。

DOM Level 2的規範，可追朔其設計理念源自於Observer pattern與C++的函數指標應用；藉由這結構，開發者僅需規劃事件物件與其關聯，並專注於事件發動後的資料處理與管理。

### 事件驅動架構 ( Event-driven architecture )

不同於事件驅動程式設計是指程式的技法，事件驅動架構是從『事件』這概念來看待系統架構；這類設計可源自事件驅動程式設計的延伸應用，或常見於伺服器端的軟體與系統架構，細節定義可參閱 Wiki 內文。

```
router.get('/', function(req, res, next) {
  res.render('index', { title: 'Express' });
});
```
> Express.js router setting with Javascript

事件驅動架構在伺服器的運作就好比 WebAPI，透過規範伺服器對應路由為『事件名稱』，若符合名稱則執行對應的『觸發函數』。
