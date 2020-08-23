## Scale-invariant feature transform、SIFT

+ [Scale-invariant feature transform wiki](https://en.wikipedia.org/wiki/Scale-invariant_feature_transform)

SIFT對尺度(Scale)、旋轉(Rotation)以及一定視角和光照變化等圖像變化都具有不變性，並且SIFT具有很強的可區分性。

SIFT算法的實質是在不同的尺度空間上查找關鍵點(特征點)，並計算出關鍵點的方向。SIFT所查找到的關鍵點是一些十分突出，不會因光照，仿射變換和噪音等因素而變化的點，如角點、邊緣點、暗區的亮點及亮區的暗點、鞍點等。

SIFT算法的缺點：

1. 演算需求效能高，導致即時性差。
2. 影像結構會導致特征點數量變動。
3. 對邊緣光滑或平滑圖像無法准確提取特征點。

## Speeded up robust features

+ [Speeded up robust features wiki](https://en.wikipedia.org/wiki/Speeded_up_robust_features)

SURF算法是SIFT算法的效能提升變型演算法，在滿足一定效果的情況下完成兩幅圖像中物體的匹配，並基本實現了實時處理。SURF也檢測空間域和尺度域上的局部極大值作爲特征，但是使用的是Hessian行列式響應而不是Laplacian行列式。

##### § 參考

+ [Introduction to SIFT (Scale-Invariant Feature Transform)](http://docs.opencv.org/master/da/df5/tutorial_py_sift_intro.html#gsc.tab=0)
+ [CHRIS MCCORMICK](https://chrisjmccormick.wordpress.com/2013/01/24/opencv-sift-tutorial/)
+ [OpenCV2學習筆記十二：特征提取算法SIFT與SURF](http://www.tamabc.com/article/1731.html)
+ [SIFT vs SURF](http://zhvillues.tumblr.com/post/119561114181/sift-vs-surf)
+ Kernel (image processing), Convolution
    - [Kernel (image processing)](https://en.wikipedia.org/wiki/Kernel_(image_processing))
    - [Ludwig ImageConvolution](https://www.scribd.com/document/251115663/Ludwig-ImageConvolution)
+ Tutorials - SIFT with Open MATLAB
+ Domain-Size Pooling in Local Descriptors and Network Architectures
