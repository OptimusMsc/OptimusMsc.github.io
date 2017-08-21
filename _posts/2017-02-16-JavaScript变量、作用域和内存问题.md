---
layout: post
title:  JavaScript变量、作用域和内存问题
date:   2017-02-16 09:20:00 +0800
categories: 前端
tag: JS
---

* content
{:toc}


基本内容
------------------------

1、ECMAScript变量包含两种类型的值：基本类型值和引用类型值。<br>
2、JavaScript变量为松散类型，松散类型变量的特点就是定义的时候不给它指定类型，变量在运行的时候可以随便改变数据类型。<br>
3、执行环境及作用域<br>
执行环境定义了变量或函数有权访问的其他数据，决定了它们各自的行为。每个执行环境都有一个与之关联的变量对象，环境中定义的所有变量和函数都保存在这个对象中。
每个函数都有自己的执行环境。当执行流进入下一个函数时，函数的环境就会被推入一个环境栈中。而在函数执行之后，栈将其环境弹出，把控制权交给之前的执行环境。
当代码在一个环境中执行时，会创建变量对象的一个作用域链，作用域链的用途是保证对执行环境有权访问的所有变量和函数的有序访问。

示例代码1:  

    var color = "blue";  
    function changeColor(){  
      if(color==="blue"){  
        color="red";  
        }else{  
         color="blue";  
        }  
    }  
    changeColor();  
    console.log("Color is now"+color);   
    

运行结果：Color is now red<br>
在上面这个例子中，变量color为全局环境的变量对象，在作用域链中可以找到它，所以在函数内部可以访问变量color，执行if语句，color变成red。<br>

示例代码2:  

    var color = "blue";  
    function changeColor(){  
    var anotherColor = "red";  
    function swapColors(){  
      var tempColor = anotherColor;  
      anotherColor = color;  
      color = tempColor;  
      //这里可以访问color、anotherColor和tempColor
    }  
    //这里可以访问color和anotherColor,但不能访问tempColor  
      swapColors();  
    }  
    //这里只能访问color  
    changeColor();  
    console.log("color is now "+ color);  

运行结果：color is now red<br>
在上面这个例子中，涉及三个执行环境，：全局环境、changeColor()的局部环境和swapColor()的局部环境，全局环境中有一个变量color和changeColor()函数，changeColor()局部环境中有一个变量anotherColor和swapColors()函数，但是可以访问变量color,swapColors()局部环境中包含一个变量tempColor，但是可以访问变量color和变量anotherColor。
这段代码环境的作用域链如下图所示
![/styles/images/JavaScript变量、作用域和内存问题/zuoyongyu.png]({{ '/styles/images/JavaScript变量、作用域和内存问题/zuoyongyu.png' | prepend: site.baseurl  }})

<br>
在执行环境中，内部环境可以通过作用域链访问外部环境的变量和函数，但是外部环境不能访问内部环境的变量和函数，每个环境只能向上搜索作用域链。


预加载、变量提升
------------------------
javascript语言的松散类型的特点以及运行时候随时更改变量类型的特点，很多程序员会认为javascript变量的定义是在运行期进行的，更有甚者有些人认为javascript代码只有运行期，其实这种理解是错误的，javascript代码在运行前还有一个过程就是：预加载，预加载的目的是要事先构造运行环境例如全局环境，函数运行环境，还要构造作用域链，而环境和作用域的构造的核心内容就是指定好变量属于哪个范畴，因此在javascript语言里变量的定义是在预加载完成而非在运行时期。<br>
JavaScript引擎的工作方式是先解析代码，获取所有被声明的变量，然后再一行一行的运行，这造成的结果，就是所有变量的声明语句都会被提升到代码的头部，这就叫做变量提升。
例:  
  
    var a = 1;  
    function test(){  
      console.log(a);//undefined  
      var a = 2;  
      console.log(a);//2  
    }  
    test();  

上面这段代码在函数的局部作用域下变量a被重新定义了，在预加载时候a的作用域范围也就被框定了，a变量不再属于全局变量，而是属于函数作用域，只不过赋值操作是在运行期执行（这就是为什么javascript语言在运行时候会改变变量的类型，因为赋值操作是在运行期进行的），所以第一次使用a变量时候，a变量在局部作用域里没有被赋值，只有栈区的标示名称，因此结果就是undefined了。（这也就是js里的变量提升的原理）

