### 一、课堂目标

1.熟悉js作用

2.熟悉js各种操作 

#### **二、知识要点**

##### 1.JavaScript简介

JS是一种具有函数优先的轻量级、解释性或即时编译型的编程语言，JS基于原型编程、多范式的动态脚本语言，并且支持面向对象、命令式和声明式(如函数式编程)风格。JavaScript主要解决的是前端与用户交互的问题，包括使用交互与数据交互。

- JS：页面行为：部分动画效果、页面与用户的交互、页面功能

##### 2.JS嵌入页面的三种方式

1、行间事件(此方式主要用于事件)

<input type="button" name

2.页面内使用script标签

3.引入外部js文件

```python
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
<!--  页面内使用js-->
  <script>
    alert('ok!')
  </script>
<!--引入外部js文件-->
  <script src="js.js"></script>
</head>
<body>
<!--行间事件-->
<input type="button" value="点击" onclick="alert('你点击了这个按钮')">
</body>
</html>
```

##### 3.JS变量

**1.基本数据类型**

- number数字类型
- string字符串类型
- boolean布尔类型
- undefined undefined类型，此类型指变量没有初始化，它的值是undefined
- null null类型，表示空对象，如果说定义的变量是为了后面保存对象使用，可以给变量初始化为null

**2.复合类型**

- object

  `var num = 123;`

  ```js
  var num=10;这种是弱类型的变量，看后面附给他什么值，他就是什么类型变量
  var n= NaN;
  var a;
  var str= 'pachong';
  var b=1, c='2', d='3';
  ```

**3.2命名规则**

JS中变量、函数、属性、函数参数命名规则：

> - 严格区分大小写
> - 第一个字符必须是字母、下划线、美元符号$
> - 其他字符可以使用字母、下划线、美元符号或数字

**3.3 JS注释**

js注释也分为两种 单行注释和多行注释

单行注释以两个/开头

//这是一个单行注释



多行注释为/*注释内容*/

/*

这是多行注释

*/

####  

每个句子结必须要加分号；

**4、获取元素**

原生JS中获取HTML元素可以使用以下方法：

- 通过ID获取 document.getElementById()
- 通过name获取 document.getElementByName()
- 通过标签名 document.getElementByTagName()
- 通过类名 document.getElementByClassName()
- 通过选择器获取一个元素 document.querySelector()
- 通过选择器获取全部元素 document.querySelectorAll()

##### 4.1使用内置对象通过ID获取指定元素(getElementById)

- ```html
  <!DOCTYPE html>
  <html lang="en">
  <head>
      <meta charset="UTF-8">
      <title>Title</title>
  <!--页面内使用js-->
  <!--    <script>-->
  <!--      window.onload=function(){-->用window.onload可以让页面加载后再触发语句，可以避免下面div标签还没加载执行时，js获取不到div标签的错误
  <!--        var div1=document.getElementById('div1');-->
  <!--        alert(div1);-->
  <!--      }-->
  
  <!--    </script>-->
  
  <!--引入外部js文件  -->
    <script src="外联js.js" defer="defer"></script>
  </head>
  <body>
  <div id="div1">这是一个div</div>
  <!--<script>-->
  <!--       var div1=document.getElementById('div1');-->
  <!--       alert(div1);-->
  
  <!--    </script>-->
  </body>
  </html>
  ```

##### 4.2使用内置对象通过标签名获取标签选择集(getElementByTagName)

- 参数为获取元素的标签名字，string类型，必须传参数，不区分大小写
- 返回值为标签选择集，并非为数组。如果没有找到该标签则返回空选择集

**getElementByName**方法获取到的是一个选择集，不是数组！但是可以使用下标的方式操作选择集中的标签元素。

```js
<script type='text/javascript'>
  window.onload=function(){
    var all_li=document.getElementsByTagName('li');
    console.log(all_li.length); //在控制台输出all_li的长度

   `//all_li.style.backgroundColor='red';/错误 不可以一次性设置多个元素`
    all_li[1].style.backgroundColor='yellow';//设置下标为1也就是第二个li的背景颜色为yellow
  };
