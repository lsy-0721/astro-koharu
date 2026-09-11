---
title: HTML
draft: false
sticky: false
tocNumbering: true
excludeFromSummary: false
math: false
quiz: false
date: 2026-09-04 22:46:45
updated: 2026-09-11 21:51:30
categories:
  - [前端]
description: 简单讲述HTML的文件结构以及组成关系
cover: img/cover/22.webp
link: ewert
---
## HTML 标签及属性

首先我们可以在 vs code 安装 Chinese(负责汉化)、HTML css support(快捷写 css 代码)、Live Server(可以在浏览器中实时预览页面变化)、Auto Rename Tag(在修改 HTML 标签的时候同步修改另一个标签)这几个插件方便操作

***

### **HTML 标签**

`HTML` 全称是 `Hypertext Markup Language（超文本标记语言）`。

HTML 通过一系列的 `标签（也称为元素）` 来定义文本、图像、链接等等。HTML 标签是由尖括号包围的关键字。

标签通常成对出现，包括开始标签和结束标签（也称为双标签），内容位于这两个标签之间，例如：

```html
<p>这是一个段落。</p>
<h1>这是一个标题。</h1>
<a href="#">这是一个超链接。</a>
```

除了双标签，也存在单标签，例如：

```html
<input type="text">
<br>
<hr>
```

区别：单标签用于没有内容的元素，双标签用于有内容的元素

***

### 文件结构

文件结构中有一个文档类型的声明，以及标签对和在标签对中的标签对和标签对还有在标签对中的文档原信息

首先创建一个文件夹，再在文件夹上方栏中输入 cmd 打开 Powershell，会默认为文件夹的位置，此时输入 code .可以打开代码编译软件(例如 vs code),也可以直接在编译文件中选择文件打开来进行操作。然后在该文件夹选择新建文件写名称以及后缀 (.html)

在写 HTML 文件时可以直接打出一个感叹号‘！’，然后通过 tap 键直接得到上面的 HTML 代码文件结构。其中名字默认叫 Document，即 Document，可以修改成其他名字

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    
</body>
</html>
```

***

### 标题标签

HTML 中有 6 个标题标签，分别用 h1 到 h6 来表示，分别是一级到六级标签，在标签对中可以先输入一个 h1 然后 tap 就可以生成一个 h1 标签对，其他标签同理

```html
<body>
    <h1>一级标签</h1>
    <h2>二级标签</h2>
    <h3>三级标签</h3>
    <h4>四级标签</h4>
    <h5>五级标签</h5>
    <h6>六级标签</h6>
</body>
```

***

### 段落标签

`<p>` 是 HTML 中的**段落标签**（Paragraph），用来定义一个**文本段落**。

```html
<body>
    <p>这是一个段落标签</p>
    <p>
        更改文本样式：<b>加粗</b>、<i>斜体</i>、<u>下划线</u>、<s>删除线</s>
    </p>
</body>
```

以下都是 HTML 中用来**改变文字样式**的标签，属于**行内元素**（不换行，只影响标签内的文字）。

#### `<b>`**&#xA0;—— 加粗**

* 作用：把文字**加粗**显示（**b**old）。

* 效果：**加粗文字**

#### `<i>`**&#xA0;—— 斜体**

* 作用：把文字显示为**斜体**（**i**talic）。

* 效果：*斜体文字*

#### `<u>`**&#xA0;—— 下划线**

* 作用：给文字加**下划线**（**u**nderline）。

* 效果：下划线文字

#### `<s>`**&#xA0;—— 删除线**

* 作用：给文字加删除线（strikethrough），表示内容已作废/不再准确。

* 效果：~~删除线文字~~

***

### 列表标签

`<li>` 是 HTML 中的**列表项标签**（List Item），用来定义列表中的每一项内容。它本身不能单独使用，必须放在列表容器标签里面。

#### **两种搭配方式**

##### **1. 无序列表&#xA0;**`<ul>`（Unordered List）—— 项目符号

```html
<ul>
  <li>苹果</li>
  <li>香蕉</li>
  <li>橙子</li>
