---
title: css
draft: false
sticky: true
tocNumbering: true
excludeFromSummary: false
math: false
quiz: false
date: 2026-09-13 14:45:22
updated: 2026-09-14 21:16:06
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

**HTML = 网页的骨架 🦴**\
\
\
\
**CSS = 网页的外衣 👕**

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
\
\
\
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
> \
> \
> \
> **内部：HTML 里面的&#x20;**`<style>`\
> \
> \
> \
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
> **font 管字体，line-height 管行高；**\
> \
> **display 管显示方式。**

代码里，`width + height + background-color + display` 可以看成是在学习“盒子怎么显示”，而 `font + line-height` 是在学习“文字怎么显示”。
