### HTML学习记录

#### <span style='color:brown;font-size:20px'>一、文本处理</span>

- ##### **段落标签**

```html
<p>段落标签</p>
<h1>标题元素标签 主标题</h1>
<h2>标题元素标签 二级子标题</h2>
<h3>标题元素标签 三级子标题</h3>
.
.
<h6>
```

- ##### **列表**

```html
<!-- 无序列表 -->
<ul>
	<li>张国荣</li>
	<li>周润发</li>
	<li>李小龙</li>
</ul>
```

```html
<!-- 有序列表 -->
<ol>
	<li>张国荣</li>
	<li>周润发</li>
	<li>李小龙</li>
</ol>
```

- ##### **斜体字、粗体字、下划线..**

```html
<!-- 斜体字 -->
<i>你好</i>
<em>你好</em>         <!-- 表示强调 默认斜体-->

<!-- 粗体字 -->
<b>你好</b>
<strong>你好</strong>  <!-- 表示内容十分重要 默认粗体 -->

<u>你好</u>

```

- ##### 超链接

  绝对URL ：href:"https://www.baidu.com"

  相对URL：

  ​					本文件：href:"demo.html"

  ​					子文件：href:"fold/demo.html"

  ​					父文件：href:"../demo.html"

```html
<p>
    <!-- 如果希望在新窗口打开链接，就把target属性设置为_blank-->
	<a href='超链接地址' title='超链接名称' target="_blank">链接名称</a>
</p>
```

###### 	链接到当前页面的某个特定位置：

​			<b>id</b> 特性：一个可以应用在所有HTML元素中的特性，id特性值必须以字母或者下划线开头，并且在同	一个页面中，不允许出现两个相同的id特性值。

​			要想链接到该页面的特定位置，该特定元素必须使用id特性，然后用\<a>元素，不同的是**href**特性值以	**#**开头。

```html
<!-- 点击链接，直接定位到<h2> -->
<a href="#arc_shot">Arc Shot</a><br />
.
.
.
<h2 id='arc_shot'>Arc Shot</h2>
<p>A shot which the subject is photographed by an enrichling or moving camera</p>
```

###### 	链接到特定页面的某个特定位置：

​			如果想要链接到其他页面的特定位置，使用相对或绝对URL，并且保证该位置有**id**属性。

```html
<a href="https://developer.mozilla.org/zhCN/docs/Games/Tutorials/2D_Breakout_game_pure_JavaScript/#下一步">javascript</a>
```

- ##### 图片

  \<img>元素

  特性：

  ​			src : 告诉浏览器在何处找到图片。特性值是一个指向网站内的某个图片的相对URL.

  ​			alt : 这个特性对图像进行文本说明，在你无法查看对象时显示出来

  ​			title：浏览器会在光标悬停在图像上时显示title特性的内容

  ​			height：以像素为单位来指定图像的高度

  ​			width：以像素为单位来指定图像的宽度

  ```html
  <img src="images/p2363058433.jpg" alt="杭州南京" title="杭州南京" width='300' height="150" />
  ```

  ###### 两种显示

  ​	在代码中插入图像的位置非常重要，因为浏览器有两种显示HTML元素的方式：

  1. <strong>块级元素总是另起一行显示。</strong>例如，\<h1>和\<p>都是块级元素
  2. <strong>内联元素位于块级元素中，并且不会另起一行显示。</strong>例如，\<b>、\<em>和\<img>都是内联元素。

  ###### 图像和图像说明

  ```html
  <figure>
  	<img src="images/p2363058438.jpg" alt="江苏南京">
  	<br />
  	<figcaption>
  		<i>来源：豆瓣 江苏南京游玩</i>
  	</figcaption>
  </figure>
  ```
  

  <hr />

  ##### Web图像

  ###### 创建图像的三条规则：

  1. 使用正确的格式保存（jpeg, png...）
  2. 以正确的大小保存图像
  3. 以像素来衡量图像										

  ###### 常用图库：

  ​					www.istockphoto.com

  ​					www.gettyimages.com 

  ​					www.veer.com  

  ​					www.sxc.hu  

  ​					www.fotolia.com

  ###### 编辑图像工具：

  ​	软件：Adobe Fireworks、Pixelmator、PainShop Pro、Paint.net

  ​	在线编辑器：www.photoshop.com、www.pixlr.com、www.splashup.com、www.ipiccy.com		

  ###### 图像格式：

  ​	JPEG：当图像中包含多种不同的颜色时，应当保存为 **jpeg** 格式。

  ​	PNG or GIF：当图像中包含少量的颜色或者大面积的同色区域时，应当将其保存为PNG或GIF。例如，徽标、插图、图表...

  <hr />

- ##### 表格

**\<table>**

