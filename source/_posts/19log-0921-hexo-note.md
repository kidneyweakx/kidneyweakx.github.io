---
title: 用Hexo免費製作一個blog
date: 2019-09-21 02:00:00
tags: [程式筆記, Javascript, hexo]
---
在種種原因之下，從Blogger牽到GitHub Pages上，陪伴我一學期的Blogger正式停止更新。紀念一下[這是原站點](https://kidneyweakx.blogspot.com/)，而讓我跳槽到Hexo的原因如下:
- Blogger 後臺真的十分陽春(上手很難進一步改動)。
- 我習慣使用的Markdown語法需要轉成html再貼上Blogger編輯器。
- 功能被Blogger本體受限。
- 加個程式框還要改css，基本上修改一下自訂主題就不會想再多做修改了。
<!-- more -->
所以我就跳槽囉~~

## Why GitHub Pages??
選擇Github Pages的原因很簡單:
1. 可以直接使用markdown語法撰寫文章
    - Markdown語法十分輕鬆，且可以簡單插入程式碼
    - 簡單做到排版，讓使用者更專注於文章內容，而非html語法
    - 基本語法[CheatSheet](https://markdown.tw/)
2. 能夠Hosting再[GitHub Pages](https://pages.github.com/)上
    - 只要在Github新建一個username.github.io的倉庫，就能透過username.github.io到達主頁
    - 不需要自己管理主機交由github來處理
3. 可以使用[git](https://git-scm.com/)管理自己的網誌
    - 可以使用branch和merge來管理目前需要更動的文章
    - 刪除文章也可以透過git恢復

## Why Hexo??
使用Hexo前我有試過[Jekyll](https://jekyllrb.com/)，因為我對Ruby比較熟悉一些。
但是Jekyll的中文資源較少，且Ruby在windows上的表現，hmmm...沒有要戰的意思，不過相對Ruby，Hexo需要的Node.js對windows更友善些。
我覺得最重要的還是Hexo作者[tommy351](https://twitter.com/tommy351)是台灣人!!還不用起來。
其實還有一些[技術性](https://zespia.tw/blog/2012/10/11/hexo-debut/)的關係啦 ！像Ruby文章一多生成網站的速度就會慢很多，雖然Jekyll也有人做出些優化的方法，不過我不想弄得那麼麻煩，所以最後就選擇Hexo啦~

## 安裝流程

> 安裝Node.js

- 先去[Node.js](https://nodejs.org/en/)官網下載安裝

> 安裝 [Hexo](https://hexo.io/zh-tw/index.html)

- npm安裝

`npm install hexo-cli -g`
- 安裝成功後，可以輸入來確定版本

`hexo version`
- 建立自己的blog

```js
hexo init blog  #初始化blog
cd blog         #切換至blog資料夾
npm install     #安裝相關套件
hexo server     #在localhost顯示頁面
```

- 將文章部屬上github

```js
deploy:
    type: github
    repository: git@github.com:yourname/yourname.github.io.git
    branch: master
```

在這邊就不贅述github和本機端連線的教學了

- 執行部屬

`hexo d`

**若發生ERROR Deploer not found，執行以下程式碼**
`npm install hexo-deployer-git --save`

## 美化Blog
當然用hexo最重要的就是美化blog囉~
而我使用[Next](https://theme-next.iissnan.com/)，將它clone至themes資料夾，再修改這邊。

```js
## Extensions
## Plugins: https://hexo.io/plugins/
## Themes: https://hexo.io/themes/
theme: next #修改這行
```

就可以依造官網調配出屬於你自己的Next。

## 使用編譯器編輯文檔
我自己是使用vscode去撰寫.md檔，可以一邊預覽一邊寫文章相當方便，且搭配終端機可以達成快速撰寫並送出的功能
```js
hexo clean
hexo d -g #d部屬 g=generate
```
就可以很輕鬆地將md檔自動轉成html並部屬到你的github上了。

## 修改標題顏色
在`source/css/_variables/base.styl`裡面有個顏色原本的色碼
用[w3s](https://www.w3schools.com/colors/colors_picker.asp)選個喜歡的顏色`hexo s`看一下
![](https://raw.githubusercontent.com/kidneyweakx/img-host/image/image/hexo01.jpg)


## Extra Live2D看板娘

這裡就不說太多
> 先安裝live2d pkg

`npm install --save hexo-helper-live2d`

> 選擇你愛的[2D娘](https://github.com/xiazeyu/live2d-widget-models)

`npm install {你選的}`

> 設定`_config.yml`加上下面這堆

```js
live2d:
  enable: true
  pluginModelPath: assets/
  model:
    use: live2d-widget-model-haru/02 # 改成你選擇的
  display:
    position: right
    width: 150 
    height: 300
  mobile:
    show: false  #手機顯示
```
---

## Reference
[Hexo 安裝教學、心得筆記](https://wwssllabcd.github.io/blog/2014/12/22/how-to-install-hexo/)
[Hexo+GitHub，新手也可以快速建立部落格](https://yaoandy107.github.io/hexo-tutorial/#more)
[用Hexo打造你的專屬Blog](https://dtes8617.github.io/2018/01/16/%E7%94%A8Hexo%E6%89%93%E9%80%A0%E4%BD%A0%E7%9A%84%E5%B0%88%E5%B1%ACBlog/)
[hexo 添加live2d看板动画](https://www.jianshu.com/p/3a6342e16e57)
[hexo-helper-live2d](https://www.npmjs.com/package/hexo-helper-live2d)