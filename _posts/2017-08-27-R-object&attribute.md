---
layout: post
title: R-常见对象和属性
categories:
  - 大数据 R 对象和属性
tags:
  - 大数据
  - R
  - 对象和属性
---

* content
{:toc}

## R中对象的5种基本类型(classes of objects)
--&nbsp;字符(character)<br>
--&nbsp;数值(numeric:real numbers)<br>
--&nbsp;整数(integer)<br>
--&nbsp;复数(complex):1+2i<br>
--&nbsp;逻辑(logical:True/False)<br>
<br>
### R中的赋值符号为<-
&emsp;例如，想新建一个值为1的变量x，则输入x<-1，回车即可<br>
&emsp;创建字符型变量，y<-"hello world"<br>
&emsp;创建逻辑型变量，t<-TRUE，需要注意的是，R中的TRUE和FALSE要全部大写<br>
&emsp;创建复数型变量，x<-1+2i<br>
### 查看变量的值的方法
&emsp;输入变量名，回车即可<br>
&emsp;例如：输入x，回车，则会显示[1] 1.其中[&nbsp;]中的1代表后面所接的元素，是x中的第1个元素；没有[&nbsp;]的1代表x中存储的内容为1<br>
&emsp;*右侧Global Environment中也会显示变量名和对应的值*<br>
### 查看对象的类型
&emsp;使用class()函数<br>
&emsp;例如：输入class(x)，回车，则可以看到x的类型为"numeric"<br>
&emsp;如果想强调变量类型为整数，则只需要在赋值的时候，在数字后面加上L(大写)，例如：x<-2L，此时class(x)会显示为"integer"<br>
**tips:<br>
&emsp;1.如果用"="代替"<-"，在99%的情况下都不会报错，但是某些及端情况会出错，所以应该尽可能使用标准赋值符号"<-"<br>
&emsp;2.R是大小写敏感的语言，x和X会代表不同的变量，注意区分大小写<br>
&emsp;3.RStudio中"#"为注释符，后面跟的内容为注释内容**
<br>
## R中对象的属性(attribute)
--&nbsp;名称(name)<br>
--&nbsp;维度(dimensions:matrix,array)<br>
--&nbsp;类型(class)<br>
--&nbsp;长度(length)<br>