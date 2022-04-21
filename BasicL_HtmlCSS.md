# 大前端



## Html
*Hyper text makeup language*

Html5  + CSS3


工具 WebStorm/ 	IDEA直接集成了 配置setting web

```html
<!-- -->		//html注释格式


<DOCTYPE html>   //告诉浏览器使用什么规范

    //这里写的不会显示
    
    
<html lang="en ">
    
    <!-- 代表网页头部 -->
    <head>
        <!-- meta 描述性标签，用来描述网页信息 -->
        <!-- meta一般用来做SEO-->
        <meta charset="UTF-8">
        <meta name="keyword" content="CC,Java">
        <meta name="description" content="learn">
        
        <!--网页标题（标签选项卡） -->
        <title>  TITLE </title>
    </head>
    
    <!-- 代表网页主体-->
    <body>
        
        
        Hello World!
        
        
    </body>
    
    </html>






```







### 基本标签



```html


<body>
    <!--标题标签 -->
    <h1>
        <h2>
            <h3>
                
                
            </h3>
        </h2>
 
    </h1>
    
    <!-- 段落标签-->
    
    <p>
        <!-- 不分段都会生成一行，没有换行，没有段落，没有空格-->
    </p>
    
    <p>     
    </p>
    
    <br/> <!-- 自闭合标签，分行-->
    
    
    <hr/><!-- 水平线标签-->
    
    <!-- 粗体标签/斜体-->
    <strong></strong>
    <em></em>
    
    <!-- 特殊符号-->
    <!-- 空格-->  &nbsp;
    <!-- 大于符号--> &gt;
    <!-- 小于符号--> &lt;
    <!-- 版权--> &copy;
    
    
</body>



```


### 图像标签



```html
<img src="" alt="">

// ../上一级目录
<img src="../resource/image.1.jpg" alt="图片名称（找不到图片时候显示）" 
     title ="悬停文字" width="" height="">
//很多属性，推荐相对路径






      


```





### 链接标签

```html
<a href="https://baidu.com">   链接文字 /点击我跳转</a>


<a href="index.html">  
	<img src="../resource/image.1.jpg" alt="图片名称（找不到图片时候显示）" 
     title ="悬停文字" width="" height="">
</a>
//图片超链接


<a href="https://baidu.com" target="_blank"> </a>
<a href="https://baidu.com" target="_self"> </a>
//在本页面打开，在新标签页打开

```



锚链接

*跳转到顶部底部等*

- 需要一个锚标记
- 跳转到标记



用name标签来标记， 用



```html
<a name="top">顶部</a>

   


<a href="#top">回到顶部</a>
<a href="index.html#down">   链接文字 /点击我跳转</a>
跳到不同页面的特定位置


```





功能性链接

邮件链接

```html
<a href="mailto:c_parenthetical@outlook.com">点击联系我</a>
```



QQ联系

在QQ推广中之输入直接就可以输出代码，加入a标签





行内元素（重新换行）和块元素<p>（不换行）



### 列表

```html
//有序列表<order list>
<ol>
    <li></li>
    <li></li>
    <li></li>
    
</ol>

    
 
<hr/>

    
    
//无序列表
<ul>
    <li></li>
    <li></li>
    <li></li>
    
</ul>
    


//自定义列表（公司网站底部）
<dl>
    <dt></dt> 	列表名称
    
    <dd></dd>	列表内容
    <dd></dd>
    
    
    
    </dl>
    
    
    
    
    
```





### 表格标签

```html
<table border="1px">
    <tr>
    <td></td>
    <td></td>    
    <td></td>
    <td></td>
    </tr>
    
    <tr>
    <td></td>
    <td></td>    
    <td></td>
    <td></td>
    </tr>
    
    <tr>
    <td></td>
    <td></td>    
    <td></td>
    <td></td>
    </tr>
</table>
     
```





### 媒体元素



```html
<video src="../resources/video/.mp4" controls autoplay></video>

<audio src="../resources/audio/.mp3" controls autoplay></audio>

<!--
autoplay 自动播放
controls 控制台/没有的话就没办法控制

-->

    
 
```









### 页面结构



```html
<!--
header	标题头部信息
footer	脚步
section
article
aside
nav			导航




-->

<body>
    
    
    
	<head><h2></h2></head>
    

    <section><h2></h2></section>
 
    
    <footer><h2></h2></footer>
        

    
</body>



```







### iframe 内联框架

*打开一个内嵌的网页*



```html
<iframe src="https://baidu.com" frameborder="" width="1000px" height="800px">
    
</iframe>
```







### !!表单语法