**\<tr>**
	\<tr>标签表示每行的开始，之后是一个或多个\<td>元素 （tr表示table row）

**\<td>**
	表格中的每个单元格用\<td>元素表示（td表示 table data）

```html
<table>
    <tr>
        <td>15</td>
        <td>15</td>
        <td>30</td>
    </tr>
    <tr>
        <td>45</td>
        <td>60</td>
        <td>45</td>
    </tr>
    <tr>
        <td>60</td>
        <td>90</td>
        <td>80</td>
    </tr>
</table>
```

###### 添加表格标题：

**\<th>**

​	\<th>元素和\<td>元素用法一样，但他表示列或行的标题。（ th 代表table heading）

```html
<th scope='col'>Sunday</th>           <!-- 行标题-->

<th scope='row'>Total sales:</th>	  <!-- 列标题-->
```

###### 跨列 \ 跨列：

​	可在<th>或<td>元素中用colspan特性和rowspan特性来实现跨行、跨列。

```html
<td colspan="2">Math</td>  <!-- Math在一行中占两列-->

<td rowspan="2">Art</td>   <!-- Art在一列中占两行-->
```

###### 表格设计：

​	\<thread> 表示表格的标题

​    \<tbody> 表示表格的内容

​    \<tfoot> 表示表格的角注

- ##### 表单

  <figure>
      <img src="表单.png" alt="表单控件" width="700" height="550"/>
      <br />
      <figcaption><i>表单控件<i></figcaption>
  </figure>

  HTML表单是由一个或多个小部件组成的。这些小部件可以是**文本字段(单行或多行)**、**选择框**、**按钮**、**复选框**或**单选按钮**。大多数情况下，这些小部件与描述其目的的标签配对——正确实现的标签能够清楚地指示视力正常的用户和盲人用户输入表单所需的内容。

  ###### 表单结构

  \<form> 元素

  ​	表格控件位于\<form>中。每个\<form>元素都应该设置action特性，通常还要设置method特性和id属性。

  ```html
  <form action="/my-handling-form-page" method="post">
  
  </form>
  ```

  **action**` 属性定义了在提交表单时,应该把所收集的数据送给谁(/那个模块)(URL)去处理。.

  **`method`** 属性定义了发送数据的HTTP方法(它可以是“get”或“post”).

  ###### 文本框（用来输入）

  \<input>元素

  ```html
  <form action="https://www.baidu.com">
      <p>
          账号
          <input type="text" name="Username" maxlength="10" />
      </p>
      <p>
          密码
          <input type="password" name="password" maxlength="21" class="span3 required"/>
      </p>
  </form>
  ```

  ​	**type**特性的值决定将要创建那种控件；

  ​	--type="text"  
  ​    --type="password"

  ​	**name** 特性值对表单控件进行标识；

  ​	**maxlength** 特性值表示输入字符的最大数量；

  ​	**placeholder** 特性值用来提示用户输入。

  \<textarea>元素：用来创建多行文本框。

  ```html
  <form action="https://www.baidu.com">
      <textarea name="sevice" cols="10", rows="4">Enter...</textarea>
  </form>
  ```

  

  ​	**rows** 特性值表示行数

  ​	**cols** 特性值表示列数

  ​	**name** 特性值对表单控件进行标识；

  **按钮（用来选择）**

  ​	**单选按钮** 

  ​		单选按钮只让用户从一系列选项中选择其中一个，一旦选中，便不能取消。可以用来条款和协议中。

  ```html
  <form>
  <p>Please select your favorite genre:
      <br />
      <input type="radio" name="genre" value="rock" checked="checked" /> Rock
      <input type="radio" name="genre" value="pop" /> Pop
      <input type="radio" name="genre" value="jazz" /> Jazz
  </p>
  </form>
  ```

  ​	\<input>元素 

  ​		--**type**="radio"

  ​		**name** 当一个问题以单选按钮的形式给用户提供一系列答案时，用来回答这个问题的name特性值	都应该相同。

  ​    	**value** 特性为选项指定了被选中时要发送服务器的值。

  ​		**checked** 特性用来指定页面加载时哪个值会被选定，同一组中的单选按钮只能有一个。

  ​	**复选框**s

  ```html
  <form>
      <p>
  		<input type="checkbox" name="genre" value="rock" checked="checked" /> Rock
  		<input type="checkbox" name="genre" value="pop" /> Pop
  		<input type="checkbox" name="genre" value="jazz" /> Jazz
  	</p>
  </form>
  ```
  ​	\<input>元素

  ​	--**type**="checkbox"

  ​	**name** 当一个问题以单选按钮的形式给用户提供一系列答案时，用来回答这个问题的name特性值	都应该相同。

  ​	**value** 特性为选项指定了被选中时要发送服务器的值。

  ​	**checked** 特性用来指定页面加载时哪个值会被选定，同一组中的单选按钮只能有一个。

  ​	**下拉列表框**

  ​		让用户在一个下拉列表中选择一个选项，常用来使用一个很长的列表选项。

  ```html
  <form>
  <p>
  	<select name="devices">
  		<option value='ipod'>ipod</option>
  		<option value="radio">radio</option>
  		<option value="computer" selected="selected">computer</option>
  	</select>
  </p>
  </form>
  ```
  ​	\<select>元素：用来创建下拉列表框，它包含两个或者两个以上的\<option>

  ​		**name** 特性用来指定这个表单控件的名称，此名称与用户选择一并发送到服务器。

  ​	\<option> 元素：同于指定用户选择的选项

  ​		**value** 特性用来指定选项的值，会被发送到服务器；

  ​		**selected** 特性用来指定页面加载时哪个值会被选定。

  ​		

- ##### 缩略语

```html
<abbr title='超文本标记语言'>HTML</abbr>
```

- ##### 上标和下标

```html
<sup>2</sup>
<sub>2</sub>
```

- ##### 换行和分割线

```html
<br />
<hr />
```

- ##### 引用

```html
<blockquote cite="引用来源">
    content			<!-- 较长引用, 默认会进行缩进 -->
