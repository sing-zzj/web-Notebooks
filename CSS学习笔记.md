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

