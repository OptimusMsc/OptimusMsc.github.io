---
layout: post
title: 爬虫-cookie
categories:
  - 爬虫 Python cookie
tags:
  - 爬虫
  - Python
  - cookie
---

* content
{:toc}


## 什么是cookie

### 是什么？有什么作用？

http请求是无状态的请求协议，不会记住用户的状态和信息，也不清楚你在这之前访问过什么。当网站需要记录用户是否登录时，就需要在用户登录后创建一些信息，并且要把这些信息记录在当前用户的浏览器中。记录的内容就是cookie。

用户使用当前的这个浏览器继续访问这个服务器时，会主动携带这个网站设置的cookie信息。

**cookie会在浏览器中记录信息，并且在访问时携带这个信息**

1. 浏览器更换或删除cookie后，信息丢失；
2. cookie在浏览器中记录的信息是不安全的，因此不能记录敏感信息。



### session

session是在服务器端进行数据的记录，并且给每个用户会生成一个session-id，并且把这个session-id设置在用户的浏览器中，也就是这是为cookie。