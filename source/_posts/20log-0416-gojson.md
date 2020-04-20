---
title: Golang Json解析問題 Struct字首大小寫 
tags:
  - 程式筆記
  - Golang
date: 2020-04-16 23:20:35
---
其實這還蠻有趣的，最近在玩golang的爬蟲，高效率的編譯和好用的colly真的還挺好上手的，但是畢竟爬蟲還是要encode成Json才好做跨平台處理。
<!-- more -->
只是莫名其妙遇到Json print出來都是 
```
[]
[]
[]
```
🤔這是甚麼狀況呢？搞了很久以為是我們Json結構設錯，加了一堆亂七八糟的限制。
結果跑了 [Gobyexample的範例](https://gobyexample.com/json)，意外發現可以跑！

就把他的struct拿過來改，發現首字母都是大寫，原本寫小寫就直接印空白的東西給我們。
這種不報錯的bug最可惡了🤬