</script>

<body>

<div>
  <ul>
    <li>第一个li</li>
    <li>第二个li</li>
    <li>第三个li</li>
    <li>第四个li</li>
    <li>第五个li</li>
  </ul> 
</div>
</body>
```



4.3使用内置对象通过类名获取类选择集

- 参数是元素中的类名string类型，必须传参数
- 返回的是选择集，没有找到则返回空选择集

```js
<script type='text/javascript'>
  window.onload=function(){
  var all_div=document.getElementsByClassName('div_name');
  console.log(all_div.length);
}
</script>
</head>
<body>
  <div class='div_name'>1</div>
	<div class='div_name'>2</div>
	<div class='div_name'>3</div>
	<div class='div_name'>4</div>
  <div class='div_name'>5</div>
</body>
```

##### 5.操作元素 

js获取到页面元素后，就可以对获取到的元素的属性进行操作，属性的操作包括读和写。

**操作属性的方法：**

> - ‘.’操作
> - “[]”操作

##### JS属性的写法：

> - HTML的属性和JS里面的属性写法一致
> - class写成className
> - style里面的属性，以“-”连接的改写成小驼峰，比如background-color在JS中为style.backgroundColor

```js
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <script>
      window.onload=function(){
        var i=document.getElementById('i');
        var a =document.getElementById('kkb_a');
        var i_name=i.name;
        var i_v=i.value;
        console.log(i_name,i_v)
        a.style.color='red';
        a.style.fontSize='48px';
      }
    </script>
</head>
<body>
<input type="text" name="input_name" id="i" value="i_v">
<a href="https://www.kaikeba.com" id="kkb_a">开课吧官网</a>
</body>
</html>
```

```js
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <script>
      window.onload=function(){
        var all_i=document.getElementsByTagName('input');
        var f=all_i[0].value;
        var px=all_i[1].value;
        var a = document.getElementById('kkb_a');
        //a.style.f = px;//这个方式是不对的，因为此时的f是一个字符串
        a.style[f]=px;

      }
    </script>
</head>
<body>
<input type="text" name="i_name" id="i_1" value="fontSize">
<input type="text" name="i_name" id="i_2" value="40px">
<a href="https://www.kaikeba.com" id="kkb_a">开课吧官网</a>
</body>
</html>
```



**innerHTML**

innerHTML可以直接读取或者写入标签包裹的内容

```js
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <script>
      window.onload=function(){
        var box=document.getElementById('box');
        var box_res=box.innerHTML;//innerHTML读取了box里面的内容
        alert(box_res);
        box.innerHTML='<input type="text" name="i_name" id="i_1" value="fontSize">';/注意这里要加引号在'<input>''
      }//这里替换了box里面的内容
    </script>
</head>
<body>
<div id="box">这是id为box的div标签</div>
</body>
</html>
```



**运算符注意点**

- == 123==‘123’--->true

js中==只判断值，不判断具体的类型，只要值相等，就返回true，实际上内部会有数据转换

- === 123==='123'--->false

  不只是判断值，还判断类型，只有两者都相等，才为true



#### 7.JS函数

**7.1JS函数定义与执行**

<script>
  //定义函数
  function func_console(){
    console.log('hello JS!');
  }
  /执行函数
  func_console();
</script>

**7.2匿名函数**

Function(){

...

}这就是一个匿名函数



###自己感觉<script></script>里面在写各种各样的动作

<body></body>是管结构的

**return关键字**

return的作用：

> - 返回函数执行的结果
> - 结束函数的运行
> - <u>阻止默认行为</u>

```js
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <script>
      function func_alert(a){
      alert(a);
      return 123; //return 结束了函数的运行
      alert(123)
      }
      console.log(func_alert(666));
    </script>
</head>
<body>

</body>
</html>
```



#### 8.调试的方法

> - alert
> - Console.log(常用的调试程序的方法)
> - Document.title

调试的时候一般来说不使用document.title,而alert()需要弹出，会阻止函数的运行。console.log不会有这个缺点，所以最常用的是console.log