</ul>
```

浏览器显示为带圆点的列表：

* 苹果

* 香蕉

* 橙子

##### **2. 有序列表&#xA0;**`<ol>`（Ordered List）—— 自动编号

```html
<ol>
  <li>打开冰箱</li>
  <li>把大象放进去</li>
  <li>关上冰箱</li>
</ol>
```

#### **几个要点**

* `<li>` 的父元素**只能是** `<ul>`、`<ol>` 或 `<menu>`，不能直接放在 `<div>` 里（虽然浏览器容错，但不合规范）。

* `<li>` 内部可以放任意内容：文字、链接、图片，甚至嵌套另一个 `<ul>` / `<ol>` 做多级菜单。

```html
<ul>
  <li>水果
    <ul>
      <li>苹果</li>
      <li>香蕉</li>
    </ul>
  </li>
  <li>蔬菜</li>
</ul>
```

* 默认情况下 `<li>` 是块级元素，前面的圆点/编号由浏览器自动生成，可以用 CSS 的 `list-style` 去掉或替换。

简单来说：`<li>`**&#xA0;= 列表里的一条**，`<ul>` 管"圆点"，`<ol>` 管"数字"。

***

### 表格标签

`<table>` 是 HTML 中的**表格标签**，用来展示行列结构的二维数据（比如成绩表、价格表、日程表）。

#### **基本结构**

一个最简表格由三层标签组成：

```html
<table>
  <tr>          <!-- 行 table row -->
    <td>姓名</td> <!-- 单元格 table data -->
    <td>年龄</td>
  </tr>
  <tr>
    <td>小明</td>
    <td>18</td>
  </tr>
</table>
```

* `<table>`：表格容器

* `<tr>`：一行（table row）

* `<td>`：一个普通单元格（table data）

***

### **HTML 属性**

属性在 HTML 中起到非常重要的作用，它们用于定义元素的行为和外观，以及与其他元素的关系。

基本语法：

```html
<开始标签 属性名="属性值">
```

* 每个 HTML 元素可以具有不同的属性

```html
<p id="describe" class="section">这是一个段落标签</p>
<a href="https://www.baidu.com">这是一个超链接</a>
```

* 属性名称不区分大小写，属性值对大小写敏感

```html
<img src="example.jpg" alt="">
<img SRC="example.jpg" alt="">
<img src="EXAMPLE.JPG" alt="">
<!--前两者相同，第三个与前两个不一样-->
```

**适用于大多数 HTML 元素的属性**

| **属性**  | **描述**                        |
| ------- | ----------------------------- |
| `class` | 为 HTML 元素定义一个或多个类名(类名从样式文件引入) |
| `id`    | 定义元素唯一的 id                    |
| `style` | 规定元素的行内样式                     |

例如：

```html
<h1 id="title"></h1>
<div class="nav-bar"></div>
<h2 class="nav-bar"></h2>
```

#### `<a>`**&#xA0;—— 超链接标签**

```html
<a href="https://www.execute.cc.cd/">这是一个超链接</a>
<a href="https://www.execute.cc.cd/" target="_blank">这是一个新窗口打开的超链接</a>
```

**作用**：定义一个链接，点击后跳转到指定地址。标签内的文字就是"可点击的文字"。

**用到的属性**：

| **属性**   | **值**                        | **作用**                            |
| -------- | ---------------------------- | --------------------------------- |
| `href`   | `https://www.execute.cc.cd/` | 必填，指定链接的目标地址（Hypertext Reference） |
| `target` | `_blank`                     | 让链接在**新标签页/新窗口**打开；不加则默认在当前页跳转    |

`target` 的常见取值：

