---
title: 安裝ruby環境發現rvm not a function bug
date: 2019-03-26 09:59:00
tags: [程式筆記, Ruby on Rails]
---
## **出現這個error** 
*rvm not a function*
```
error:Warning! PATH is not properly set up, '/home/me/.rvm/gems/ruby-2.x.x-p247/bin' is not available, usually this is caused by shell initialization files 
```
## **輸入**
```
rvm reset
rvm version
```

當輸入rvm version 不再跳出rvm not a function 就解決這個問題了