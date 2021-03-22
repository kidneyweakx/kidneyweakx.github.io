---
title: Hexo升級V5排除疑難雜症
date: 2021-03-18 10:26:00
tags: [程式筆記, Javascript, hexo]
---
因為剛好把電腦重灌，然後這個blog就躺在D槽等著我幫他換新的環境，然後他就被我快樂的升級了。

``` bash
hexo: 5.4.0
hexo-cli: 4.2.0
os: Windows 10 20H2
node: 14.16.0
```
<!-- more -->
## hexo 更新V5.0

hexo 更新到V5的步驟相當容易

```bash
npm install -g npm-upgrade
npm-upgrade
npm i
```

就可以自動更新了，但是版本大更新，往往都會附帶一些小問題，像他就給我了幾個warning

### 更新後Error

```bash
Deprecated config detected: "external_link" with a Boolean value is deprecated. See https://hexo.io/docs/configuration for more details.
```

### 解決方法

修改_config.yml的部分成新版的，原始external_link只有true的選項，更新後可決定是否開啟新分頁

```yaml
# Writing
new_post_name: :title.md # File name of new posts
default_layout: post
titlecase: false # Transform title into titlecase
# 修改這個部分
external_link:
  enable: true # Open external links in new tab
  field: site # Apply to the whole site
  exclude: ''
filename_case: 0
render_drafts: false
post_asset_folder: false
relative_link: false
future: true
highlight:
  enable: true
  line_number: true
  auto_detect: false
  tab_replace: ''
  wrap: true
  hljs: false
prismjs:
  enable: false
  preprocess: true
  line_number: true
  tab_replace: ''
```

---

## hexo-git-backup push出錯

這次更新也讓我使用的hexo-git-backup module出現大問題

```bash
error: src refspec master does not match any
error: failed to push some refs to 'github'
```

這個問題在 issue[#40](https://github.com/coneycode/hexo-git-backup/issues/40)有人做解答

大概解決大概解決方式如下，在node_module/hexo-git-backup中找到上面那行，並把master改成backup，畢竟自己的branch是backup，所以沒辦法找到

```jsx
// 找到這行
// commands.push(['push', '-u', t, 'master:' + repo[t].branch, '--force']);
// 更換成這行
commands.push(['push', '-u', t, 'backup:' + repo[t].branch, '--force']);
```