| **值**     | **含义**     |
| --------- | ---------- |
| `_self`   | 当前窗口打开（默认） |
| `_blank`  | 新窗口/新标签页打开 |
| `_parent` | 父框架中打开     |
| `_top`    | 最顶层窗口打开    |

#### `<br>`**&#xA0;—— 换行标签**

```html
<br>
```

**作用**：强制换行，相当于在文字里按了一下回车。

**特点**：

* 是**单标签**（空元素），没有结束标签，写成 `<br>` 或 `<br/>` 都行。

* 只换行，**不产生段落间距**。如果要有间距，应该用 `<p>` 分段。

* 不能靠它来撑开布局间距，那属于 CSS 的活。

#### `<hr>`**&#xA0;—— 水平分割线标签**

```html
<hr>
```

**作用**：画一条水平横线，用来分隔上下内容（Horizontal Rule）。

**特点**：

* 也是**单标签**，没有结束标签。

* 默认样式是一条占满宽度、带 3D 立体感的灰线。

* 现在一般用 CSS 重写样式，比如：

```html
hr {
  border: none;
  border-top: 1px solid #ccc;
}
```

#### `<img>`**&#xA0;—— 图片标签**

```html
<img src="爱丽丝.jpg" alt="">
<img src="ailis.jpg" alt="该图片无法显示">
<img src="https://blog.hoshiumi.xyz/img/avatar.webp" alt="" width="200px" height="200px">
```

**作用**：在页面中插入一张图片。

**用到的属性**：

| **属性**   | **示例**                                | **作用**                    |
| -------- | ------------------------------------- | ------------------------- |
| `src`    | `爱丽丝.jpg` / `https://.../avatar.webp` | **必填**，图片的路径或网址（Source）   |
| `alt`    | `该图片无法显示`                             | 图片加载失败时显示的替代文字；也是给屏幕阅读器读的 |
| `width`  | `200px`                               | 图片宽度                      |
| `height` | `200px`                               | 图片高度                      |

**关于三张图的区别：**

1. `src="爱丽丝.jpg"` —— 相对路径，找同目录下的本地图片；`alt=""` 为空，加载失败时什么都不显示。

2. `src="ailis.jpg"` —— 同样是本地图片，但 `alt="该图片无法显示"`，**如果文件名不对/图片不存在，就会显示出这句话**。这就是 `alt` 最直观的作用。

3. `src="https://..."` —— 用的是**网络地址**，图片来自远程服务器；同时设了 `width` 和 `height` 为 200px，把图片缩放成 200×200 显示。

**注意点：**

* `img` 也是**单标签**，没有结束标签。

* `width` / `height` 写 `200px` 或直接写 `200` 都行；但更推荐用 CSS 控制尺寸。

* 只设 `width` 或只设 `height`，图片会**按比例缩放**；两个都设且比例不符，图片会被**拉伸变形**。

* `alt` 建议**每张图都写**，这是无障碍访问和无障碍规范的要求，别留空。

***

## HTML 区块

### **块元素（block）**

块级元素通常用于组织和布局页面的主要结构和内容，例如段落、标题、列表、表格等。它们用于创建页面的主要部分，将内容分隔成逻辑块。

* 块级元素通常会从新行开始，并占据整行的宽度，因此它们会在页面上呈现为一块独立的内容块。

* 可以包含其他块级元素和行内元素。

* 常见的块级元素包括 `<div>`，`<p>`，`<h1>` 到 `<h6>`，`<ul>`，`<ol>`，`<li>`，`<table>`，`<form>` 等。

#### **块级元素**`<div>`

块级元素的特点是：**独占一行，占据整行宽度，可以包含其他块级元素和行内元素，用于组织和布局页面的主要结构。**

```html
    <div class="nav">
        <a href="#">链接 1</a>
        <a href="#">链接 2</a>
        <a href="#">链接 3</a>
        <a href="#">链接 4</a>
        <a href="#">链接 5</a>
    </div>

    <div class="content">
        <h1>文章标题</h1>
        <p>文章内容</p>
        <p>文章内容</p>
        <p>文章内容</p>
        <p>文章内容</p>
    </div>
```

