---
title: Hexo Next 主題增加評論系統 utterances
date: 2019-10-26 23:30:00
tags: [程式筆記, Javascript, hexo]
---
## 前言
> 剛好在搞`hexo`的裝潢，想到自己還沒有評論區
- `Next`其實本來就內建很多評論系統了，例: Disqus、gitment等...
- Disqus我平常沒甚麼在用，再辦一個帳號對我懶癌發作的人很痛苦；於是就找上了`gitment`一個將Github issue成為評論系統的工具。
- 不過我在爬文時又看到這篇[建议大家弃用 Gitalk 和 Gitment 等权限过高的 Github OAuth App](https://www.v2ex.com/t/535608)。
- hmmm...我不想被惡意工程師搞QAQ

## Why Utterances
所以我選了[utterance](https://utteranc.es/)<br>
它也是運用Github去儲存評論，十分有趣的做法。<br>
而且要求的權限少很多，真是優質的工具。

## 配置

### 授權
授權utterances可以拿到評論後提交到`repo`中的`Issues`裡<br>
先點這個網址 https://github.com/apps/utterances<br>
它就會和你要授權，我是選hexo的那個blog repo
![](https://raw.githubusercontent.com/kidneyweakx/img-host/image/image/utter-01.jpg)

### 設置
來這個網址 https://utteranc.es/ <br>
在`configuration`的repo:中打上你剛才授權的`repo`
![](https://raw.githubusercontent.com/kidneyweakx/img-host/image/image/utter-02.jpg)
接著把這段script複製下來
![](https://raw.githubusercontent.com/kidneyweakx/img-host/image/image/utter-03.jpg)
ex. 可以加`label`讓評論在`Issues`裡更好看
