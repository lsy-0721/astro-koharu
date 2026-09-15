---
title: css
draft: false
sticky: true
tocNumbering: true
excludeFromSummary: false
math: false
quiz: false
date: 2026-09-13 14:45:22
updated: 2026-09-15 21:38:44
categories:
  - [前端]
description: 如果css是外貌，那HTML早已成为我的心
cover: img/cover/24.webp
link: front-end/css
---
# gogogo，出发咯！

## **CSS 简介**

什么是 CSS?

CSS 全名是 `Cascading Style Sheets`，中文名 `层叠样式表`。

用于定义网页样式和布局的样式表语言。

通过 CSS，你可以指定页面中各个元素的颜色、字体、大小、间距、边框、背景等样式，从而实现更精确的页面设计。

***

## HTML 与 CSS 的关系

可以把 **HTML 和 CSS** 简单理解成：

> **HTML 负责“内容和结构”，CSS 负责“样式和外观”。**

### HTML：搭建网页骨架

HTML 决定网页上**有什么东西**。

比如：

```html
<h1>我的网页</h1>
<p>这是网页内容</p>
<button>点击我</button>
```

它告诉浏览器：

* 这是一个标题

* 这是一个段落

* 这是一个按钮

***

### CSS：负责网页的外观

CSS 决定这些东西**长什么样**。

```css
h1 {
    color: red;
    font-size: 30px;
}

button {
    background: blue;
    color: white;
}
```

它可以控制：

* 颜色

* 字体大小

* 背景

* 宽高

* 间距

* 位置

* 边框

* 动画等

***

### 两者结合

例如：

```html
<h1>你好，世界！</h1>
```

```css
h1 {
    color: red;
    font-size: 40px;
}
```

最终浏览器看到的就是一个**红色、40px 大小的“你好，世界！”**。

***

### 一句话记忆

**HTML = 网页的骨架**\
**CSS = 网页的外衣**

以后还会学到 **JavaScript**，可以理解成：

**HTML 负责结构 + CSS 负责样式 + JavaScript 负责行为**。

***

## CSS 语法

CSS 通常由选择器、属性和属性值组成，多个规则可以组合在一起，以便同时应用多个样式。

```css
选择器 {
    属性1：属性值1；
    属性2：属性值2；
}
```

1. 选择器的声明中可以写无数条属性

2. 声明的每一行属性，都需要以英文分号结尾；

3. 声明中的所有属性和值都是以键值对这种形式出现的；

示例：

```css
/*这是一个 p 标签选择器 */
p {
    color: blue;
    font-size: 16px;
}
```

***

## CSS 三种导入方式

下面是三种常见的 CSS 导入方式：

1. 内联样式（Inline Styles）

2. 内部样式表（Internal Stylesheet）

3. 外部样式表（External Stylesheet）

**三种导入方式的优先级：**\
内联样式 > 内部样式表 > 外部样式表

***

用以下代码来比较理解：

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>css导入方式</title>
    <link rel="stylesheet" href="./css/style.css">
    <style>
        p {
            color: blue;
            font-size:20px;
        }
        h2{
            color:aqua;
        }
        h3{
            color:blueviolet;
        }
        h1{
            color: antiquewhite;
        }
    </style>
</head>
<body>
    <p>这是一个应用了css样式的文本</p>
    <h1 style="color: chocolate;">这是一个一级标题标签，使用内联样式</h1>
    <h2>这是一个二级标题标签，应用内部样式</h2>
    <h3>这是一个三级标题标签，应用外部样式</h3>
</body>
</html>
```

**style.css:**

```text
h3{
    color: red;
}
```

### 先看 HTML

`<head>` 中有：

```html
<link rel="stylesheet" href="./css/style.css">

<style>
    p {
        color: blue;
        font-size: 20px;
    }

    h2 {
        color: aqua;
    }

    h3 {
        color: blueviolet;
    }

    h1 {
        color: antiquewhite;
    }
</style>
```

而 `<body>` 中有：

```html
<p>这是一个应用了css样式的文本</p>

<h1 style="color: chocolate;">
    这是一个一级标题标签，使用内联样式
</h1>

<h2>这是一个二级标题标签，应用内部样式</h2>

<h3>这是一个三级标题标签，应用外部样式</h3>
```

另外，外部 `style.css` 中写的是：

```css
h3 {
    color: red;
}
```

***

### 再认识三种 CSS

#### 外部样式表

就是单独创建一个 `.css` 文件。

比如`style.css`：

```css
h3 {
    color: red;
}
```

然后 HTML 通过：

```html
<link rel="stylesheet" href="./css/style.css">
```

把它引入进来。

所以：

```html
<h3>这是一个三级标题标签，应用外部样式</h3>
```

会变成**红色**。

***

#### 内部样式表

就是直接在 HTML 的 `<style>` 标签里面写 CSS。

例如：

```html
<style>
    h2 {
        color: aqua;
    }
</style>
```

所以：

```html
<h2>这是一个二级标题标签，应用内部样式</h2>
```

会变成 **aqua（青色）**。

这就是**内部样式表**。

***

#### 内联样式

内联样式就是**直接写在 HTML 标签里面**。

比如：

```html
<h1 style="color: chocolate;">
    这是一个一级标题标签，使用内联样式
</h1>
```

这里：

```html
style="color: chocolate;"
```

就是内联 CSS。

所以 `<h1>` 最终显示为 **chocolate（巧克力色）**。

***

#### 重点：优先级

你可以先记住：

```text
内联样式
   ↓
内部样式表
   ↓
外部样式表
```

**一般来说：**

> **内联样式 > 内部样式表 > 外部样式表**

但是代码目前**没有直接体现出三者发生冲突**。

为什么？

因为：

```text
p  → 内部样式
h1 → 内联样式
h2 → 内部样式
h3 → 外部样式
```

它们分别控制不同的标签。

***

##### **我们故意制造一个“冲突”**

这个最重要。

现在的 `h3`有两个 css：

**外部 CSS：**

```css
h3 {
    color: red;
}
```

**内部 CSS：**

```css
<style>
    h3 {
        color: blueviolet;
    }
</style>
```

你会发现：

**外部说：红色**

```text
red
```

**内部说：紫罗兰色**

```text
blueviolet
```

这时候谁优先？

在这个例子里，**内部样式表中的规则最终会覆盖外部样式表中相同条件的规则**，因此 `h3` 会显示为 `blueviolet`。

***

##### **再制造一次冲突**

现在假设我们把`<h3>` 改成：

```html
<h3 style="color: green;">
    这是一个三级标题标签
</h3>
```

此时三个地方都有 `h3` 的颜色：

**外部：**

```css
h3 {
    color: red;
}
```

**内部：**

```css
h3 {
    color: blueviolet;
}
```

**内联：**

```html
<h3 style="color: green;">
```

那么最终：

```text
外部样式：red
      ↓
内部样式：blueviolet
      ↓
