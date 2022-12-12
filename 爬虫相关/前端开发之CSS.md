### 目标

1.掌握CSS中的各种选择器

2.熟悉CSS基础样式

### 知识要点

##### 1.**CSS简介**

**1.1CSS定义**

CSS是一种用来表现HTML文件样式的语言，不仅可以静态修饰网页，还可以配合各种脚本语言动态地对网页元素进行格式化。CSS能够对网页中元素位置的排版进行像素级精确控制，支持几乎所有的字体字号样式，拥有对网页对象和模型样式编辑的能力

简单来说：CSS就是前端页面的化妆术  

- CSS基本语法

选择器(属性：值；属性：值；属性：值；)

选择器是指将样式和页面元素关联起来的名称

属性是指希望设置的样式属性，每个属性有一个或多个值

css注释 ctrl+shift+/

  

div{

​		Width:500px;

​		height:500px;

​		color:green

}

内嵌式：在head里写

外联式，通过link标签

导入式



font同时设置文字的几个属性

font:是否加粗 字号/行高 字体

如font：normal 24px/48px '宋体'；

Text-decoration:设置文字下划线：none没有下划线

Text-indent:24px首行缩进

Text-align:center 设置文字水平居中



#### CSS选择器

**1.id选择器**

通过id名来选择元素，元素的id名称不能重复，所以使用id作为选择器只能对应一个页面上的元素，不能复用，id一般来说是给程序使用，不推荐作为CSS选择器使用

**2.标签选择器**

标签选择器会针对所有的标签进行应用样式，所以在使用时尽量和层级选择器一起使用。

<p>{color:green;
  }
</p>

**3.类选择器**

类选择器是通过类名选择元素，一个类可以应用于多个元素，一个元素也可以使用多个类。是CSS中用的最多的一种选择器

多个类选择器class="r bl y"

多个类选择器同时修改一个标签的同一个属性时，会选择类选择器的最后一个

在title里.r{里面写元素属性

}

**4.层级选择器**

针对不同的块用不同的颜色

**5.伪类、伪元素选择器**

常用的伪类选择器hover：当鼠标悬浮在元素上的时候的状态

伪元素选择器before和after：通过样式往标签中插入内容

```python
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>caomi</title>
    <style>
        .a{color:red}
        .a:hover{color:blueviolet}/悬停变色
        .b:before{content: '插入在前面'}
        .c:after{content: '插入在后面'} 

    </style>
</head>
<body>
<h1 class="a">这是第一级标题</h1>
<h2 class="b">这是第二级标题</h2>
<h3 class="c">这是第三级标题</h3>
```



#### CSS盒子模型

css盒模型本质上是一个盒子，封装周围的HTML元素，它包括：边距，边框，填充和实际内容

设置对应的样式分别为：盒子的宽度width,盒子的高度height，盒子的边框border，盒子内的内容和边框之间的间距padding，盒子与盒子之间的间距margin

![image-20221122155920662](https://tva1.sinaimg.cn/large/008vxvgGgy1h8eatdq6gsj30h60aqgma.jpg)

**设置宽高(width,height)**

> width：300px；这里的宽度指内容的宽度，不是整个盒子的宽度
>
> Height：300px，指的是内容的高度

**设置边框(border)**

设置边框可以指定某一边，也可以一次性设置四个边

设置上边框

`Border-top-color:blue;`

`Border-top-width:10px;`

`Border-top-style:solid`

`上面三个可以合成一句`

`Border-top:blue 10px solid;`

如果想设置其他三个边，只需把top修改为对应的边即可，border-left; border-right; border-bottom

如果四个边设置的一样可以直接设置为

`Border:blue 10px solid;`

**设置内间距padding**



**CSS元素溢出**

overflow

```python
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Titleaaa</title>
  <style>
    div{
        width:100px;
        height:120px;
        border:2px red solid;
        overflow:auto /溢出
    }
  </style>
</head>
<body>
<div>
  <p>asdfdsfdsfdsfdsfdffsd</p>
</div>
</body>
</html>
```

**浮动**

Float:left







