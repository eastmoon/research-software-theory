# 異步執行 ( Asynchronous execute )

在單一應用程式中，常見的介面操作中的異步 ( 非同步 ) 流程、演算法中的多工並行計算，皆是使用多執行續來解決，在此統稱為『異步執行』。

## Thread

在作業系統的分時多工系統、分散運算系統，皆會提到多執行程序 ( multi process )、多執行續 ( multi threads)的方式，其目的在：

+ 避免單一執行程序鎖住資源導致死結 ( Deadlock )
+ 避免多核系統無法有效而充分運用

單就分時多工的系統架構，依據現有系統來看其相對性為：

+ 作業系統分時對象為多執行程序，確保可同時讓多個執行程序運作
+ 執行程序分時對象為多執行續，確保可同時讓多個執行續運作

因此

+ 單一執行程序效能上限受制作業系統
+ 單一執行續效能上限受制於執行程序

## Async、Await

在僅有單一執行續的 JavaScript 中，為了解決非同步訊息取回，延伸出了 ajax ( Asynchronous JavaScript and XML )，從而延伸出 Promise、Generator 框架，此框架特性在於：

+ 優點：異步運作，可用於動畫運作、取得遠端資料
+ 缺點：函數程序的回呼地獄 ( Callback Hell )

為了改善此框架缺點，並提高可讀性，因此誕生了 async、await 語法框架；而實際上這語法，等同於建立多個微小執行續，以確保每個函數間都是可獨立執行，在腳本邏輯規範上保持同步與異步運作。

要注意的是，在結論上來看，async、await 框架可以替代簡單的 thread 運作，但若演算法本身涉及執行續的狀態控制、不確定生存時間的執行續，則應使用 thread 來撰寫。

## 參考

+ [Thread - python document](https://docs.python.org/3/library/threading.html)
  - [Python 3 - Multithreaded Programming](https://www.tutorialspoint.com/python3/python_multithreading.htm)
  - [Python Multithreading and Multiprocessing Tutorial](https://www.toptal.com/python/beginners-guide-to-concurrency-and-parallelism-in-python)
  - [Python 多執行緒 threading 模組平行化程式設計教學](https://blog.gtwang.org/programming/python-threading-multithreaded-programming-tutorial/)
+ [Coroutines and Tasks - Python document](https://docs.python.org/3/library/asyncio-task.html)
  - [Python Async/Await入門指南](https://zhuanlan.zhihu.com/p/27258289)
+ [A better way for asynchronous programming: asyncio over multi-threading](https://towardsdatascience.com/3457d82b3295)
