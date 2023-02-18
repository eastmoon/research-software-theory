# 抽象與介面 ( Abstract and Interface )

## 抽象類別(abstract class)

**僅有抽象概念但不具實做的類別**

抽象類別基於繼承概念，將類別分為『抽象』與『實做』，並以延伸(extends)建立關係。

```
A 『is a』 B
```

以此來說，A是抽象類別B的實做類別。
例如：卡車『is a』車，車是抽象的概念，而卡車則才具有車的實際行為。

## 介面(interface)

**功能定義**

介面是基於抽象類別概念，但僅保留關係的定義，將類別分為『介面』與『實做』，並以實行(implement)建立關係。

```
A 『can do』 B
```

以此來說，A是介面B的實做類別，而B僅是告知A你應該具有的功能。
例如：卡車『can do』加速，加速是功能定義，而卡車才具有這定義的實際行為。

## 結論

這兩者皆不具有具體內容，亦皆需抽象出行為。
但差別在於一個類別僅能繼承一個抽象類別，但可實做多個介面。

由於ES6的規範，類別可以制定抽象類別，但無法實做介面。
但基於弱形態的變數規範，物件存取並無嚴格規範。
因此透過系統存取的資料物件，取回後若有嚴格行為，僅需要透過形態檢查，即可確保操作，亦可確保最低可執行空行為。

## 文獻

+ [你搞懂抽象類別與介面了嗎？](http://missrices.pixnet.net/blog/post/28220534)
+ [Object-Oriented JavaScript — A Deep Dive into ES6 Classes](https://www.sitepoint.com/object-oriented-javascript-deep-dive-es6-classes/)
