---
layout: post
title: R-缺失值
categories:
  - 大数据 R 缺失值
tags:
  - 大数据
  - R
  - 缺失值
---

* content
{:toc}

## 缺失值(missing&nbsp;value)
--&nbsp;NA/NaN:NaN属于NA,NA不属于NaN(NaN一般用来表示数字的缺失值，而NA可以表示任何类型的缺失值)<br>
--&nbsp;NA有类型属性：integer&nbsp;NA，character&nbsp;NA等<br>

## 使用is.na(&nbsp;)和is.nan(&nbsp;)判断向量中是否含有缺失值
&emsp;例如：<br>
&emsp;&emsp;若输入<br>

	x <- c(1,NA,2,NA,3)
	is.na(x)
	is.nan(x)

运行后会返回<br>

	is.na(x)
	[1] FALSE  TRUE FALSE  TRUE FALSE
	is.nan(x)
	[1] FALSE FALSE FALSE FALSE FALSE

&emsp;&emsp;若输入<br>

	y <- c(1,NaN,2,NaN,3)
	is.na(y)
	is.nan(y)

运行后会返回<br>

	is.na(y)
	[1] FALSE  TRUE FALSE  TRUE FALSE
	is.nan(y)
	[1] FALSE  TRUE FALSE  TRUE FALSE

说明，如果y中包含NAN，则可以被is.na(&nbsp;)检测出来<br>




