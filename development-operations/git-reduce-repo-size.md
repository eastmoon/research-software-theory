# Reducing the repository size

+ 列出專案關聯列表

```
git rev-list --objects --all
```
> 依據 .git 的檔案記錄列表列出受版本控制的噹案與其代碼

+ 列出前五個最大檔案

```
git rev-list --objects --all | grep "$(git verify-pack -v .git/objects/pack/*.idx | sort -k 3 -n | tail -5 | awk '{print$1}')"
```
> 依據 .git 記錄查詢n所有保存的壓所檔案 ( *.idx )，在將搜尋結果排序 ( sort ) 後取得前 5 筆記錄 ( tail -5 )
> 若要需列出的 x 數量，則應修改腳本為 ```tail -x```

+ 移除檔案並指定該檔案不再受版本控制
    - 移除 .tar 的 .git 中的快取 ( 不在接受版本控制 )
    ```
    git filter-branch --force --prune-empty --index-filter 'git rm -rf --cached --ignore-unmatch *.tar' --tag-name-filter cat -- --all
    ```
    - 移除 .tgz 的 .git 中的快取 ( 不在接受版本控制 )
    ```
    git filter-branch --force --prune-empty --index-filter 'git rm -rf --cached --ignore-unmatch *.tgz' --tag-name-filter cat -- --all
    ```

+ 執行垃圾處理程序，並統計專案大小

```
git reflog expire --expire-unreachable=now --expire=now --all
git gc --prune=now
git count-objects -vH
```

+ 上傳修正紀錄

```
git commit -m 'delete .git legacy file'
git push
```
