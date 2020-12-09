# Git 議題

Git 是版本控制的基本工具，相關文件可以參考官方說明文件。

+ [Git Documnet](https://git-scm.com/book/zh-tw/v2/%E9%96%8B%E5%A7%8B-%E9%97%9C%E6%96%BC%E7%89%88%E6%9C%AC%E6%8E%A7%E5%88%B6)

在 DevOps 中的持續整合 ( CI、Continuous integration ) 需要優先解決問題就是通一軟體專案的軟體庫，而 Git 提供的就是一個可用於多人管理程式原始碼的機制，其中 Repository ( 庫 )、Branch ( 分支 ) 的運用更直接影響 Git-Flow 的設計，從而影響著軟體編譯、發佈、部屬的腳本機制；亦可說持續整合的腳本內主要就是使用 Git command line 在控制。

常見的 Git 命令

+ [clone](https://git-scm.com/docs/git-clone)
+ [fetch](https://git-scm.com/docs/git-fetch)
+ [pull](https://git-scm.com/docs/git-pull)
+ [push](https://git-scm.com/docs/git-push)
+ [checkout](https://git-scm.com/docs/git-checkout)
+ [merge](https://git-scm.com/docs/git-merge)
+ [rebase](https://git-scm.com/docs/git-rebase)

## 合併庫

**git submodule 是 link 的概念，而 git subtree 則是 copy的概念**
> from twtrubiks

+ [Submodule vs Subtree](https://blog.puckwang.com/post/2020/git-submodule-vs-subtree/)
+ [神奇的 Git Subtree](https://hexo.crboy.net/2016/09/amazing-git-subtree/)
+ [git subtree tutorial](https://github.com/twtrubiks/Git-Tutorials/blob/master/git_subtree_turorial.md)

## 遠端分支

**Git 的分支分為本地 ( Local ) 與遠端 ( Remote )，而遠端可以是不同主機，只要此遠端庫是從其中一個庫分支出來即可**

+ [Git Document : git remote](https://git-scm.com/docs/git-remote)
+ [Git Local 端與 Remote 端的分支操作](https://medium.com/@sean22492249/3dc360be3b5b)
+ [How To Push Git Branch To Remote](https://devconnected.com/how-to-push-git-branch-to-remote/)

## .git 冗餘資料處理
> [git script document](./git-reduce-repo-size.md)

**Git 本身的原理記錄檔案快照，也是就是完整的備份，而不是差異備份。**
> from Code Alchemist

依據相關文件說明，Git 是對所有檔案建立目錄，而每個 Commit 是所有檔案快照的組合；亦即若有一檔案有更新，則此檔案在目錄的相關記錄會變更，而此次的 Commit 會記錄使用新的檔案代碼，因此若不斷更改同個檔案則該檔案會不斷備份。

由此可知，原則上 Git 使用原則是『常態修改的檔案越小越好，避免存放壓縮檔、圖檔、音檔等大容量檔案』

+ [Git Document : git rev-list](https://git-scm.com/docs/git-rev-list)
    - [git rev-list 文件](https://cloud.tencent.com/developer/section/1138780)
+ [Git Document : git rm](https://git-scm.com/docs/git-rm)
+ [Reducing the repository size using Git](https://repository.prace-ri.eu/git/help/user/project/repository/reducing_the_repo_size_using_git.md)
+ [git rm與git rm --cached](https://www.itread01.com/content/1541861779.html)
+ [Git gc 指令學習，回收消失在歷史之中的commit所佔用的空間](http://marscoding.blogspot.com/2016/01/git-gc-commit.html)
+ [解決github項目體積過大的問題](https://codertw.com/%E7%A8%8B%E5%BC%8F%E8%AA%9E%E8%A8%80/684259/)
+ [如何给git仓库瘦身](https://www.techug.com/post/git-reduce-volumn-tips.html)
+ [Git不小心commit了很大的檔案怎麼辦？](https://www.itread01.com/content/1541997604.html)