1. **划分页面大区块（布局结构）：** 使用两个 `<div>`，分别赋予了 `class="nav"`（导航区）和 `class="content"`（内容区）。这是 `div` 的典型用法——用于创建页面的主要部分，将内容分隔成逻辑块。

2. **独占一行：** `.nav` 和 `.content` 这两个 `<div>` 在浏览器中渲染时，会各自占据一整行。导航栏的 `<div>` 结束后，内容区的 `<div>` 会自动从下一行开始，绝不会挤在同一行。

3. **可以容纳万物（包含其他元素）：**

   * 第一个 `<div>` 内部包含了多个行内元素 `<a>`（超链接）。

   * 第二个 `<div>` 内部包含了块级元素 `<h1>` 和 `<p>`。

   * 这说明：`div` 可以作为容器，包裹其他块级元素和行内元素

***

### **行内元素（inline）**

行内元素通常用于添加文本样式或为文本中的一部分应用样式。它们可以在文本中插入小的元素，例如超链接、强调文本等。

* 行内元素通常在同一行内呈现，不会独占一行。

* 它们只占据其内容所需的宽度，而不是整行的宽度。

* 行内元素不能包含块级元素，但可以包含其他行内元素。

* 常见的行内元素包括 `<span>`，`<a>`，`<strong>`，`<em>`，`<img>`，`<br>`，`<input>` 等。

#### **行内元素&#xA0;**`<span>`

根据之前的幻灯片，行内元素的特点是：**在同一行内呈现，不会独占一行；只占据内容所需的宽度；通常用于添加文本样式或包裹文本中的一小部分。**

```html
    <span>这是第1个span标签</span>
    <span>这是第2个span标签</span>
    <span>这是第3个span标签</span>
    <span>这是第4个span标签</span>
    <hr>
    <span>链接点这里<a href="#">链接</a></span>
```

1. **排在同一行（不独占）：** 这 5 个 `<span>` 标签会像文字一样，从左到右依次排列在同一行（如果屏幕不够宽才会自动换行）。它们不会像前面的 `<div>` 那样各自占据一整行。

2. **宽度由内容决定：** `<span>这是第1个span标签</span>` 这个元素的宽度，仅仅是这行文字加上两边微小的留白宽度，而不是整行的宽度。

3. **用于局部文本处理：** 之前提到 `span` 可以“在文本中插入小的元素”。注意代码的最后一行：`<span>链接点这里<a href="#">链接</a></span>`。这里用 `<span>` 包裹了一段普通的文字“链接点这里”和一个行内元素 `<a>`。因为 `<span>` 是行内元素，它允许这段文字和后面的链接无缝地拼接在同一行里，非常适合用来对段落中的某几个字进行单独的样式设置（比如变红、加粗，而不影响整体排版）。

***

### **总结对比**

| **特性**   | `<div>`**&#xA0;(块级 block)**        | `<span>`**&#xA0;(行内 inline)**                 |
| -------- | ---------------------------------- | --------------------------------------------- |
| **排版表现** | 霸道的“大盒子”，独占一行，通常用于页面大框架布局。         | 随和的“小标签”，跟着文字走，同在一行，用于局部文字修饰。                 |
| **代码体现** | 实现了“导航栏”和“文章内容”上下垂直排列的结构。          | 实现了多段提示文字水平排列在同一行，以及文字与链接的混排。                 |
| **嵌套规则** | 可以装 `<h1>`、`<p>`、`<a>`、`<span>` 等。 | 不能装 `<div>`、`<h1>` 等块级元素，但可以装文本和 `<a>` 等行内元素。 |

***

## HTML 表单

