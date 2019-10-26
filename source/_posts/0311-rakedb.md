---
title: 介紹rake三兄弟(rake db 發生問題時使用)
date: 2019-03-11 09:30:00
tags: [程式筆記, Ruby on Rails]
---
## **rails db 有問題自救**
__照順序輸入或單獨執行migrate__
```
rake db:drop  #刪除數據庫
rake db:create #新建數據庫
rake db:migrate #更改數據庫(有時可單獨執行)
```