内联样式：green
```

**最终显示绿色。**

***

### 用代码记忆最简单

你可以把这份代码理解成：

| 写在哪里          | 代码                            | 作用    |
| ------------- | ----------------------------- | ----- |
| 外部 CSS 文件     | `h3 { color: red; }`          | 控制 h3 |
| `<style>`     | `h2 { color: aqua; }`         | 控制 h2 |
| 标签 `style=""` | `h1 style="color: chocolate"` | 控制 h1 |

所以记住：

> **外部：单独的&#x20;**`.css`**&#x20;文件**\
> **内部：HTML 里面的&#x20;**`<style>`\
> **内联：HTML 标签里面的&#x20;**`style=""`

而在**相同选择器发生冲突**、且没有其他更高优先级因素干扰时，可以先按：

> 🥇 **内联样式 > 内部样式表 > 外部样式表**

来理解。

**不过严格来说，CSS 的最终优先级并不只是由“内联/内部/外部”决定，还涉及选择器优先级和代码顺序。**&#x4F60;现在刚学 CSS 的话，先把上面这个关系记牢就够了。

***

## CSS 选择器

选择器是 CSS 中的关键部分，它允许你针对特定元素或一组元素定义样式。

**有以下几种类型：**

* 元素选择器

* 类选择器

* ID 选择器

* 通用选择器

* 子元素选择器

* 后代选择器（包含选择器）

* 并集选择器（兄弟选择器）

* 伪类选择器

***

### 什么是 CSS 选择器？

**选择器就是用来“选中 HTML 元素”的。**

同样我们用代码来进行理解：

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>css 选择器</title>
    <style>
        /* 元素选择器 */
        h2{
            color:blue;
        }
        /* 类选择器 */
        .highlight{
            background-color: yellow;
        }
        /* ID选择器 */
        #header{
            font-size: 24px;
        }
        /* 通用选择器 */
        *{
            font-family:'KaiTi';
            font-weight: bolder;
        }
        /* 子元素选择器 */
        .father > .son{
            color:red;
        }
        /* 后代选择器 */
        .father p{
            color:green;
            font-size:larger;
        }
        /* 相邻元素选择器 */
        h3 + p{
            background-color:orange;
        }
        /* 伪类选择器 */
        #element:hover{
            background-color:purple;
        }

        /* 
        选中第一个子元素:first-child
                        :nth-child()
                        :active
        */

        /* 
        伪元素选择器
        ::before
        ::after
        */
    </style>
</head>  
<body>
    <h1>不同类型的css选择器</h1>

    <h2>这是一个元素选择器示例</h2>

    <h3 class="highlight">这是一个类选择器示例</h3>

    <h3>这是另一个类选择器示例</h3>

    <h4 id="header">这是一个ID选择器示例</h4>

    <div class="father">
        <p class="son">这是一个子元素选择器示例</p>
        <div>
            <p class="grandson">这是一个后代选择器示例</p>
        </div>
    </div>

    <p>这是一个普通的p标签</p>
    <h3>这是一个相邻兄弟选择器示例</h3>
    <p>这是另一个p标签</p>

    <h3 id="element">这是一个伪类选择器示例</h3>
</body>
</html>
```

例如 HTML 中有：

```html
<h2>这是一个元素选择器示例</h2>
```

CSS 中：

```css
h2 {
    color: blue;
}
```

这里的：

```text
h2
```

就是**选择器**。

意思是：

> 找到页面中所有的 `<h2>` 元素，然后给它们设置样式。

代码中从第 8 行开始就是通过不同选择器来选中不同元素。

***

### 元素选择器

代码：

```css
h2 {
    color: blue;
}
```

HTML：

```html
<h2>这是一个元素选择器示例</h2>
```

#### 什么是元素选择器？

直接使用 **HTML 标签名** 作为选择器。

例如：

```html
p {
    color: red;
}

h1 {
    font-size: 30px;
}

div {
    background-color: yellow;
}
```

意思分别是：

> 所有 `<p>` 标签变红。

> 所有 `<h1>` 标签字体变大。

> 所有 `<div>` 标签背景变黄。

所以可以记住：

```text
标签名 → 元素选择器
```

例如：

```css
p {}
h1 {}
div {}
```

***

### 类选择器

代码：

```html
.highlight {
    background-color: yellow;
}
```

HTML：

```html
<h3 class="highlight">这是一个类选择器示例</h3>
```

这里 HTML：

```html
class="highlight"
```

定义了一个类。

CSS 使用：

```css
.highlight
```

来选中它。

注意前面的：

```text
.
```

这个点非常重要。

#### 类选择器的写法

```text
.类名 {
    属性: 属性值;
}
```

例如：

```css
.red {
    color: red;
}
```

HTML：

```html
<p class="red">你好</p>
```

那么这个 `<p>` 就会变成红色。

***

#### 为什么要使用 class？

因为一个 class 可以给**多个元素使用**。

例如：

```html
<p class="highlight">第一段</p>
<p class="highlight">第二段</p>
<h3 class="highlight">第三个元素</h3>
```

那么：

```css
.highlight {
    background-color: yellow;
}
```

三个元素都会有黄色背景。

所以：

```text
class → 一类元素
```

***

### ID 选择器

代码：

```css
#header {
    font-size: 24px;
}
```

HTML：

```html
<h4 id="header">这是一个ID选择器示例</h4>
```

这里：

```html
id="header"
```

对应 CSS：

```css
#header
```

ID 选择器前面使用：

```css
#
```

所以：

```css
#id名称 {
    
}
```

例如：

```css
#box {
    color: red;
}
```

```html
<div id="box">这是一个盒子</div>
```

***

### class 和 id 的区别

这是学习 CSS 选择器时非常重要的知识。

**class**

```html
<p class="text">你好</p>
<p class="text">世界</p>
```

```css
.text {
    color: red;
}
```

可以多个元素使用。

**id**

```html
<p id="text">你好</p>
```

```css
#text {
    color: red;
}
```

通常用于标识一个特定元素。

可以简单记：

```text
. → class → 一类元素

# → id → 特定元素
```

***

### 通用选择器

代码：

```css
* {
    font-family: 'KaiTi';
    font-weight: bolder;
}
```

这里的：

```css
*
```

就是**通用选择器**。

意思是：

> 选中页面中的所有元素。

例如：

```css
* {
    margin: 0;
    padding: 0;
}
```

这是非常常见的 CSS 写法。

意思就是：

> 把所有元素的 margin 和 padding 设置为 0。

你的代码中使用 `*` 给所有元素设置了字体和字体粗细。

所以：

```text
* → 所有元素
```

***

### 子元素选择器

代码：

```css
.father > .son {
    color: red;
}
```

HTML：

```html
<div class="father">
    <p class="son">这是一个子元素选择器示例</p>
    
    <div>
        <p class="grandson">这是一个后代选择器示例</p>
    </div>
</div>
```

这里最重要的是：

```css
>
```

它表示：

> **直接子元素**

***

#### 看一下 HTML 结构

可以把它理解成：

```text
father
│
├── son
│
└── div
     │
     └── grandson
```

其中：

```typescript
father → son
```

是**直接父子关系**。

但是：

```text
father → grandson
```

中间隔了一个 `<div>`，所以不是直接子元素。

因此：

