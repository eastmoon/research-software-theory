## Imperative and Declarative


#### § 定義與說明

**『Imperative programming is a programming paradigm that uses statements that change a program’s state.』**

命令式程式設計 ( Imperative programming ) 是一種中以描述式來變更程式狀態的一種程式設計範例。

```
int a = 1;
a += 1;
a += 1;
a += 1;
print(a)
```
> 在已知的範例中，命令式程式設計是盡可能使用程式語言本身的語法進行狀態改變，邏輯陳述。

**『Declarative programming is a programming paradigm that expresses the logic of a computation without describing its control flow.』**

宣告式程式設計 ( Declarative programming ) 是一種不描述控制流程的邏輯表達方式。

```
int a = 1
a = increase(a, 3)
print(a)
```
> 在已知的範例中，宣告式程式設計是盡可能使用抽象化後的行為函數進行邏輯陳述。

這兩類程式設計並無好壞之分，在大多數情況下，程式設計初期皆是使用命令式撰寫，其後會自然地往宣告式程式發展 ( 抽象化 )；而引用的第三方函式庫也會提供大量的類別與函式，若是提供完整功能的第三方函式庫，則實際撰寫完成的功能，就會是一個完全以宣告式程式設計完成的程式。

```
fromEvent(document, 'click')
  .pipe(scan(count => count + 1, 0))
  .subscribe(count => console.log(`Clicked ${count} times`));
```
> 以 RxJS 為範例

#### § 結論

就觀念來說，一個完整的軟體的宣告式比例就決定此程式的抽象化與依賴函式庫程度，若宣告式比例高，則表示程式可變動範圍會受限制，這是因為程式的邏輯已被抽象化後的宣告函數隱藏，進而導致改動宣告式內的命令陳述會直接牽動所有引用的邏輯，亦或是因第三方未提供功能進而無法或修改相對的技術錯誤。

反之，若一個完整的軟體其命令式比例就決定此程式的維護性、再用率程度，完全未進行抽象化、未使用第三方的程式，有極高可能會出現大量重複的邏輯與大量用途不明的變數；對此，最適當的修正式往宣告式程式設計方式發展，然而這就必須注意抽象化或引用第三方的結果是否足夠應對未來可能的變化。

## 參考

+ [Reactive programming](https://en.wikipedia.org/wiki/Reactive_programming)
+ [5 Things to Know About Reactive Programming](https://developers.redhat.com/blog/2017/06/30/5-things-to-know-about-reactive-programming/)
