## 電腦圖學

+ [Computer Graphics wiki](https://en.wikipedia.org/wiki/Computer_graphics)

電腦圖學是一種利用電腦模擬物體的外觀、動態的演算方式，其影響領域從軟體上的繪圖演算法、著色演算、物理模擬等，應用上的各類實境系統、電腦遊戲，甚至硬體設備的GPU、MMX指令等。

### 3D Coordinate Systems

+ 左手系座標系統

以右方為X軸的正向，上方為Y軸的正向，Z軸是以朝遠方為正向

+ 右手系座標系統

以右方為X軸的正向，上方為Y軸的正向，Z軸是以朝己方為正向

### Location、Matrix

對於物體，不論於幾維空間，其主要操作物體可分為下列三個：

+ 位移（Translate）

座標設定，二維(X, Y)，三維(X, Y, Z)。

+ 旋轉（Rotate）

物體面向設定，物體有預設的面向軸，使用旋轉則會針對特定軸進行轉動，調整物體面向的方位；旋轉通常必須指定一個旋轉軸(X, Y, Z)及一個旋轉量(R)，集合為(X, Y, Z, R)；旋轉量的表示值可分為，角度量與弳度量。

+ 縮放（Scale）

物體體積設定，物體預設縮放比為1，改變縮放比可調整物體大小；物體進行縮放時，不但可以改變物體外觀的大小，亦會改變其在三維空間中的位置；若物體的中心點不在原點，或是三個軸做不等比例縮放，上述問題即會發生；縮放通常必須指定一個縮放軸(X, Y, Z)及一個縮放量(S)，集合為(X, Y, Z, S)。

矩陣表示式：

+ [Transformation Matrix](https://en.wikipedia.org/wiki/Transformation_matrix)

物體於空間轉移時，其變化可透過轉換矩陣(Transformation Matrix)來計算。

```
F(t) = M * F(t-1)

Ratation Matrix (R) =
┌    	         ┐
│R11 R12 R13  0│
│R21 R22 R23  0│
│R31 R32 R33  0│
│ 0   0   0   1│
└              ┘
Translation Matrix (T) =
┌    	         ┐
│ 1   0   0   X│
│ 0   1   0   Y│
│ 0   0   1   Z│
│ 0   0   0   1│
└              ┘
Transform Matrix (Tr) =
┌	                            ┐
│R11 R12 R13 R11*X+R12*Y+R13*Z│
│R21 R22 R23 R21*X+R22*Y+R23*Z│
│R31 R32 R33 R31*X+R32*Y+R33*Z│
│ 0   0   0         1         │
└                             ┘
```

### 幾何模型

對於維度空間中的物體，共有以下列常見的模型結構予以表示其呈現狀態與外貌。

+ 線架構模型（Wireframe Model）

僅定義物體形狀，並以點與線構成的模型。

+ 表面模型（Surface Model）

僅定義物體形狀，表面(Surface)會以材質貼圖的模型。

+ 實體模型（Solid Model）

定義物體外觀形狀、內部形體、物理特性，完整設定其物體，使其極度接近真實物體。

+ 分子系統模型（Particle System Model）

無法以物體模型表達的形狀，如：雨、雲、霧、燃燒等，此將以最小單位的物體模型、發光體為基礎，以演算法推算群集內的基本單位運作，使其模擬出目標模型。

### 著色法

電腦圖學在繪製(Rendering)時，會透過當前攝影機、環境、光源，對物體進行投影(Projection)，投影過程中，會經由各種資訊對物體表面材質進行著色(Shading)。

+ 框線著色法（Wireframe Shading）

僅顯示模型的邊緣，不對表面進行著色；此方式用於加快圖形的顯示速度，用於觀察狀態；缺點是較不易完整了解模型的實際形狀。

+ 不打光著色（Unlit Shading）

不計算光源導致的影響，僅對表面著上相同基色，用於確認外觀。

+ 平面著色法（Flat Shading）

計算場景中光源對物體的影響，表面會因為光源特性與選擇的照明效果方式改變其色調；演算是以面維單位計算對光的影響，單一平面受到的光影響平均。

+ 高斯著色法（Gouraud Shading）

計算場景中光源對物體的影響，表面會因為光源特性與選擇的照明效果方式改變其色調；演算是針對每個端點上的亮度，以內插法(Interpolation)的方式，計算出平面上每一個畫素(Pixel)的亮度，以產生比平面著色法更加真實的視覺效果。

+ Phong著色法（Phong Shading）
    - [Phong shading wiki](https://en.wikipedia.org/wiki/Phong_shading)

改良的高斯著色法，除增加法向量計算外，對於光源設上權重，使光的影響層次分明，提高更加真實的視覺效果。

### 照明效果

電腦圖學在繪製時，著色會因為光源的位置、方向影響實際上色的色調、亮度，但光源複雜時，依不同照明效果，光的計算方式亦會改變。

+ 光跡追蹤法（Ray Tracing）

模擬人類瞳孔成像的原理，透過物體表面的多重反射效果，以達到成像的目的；演算概念是透過相機為眼，依據視線向量，在表面產生的法向量來追蹤光源位置與實際成像效果。

+ 熱幅射成像法（Radiosity）

光跡追蹤法並無法考慮光線在物體間散射的效應，且僅用點光源做為圖像計算光源，產生的影像容易有明顯的明暗分野；演算概念以熱學的輻射原理為基礎，利用封閉空間中能量守恆的原理，提出廣義的照明計算模式；使其可精確的模擬物體間散射光交互影響的光線反射，例如金屬物件在受光後會散射出的弱光源亦會列入計算。


### 三維空間的光源，Light in 3D

+ Spot Lights，聚光源

從特定位置朝單一方向，以圓錐形(corn)擴散的光源，具有位置(position)、方向屬性(orientation)；圓錐的形狀是由陰影(umbra)及半影(penumbra)的角度來決定，陰影影響強度中心範圍、半影響柔光外緣範圍。

![](https://upload.wikimedia.org/wikipedia/commons/thumb/0/0d/Umbra01.svg/1280px-Umbra01.svg.png)
+ [Shadow](http://www.cyberphysics.co.uk/topics/light/shadow/shadow.htm)

+ Point Lights，點光源

從特定位置向四周放射一圓球範圍的光源，具有位置，但不具方向屬性；物體離點光源的距離影響其受光度，距離越近越亮(Brighter)，越遠越暗(Darker)。

+ Area Lights，區域光

於特定位置放置二維光源矩陣，往四周放射光源，具有位置，但不具方向屬性；此類光源用於模擬如螢光燈等光源集合，其形狀不限定為方形，亦可為圓形；當二維矩陣縮小到單點，區域光將等同點光源。

+ Directional Lights，有向光

從無限遠位置而來的平行有向光線，具有方向，但不具位置屬性；用於模擬太陽光，或光源過遠過大，在此區域光線是接近平行的情況。

+ Volume Light，發光體

於特定位置放置的造型發光物體，往四周放射光源，具有位置，但不具方向屬性；其光線放射過程類同點光源，若將造型設計成矩陣平面，則與區域光相似；發光體是將空間中的物體指定為發光源，不同物體外型，會使得光源強弱、影響範圍呈現不規則狀態。

+ Ambient Light，環境光

對環境中的每個物體的各個方向打上都具有相同強度的光源，不具位置 (position)、方向屬性 (orientation)；這是模擬環境所有物體皆會反射柔光的情況下產生的效果，不同於有向光的單一方向，放向來自天空、地面、相鄰物體；但於程式模擬中，則將其視為光線來自四周，亦即直接對物體各部位給予等量的光度，並且不會產生陰影。
> 環境光依據不同系統，會有不同情境的設定，例如開啟影子，亦表示對於不同系統而論，環境光可為單一塗色或採用複數有向光、巨大發光體構成。


## 參考

+ [Understanding Different Light Types](http://blog.digitaltutors.com/understanding-different-light-types/)
+ [LIGHTING IN MAYA](http://web.cse.ohio-state.edu/~parent/classes/682/WI12/TechReports/lighting.pdf)
+ [Types of Lights](http://digital-lighting.150m.com/ch02lev1sec2.html)
+ [第16回 光源の方向設定スクリプト, 光源の種類](https://shade3d.jp/training/shallwecustomize/16.html)
+ [多媒體，CH.5 圖形 (Graphics)](http://www.cs.nthu.edu.tw/~snyang/mmedia/mm_ch5.html)
+ [電腦繪圖](http://www.me.lhu.edu.tw/~tin/g/VR/chap5.pdf)
