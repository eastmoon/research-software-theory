## Event system

### Event-driven programming

+ [Event-driven programming wiki](https://en.wikipedia.org/wiki/Event-driven_programming)

事件驅動程式設計，是一種點腦程式設計模型，其撰寫方式源自於互動程式(Interactive program)，從最早的DOS程式到現今廣泛運用的各種平台，僅要有使用者互動的行為，就存在事件驅動程式設計。

典型的事件驅動程式設計共有兩種要素：

+ 事件迴圈
+ 觸發函數

以下為其程式結構
```
{
	do {
		switch(...) {
			case EVENT : {...} break;
		}
	} while(...)
}
```

由於軟體的發展，對於使用於框架之下的事件驅動，多半無需管理事件迴圈，亦即迴圈運作已交由框架管理，例如Unity系統固定觸發的Update行為，即使於Win32SDK框架之下，此部分也交由作業系統管理。

因此，對於觸發函數的撰寫方式，即成為當前程式設計常見的議題；亦即討論著，MVC的Controller應該如何規劃與設計。

### DOM Event system

+ [DOM events](https://en.wikipedia.org/wiki/DOM_events)
+ [An Introduction To DOM Events](https://www.smashingmagazine.com/2013/11/an-introduction-to-dom-events/)
+ [Document Object Model (DOM) Level 3 Events Specification](https://www.w3.org/TR/2013/WD-DOM-Level-3-Events-20131105/)

文件物件模型 ( DOM、Document Object Model )，最早可追朔至1990年代，第一次瀏覽器大戰 ( Browser wars )，因為當時賦予瀏覽器的功能，JavaScript、ActiveX，乃至於DHTML的設計方式，進而產生了DOM，並由W3C進行標準化。

現今DOM規範達到Level 4 ( 2015公佈 )，但對於事件系統，有最主要的兩個版本。

○ DOM Level 0

**『Each event can only have one event handler registered.』**

DOM最早的規範中，開發者可經由單行(inline)命令，在HTML標籤內加上要驅動的事件，如onClick，並指定負責的觸發函數；而於JavaScript中，則撰寫觸發函數，等待HTML標籤接受瀏覽器將事件觸發。

但於DOM Level 0中，事件驅動僅能一對一，亦即單一事件僅能觸發單一函數，若要多重觸發、跨層即改寫資訊，皆必須由開發者自行處理。

● DOM Level 2

**『Bubbling structure and Event-listener, and multiple event handlers can be registered for the same event.』**

於2000年，DOM Level 2規範的事件系統，增加泡沫事件系統、單一事件多重觸發，並且不在限定事件來源；亦即開發者可自定是建規格，這規範從而影響了後期的軟體與語言規範。

DOM Level 2的規範，可追朔其設計理念源自於Observer pattern與C++的函數指標應用；藉由這結構，開發者僅需規劃事件物件與其關聯，並專注於事件發動後的資料處理與管理。