```html
<form method="post" action="result.html">
    
</form>

<!--
action： 向哪里提交表单信息
method：get明文（好调试），post安全

-->
<p>

<input name ="" type="text" value="zzzz" maxlength="8" size="30">
    
</p>


//单选框标签
<p>
Gender：
<input name ="sex" type="radio"/>male
<input name="sex" type="girl" checked/>female	//默认
    
</p>

type: 
name:名称
value:元素初始值
size
checked

```



```html
//多选框
<input type="checkbox" value="sleep" name="hobby"/>
<input type="checkbox" value="code" name="hobby" checked/>	//默认
<input type="checkbox" value="game" name="hobby"/>
<input type="checkbox" value="chat" name="hobby"/>



//按钮
<input type="button" name="btn1" value="点击变长">


//图片变成一个按钮
<input type="image" src="index.html">


<input type="reset">	//重置按钮
<input type="button">	//普通按钮
<input type="submit">	//提交按钮
<input type="image">	//图片按钮






       

```







```html

//下拉框：不是input

<select name ="列表名称">
    
    <option value="C">china</option>
    <option value="U">USA</option>
    <option value="S" selected>Sweden</option>   //默认的值
    <option value="I">India</option>
    
</select>



<textarea name="textarea" cols="50" rows="10">文本内容</textarea>



//文件域

<input type="file" name="files">
<input type="button" value="upload" name="upload">





//邮件验证//缺少@就不行，初级验证

<input type="email" name="email">

//URL验证
<input type="url" name="url">

//数字验证
<input type="number" name="num" max="" min="" step="">


//滑块调整音量
<input type="range" name="" min="" max="" step=""/>

//搜索框
<input type="search" name="search">







```





### 表单应用

```html
//只读不能更改
readonly
<input type="text" name="" value="admin" readonly>

//禁用
disabled

//隐藏 传递默认值
hidden




//点文字直接指向位置
//增强鼠标可用性
//只要指定id-for就可以
<lable for="mark">点我试试</lable>
<input type="text" id="mark">





```





- Hidden
- Readonly
- Disabled







### 表单初级验证

- placeholder 在输入框中提示输入， 只要输入就消失
- required 必须输入，不能为空
- pattern 正则表达式





```html
<input type="text" name="" value="admin" placeholder="请输入用户名">
<input type="text" name="" value="admin" required>
<input type="text" name="" value="admin" pattern>



//可以搜索学习正则表达式
<input type="text" name="Diymail">
```





高级验证需要js

















## CSS



### Basic

- CSS
- CSS选择器
- 美化网页(文字/阴影/超链接/列表/渐变)
- 盒子模型
- 浮动
- 定位
- 网页动画（特效）





Cascading Style Sheet 层叠级联样式表

美化网页

字体/颜色/



CSS2	DIV块 分离html和css

CSS2.1 浮动/定位

Css 3 圆角/阴影/动画/浏览器兼容





### CSS语法

```css
选择器{
    声明1；
    声明2；
    声明3；
}
```





```html
关联html和css
<head>
<link rel="stylesheet" href="css/style.css">      
</head>






```



1. 内容表现分离
2. 网页结构统一，可以复用
3. 样式丰富
4. html css分离
5. 利用SEO，容易被搜索引擎收录（Vue不容易被收录）









### CSS导入方式

```html
//1、行内样式，效果最差

<h1 style="color:red">
    
</h1>


//2、style标签 内部样式，没有行内优先级高

<style>
/*
    */
    h1{
        color:green;
    }

</style>



//外部样式<link> 就近原则
<link rel="stylesheet" href="css/style.css">


//导入式 慢慢消失，不好用，先展示骨架
<style>
	@import url("css/style.css");
</style>


```





外部样式和内部样式符合就近原则，谁和标签进谁ok









### !!选择器



> 选择页面上某一个或者某一类元素



基本选择器

- 标签选择器
- 类选择器
- ID选择器







```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    
    <style>
    h1[
        /*标签选择器会选择页面上所有的这个标签*/
        color:#a13d30;			//IDEA可以自己选择颜色
        border-radius: 24px;
        ]
    p{
            font-size="";
        }
      
        
        
        .CCC{
            /*类选择器（.class 名称）*/
            
            
            
        }
        
        /*ID选择器(#ID 名称)
        ID必须保证全局唯一*/
        
        #zhang{
            
        }
        
        
        
        
    
    </style>
    
    </head>

<body>
    
    <h1 class="CCC">
        Java learning
    </h1>
    <p id="zhang">
        CCC learning
    </p>
    
    
    </body>






```



- 不遵循就近

  ID选择器 > Class选择器 > 标签选择器 





#### 层次选择器

















































```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    
    <style>
    
    
    </style>
    
    </head>

<body>
    
    <h1>
        Java learning
    </h1>
    <p>
        CCC learning
    </p>
    
    
    </body>





```