```css
.father > .son
```

只能选中：

```html
<p class="son">
```

不能选中：

```html
<p class="grandson">
```

***

### 后代选择器

你的代码：

```css
.father p {
    color: green;
    font-size: larger;
}
```

这里没有 `>`。

中间只有一个空格：

```css
.father p
```

这个空格表示：

> 选择 `.father` 里面的所有 `p` 元素。

***

例如：

```html
<div class="father">
    <p>第一层 p</p>

    <div>
        <p>第二层 p</p>
    </div>
</div>
```

那么：

```css
.father p {
    color: green;
}
```

两个 `<p>` 都会被选中。

因为它们都是 `.father` 的**后代元素**。

***

### 子元素和后代元素的区别

这是一个非常容易考的知识点。

**子元素**

```css
.father > p
```

只找**直接下一层**。

**后代元素**

```css
.father p
```

可以找**里面所有层级**。

可以这样记：

```text
>     → 儿子
空格  → 所有后代
```

***

### 相邻兄弟选择器

代码：

```css
h3 + p {
    background-color: orange;
}
```

HTML：

```html
<p>这是一个普通的p标签</p>

<h3>这是一个相邻兄弟选择器示例</h3>

<p>这是另一个p标签</p>
```

这里：

```css
+
```

表示：

> **选择紧跟在某个元素后面的兄弟元素。**

也就是：

```css
h3 + p
```

意思：

> 找到 `h3`，然后选择它后面紧挨着的那个 `p`。

因此：

```html
<h3>这是一个相邻兄弟选择器示例</h3>
<p>这是另一个p标签</p>
```

这个 `<p>` 会变成橙色背景。

***

#### 为什么前面的 p 不会变？

因为：

```html
<p>这是一个普通的p标签</p>
<h3>...</h3>
<p>这是另一个p标签</p>
```

第一个 `<p>` 在 `h3` **前面**。

而：

```css
h3 + p
```

要求：

```text
h3
↓
紧挨着
↓
p
```

所以只能选中后面的那个 `<p>`。

代码中这一部分就是这个例子。

***

### 伪类选择器

代码：

```css
#element:hover {
    background-color: purple;
}
```

HTML：

```html
<h3 id="element">这是一个伪类选择器示例</h3>
```

这里：

```css
:hover
```

就是**伪类**。

它表示：

> 当鼠标移动到这个元素上时。

所以：

```css
#element:hover {
    background-color: purple;
}
```

表示：

> 当鼠标移动到 `id="element"` 的元素上时，让背景变成紫色。

***

#### 常见伪类

代码下面也列出了：

```css
:first-child
:nth-child()
:active
```

##### ① `:hover`

鼠标悬停：

```css
p:hover {
    color: red;
}
```

***

##### ② `:first-child`

选择第一个子元素：

```css
p:first-child {
    color: red;
}
```

***

##### ③ `:nth-child()`

选择指定位置的子元素：

```css
p:nth-child(2) {
    color: blue;
}
```

表示选择第二个子元素中的 `p`。

***

##### ④ `:active`

元素被激活时。

例如：

```css
button:active {
    background-color: red;
}
```

按住按钮的时候触发。

代码注释中也列出了这些伪类。

***

### 伪元素选择器

代码最后还写到了：

```css
::before
::after
```

这属于**伪元素选择器**。

和伪类要区分开：

```text
伪类    → :
伪元素  → ::
```

例如：

```css
p::before {
    content: "★";
}
```

HTML：

```html
<p>你好</p>
```

最终效果类似：

```text
★你好
```

`::before` 可以理解成：

> 在元素内容前面添加内容。

而：

```css
p::after {
    content: "!";
}
```

就是在后面添加内容。

代码中也专门列出了 `::before` 和 `::after`。

***

### 把这份代码总结成一张表

| 选择器     | 写法               | 作用                       |
| ------- | ---------------- | ------------------------ |
| 元素选择器   | `h2`             | 选择所有 h2                  |
| 类选择器    | `.highlight`     | 选择 class 为 highlight 的元素 |
| ID 选择器  | `#header`        | 选择指定 ID 的元素              |
| 通用选择器   | `*`              | 选择所有元素                   |
| 子元素选择器  | `.father > .son` | 选择直接子元素                  |
| 后代选择器   | `.father p`      | 选择所有后代 p                 |
| 相邻兄弟选择器 | `h3 + p`         | 选择 h3 后面紧挨着的 p           |
| 伪类选择器   | `#element:hover` | 鼠标悬停时触发                  |
| 伪元素选择器  | `p::before`      | 在元素前添加内容                 |

***

### 最容易混淆的几个符号

你学习的时候重点记住下面这几个：

```css
*       /* 所有 */

.abc    /* class */

#abc    /* id */

A > B   /* A 的直接子元素 B */

A B     /* A 里面所有 B */

A + B   /* A 后面紧挨着的 B */

A:hover /* A 鼠标悬停 */
```

可以用一句话记：

> **点是类，井是 ID，星是全部，大于号找儿子，空格找后代，加号找隔壁，冒号表示状态。**

这份代码其实已经把 CSS 选择器的核心框架搭出来了。尤其是 `.father > .son`**&#x20;和&#x20;**`.father p`，一定要重点理解，因为它们分别对应「子元素」和「后代元素」，是后面学习 CSS 结构选择的基础。

***

## CSS 常用属性

我们用依旧用代码来进行理解：

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>css 常用属性</title>
    <style>
        .block {
            width: 200px;
            height: 100px;
            background-color: lightblue;
        }
        .inline {
            background-color: lightgreen;
            width: 200px;
            height: 100px;
        }
        .inline-block {
            width: 100px;
            height: 100px;
            background-color: lightcoral;
        }
        .div-inline {
            display: inline;
            background-color: lightyellow;
        }
        .span-inline-block {
            display: block;
            width: 150px;
            background-color: lightgray;
        }
    </style>
</head>
<body>
    <h1 style="font: bonder 50px 'kaiti';">这是一个 font 复合属性示例</h1>

    <p style="line-height: 40px;"> 先装模作样，再有模有样，最后像模像样，一定要相信自己，敢想敢做，能理解的在理解中执行，不能理解的在执行中理解，假装自己很厉害，也许就真的会变得很厉害</p>

    <div class="block">这是一个块级元素</div>

    <span class="inline">这是一个行内元素</span>

    <img src="爱丽丝.jpg" alt="" class="inline-block">
    <img src="爱丽丝.jpg" alt="" class="inline-block">
    <img src="爱丽丝.jpg" alt="" class="inline-block">
    
    <h2>display</h2>

    <div class="div-inline">这是一个转换成行内元素的div标签</div>

    <span class="span-inline-block">这是一个转换成行内块元素的span标签</span>
