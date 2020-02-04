---
title: 辨識錯誤 tensorflow KeyError "The name 'import/input' refers to an Operation not in the graph."
date: 2019-04-07 20:00:00
tags: [程式筆記, Tensorflow]
---
## **近期遇到的小錯誤**
```python
KeyError: "The name 'import/input' refers to an Operation not in the graph."
```
![](https://raw.githubusercontent.com/kidneyweakx/img-host/image/image/tensor01.PNG)

簡單來解釋就是他的名字你打錯了 所以input才會input錯
<!-- more -->
我自己爬文去嘗試了各種"Mul" "input"之類的都錯

最後看到這篇文章 [link](https://developer.arm.com/technologies/machine-learning-on-arm/developer-material/how-to-guides/optimizing-neural-networks-for-mobile-and-embedded-devices-with-tensorflow/determine-the-names-of-input-and-output-nodes)

## **懶人包**
> 先用tensorflow的工具將.pb轉成可以用tensorboard可以觀看的格式，再查出**input_layer**(我的是placeholder)和output_layer是甚麼名字再重新修正。



這是我的程式碼(再依照個人需求更改)
```python
python tensorflow\examples\label_image\label_image.py --graph=tmp\output_graph.pb --label=tmp\output_labels.txt --image=tmp\91076.png --input_layer=Placeholder --output_layer=final_result
```

輸出
![](https://raw.githubusercontent.com/kidneyweakx/img-host/image/image/tensor02.PNG)