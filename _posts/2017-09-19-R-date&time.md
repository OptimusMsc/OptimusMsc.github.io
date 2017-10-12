---
layout: post
title: R-日期与时间
categories:
  - 大数据 R 日期 时间
tags:
  - 大数据
  - R
  - 日期
  - 时间
---

* content
{:toc}

## 日期与时间(date&time)
### 日期；Date
&emsp;&emsp;·&nbsp;距离1970-01-01的天数/date(&nbsp;)/Sys.Date(&nbsp;)<br>
&emsp;&emsp;·&nbsp;weekdays(&nbsp;)/months(&nbsp;)/quarters(&nbsp;)/julian(&nbsp;)<br>

#### 使用date(&nbsp;)获取当前时间
&emsp;运行x <- date(&nbsp;)，可以得到<br>

	[1] "Tue Sep 19 17:28:01 2017"

&emsp;存储类型为"character"型<br>

#### 使用Sye.Date(&nbsp;)获取当前日期
&emsp;运行x2 <- Sys.Date(&nbsp;)，可以得到<br>

	 "2017-09-19"

&emsp;存储类型为"Date"型<br>

#### 使用as.Date(&nbsp;)函数将任意日期存储为Date类型
&emsp;例如：x3 <- as.Date("2018-01-01")，运行x3以及class(x3)将会得到<br>
	
	[1] "2018-01-01"
	[1] "Date"

&emsp;需要注意的是，as.Date(&nbsp;)函数中填入的为字符型变量，年月日之间需要用**-**隔开，月和日均需要输入两位数<br>

#### 使用weekdays(&nbsp;)、months(&nbsp;)、quarters(&nbsp;)、julian(x3)函数可以获取Date类型的变量中的"星期"、"月份"、"季度"、"距离1970-01-01过了多少天"属性
&emsp;例如：weekdays(x3)、months(x3)、quarters(x3)、julian(x3)会得到<br>

	[1] "星期一"
	[1] "一月"
	[1] "Q1"
	[1] 17532
	attr(,"origin")
	[1] "1970-01-01"

#### Date类型的数值可以直接进行数学运算
&emsp;例如；新建Date型变量x4 <- as.Date("2019-01-01")，输入x4-x3，会得到<br>

	Time difference of 365 days

&emsp;若只想得到数字结果，只需要强制转换为numeric类型即可，输入as.numeric(x4-x3)，会得到<br>
	
	[1] 365

### 时间：POSIXct/POSIXlt
&emsp;&emsp;·&nbsp;距离1970-01-01的秒数/Sys.time(&nbsp;)<br>
&emsp;&emsp;·&nbsp;POSIXct：整数，常用于存入数据框<br>
&emsp;&emsp;·&nbsp;POSIXlt：列表，还包含星期、年、月、日等信息<br>

#### 使用Sys.time(&nbsp;)获取当前的系统时间
&emsp;运行x <- Sys.time(&nbsp;)，可以得到<br>

	[1] "2017-09-20 11:12:54 CST"

&emsp;存储类型为"POSIXct"型<br>

#### 使用as.POSIXlt(&nbsp;)函数将"POSIXct"转换为"POSIXlt"型
&emsp;运行p <- as.POSIXlt(x)，可以得到<br>
	
	[1] "2017-09-20 11:12:54 CST"

&emsp;存储类型为"POSIXlt"型<br>	

#### 使用names(&nbsp;)和unclass(&nbsp;)函数查看POSIXlt类型中存了哪些变量
&emsp;运行names(unclass(p))，可以得到<br>

	 [1] "sec"    "min"    "hour"   "mday"   "mon"    "year"   "wday"   "yday"   "isdst"  "zone"   "gmtoff"

#### 使用$获取每个对应变量的具体值
&emsp;例如：运行p$sec，可以得到<br>

	[1] 54.43747

&emsp;即p存储的sec变量的值为54.43747<br>

#### 使用as.POSIXct(&nbsp;)函数将"POSIXlt"转换为"POSIXct"型
&emsp;例如：运行q <- as.POSIXct(p)，class(q)可以得到q为"POSIXct"型<br>