</body>
</html>
```

***

### CSS 属性是什么？

先理解一个最基本的概念。

比如代码里：

```css
.block {
    width: 200px;
    height: 100px;
    background-color: lightblue;
}
```

这里：

```typescript
width
height
background-color
```

就是 **CSS 属性**。

而：

```text
200px
100px
lightblue
```

是属性对应的**属性值**。

所以 CSS 基本写法就是：

```css
选择器 {
    属性: 属性值;
}
```

例如：

```css
.box {
    width: 200px;
}
```

意思就是：

> 找到 `.box` 元素，把它的宽度设置成 `200px`。

CSS 常用属性有很多，可以去菜鸟教程、集知盒子等查找，也可以向 AI 询问，接下来我会说明一些代码中用到的 CSS 属性

***

### width：设置宽度

代码里面：

```css
.block {
    width: 200px;
}
```

`width` 的意思就是：

> **设置元素的宽度。**

例如：

```css
.box {
    width: 200px;
}
```

可以理解成：

```text
       200px
←──────────────→
┌──────────────┐
│              │
│     内容      │
│              │
└──────────────┘
```

**常见单位**

例如：

```text
width: 200px;
```

表示固定 200 像素。

也可以使用百分比：

```text
width: 50%;
```

表示：

> 宽度是父元素宽度的 50%。

***

### height：设置高度

代码中：

```css
.block {
    height: 100px;
}
```

`height` 就是：

> **设置元素的高度。**

例如：

```css
.box {
    width: 200px;
    height: 100px;
}
```

就是：

```text
        200px
←────────────────→
┌────────────────┐
│                │ ↑
│                │ │
│                │ 100px
│                │ │
│                │ ↓
└────────────────┘
```

所以：

```text
width: 200px;
height: 100px;
```

就是设置一个：

> **宽 200px，高 100px 的盒子。**

***

### background-color：背景颜色

代码：

```css
.block {
    background-color: lightblue;
}
```

`background-color`：

> **设置元素的背景颜色。**

例如：

```css
.box {
    background-color: pink;
}
```

那么这个盒子的背景就是粉色。

你代码里面用了：

```css
background-color: lightblue;
background-color: lightgreen;
background-color: lightcoral;
background-color: lightyellow;
background-color: lightgray;
```

其实就是通过不同颜色，把不同类型的元素区分开来。

***

### font：字体复合属性

文件里还有：

```html
<h1 style="font: bonder 50px 'kaiti';">
    这是一个 font 复合属性示例
</h1>
```

这里就是在使用：

```css
font
```

`font` 是一个**复合属性**。

也就是说，一个 `font` 可以同时设置多个字体相关的属性。

例如我们平时可能分别写：

```css
font-style: italic;
font-weight: bold;
font-size: 50px;
font-family: "楷体";
```

也可以使用 `font` 进行简写。

你这个例子主要是在展示 `font` 复合属性的写法。

***

### line-height：行高

代码里面：

```text
<p style="line-height: 40px;">
    先装模作样，再有模有样……
</p>
```

这里：

```css
line-height: 40px;
```

就是：

> **设置文字每一行所占的高度。**

例如：

```css
p {
    line-height: 40px;
}
```

如果文字有多行：

```text
第一行文字
第二行文字
第三行文字
```

那么每一行之间的高度会受到 `line-height` 的控制。

***

### ine-height 一个非常常见的用途

比如：

```css
.box {
    height: 50px;
    line-height: 50px;
}
```

如果里面只有一行文字：

```text
┌──────────────────────┐
│        我是文字       │
└──────────────────────┘
```

文字可以比较方便地实现**单行垂直居中**。

所以你以后看到：

```css
height: 50px;
line-height: 50px;
```

可以想到：

> **让单行文字在这个盒子里垂直居中。**

***

### display：显示方式

这个是这份代码里非常重要的一个属性。

代码中：

```css
.div-inline {
    display: inline;
}
```

以及：

```css
.span-inline-block {
    display: block;
}
```

这里的 `display` 可以理解成：

> **规定元素以什么方式显示。**

常见的就是：

```css
display: block;
```

```text
display: inline;
```

```text
display: inline-block;
```

***

#### display: block

```css
.box {
    display: block;
}
```

表示：

> 让元素按照**块级元素**的方式显示。

特点：

* 独占一行

* 可以设置宽度

* 可以设置高度

***

#### display: inline

```css
.box {
    display: inline;
}
```

表示：

> 让元素按照**行内元素**的方式显示。

特点：

* 不独占一行

* 多个元素可以排在一起

* 宽高控制受到限制

文件中的：

```css
.div-inline {
    display: inline;
}
```

就是把原本的 `div` 改成行内显示。

***

#### display: inline-block

```css
.box {
    display: inline-block;
}
```

表示：

> **按照行内方式排列，但是具有块级盒子的特性。**

例如：

```css
.box {
    display: inline-block;
    width: 100px;
    height: 100px;
}
```

可以让多个盒子：

```text
┌───────┐ ┌───────┐ ┌───────┐
│ 盒子1 │ │ 盒子2 │ │ 盒子3 │
└───────┘ └───────┘ └───────┘
```

同时还可以控制：

```css
width
height
```

***

### 把文件的知识串起来

其实这个 `css常用属性.html` 可以用一个盒子来理解：

```css
.box {
    width: 200px;
    height: 100px;
    background-color: lightblue;
    display: inline-block;
}
```

每一句负责不同的事情：

```text
width
↓
控制盒子的宽度

height
↓
控制盒子的高度

background-color
↓
控制盒子的背景颜色

display
↓
控制盒子怎么排列、怎么显示
```

而文字相关：

```css
font
↓
控制字体

line-height
↓
控制文字行高
```

***

### 这几个属性建议你这样记

| CSS 属性             | 作用       | 记忆   |
| ------------------ | -------- | ---- |
| `width`            | 设置宽度     | 多宽   |
| `height`           | 设置高度     | 多高   |
| `background-color` | 设置背景颜色   | 什么颜色 |
| `font`             | 设置字体相关样式 | 什么字体 |
| `line-height`      | 设置行高     | 一行多高 |
| `display`          | 设置显示方式   | 怎么排列 |

**最简单的口诀：**

> **width 宽，height 高，background 背景色；**\
> \
> \
> \
> **font 管字体，line-height 管行高；**\
> \
> \
> \
> **display 管显示方式。**

代码里，`width + height + background-color + display` 可以看成是在学习“盒子怎么显示”，而 `font + line-height` 是在学习“文字怎么显示”。

***

## CSS 盒子模型

**理解盒子模型是构建网页模型的基础，它能帮助你更精确的控制元素在页面中的位置和大小**

盒子模型相关属性

| 属性名              | 说明                                          |
| ---------------- | ------------------------------------------- |
| **内容（Content）**  | 盒子包含的实际内容，比如文本、图片等。                         |
| **内边距（Padding）** | 围绕在内容的内部，是内容与边框之间的空间。可以使用 `padding` 属性来设置。  |
| **边框（Border）**   | 围绕在内边距的外部，是盒子的边界。可以使用 `border` 属性来设置。       |
| **外边距（Margin）**  | 围绕在边框的外部，是盒子与其他元素之间的空间。可以使用 `margin` 属性来设置。 |

***

### 什么是 CSS 盒子模型？

在 CSS 中，我们可以把一个 HTML 元素想象成一个**盒子**。

这个盒子从里面到外面依次是：

```text
┌───────────────────────────────┐
│          Margin 外边距         │
│   ┌───────────────────────┐   │
│   │     Border 边框        │   │
│   │  ┌─────────────────┐  │   │
│   │  │ Padding 内边距   │  │   │
│   │  │  ┌───────────┐  │  │   │
│   │  │  │  Content  │  │  │   │
│   │  │  │   内容     │  │  │   │
│   │  │  └───────────┘  │  │   │
│   │  └─────────────────┘  │   │
│   └───────────────────────┘   │
└───────────────────────────────┘
```

简单记：

> **内容 → 内边距 → 边框 → 外边距**

也就是：

```text
Content → Padding → Border → Margin
```

***

我们通过这段代码来了解：

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>css 盒子模型</title>
    <style>
        .demo{
            background-color: lightblue;
            display: inline-block;
            border:5px solid darkblue;
            padding: 20px;
            margin: 20px;
        }
        .border-demo{
            background-color:yellow;
            width: 200px;
            height: 100px;
            border-style: solid dashed dotted double;
            border-width: 5px 10px 15px 20px;
            border-color: red;
            /* border-left: 5px solid red;
            border-left-color: aliceblue; */
        }
    </style>
</head>

<body>
    <div class='demo'>好水好水 如鱼得水</div>
    <div class="border-demo">这是一个边框示例</div>
</body>
</html>
```