我们来看这一段代码分析各个表单标签的作用

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>html 表单</title>
</head>
<body>
    <form>
        <label for="username">用户名：</label>
        <input type="text" id="username" value="请输入文本">
        <br>
        <label for="pwd">密码：</label>
        <input type="password" id="pwd" placeholder="请输入文本">
        <br>

        <label>性别：</label>
        <input type="radio" name="gender">男
        <input type="radio" name="gender">女
        <input type="radio" name="gender">保密
        <br>

        <label>爱好：</label>
        <input type="checkbox" name="hobby">唱歌
        <input type="checkbox" name="hobby">跳舞
        <input type="checkbox" name="hobby">rap
        <input type="checkbox" name="hobby">篮球
        <br>

        <input type="submit" value="上传">
    </form>

    <form action="#"></form>
</body>
</html>
```

***

### `<form>`：表单的“总容器”

`<form>` 是 HTML 表单的核心标签。

可以把它理解成：\
**一个表单区域，里面放各种需要用户填写、选择、提交的数据。**

例如：

```html
<form>
    用户名
    密码
    性别
    爱好
    提交按钮
</form>
```

这些内容就属于同一个表单。

#### `action` 属性

后面还有：

```html
<form action="#"></form>
```

`action` 用来指定：\
**用户点击提交按钮后，表单数据发送到哪里。**

例如：

```html
<form action="login.php">
```

用户点击提交后，数据就会发送给：login.php

再比如：

```html
<form action="/login">
```

表示发送到网站的：/login

#### 那 `action="#"` 是什么意思？

```html
<form action="#">
```

通常表示当前页面的锚点/当前页面位置。

在学习 HTML 表单的时候，经常用它作为一个临时占位符。

所以这段代码：

```html
<form action="#"></form>
```

里面什么都没有，所以这个 `<form>` 实际上没有发挥作用。

如果你只是练习表单，可以直接删除。

***

### `<label>`：表单项目的文字说明

```html
<label for="username">用户名：</label>
```

`label` 的作用就是：**给表单控件添加文字说明。**

例如：

```html
<label>用户名：</label>
<input type="text">
```

浏览器看到的就是：用户名：[输入框]

***

### `label` 的 `for` 属性

我们看代码中这一段：

```html
<label for="username">用户名：</label>
<input type="text" id="username">
```

这里有一个非常重要的对应关系：

```text
label 的 for
        ↓
      username

input 的 id
        ↓
      username
```

也就是：

```html
for="username"
```

对应：

```html
id="username"
```

#### 为什么要这样写？

这样用户点击：

```text
用户名：
```

这个文字的时候，浏览器会自动把焦点放到输入框里。

例如：

```html
<label for="username">用户名：</label>
<input type="text" id="username">
```

点击“用户名”：

```text
用户名：[________________]
   ↑
