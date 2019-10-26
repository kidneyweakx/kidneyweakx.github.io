---
title: 解決安裝oracle12c遇到[INS-30131]的問題
date: 2019-03-31 23:01:00
tags: [程式筆記, OracleDB]
---
## 測試環境
**win10**

## **error [INS-30131]**
![](https://raw.githubusercontent.com/kidneyweakx/img-host/image/image/orcl01.PNG)
## **解決方法**

開啟cmd輸入
```
路徑(依位置更改)/setup.exe -ignorePrereq -J"-D oracle.install.db.validate.supportedOSCheck=false"
```
就可以進入安裝不跳error了