先看第一个盒子 `.demo`

代码：

```css
.demo{
    background-color: lightblue;
    display: inline-block;
    border: 5px solid darkblue;
    padding: 20px;
    margin: 20px;
}
```

这里涉及了盒子模型的几个核心属性。

***

### Content：内容

HTML：

```html
<div class="demo">好水好水 如鱼得水</div>
```

这里：

```text
好水好水 如鱼得水
```

就是盒子的 **Content（内容）**。

也就是：

```text
┌───────────────┐
│ 好水好水 如鱼得水 │ ← Content
└───────────────┘
```

***

### Padding：内边距

代码：

```css
padding: 20px;
```

`padding` 就是**内容和边框之间的距离**。

例如：

```text
┌──────────────────────┐
│                      │
│    ┌────────────┐    │
│    │   内容      │    │
│    └────────────┘    │
│                      │
└──────────────────────┘
       ↑
    padding
```

你的：

```css
padding: 20px;
```

表示：

> 上、右、下、左四个方向的内边距都是 `20px`。

所以：

```text
padding-top    = 20px
padding-right  = 20px
padding-bottom = 20px
padding-left   = 20px
```

***

### Border：边框

代码：

```css
border: 5px solid darkblue;
```

这里实际上同时设置了三个东西：

```text
border-width: 5px;
border-style: solid;
border-color: darkblue;
```

也就是：

```css
border: 边框宽度 边框样式 边框颜色;
```

所以：

```css
border: 5px solid darkblue;
```

可以理解为：

> 边框宽度是 `5px`，样式是实线 `solid`，颜色是深蓝色。

结构就是：

```text
内容
 ↓
padding
 ↓
┌─────────────────┐
│     border      │ ← 5px
│  ┌───────────┐  │
│  │   内容     │  │
│  └───────────┘  │
└─────────────────┘
```

***

### Margin：外边距

代码：

```css
margin: 20px;
```

`margin` 是**盒子和其他元素之间的距离**。

例如：

```text
        margin
    ↓          ↓

  ┌─────────────────┐
  │      盒子        │
  └─────────────────┘

        ↑
      margin
```

你的代码：

```css
margin: 20px;
```

表示：

```text
上：20px
右：20px
下：20px
左：20px
```

所以两个盒子之间如果存在 `margin`，就会产生间距。

***

### 把 `.demo` 整个盒子串起来

现在把这几个属性放到一起：

```css
.demo{
    background-color: lightblue;
    display: inline-block;
    border: 5px solid darkblue;
    padding: 20px;
    margin: 20px;
}
```

可以理解成：

```text
              Margin 20px
        ↓────────────────────↓
        
        ┌────────────────────┐
        │      Border 5px     │
        │  ┌──────────────┐  │
        │  │ Padding 20px │  │
        │  │              │  │
        │  │  Content     │  │
        │  │ 好水好水 如鱼得水│  │
        │  │              │  │
        │  └──────────────┘  │
        └────────────────────┘
```

这就是 CSS **盒子模型**。

***

### `display: inline-block` 又是什么？

代码还有：

```css
display: inline-block;
```

这个属性不是盒子模型本身的组成部分，但它会影响盒子的排列方式。

默认情况下：

```html
<div>盒子1</div>
<div>盒子2</div>
```

`div` 是块级元素，通常会：

```text
┌───────┐
│ 盒子1 │
└───────┘

┌───────┐
│ 盒子2 │
└───────┘
```

一行一个。

而：

```css
display: inline-block;
```

可以让元素具有类似行内元素的排列特征，同时又保留盒子的宽高、padding、border、margin 等特性。

可以简单理解成：

> **inline-block = 可以像文字一样横向排列，同时又像盒子一样设置尺寸。**

***

### 再看 `.border-demo`

第二个盒子：

```css
.border-demo{
    background-color:yellow;
    width: 200px;
    height: 100px;
    border-style: solid dashed dotted double;
    border-width: 5px 10px 15px 20px;
    border-color: red;
}
```

这个例子主要是用来讲 **Border 的四个方向分别设置**。

***

### `border-style` 四个值

代码：

```css
border-style: solid dashed dotted double;
```

四个值分别对应：

```text
        上
      solid
        ↑
左 double ← 盒子 → 右 dashed
        ↓
      dotted
        下
```

CSS 四值规则是：

```text
上 → 右 → 下 → 左
```

也就是顺时针，所以：

```css
border-style: solid dashed dotted double;
```

等价于：

```css
border-top-style: solid;
border-right-style: dashed;
border-bottom-style: dotted;
border-left-style: double;
```

也就是：

| 方向 | 样式          |
| -- | ----------- |
| 上  | `solid` 实线  |
| 右  | `dashed` 虚线 |
| 下  | `dotted` 点线 |
| 左  | `double` 双线 |

***

### `border-width` 也是一样

代码：

```css
border-width: 5px 10px 15px 20px;
```

同样遵循：

> **上 → 右 → 下 → 左**

所以：

```text
上：5px
右：10px
下：15px
左：20px
```

等价于：

```css
border-top-width: 5px;
border-right-width: 10px;
border-bottom-width: 15px;
border-left-width: 20px;
```

***

### `border-color`

代码：

```css
border-color: red;
```

这里只有一个值，表示：

> 四个方向的边框颜色全部都是红色。

所以：

```text
上：红色
右：红色
下：红色
左：红色
```

***

这里还有一个非常重要的知识点：

### 盒子的实际大小

第二个盒子：

```css
width: 200px;
height: 100px;
```

同时：

```css
border-width: 5px 10px 15px 20px;
```

注意！

默认情况下 CSS 使用：

```css
box-sizing: content-box;
```

因此：

```text
width = 内容宽度
height = 内容高度
```

所以 `.border-demo`：

**宽度**

内容：

