## Cross Compiler

**『A cross compiler is a compiler capable of creating executable code for a platform other than the one on which the compiler is running. For example, a compiler that runs on a Windows 7 PC but generates code that runs on Android smartphone is a cross compiler.』**
> [Cross compiler wiki](https://en.wikipedia.org/wiki/Cross_compiler)

從眾多文獻討論與方法來看 Cross-Compiler，可以區分成兩個主題：

+ 作業系統
> 典型解釋是在 Windows 上編譯在 Andorid 上執行的軟體

+ CPU 架構
> 典型解釋是在 Linux OS 上編譯用於不同 x86、arm、s390x 的 CPU 上可執行的軟體



#### 參考

+ 利用虛擬環境編譯相對架構下的執行檔
    - https://docs.conan.io/en/latest/howtos/run_conan_in_docker.html
		- https://build2.org/
		- docker pull --platform 指令為 experimental (daemon)API 1.32+，Set platform if server is multi-platform capable；依據這說明仍舊需依靠主機本身的規格
+ 依據 makefile 運作原理解釋其專案運作方式
		- https://mropengate.blogspot.com/2018/01/makefile.html
		- https://zh.m.wikibooks.org/wiki/CMake_%E5%85%A5%E9%96%80
		- 原理解釋：
		    + C++ 專案是以專案資料夾為單一專案，透過 makefile 產生必要的編譯輸出檔案
        + 藉由 makefile 腳本指令，安裝至相對作業系統的執行環境中
				    - 產生的 .h 檔案會移動到 /usr/local/include
            - 產生的 .so 相關檔案會移動到 /usr/local/lib
        + 藉由系統指令 ( systemctl、service ) 呼叫其執行運作
    - 依據 cmake 設定
		    + https://gitlab.kitware.com/cmake/community/-/wikis/doc/cmake/CrossCompiling
    - 依據 gcc 參數設定
        + https://gcc.gnu.org/onlinedocs/gcc/ARM-Options.html

+ [Multi Architecture Docker Image using Cross Compilation — Part 1](https://imdurgadas.medium.com/65bd26d4b017)
