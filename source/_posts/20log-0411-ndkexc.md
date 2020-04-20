---
title: NDK編譯動態庫.so錯誤 executing external native build for cmake
tags:
  - 程式筆記
  - Javascript
date: 2020-04-11 13:42:35
---

剛好在把C++的動態庫加入flutter中，想說寫個Native Java版試試看，結果遇到了這種鬼問題😱😱😱。
```Java
bug: Error > "executing external native build for cmake"
```
本來以為是CMakeLists.txt裡面有一些語法問題，結果仔細改寫了一下，問題依舊。

[參考了這篇](https://blog.csdn.net/kidults/article/details/80599923)想說有可能會改善，結果還是執行到一半報相同的錯誤。
HMMMM🤔......中間又各種改build.gradle和cmake，發現怎麼解都無法編譯成功。
<!-- more -->
翻了一下留言看到這個[解法](https://blog.csdn.net/qq_36818970/article/details/88797526)。
把我的gradle版本降級到3.2.1竟然就可以編譯了
![](https://raw.githubusercontent.com/kidneyweakx/img-host/image/image/20200411-ndkerror.png)

我猜是因為SDK工具缺少一些依賴的工具吧~不過也沒有想要釐清的意思，繼續當搬磚仔，解決這個問題才是惡夢的開始呢。