```text
200px
```

左右边框：

```text
左 20px + 右 10px
```

实际盒子宽度：

```text
20 + 200 + 10
= 230px
```

**高度**

内容：

```text
100px
```

上下边框：

```text
上 5px + 下 15px
```

实际盒子高度：

```text
5 + 100 + 15
= 120px
```

所以：

```text
内容区域：200 × 100

整个盒子：
宽度 = 230px
高度 = 120px
```

***

### 最终总结

这份代码主要涉及 **6 个知识点**：

**① Content 内容**

```html
<div>好水好水 如鱼得水</div>
```

盒子里面真正显示的内容。

**② Padding 内边距**

```css
padding: 20px;
```

**内容 ↔ 边框**之间的距离。

**③ Border 边框**

```css
border: 5px solid darkblue;
```

盒子的边界。

**④ Margin 外边距**

```css
margin: 20px;
```

**盒子 ↔ 其他元素**之间的距离。

**⑤ Border 四值写法**

```css
border-width: 5px 10px 15px 20px;
```

记住：

> **上右下左（顺时针）**

**⑥&#x20;**`width`**&#x20;/&#x20;**`height`

```css
width: 200px;
height: 100px;
```

默认 `content-box` 下，设置的是**内容区域的大小**，不是整个盒子的最终大小。

***

### ⭐ 最后记一个公式

在默认 `content-box` 下：

**元素实际宽度：**

```text
width
+ padding-left
+ padding-right
+ border-left
+ border-right
```

**元素实际高度：**

```text
height
+ padding-top
+ padding-bottom
+ border-top
+ border-bottom
```

而 `margin` **不算进盒子本身的尺寸**，但会影响它与其他元素之间的距离。

一句话记忆：

> **Content 是内容，Padding 撑开内部空间，Border 是边界，Margin 推开外部元素。**

***

## 传统网页布局方式

在学习浮动之前，先了解传统的网页布局方式

网页布局方式有以下五种：

* 标准流（普通流、文档流）：网页按照元素的书写顺序依次排列

* 浮动

* 定位

* `Flexbox` 和 `Grid`（自适应布局）

`标准流` 是由块级元素和行内元素按照默认规定的方式来排列，块级就是占一行，行内元素一行放好多个元素。

***

### 浮动

元素脱离文档流，根据开发者的意愿漂浮到网页的任意方向。

`浮动` 属性用于创建浮动框，将其移动到一边，直到左边缘或右边缘触及包含块或另一个浮动框的边缘，这样即可使得元素进行浮动。

**语法：**

```text
选择器 {
    float: left/right/none;
}
```

**注意：** 浮动是相对于父元素浮动，只会在父元素的内部移动。

***

#### 浮动的三大特性

学习浮动要先了解浮动的三大特性：

* **脱标：** 脱离标准流。

* **一行显示，顶部对齐**

* **具备行内块元素特性**

***

代码部分如下：

```text
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>浮动</title>
    <style>
        .father{
            border: 5px solid darkblue;
            /* height: 200px; */
            background-color: lightblue;
            /* overflow: hidden; */
        }
        .father::after{
            content: '';
            display: table;
            clear: both;
        }
        .left-son{
            float: left;
            width: 200px;
            height: 100px;
            background-color: lightgreen;
        }
        .right-son{
            float: right;
            width: 200px;
            height: 100px;
            background-color: lightcoral;
        }
    </style>
</head>
<body>
    <div class="father">
        <div class="left-son">左浮动</div>
        <div class="right-son">右浮动</div>
    </div>
    <p>不要因为饥饿就去吃垃圾食品，不要因为贫穷就乱选工作，不要因为寂寞就随便牵手，不要因为任何匮乏而降低标准，这个世界上选择无限。数千个擦肩而过，你选择谁，谁就和你有缘分，纵然没有甲，也终究会有乙。</p>
</body>
</html>
```

这份代码主要就是通过一个**父盒子&#x20;**`.father`**&#x20;+ 左右两个子盒子**来演示 CSS 浮动，以及浮动之后的**脱标、排列和清除浮动**。

***

#### 先看 HTML 结构

```html
<div class="father">
    <div class="left-son">左浮动</div>
    <div class="right-son">右浮动</div>
</div>

<p>不要因为饥饿就去吃垃圾食品……</p>
```

可以把它理解成：

```text
父盒子 father
│
├── 左盒子 left-son
│
└── 右盒子 right-son

下面还有一个 p 段落
```

其中 `.father` 是**父元素**，两个 `.son` 是它的**子元素**。

***

#### 什么是浮动？

代码中最关键的就是：

```css
.left-son {
    float: left;
}

.right-son {
    float: right;
}
```

`float` 就是**浮动属性**。

基本语法：

```css
选择器 {
    float: left;
}
```

常见取值：

```css
float: left;   /* 左浮动 */
float: right;  /* 右浮动 */
float: none;   /* 不浮动 */
```

***

#### 左浮动和右浮动

代码中：

```css
.left-son {
    float: left;
}
```

表示：

> `.left-son` 向父元素的左侧浮动。

而：

```css
.right-son {
    float: right;
}
```

表示：

> `.right-son` 向父元素的右侧浮动。

所以最终效果大致是：

```text
┌──────────────────────────────┐
│┌────────┐              ┌────────┐│
││ 左浮动 │              │ 右浮动 ││
│└────────┘              └────────┘│
└──────────────────────────────┘
```

这就是浮动非常典型的使用方式：**让原本上下排列的块级元素出现在同一行。**

***

#### 脱离标准流：浮动的第一个特点

这是学习浮动最重要的知识。

正常情况下：

```html
<div>盒子1</div>
<div>盒子2</div>
```

两个 `div` 都是块级元素，所以会：

```text
盒子1
盒子2
```

也就是**一个占一行**。

但是加上：

```css
div {
    float: left;
}
```

之后：

```text
盒子1  盒子2
```

因为浮动元素会**脱离标准流**。

你可以简单理解为：

> **原来按照正常顺序排队，现在浮起来了，不再按照普通标准流占据原来的位置。**

***

#### 一行显示：浮动的第二个特点

这份代码特别适合说明这一点。

左盒子：

```css
width: 200px;
height: 100px;
float: left;
```

右盒子：

```css
width: 200px;
height: 100px;
float: right;
```

两个盒子虽然都是 `div`，本来应该一上一下：

```text
左浮动
右浮动
```

但是浮动以后：

```text
左浮动                         右浮动
```

出现在同一行。

因此可以记住：

> **浮动元素可以在一行中排列。**

***

#### 顶部对齐：浮动的第三个特点

如果多个元素都浮动，它们会尽量在同一行排列，并且**顶部对齐**。

例如：

```css
.box1 {
    float: left;
}

.box2 {
    float: left;
}
```

效果类似：

```text
┌───────┐ ┌───────┐
│ box1  │ │ box2  │
│       │ │       │
│       │ └───────┘
│       │
└───────┘
```

它们会从上方开始排列。

***

#### 浮动后的元素具有“行内块”的特点

浮动元素还有一个非常重要的特点：

