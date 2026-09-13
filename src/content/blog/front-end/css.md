---
title: css
draft: false
sticky: true
tocNumbering: true
excludeFromSummary: false
math: false
quiz: false
date: 2026-09-13 14:45:22
updated: 2026-09-13 16:55:00
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

### 一句话记忆

**HTML = 网页的骨架 🦴**\
\
\
\
\
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
