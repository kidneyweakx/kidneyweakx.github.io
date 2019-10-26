---
title: css 重點筆記
date: 2019-03-14 22:46:00
tags: [程式筆記, css]
---
## margin 與 padding 的差異
- 位置是他們最大的差異
- margin 是外邊距，有負值，別稱 填充
- padding 是內邊距，別稱 空白邊
## 甚麼是 box model
- 框模型(box model)是包含border(邊框)、margin(外邊距)、padding(內邊距)和處理元素內容的處理方式。

## 為何要使用 em 而非 px 來定義字的大小
- 為了在internet explorer調整文本大小
- em可以在所有瀏覽器更改文字大小，px在部分瀏覽器不行
- px是用來調邊距的單位

[參考網址](http://www.w3school.com.cn/css/css_boxmodel.asp)
---
#### **[問答]** h1 {margin : 10px 0px 15px 5px;} 的margin-top、margin-right、margin-left、margin-bottom 各是多少？
- 照順時鐘順序排列
top 10px
right 0px
bottom 15px
left 5px
learn.from here


---
### **Extra**

1. 如果缺少左外邊距的值，則使用右外邊距的值。
2. 如果缺少下外邊距的值，則使用上外邊距的值。
3. 如果缺少右外邊距的值，則使用上外邊距的值。