> **浮动元素具有类似行内块元素的特性。**

比如代码中：

```css
.left-son {
    float: left;
    width: 200px;
    height: 100px;
}
```

虽然 `.left-son` 是：

```html
<div>
```

而 `div` 本来是**块级元素**，但是浮动之后，它可以和其他浮动元素在一行排列，同时还可以设置：

```css
width
height
```

所以可以简单记：

```text
块级元素
   ↓
设置 float
   ↓
脱离标准流
   ↓
可以一行排列
   ↓
具有行内块元素的一些特点
```

***

#### 为什么父盒子要清除浮动？

这是这份代码里面非常值得重点学习的地方。

父盒子：

```css
.father {
    border: 5px solid darkblue;
    background-color: lightblue;
}
```

但是这里没有设置：

```css
height
```

而两个子元素全部浮动了：

```css
.left-son {
    float: left;
}

.right-son {
    float: right;
}
```

这时候就可能出现一个经典问题：

> **父元素高度塌陷。**

因为子元素已经脱离标准流，父元素在计算高度的时候，可能无法正常根据浮动子元素撑开。

可以理解成：

```text
父盒子
┌──────────────────────┐
│                      │
└──────────────────────┘
 ↑
父盒子不知道浮动子元素占了多高
```

***

#### 清除浮动

这份代码使用的是：

```css
.father::after {
    content: '';
    display: table;
    clear: both;
}
```

这是一个非常经典的**伪元素清除浮动**方法。

逐个看：

##### ① `::after`

```css
.father::after
```

表示给 `.father` 添加一个**最后面的伪元素**。

***

##### **②&#x20;**`content`

```css
content: '';
```

伪元素通常需要 `content` 才能生成。

这里生成一个空内容：

```css
content: '';
```

***

##### ③ `display: table`

```css
display: table;
```

让这个伪元素形成合适的布局特性。

***

##### **④&#x20;**`clear: both`

最关键的是：

```css
clear: both;
```

意思是：

> **清除左右两边的浮动影响。**

其中：

```css
clear: left;
```

清除左浮动。

```css
clear: right;
```

清除右浮动。

```css
clear: both;
```

**同时清除左、右浮动。**

所以：

```css
.father::after {
    content: '';
    display: table;
    clear: both;
}
```

可以理解为：

> **在父盒子的最后面增加一个元素，把左右浮动清除掉，从而让父盒子能够正确包住浮动的子元素。**

***

#### **代码里还有两种被注释掉的方法**

代码中还有：

```css
/* height: 200px; */
```

以及：

```css
/* overflow: hidden; */
```

这份代码实际上也在展示**解决浮动带来的父元素高度问题的其他方式**。

##### **方法一：给父元素固定高度**

```css
.father {
    height: 200px;
}
```

这样父盒子自己有高度。

但是这种方式不够灵活，因为如果里面的内容高度发生变化，就可能出现问题。

***

##### **方法二：**`overflow: hidden`

```css
.father {
    overflow: hidden;
}
```

也可以帮助父元素处理内部浮动带来的高度问题。

***

##### **方法三：伪元素清除浮动**

当前代码采用的是：

```css
.father::after {
    content: '';
    display: table;
    clear: both;
}
```

这也是非常常见的一种写法。

***

#### 最后的 `<p>` 是用来观察什么的？

代码最后还有：

```html
<p>
    不要因为饥饿就去吃垃圾食品……
</p>
```

这个段落可以帮助我们观察：

> **浮动元素会对后面的标准流元素产生影响。**

因为浮动元素脱离标准流以后，后面的普通内容可能会出现**环绕浮动元素**的效果。

这也是为什么以前做网页的时候，经常使用：

```text
左边：图片
右边：文字
```

例如：

```text
┌──────────┐  这是一段文字，这是一段文字
│          │  这是一段文字，这是一段文字
│   图片   │  这是一段文字，这是一段文字
│          │  这是一段文字
└──────────┘  这是一段文字
```

这就是浮动非常经典的应用场景。

***

#### 把这份代码总结成一张知识图

```text
                 CSS 浮动 float
                       │
          ┌────────────┼────────────┐
          ↓            ↓            ↓
       float:left   float:right   float:none
          │            │
          └──────┬─────┘
                 ↓
            元素脱离标准流
                 │
        ┌────────┼────────┐
        ↓        ↓        ↓
     一行显示   顶部对齐   类似行内块
                 │
                 ↓
          父元素高度塌陷问题
                 │
        ┌────────┼────────┐
        ↓        ↓        ↓
     固定高度  overflow  清除浮动
                         │
                         ↓
                  clear: both
```

**这份代码最核心的三个知识点就是：**

1. `float: left/right` —— **让元素浮动**

2. 浮动元素 —— **脱离标准流，可以一行排列**

3. 浮动带来的父元素高度问题 —— **使用&#x20;**`clear: both`**&#x20;等方式清除浮动**。

***

### 定位

定位布局可以精准定位，但缺乏灵活性

**定位方式：**

* **相对定位**：相对于元素在文档流中的正常位置进行定位。

* **绝对定位**：相对于其最近的已定位祖先元素进行定位，不占据文档流。

* **固定定位**：相对于浏览器窗口进行定位，不占据文档流，固定在屏幕上的位置，不随滚动而移动。

***

这个代码主要演示了 CSS 定位中的三种方式：**相对定位、绝对定位、固定定位**。

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>定位</title>
    <style>
        .box1{
            height: 350px;
            background-color: lightblue;
        }
        .box-normal{
            width: 100px;
            height: 100px;
            background-color: lightgreen;
        }
        .box-relative{
            width: 100px;
            height: 100px;
            background-color: lightcoral;
            position: relative;
            top: 50px;
            left: 50px;
        }
        .box2{
            height: 350px;
            background-color: lightblue;
            margin-bottom: 20px;
        }
        .box-absolute{
            width: 100px;
            height: 100px;
            background-color: lightyellow;
            position: absolute;
            left: 120px;
        }
        .box-fixed{
            width: 100px;
            height: 100px;
            background-color: lightgray;
            position: fixed;
            top:300px;
            right: 0;
        }
    </style>
</head>
<body>
    <h1>相对定位</h1>
    <div class="box1">
        <div class="box-normal"></div>
        <div class="box-relative"></div>
        <div class="box-normal"></div>
    </div>
    <h1>绝对定位</h1>
    <div class="box2">
        <div class="box-normal"></div>
        <div class="box-absolute"></div>
        <div class="box-normal"></div>
    </div>
    <h1>固定定位</h1>
    <div class="box-fixed"></div>
</body>

