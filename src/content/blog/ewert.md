---
title: HTML
draft: false
sticky: false
tocNumbering: true
excludeFromSummary: false
math: false
quiz: false
date: 2026-09-04 22:46:45
updated: 2026-09-10 22:58:11
categories:
  - [前端]
description: 简单讲述HTML的文件结构以及组成关系
cover: img/cover/22.webp
link: ewert
---
## 开始部分

首先我们可以在 vs code 安装 Chinese(负责汉化)、HTML css support(快捷写 css 代码)、Live Server(可以在浏览器中实时预览页面变化)、Auto Rename Tag(在修改 HTML 标签的时候同步修改另一个标签)这几个插件方便操作

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

```html
<body>
    <p>这是一个段落标签</p>
    <p>
        更改文本样式：<b>加粗</b>、<i>斜体</i>、<u>下划线</u>、<s>删除线</s>
    </p>
</body>
```

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

#### **2. 有序列表&#xA0;**`<ol>`（Ordered List）—— 自动编号

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