点击这里
```

输入框就会获得焦点。

***

#### `for` 和 `id` 必须对应

正确：

```html
<label for="username">用户名：</label>
<input id="username">
```

错误：

```text
<label for="username">用户名：</label>
<input id="user">
```

因为：

```text
for="username"
```

找不到：

```text
id="username"
```

***

### `<input>`：表单中最重要的标签

代码里大量使用了：

```html
<input>
```

`input` 是 HTML 表单中最常用的标签之一。

它本身是一个**表单控件**。

但是：

```html
<input>
```

到底是什么控件，要看它的：**type**属性。

例如：

```html
<input type="text">
```

是文本输入框。

```html
<input type="password">
```

是密码框。

```html
<input type="radio">
```

是单选框。

```html
<input type="checkbox">
```

是复选框。

```html
<input type="submit">
```

是提交按钮。

所以可以记住：

`input`**&#x20;是外壳，**`type`**&#x20;决定它具体是什么。**

***

### `type="text"`：普通文本输入框

代码：

```text
<input type="text" id="username" value="请输入文本">
```

这里：

```text
type="text"
```

表示这是一个：\
**单行文本输入框**

浏览器大概显示：

```text
[请输入文本        ]
```

用户可以在里面输入：

```text
水鱼
```

***

### `id="username"`：给元素一个唯一身份证

这里：

```text
id="username"
```

相当于给这个 `<input>` 一个唯一的名字。

例如：

```html
<input type="text" id="username">
```

这个元素的 ID 就是：

```text
username
```

它可以被：

* `<label>` 找到

* CSS 找到

* JavaScript 找到

例如：

```html
<label for="username">用户名：</label>
<input id="username">
```

就是利用 `id` 和 `for` 建立关系。

***

### `value="请输入文本"`：输入框的默认值

代码：

```html
<input type="text" id="username" value="请输入文本">
```

这里：

```text
value="请输入文本"
```

表示：\
**输入框一开始就已经有一个值。**

显示：

```text
用户名：[请输入文本]
```

注意，这个东西和 `placeholder` **非常容易搞混**。

***

### `value` 和 `placeholder` 的区别

#### `value`

```html
<input value="请输入文本">
```

表示：\
输入框里面**真的有这个值**。

例如：

```html
<input value="张三">
```

表单提交的时候，如果用户没有修改，`张三` 就可能作为这个输入框的值提交。

***

#### `placeholder`

```text
<input placeholder="请输入文本">
```

表示：\
**提示用户应该输入什么。**

例如：

```html
<input placeholder="请输入用户名">
```

显示：

```text
[请输入用户名]
```

但是这个文字不是用户真正输入的数据。

用户一输入：

```text
[水鱼]
```

`请输入用户名` 就消失了。

***

### `type="password"`：密码输入框

代码：

```html
<input type="password" id="pwd" placeholder="请输入文本">
```

这里：

```html
type="password"
```

表示：\
**密码输入框**

用户输入：

```text
123456
```

浏览器一般显示成：

```text
••••••
```

而不是直接显示：

```text
123456
```

这样可以避免密码直接显示出来。

***

#### `id="pwd"`

```html
id="pwd"
```

给密码框设置一个唯一 ID。

所以

```html
<label for="pwd">密码：</label>
<input type="password" id="pwd">
```

也是：

```text
label 的 for
       ↓
      pwd

input 的 id
       ↓
      pwd
```

点击“密码”文字，就会定位到密码输入框。

***

### `placeholder`：占位提示文字

代码中：

```html
placeholder="请输入文本"
```

它的意思是：\
**当用户还没有输入内容时，显示一段提示文字。**

例如：

```html
<input type="text" placeholder="请输入用户名">
```

显示：

```text
[请输入用户名]
```

用户开始输入：

```text
[水鱼]
```

提示文字就没了。

#### 一个很重要的特点

`placeholder` **不是实际输入值**。

例如：

```html
<input placeholder="请输入用户名">
```

用户什么都没输入，那么：

```text
value = ""
```

而不是：

```text
value = "请输入用户名"
```

***

### `type="radio"`：单选框

代码：

```html
<input type="radio" name="gender">男
<input type="radio" name="gender">女
<input type="radio" name="gender">保密
```

`radio` 就是：\
**单选按钮**

例如：

```text
○ 男
○ 女
○ 保密
```

用户通常只能选择其中一个。

***

#### 为什么三个 radio 只能选一个？

关键就在这里：

```html
name="gender"
```

三个 `<input>`：

```html
<input type="radio" name="gender">男
<input type="radio" name="gender">女
<input type="radio" name="gender">保密
```

它们拥有相同的：

```html
name="gender"
```

浏览器就知道：\
这三个 radio 属于同一组。

所以：

```text
○ 男
○ 女
○ 保密
```

只能选一个。

***

#### 如果 name 不一样呢？

例如：

```html
<input type="radio" name="a">男
<input type="radio" name="b">女
<input type="radio" name="c">保密
```

那么它们属于三个不同的组。

就可能出现：

```text
● 男
● 女
● 保密
```

三个都能选。

所以记住：\
**radio 是否互斥，主要看&#x20;**`name`**&#x20;是否相同。**

***

### `name`：表单数据的“字段名”

`name` 是表单中一个非常重要的属性。

例如：

```html
<input type="text" name="username">
```

可以理解成：

```text
字段名 = username
字段值 = 用户输入的内容
```

比如用户输入：

```text
水鱼
```

提交时可以理解为：

```text
username=水鱼
```

***

再比如：

```html
<input type="password" name="password">
```

用户输入：

```text
123456
```

可以理解成：

```text
password=123456
```

***

#### 现在代码有一个可以改进的地方

现在：

```html
<input type="text" id="username" value="请输入文本">
```

只有：

```text
id="username"
```

没有：

```text
name="username"
```

如果真正要提交表单数据，建议写：

```html
<input type="text" id="username" name="username" placeholder="请输入用户名">
```

这里：

```text
id
↓
主要用于元素定位、label、CSS、JS