</html>
```

***

#### 什么是定位？

CSS 中的 `position` 就是用来控制元素的**定位方式**。

代码里分别用了：

```css
position: relative;
```

```css
position: absolute;
```

```css
position: fixed;
```

它们最大的区别可以先记成：

| 定位              | 参照物        | 是否脱离文档流 |
| --------------- | ---------- | ------- |
| `relative` 相对定位 | 自己原来的位置    | ❌ 不脱离   |
| `absolute` 绝对定位 | 最近的已定位祖先元素 | ✅ 脱离    |
| `fixed` 固定定位    | 浏览器窗口      | ✅ 脱离    |

***

#### 相对定位 `relative`

看代码：

```css
.box-relative{
    width: 100px;
    height: 100px;
    background-color: lightcoral;
    position: relative;
    top: 50px;
    left: 50px;
}
```

这里最重要的是：

```css
position: relative;
```

表示这个元素采用**相对定位**。

同时：

```css
top: 50px;
left: 50px;
```

表示：

* `top: 50px` → 向下移动 50px

* `left: 50px` → 向右移动 50px

所以可以简单理解为：

> **先按照正常位置摆放，再从自己的原位置进行移动。**

***

#### 为什么叫“相对”？

HTML：

```html
<div class="box1">
    <div class="box-normal"></div>
    <div class="box-relative"></div>
    <div class="box-normal"></div>
</div>
```

正常情况下三个盒子会依次排列：

```text
┌───────────────────────┐
│ □                     │
│                       │
│ □                     │
│                       │
│ □                     │
└───────────────────────┘
```

第二个盒子：

```css
position: relative;
top: 50px;
left: 50px;
```

移动以后：

```text
┌───────────────────────┐
│ □                     │
│                       │
│   □                   │
│                       │
│ □                     │
└───────────────────────┘
```

**关键点：它原来的位置依然保留。**

所以第三个盒子不会因为第二个盒子移动了，就跑到第二个盒子原来的位置。

这就是相对定位最大的特点：

> **移动了，但是原来的位置还占着。**

***

#### `top`、`left` 到底是什么？

定位经常会搭配这几个属性：

```css
top
bottom
left
right
```

例如：

```css
top: 50px;
```

表示：

> 距离原定位位置的上方偏移 50px，也就是**向下移动 50px**。

```css
left: 50px;
```

表示：

> 向右移动 50px。

可以这样记：

```text
top: 50px
   ↓
   元素向下

left: 50px
   →
   元素向右
```

反过来：

```css
top: -50px;
```

就是向上移动。

```css
left: -50px;
```

就是向左移动。

***

#### 绝对定位 `absolute`

再看代码：

```css
.box-absolute{
    width: 100px;
    height: 100px;
    background-color: lightyellow;
    position: absolute;
    left: 120px;
}
```

这里：

```css
position: absolute;
```

就是**绝对定位**。

绝对定位和相对定位最大的区别：

> **绝对定位会脱离正常文档流。**

***

#### 什么叫脱离文档流？

这里有：

```html
<div class="box-normal"></div>
<div class="box-absolute"></div>
<div class="box-normal"></div>
```

如果没有定位：

```text
□
□
□
```

三个盒子正常排列。

但是第二个盒子：

```css
position: absolute;
```

以后，它就相当于：

> “我不参与普通排队了。”

所以后面的元素会按照正常文档流继续排列。

可以粗略理解成：

```text
正常文档流：

□
□
□


绝对定位：

□

□

      □ ← 绝对定位元素
```

因此绝对定位元素可以**压在其他元素上面**。

***

#### 绝对定位到底相对于谁？

这是绝对定位最重要的知识点之一。

代码：

```css
.box-absolute{
    position: absolute;
    left: 120px;
}
```

那么这个元素的 `left: 120px` **到底是相对于谁？**

答案：

> **相对于最近的“已定位祖先元素”。**

例如：

```html
<div class="father">
    <div class="son"></div>
</div>
```

如果：

```css
.father {
    position: relative;
}

.son {
    position: absolute;
    left: 20px;
}
```

那么：

```text
father
┌─────────────────────────┐
│  son                    │
│  □                      │
└─────────────────────────┘
← 20px →
```

`.son` 会相对于 `.father` 定位。

***

#### 值得注意的地方

`.box2`：

```css
.box2{
    height: 350px;
    background-color: lightblue;
    margin-bottom: 20px;
}
```

它**没有设置**：

```css
position: relative;
```

所以 `.box-absolute` 找不到一个合适的已定位父元素时，会继续向上寻找。

代码中：

```html
<div class="box2">
    <div class="box-normal"></div>
    <div class="box-absolute"></div>
    <div class="box-normal"></div>
</div>
```

这正好可以用来理解为什么实际开发中经常写：

```css
.box2 {
    position: relative;
}
```

然后：

```css
.box-absolute {
    position: absolute;
    left: 120px;
}
```

意思就是：

> `.box2` 作为定位父级，`.box-absolute` 在 `.box2` 内部进行绝对定位。

这也是非常常见的 CSS 写法。

***

#### 固定定位 `fixed`

最后看代码：

```css
.box-fixed{
    width: 100px;
    height: 100px;
    background-color: lightgray;
    position: fixed;
    top:300px;
    right: 0;
}
```

这里：

```css
position: fixed;
```

就是**固定定位**。

它最大的特点：

> **相对于浏览器窗口进行定位。**

***

##### `top: 300px`

```css
top: 300px;
```

表示：

> 距离浏览器窗口顶部 300px。

***

##### `right: 0`

```css
right: 0;
```

表示：

> 紧贴浏览器窗口右边。

所以最终效果大概是：

```text
浏览器窗口
┌──────────────────────────────┐
│                              │
│                              │
│                              │
│                              │
│                         ┌────┤
│                         │ □  │ ← right: 0
│                         │    │
│                         └────┤
│                              │
│                              │
└──────────────────────────────┘
              ↑
         top: 300px
```

***

#### 固定定位为什么经常用于网站按钮？

例如网站右下角经常有：

```text
┌──────────────────────────┐
│                          │
│        网页内容          │
│                          │
│                          │
│                    ┌───┐ │
│                    │ ↑ │ │
│                    └───┘ │
└──────────────────────────┘
```

这个“返回顶部”按钮就很适合：

```css
position: fixed;
right: 20px;
bottom: 20px;
```

这样不管页面滚到哪里：

> **按钮始终固定在浏览器窗口右下角。**

代码中的 `.box-fixed` 就是在演示这个效果。

***

#### 三种定位放在一起对比

可以把这个文件记成一句话：

##### ① 相对定位

```css
position: relative;
top: 50px;
left: 50px;
```

**相对于自己原来的位置移动。**

```text
原位置 □
       ↘
        □
```

而且：

**原来的位置仍然保留。**

***

##### ② 绝对定位

```css
position: absolute;
left: 120px;
```

**相对于最近的已定位祖先元素定位。**

并且：

**脱离正常文档流。**

***

##### ③ 固定定位

```css
position: fixed;
top: 300px;
right: 0;
```

**相对于浏览器窗口定位。**

并且：

**脱离正常文档流，滚动页面时仍然固定在窗口的位置。**

***

#### 最重要的记忆口诀

你可以直接记这个：

> **relative：自己动，原位留。**\
> **absolute：找父级，脱离流。**\
> **fixed：盯窗口，固定住。**

还有一个非常重要的搭配：

```css
父元素 {
    position: relative;
}

子元素 {
    position: absolute;
}
```

这套组合在实际网页开发中**非常常见**，比如图片上的文字、卡片角标、按钮、图标等。
