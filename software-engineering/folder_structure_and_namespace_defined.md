## 檔案結構與命名空間定義

+ 命名空間

用於軟體專案結構，區分類別的群集用名稱。

+ 檔案結構

用於檔案結構，區分類別原始碼檔案用檔案夾名稱。

### 專案名稱

```
[com / org].company.project
```

### 函式庫 ( Library )

```
Library
 ├ Core
 ├ Pattern
 └ Interface
```

### 專案函式庫 ( Project Library )

```
Project Library
 ├ Framework
 ├ Library
 ├ Pattern
 ├ Interface
 └ [Project Instance]
```

### 框架庫 ( Framework Library )

以MVC ( Model-View-Controller )為例

```
Framework
 ├ Model
 ├ View
 ├ Controller
 └ Core
```

### 設計規範與注意