</blockquote>

<q>
	content          <!-- 较短引用 默认加上双引号-->
</q>

<!--当引用电影，书籍..来表明引用来源 -->
<cite> content </cite>
```

- ##### 内容修改

```html
<ins></ins>元素用来显示已经插入到文档中的内容，通常带有下划线
<del></del>元素用来显示已经从文档中删除的文本，通常带有删除线
<s></s>元素表示不准确或不相关并不予以删除的内容
```



- ##### \<head> 里面的标签设置

```html
<title> content </title> <!-- 内容显示在浏览器的顶端-->

```



#### <span style='color:brown'>二、文档的基本组成部分</span>

网页的外观多种多样，但是除了全屏视频或游戏，或艺术作品页面，或只是结构不当的页面以外，都倾向于使用类似的标准组件：

- 页眉

  通常横跨于整个页面顶部有一个大标题 和/或 一个标志。 这是网站的主要一般信息，通常存在于所有网页。

- 导航栏

  指向网站各个主要区段的超链接。通常用菜单按钮、链接或标签页表示。类似于标题栏，导航栏通常应在所有网页之间保持一致，否则会让用户感到疑惑，甚至无所适从。许多 web 设计人员认为导航栏是标题栏的一部分，而不是独立的组件，但这并非绝对；还有人认为，两者独立可以提供更好的 [无障碍访问特性](https://developer.mozilla.org/zh-CN/docs/learn/Accessibility)，因为屏幕阅读器可以更清晰地分辨二者。

- 主内容

  中心的大部分区域是当前网页大多数的独有内容，例如视频、文章、地图、新闻等。这些内容是网站的一部分，且会因页面而异。

- 侧边栏

  一些外围信息、链接、引用、广告等。通常与主内容相关（例如一个新闻页面上，侧边栏可能包含作者信息或相关文章链接），还可能存在其他的重复元素，如辅助导航系统。

- 页脚

  横跨页面底部的狭长区域。和标题一样，页脚是放置公共信息（比如版权声明或联系方式）的，一般使用较小字体，且通常为次要内容。 还可以通过提供快速访问链接来进行 [SEO](https://developer.mozilla.org/zh-CN/docs/Glossary/SEO)。



为了实现语义化标记，HTML 提供了明确这些区段的专用标签，例如：

- \<header>：页眉。
- \<nav>：导航栏，经常嵌套在\<header>中。
- \<main>：主内容。主内容中还可以有各种子内容区段，可用\<article>、\<section>、\<div>和 等元素表示。
- \<aside>：侧边栏，经常嵌套\<main>中。
- \<footer>：页脚。

#### <span style='color:brown'>三、多媒体与嵌入</span>

在HTML中镶嵌图片

```html
<img src="images/dinosaur.jpg"
     alt="一只恐龙头部和躯干的骨架，它有一个巨大的头，长着锋利的牙齿。"
     width="400"
     height="341"
     title="A T-Rex on display in the Manchester University Museum">
```

```html
<figure>
  <img src="https://raw.githubusercontent.com/mdn/learning-area/master/html/multimedia-and-embedding/images-in-html/dinosaur_small.jpg"
     alt="一只恐龙头部和躯干的骨架，它有一个巨大的头，长着锋利的牙齿。"
     width="400"
     height="341">
  <figcaption>曼彻斯特大学博物馆展出的一只霸王龙的化石</figcaption>
</figure>
```

