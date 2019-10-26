---
title: 完整重灌Linux 必裝軟體及微調系列
date: 2019-03-26 22:19:00
tags: [程式筆記, Linux]
---
**這幾天重灌了好幾次的Ubuntu 18.04@@**

1. 第一次新手測試，然後因為Libreoffice在渲染windows傳來的文件有點當的關係就回去灌了windows，結果發現並沒有比較好。
2. 第二次就是灌完windows那一瞬間後悔，結果重新裝好Ubuntu發現其實還是可以日常使用。
3. 然後在灌完bumblebee之前都還很健康，一灌完整個驅動都出問題啦，只好迅速的重灌

#### 下面就逐一介紹我都裝什麼，還有怎麼設定的

**粗體為我個人認為必裝**
1. (**美化terminal**)zsh+oh my zsh ([我是按照這篇來的](https://segmentfault.com/a/1190000015283092))
2. (**hime**)詞音輸入法([相當詳細的介紹及設定](https://blog.goodjack.tw/2013/08/linux-phonetic-setting.html))讓我的輸入法和windows接近
3. (**夜間模式**)redshift 腳本([腳本這裡改的](https://blog.csdn.net/dr_unknown/article/details/53766921))
4. **開機就亮numlock**，這對用鍵盤非常重要 ([非常實用的文章](https://blog.csdn.net/artourins/article/details/86411786))
5. gnome tweak調整dpi什麼之類的 和一些主題
6. (google drive同步)rclone rclone browser，有GUI方便很多
7. (**電源管理**)tlp powertop 省電神器
8. (coding)eclipse & android-studio Java 開發兩大神器，軟體中心就有了很方便，再載個vscode整個就滿分了。
9. 一定要說的是不要做死去載bumblebee，雖然很方便可是刪除後很多apt-get的問題
10. apt-get 問提要靠強制刪除dpkg解決，有點麻煩@@
11. /etc/fstab設定 第一次設一直開不了機搭配
`ln -s` 很好用
12. 將ubuntu home資料夾換成英文的目錄

```
export LANG=en_US 
xdg-user-dirs-gtk-update
```