# inode 限制

Linux 最傳統的磁碟檔案系統 (filesystem) 使用的是 EXT2、EXT3、EXT4，其檔案結構是以 block 與 indoe 構成。

+ [block](https://linux.vbird.org/linux_basic/centos7/0230filesystem.php#block)：用於存放資料的區塊，而區塊的大小配合單檔最大限制，則決定了系統最大支援容量。
+ [inode](https://linux.vbird.org/linux_basic/centos7/0230filesystem.php#inode)：用於描述一個檔案的資訊，其中包括變更時間、儲存區塊等。

一個檔案系統在透過 ```mkfs.ext4``` 分隔時，是依據以下設定產生 inode 數量：

```
inode_count = (blocks_count * block_size) / inode_ratio
```
> indoe_ratio 未透過 ```-i bytes-per-inode``` 設定，則會由 ```/etc/mke2fs.conf``` 內的預設值 16384 來計算。

在不做任何額外設定下，檔案系統的區塊會決定對應多少個 inode，亦即一個檔案系統可以擁有多少個檔案，而當檔案大小改變會產生如下問題：

+ 檔案太小，導致 inode 索引表數量用完而無法建立檔案
+ 檔案太大，導致 indoe 指向多個 block，導致讀檔效率差  

原則上，對於不同的檔案結構要採用不同的 block_size、inode_ratio，以此確保有效的存取資料，若在錯誤的檔案系統設定內存放不合時宜的檔案，會導致如上述的異常。

## 文獻

+ [鳥哥 第七章、Linux 磁碟與檔案系統管理](https://linux.vbird.org/linux_basic/centos7/0230filesystem.php)
    - [inode wiki](https://zh.wikipedia.org/wiki/Inode)
    - [Linux學習之理解inode](https://www.796t.com/content/1542281710.html)

+ [Filssystem command](https://www.binarytides.com/linux-command-check-disk-partitions/)
    - [fdisk](https://man7.org/linux/man-pages/man8/fdisk.8.html)，操作磁區表
        + [10 fdisk Commands to Manage Linux Disk Partitions](https://www.tecmint.com/fdisk-commands-to-manage-linux-disk-partitions/)
    - [df](https://man7.org/linux/man-pages/man1/df.1.html)，報告檔案系統空間使用狀況
        + [Linux 檢查硬碟使用量 df 指令教學與指令稿範例](https://blog.gtwang.org/linux/linux-df-command-check-disk-space-usage-tutorial-script-example/)
        + [How to Check Inode Usage in Linux](https://fedingo.com/how-to-check-inode-usage-in-linux/)
    - [du](https://linux.die.net/man/1/du)，估計檔案空間使用狀況
    - [Linux - 通過LVM對磁碟進行動態擴容](https://www.zendei.com/article/71761.html)
        - [LVM方式掛載硬碟及擴容](https://iter01.com/614819.html)
        - [Ubuntu 18.04 server 擴容(LVM)磁碟](https://www.796t.com/content/1542570486.html)

+ [mkfs.ext4](https://linux.die.net/man/8/mkfs.ext4)
    - [Linux調整系統inode數量例項](https://www.itread01.com/p/182617.html)
    - [Number of Bytes per Inode](https://docs.oracle.com/cd/E19504-01/802-5750/fsfilesysappx-14/index.html)
        + [How many bytes per inodes?](https://stackoverflow.com/questions/3618820)
        + [What is the difference between "inode size" and "Bytes per inode"](https://unix.stackexchange.com/questions/174334)
