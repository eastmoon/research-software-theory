## Reactive Programming

#### § 定義與說明

**『In computing, reactive programming is a declarative programming paradigm concerned with data streams and the propagation of change.』**

反應式程式設計 ( Reactive Programming ) 是一種重視資料流與傳播變動的宣告式程式設計範例。

**Reactive programming has been proposed as a way to simplify the creation of interactive user interfaces and near-real-time system animation.**
> For example, in a model–view–controller (MVC) architecture, reactive programming can facilitate changes in an underlying model that are reflected automatically in an associated view.

常見的一種範例應用，是反應式程式設計運用於簡化使用者介面互動與近即時系統動畫；例如，在 MVC 架構中，反應式程式設計會直接變更底層資料模組，並自動反射至相關聯的呈現介面。

常見的一種範例應用，是反應式程式設計運用於異步資料流；例如，在頁面點擊行為後觸發的異步資料存取與反應，或者建立長連線 ( Socket ) 後聆聽到伺服器端的訊號並反應。

#### § 結論

反應式程式設計，亦稱為流式設計，此類設計常見於互動架構中，以及相關介面設計的第三方函式庫。

+ [RxJS](https://rxjs-dev.firebaseapp.com/guide/overview)、[RxJava](https://github.com/ReactiveX/RxJava)
+ [Flux](https://facebook.github.io/flux/docs/in-depth-overview)、[Redux](https://redux.js.org/)

這類第三方函式庫，多是未了補充或強化介面架構對於互動、動畫設計不完備的部分，但需注意由於此類第三方函式庫會存在與介面架構設計理念衝突的可能，在引用時必需先注意原始框架的不完備之處，在局部的引用，避免架構與工具相依過度，導致版本衝突或學習複雜度提升；極少情況下，原為外部第三方工具會被引用入架構，亦或架構日後版本新增相似功能，在這情況下就需選擇是否繼續沿用第三方。
## 參考

+ [Reactive programming](https://en.wikipedia.org/wiki/Reactive_programming)
+ [5 Things to Know About Reactive Programming](https://developers.redhat.com/blog/2017/06/30/5-things-to-know-about-reactive-programming/)
