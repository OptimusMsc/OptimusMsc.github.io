---
layout: post
title: R-数据框
categories:
  - 大数据 R 数据框
tags:
  - 大数据
  - R
  - 数据框
---

* content
{:toc}

## 数据框(data frame)
--&nbsp;主要用于存储*表格数据*(tabular&nbsp;data)<br>
--&nbsp;视为各元素长度相同的列表<br>
&emsp;&emsp;·&nbsp;每个元素代表*一列数据*<br>
&emsp;&emsp;·&nbsp;每个元素的长度代表*行数*<br>
&emsp;&emsp;·&nbsp;元素类型可以不同<br>

### 使用data.frame(&nbsp;)函数创建数据框
&emsp;例如：df <- data.frame(id = c(1,2,3,4), name = c("a","b","c","d"), gender = c(TRUE,TRUE,FALSE,FALSE))，即可得到<br>

	  id name gender
	1  1    a   TRUE
	2  2    b   TRUE
	3  3    c  FALSE
	4  4    d  FALSE

&emsp;可以使用nrow(&nbsp;)和ncol(&nbsp;)来查看数据框的行列数<br>
&emsp;例如：nrow(df)和ncol(df)会得到<br>

	> nrow(df)
	[1] 4
	> ncol(df)
	[1] 3	

&emsp;数据框中的**元素类型**也可以**一致**<br>
&emsp;例如：df2 <- data.frame(id = c(1,2,3,4), score = c(80,86,90,100))，会得到&emsp;<br>

	  id score
	1  1    80
	2  2    86
	3  3    90
	4  4   100

&emsp;这种特殊情况下，可以将数据框转换为矩阵，使用data.matrix(&nbsp;)函数，输入data.matrix(df2)，会得到<br>

	     id score
	[1,]  1    80
	[2,]  2    86
	[3,]  3    90
	[4,]  4   100

