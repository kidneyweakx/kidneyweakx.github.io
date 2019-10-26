---
title: Rails error 小處理紀錄
date: 2019-03-27 22:58:00
tags: [程式筆記, Ruby on Rails]
---
## Runtime **error**
```ruby
'Could not find a JavaScript runtime' but execjs AND therubyracer are in Gemfile
```
## **solution.**

只要在gemfile加入
```ruby
gem 'execjs'
gem 'therubyracer', :platforms => :ruby
```
就解決了

## 出現這個warning
```ruby
add gem 'sqlite3'
```

可是在gemfile裡已經有了sqlite3卻出現錯誤

## **solution.**

將原本
```ruby
gem 'sqlite3'
```
改成
```ruby
gem 'sqlite3','~> 1.3.0'
```