name
↓
主要用于表单提交的数据字段名
```

这是非常重要的区别。

***

### `type="checkbox"`：复选框

代码：

```text
<input type="checkbox" name="hobby">唱歌
<input type="checkbox" name="hobby">跳舞
<input type="checkbox" name="hobby">rap
<input type="checkbox" name="hobby">篮球
```

`checkbox` 表示：\
**复选框**

和 radio 最大的区别：

**radio**

```text
性别：

○ 男
○ 女
○ 保密
```

通常只能选一个。

**checkbox**

```text
爱好：

☑ 唱歌
☑ 跳舞
☐ rap
☑ 篮球
```

可以选择多个。

***

#### 为什么 checkbox 可以选择多个？

虽然这里：

```html
name="hobby"
```

都是一样的，但是 checkbox 和 radio 的行为不同。

```html
<input type="checkbox" name="hobby">唱歌
<input type="checkbox" name="hobby">跳舞
<input type="checkbox" name="hobby">rap
<input type="checkbox" name="hobby">篮球
```

可以同时选择：

```text
☑ 唱歌
☑ 跳舞
☐ rap
☑ 篮球
```

所以：

> `radio`：同一个 `name` 通常只能选一个\
> \
> `checkbox`：可以同时选多个

***

### `type="submit"`：提交按钮

代码最后：

```html
<input type="submit" value="上传">
```

这里：

```html
type="submit"
```

表示：\
**提交表单**

浏览器会显示一个按钮：

```text
┌──────┐
│ 上传 │
└──────┘
```

用户点击之后，就会触发表单提交。

***

### `submit` 的 `value`

这里：

```html
value="上传"
```

和前面的 `value` 有一点不同。

对于：

```html
<input type="text" value="请输入文本">
```

`value` 是输入框的初始值。

而：

```html
<input type="submit" value="上传">
```

这里的 `value` 是：\
**按钮上显示的文字。**

例如：

```html
<input type="submit" value="登录">
```

按钮：

```text
┌──────┐
│ 登录 │
└──────┘
```

如果：

```html
<input type="submit" value="注册">
```

就是：

```text
┌──────┐
│ 注册 │
└──────┘
```

***

### 你现在需要重点记住的属性

如果你正在系统学习 HTML 表单，我建议先把这几个记牢：

| 标签/属性         | 作用                |
| ------------- | ----------------- |
| `<form>`      | 表单的大容器            |
| `action`      | 表单提交到哪里           |
| `<label>`     | 表单控件的文字说明         |
| `for`         | 指向对应 input 的 `id` |
| `<input>`     | 表单控件              |
| `type`        | 决定 input 是什么类型    |
| `text`        | 普通文本框             |
| `password`    | 密码框               |
| `radio`       | 单选框               |
| `checkbox`    | 复选框               |
| `submit`      | 提交按钮              |
| `id`          | 元素的唯一标识           |
| `name`        | 表单提交时的字段名         |
| `value`       | 控件的值/按钮显示文字       |
| `placeholder` | 输入提示文字            |
| `<br>`        | 换行                |
