### CSS笔记 

------

#### 基本知识点

##### 规则：选择器 + 声明 	

<img src="images/css规则.png" title="css规则" width="100" height="150"/>

**选择器**表明应用规则的元素。同一条规则可以应用到过个元素上，前提是需要将这个元素用逗号隔开

**声明**用于表明应该如何显示选择器指明的元素。声明分为两个部分（属性和值）并用冒号隔开。

##### 常用网站

在线调试不同浏览器网址：

BrowserCam.com

BrowserLab.Adobe.com

BrowserShots.org

CrossBrowserTesting.com

CSS bug解决网址:

PositionIsEverything.net

QuirksMode.org

拾色工具网址：

https://colorschemedesigner.com/csd-3.5/

对比度调试网址：

https://snook.ca/technical/colour_contrast/colour.html

##### 标签属性

前景色color：

​	RGB值：rgb(100.100.90)

​	十六进制编码：#eese8o

​	颜色名称：Red

CSS3：透明度（opacity, rgba）

opacity属性允许你指定元素及其子元素的透明度，该值介于（0.0~1.0）

rgba属性允许你添加透明度

```css
p.one {
    background-color: rgb(0.0.0);
    opacity :0.5;
}
p.two {
    background-color: rgb(0.0.0);
    background-color: rgba(0.0.0.0.5);
}
```

CSS3：HSL和HSLA

CSS3引入了一种全新的并且直观的方式来指定颜色，通过色调、饱和度和明度来确定是颜色。

```css
body {
    background-color: #C8C8C8;
    background-color: hsl(0.0%.78%);
    
}
p {
    background-color: #ffff;
    background-color: hsla(0.0%.78%.0.5);
    
}
```



#### 1、CSS导入HTML方式

- 行外导入：使用link元素
- 内部写入：使用style元素
- 行内写入：在标签内部使用style元素


```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charest="utf-8">
    <title>firstHtml</title>
    <!-- 内部样式 -->
    <link rel="stylesheet" href="style.css" type="text/css" />
    <!-- 外部样式 -->
    <style>
        h1{
            color: brown;
        }
    </style>
</head>

<body>
    <!-- 行内样式 -->
    <h1 style="color: aqua;">Hello World!</h1>
</body>

</html>
```

#### 2、选择器
##### 2.1、基本选择器

- 通用选择器：应用到所有的元素 "* {}"
- 类型选择器：匹配元素名称与选择器相同的元素"h1,h2,h3 {}"

- 标签选择器：直接应用到所选的所有标签"标签{}"
- 类选择器：应用到所选择的class特性值上，可以跨标签使用 ".class的特性值{}"
- id选择器：应用到所选择的id特性值上"#id的特性值{}"

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="utf-8">
    <title>选择器的使用</title>

    <style>
        /* 标签选择器 */
        p{
            color: rgb(165, 6, 228);
        }
        /* 类选择器 */
        .school{
            color: crimson;
        }
        /* id选择器 */
        #sex{
            color: rgb(219, 241, 14);
        }

    </style>
</head>
<body>
    <p>姓名：</p>
    <p>年龄：</p>
    <p id="sex">性别：</p>
    <p class="school">学校：</p>
</body>
</html>
```

##### 2.2、层次选择器

- 后代选择器：选择子孙元素 " "
```css
body p{
    color: violet;
}
```
- 子选择器：只选择子元素，不选择孙子元素 ">"
```css
body > p{
        background-color: darkslategray;
        color: rgba(223, 18, 18, 0.747);
}
```
- 相邻兄弟选择器：只选择下一个兄弟元素 "+"
```css
.two + li{
    color:yellow;
}
```
- 通用选择器：选择下面的所有兄弟元素 "~"
```css
#sex ~ p{
    color: teal;
}
```

##### 2.3、结构伪类选择器（带条件的选择器）
伪类：条件
```css
/* 选中 ul 下第一个li标签 */
ul li:first-child{
    background-color: teal;
}
/* 选中 ul 下最后一个li标签 */
ul li:last-child{
    background-color: violet;
}
/* 选中第二个li标签 */
li:nth-of-type(2){
    background-color: red;
}
```

##### 2.4、选择器优先级

###### 2.4.1、级联规则

1. 就近原则：如果两个选择器完全相同或者同类，第二个选择器优先于第一个选择器；

   ***注：id选择器> 类选择器 > 标签选择器 > 类选择器***

2. 具体性原则：如果第一个选择器比其它的选择器更加具体，那么具体的选择器优选与其他选择器；

3. 重要性：在任意属性值的后面添加**！important**来强调这条规则比应用于同一元素的其他规则更加重要。

   ```css
   p b {
       color:blue !important;
   }
   ```

###### 2.4.2、继承

#### 3.CSS的元素显示模式

##### 3.1 块元素

常见块元素：h1 ~ h6、p、div、ul、ol、li ...

特点：

- 独占一行
- 宽度、高度、外边距、内边距都可以控制
- 宽度默认是容器（父级宽度）的100%
- 本身是一个盒子，里面可以放行内或者块级元素

注意：\<p>，\<h1>等文字类元素主要放文字，里面不能再放块级元素了；

##### 3.2 行内元素（内联元素）

常见行内元素：a、strong、b、strong、em、span、i ...

特点：

- 相邻行内元素在一行上
- 高、宽不能设置
- 默认宽度就是本身宽度
- 行内元素本身只能容纳文本或其他行内元素

注意：\<a>链接元素可以放块级元素，但是需要转换一下块级模式最安全。

##### 3.3 行内块元素

又称特殊的行内元素，有 \<img />、\<input />、\<td>，既有块元素特点又包含行内元素特点。

特点：

- 相邻行内元素在一行上显示，但是它们之间会有空隙
- 默认宽度就是本身宽度
- 高度、宽度、外边距和内边距都可以设置

##### 3.4 （块 / 内联）元素之间的相互转换

```css
display: block;
display: inline;
display: inline-block;
```

#### 4.背景设置

##### 4.1 常用背景属性大全

| 属性                  |   作用   |   值   |
| :-------------------- | ---- | ---- |
| background-color      |    背景颜色  | 预定义的颜色值/十六进制/RGB代码 |
| background-image      |      背景图片| url(图片路径) |
| background-repeat     |     是否平铺 | repeat/no-repeat/repeat-x/repeat-y |
| background-position   |     背景位置 | length/position |
| background-attachment |    背景附着  | scroll（背景滚动）/fixed（背景固定） |
| 背景简写              |    书写更简单  | 颜色 图片地址 平铺 滚动 位置 |
| 背景色半透明          |     背景颜色半透明 | 1.background: rgba(0,0,0,0.6);<br />2.opacity: 0.6; |
|  |  |  |

##### 4.2 背景图片位置

```css
background-position: x y;
```

x，y可以使用方位名词或者精确单位，且可以混搭使用

方位名词：top，center，bottom，left，right

##### 4.3 单行文字垂直居中

方案：让文字的行高（line-height）等于盒子的高度，就可以让文字在当前盒子内垂直居中了。

#### 5.链接样式（伪类选择器应用）

:link 允许你设置还没有访问过的链接

:visited 允许你设置已经点击过的链接样式

:hover 允许你你将定位设备（例如 光标）悬停于某个元素上时生效

:active 只有元素进行操作时生效（例如 点击、右键...）

```css
a:link {
    color:red;
    text-decoration: none; /* 是否显示下划线*/
}
a:visited{
	color:black;
}
```

