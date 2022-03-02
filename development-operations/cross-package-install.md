## 安裝 arm64 套件於 amd64 架構

+ 主機架構：amd64
+ 作業系統：Ubuntu 18.04
+ 虛擬環境：Docker

#### 設定 source list 以下載不同架構套件

```
sed -i 's/deb /deb [arch=i386,amd64] /g' /etc/apt/sources.list
touch /etc/apt/sources.list.d/armsource.list
echo deb [arch=arm64] http://ports.ubuntu.com/ bionic main restricted >> /etc/apt/sources.list.d/armsource.list
echo deb [arch=arm64] http://bg.ports.ubuntu.com/ bionic main restricted >> /etc/apt/sources.list.d/armsource.list
dpkg --add-architecture arm64
apt-get update -y
apt-get install -y hello:arm64
```

執行內容結果是套件有找到，但會因為出現如下的 unmet dependencies 問題，若依相依要求安裝，則會因為 ```libc6:arm64``` 要求會從根本更新大量套件導致虛擬環境異常。

```
Some packages could not be installed. This may mean that you have
requested an impossible situation or if you are using the unstable
distribution that some required packages have not yet been created
or been moved out of Incoming.
The following information may help to resolve the situation:

The following packages have unmet dependencies:
 hello:arm64 : Depends: libc6:arm64 (>= 2.17) but it is not going to be installed
E: Unable to correct problems, you have held broken packages.
```

#### 使用 aptitude 安裝

基於 unmet dependencies 的處理議題，相關文獻有建議使用 ```apt-get install -f``` 指令來修復錯誤，但對當前議題並無明顯改善；因此參考文獻另外提及的套件安裝工具 ```aptitude``` 來協助

+ [aptitude Command-line reference](https://www.debian.org/doc/manuals/aptitude/rn01re01.en.html)
+ [How do I resolve `The following packages have unmet dependencies`](https://stackoverflow.com/questions/26571326)
+ [What is APT and Aptitude? and What’s real Difference Between Them?](https://www.tecmint.com/difference-between-apt-and-aptitude/)

```
apt-get install -y aptitude
aptitude install -y libmysqlclient-dev:arm64
```

有完成並處理 unmet dependencies，但並未安裝，也無法確定下載處理後的內容所在位置

#### 參考 Installing cross-dependencies 程序

基於問題在於安裝工具無法安裝相依，那考量以原始碼安裝，因此參考 [MultiarchHOWTO](https://wiki.debian.org/Multiarch/HOWTO) 文獻所述內容。

```
apt-get build-dep -a arm64 libmysqlclient-dev
```

有完成並處理，但並未安裝，也無法確定下載處理後的內容所在位置

#### 下載後安裝

假設相依主因是檢查程序導致，那考量下載後是否可規避。

+ [Ubuntu環境下，如何下載「Package」](http://samwhelp.github.io/blog/read/linux/ubuntu/package/how-to-download-package/)

```
apt-get download libmysqlclient-dev:arm64
```

可以下載，但在執行安裝時仍然會出現 unmet dependencies 問題
