---
layout: post
title: R-安装与帮助
<!--date:	2017-08-27-->
categories:
  - 大数据 R 环境配置
tags:
  - 大数据
  - R
  - 环境配置
---

* content
{:toc}

## R的获取与安装

R的下载地址:cran.r-project.org<br>
Windows操作系统下，选择“Download R for Windows”，然后选择“base”，会显示当前R的最新版本，点击下载<br>
<br>
## RStudio的获取与安装<br>
RStudio的下载地址:rstudio.com<br>
在RStudio模块下点击Download，进入版本类型界面，选择RStudio Desktop，然后根据系统版本选择对应的安装程序进行下载<br>
<br>
## R中的包(package)
### 扩展R基本功能的机制/集成了众多函数
### 通常在CRAN/Bioconductor/GitHub等上面获取包
--&nbsp;直接在RStudio的命令行中输入以下代码即可安装包<br>
&emsp;install.packages("包名")  //在CRAN上获取包<br>
&emsp;install_github()  //在GitHub上获取包<br>
&emsp;例如:安装机器学习需要用到的包caret,打开RStudio，在命令行中输入install.packages("caret")，键入回车即可<br>
--&nbsp;安装完之后，使用包内的函数之前，需要加载对应的包，加载的代码为library(包名)<br>
&emsp;例如:library(caret)<br>
--&nbsp;tips:当包加载完之后，直接在命令行输入data()，回车，就能打开包中所有所含函数集的详细信息;<br>
&emsp;如果想查看某一个数据集的具体信息，只需在命令行中输入 ?数据集名称 ，即可。<br>
&emsp;例如?InsectSprays,即(帮助文档)可查看InsectSprays数据集的详细信息(帮助文档)<br>
<br>
## 获取帮助
### ?函数名(R的帮助文档)
### Google/Stackoverflow
### 如何问问题
-&nbsp;操作系统、版本、哪一步产生的错误、预期是什么、得到的结果是什么、其他有用的信息<br>
-&nbsp;例如:Win7 R 3.2.0 lm()  "seg fault on large data frame"<br>