---
link: front-end/javascript
title: JavaScript
draft: false
sticky: true
tocNumbering: true
excludeFromSummary: false
math: false
quiz: false
date: 2026-09-16 14:28:32
updated: 2026-09-16 20:50:11
categories:
  - [前端]
description: JavaScript与Java就像两条平行线，永不相交
cover: img/cover/26.webp
---
# 什么是 JavaScript

JavaScript 简称 JS。

JavaScript 是一种轻量级、解释型、面向对象的脚本语言。它主要被设计用于在网页上实现动态效果，增加用户与网页的交互性。

作为一种客户端脚本语言，JavaScript 可以直接嵌入 HTML，并在浏览器中执行。

与 HTML 和 CSS 不同，JavaScript 使得网页不再是静态的，而是可以根据用户的操作动态变化的。

***

## JavaScript 的作用

JavaScript 在前端开发中扮演着重要的角色，其应用领域包括但不限于：

* **客户端脚本**：用于在用户浏览器中执行，实现动态效果和用户交互。

* **网页开发**：与 HTML 和 CSS 协同工作，使得网页具有更强的交互性和动态性。

* **后端开发**：使用 Node.js，JavaScript 也可以在服务器端运行，实现服务器端应用的开发。

***

我们就**完全按照这两个文件里的代码**来讲 JavaScript，重点理解：**JavaScript 是什么、**`<script>`**&#x20;标签、内联 JS、外联 JS、**`console.log()`**、**`alert()`**，以及 JS 的执行位置。**

代码如下：

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>JS 导入方式</title>
    <script>
        console.log("Hello,head标签的内联样式");
    </script>
    <script src="./js/myscript.js"></script>
</head>
<body>
    <h1>JavaScript 导入方式</h1>
    <script>
        console.log("Hello,body标签的内联样式");
        alert("Hello,内联样式弹窗");
    </script>
</body>
</html>
```

**myscript.js**

```javascript
console.log('Hello,外联样式');
```

***

先看这段代码

HTML 中主要有三处 JavaScript：

```html
<script>
    console.log("Hello,head标签的内联样式");
</script>

<script src="./js/myscript.js"></script>
```

以及：

```html
<script>
    console.log("Hello,body标签的内联样式");
    alert("Hello,内联样式弹窗");
</script>
```

外部 JS 文件中是：

```javascript
console.log('Hello,外联样式');
```

***

## JavaScript 是干什么的？

前面我们讲过：

> **HTML：负责网页的结构**\
> \
> \
> \
> **CSS：负责网页的样式**\
> \
> \
> \
> **JavaScript：负责网页的行为和交互**

可以简单理解成：

```text
HTML        →  网页有什么
CSS         →  网页长什么样
JavaScript  →  网页怎么动、怎么响应操作
```

比如：

**HTML**

```html
<button>点击我</button>
```

只能创建一个按钮。

**CSS**

```css
button {
    color: red;
}
```

可以让按钮变红。

**JavaScript**

```javascript
alert("你好！");
```

可以让浏览器弹出提示框。

所以 JavaScript 的核心作用就是：

> **让网页从“静态页面”变成“可以进行交互的页面”。**

***

### `<script>` 标签

HTML 中出现了：

```html
<script>
    console.log("Hello,head标签的内联样式");
</script>
```

这里的：

```html
<script>
</script>
```

就是 HTML 中专门用来**编写或引入 JavaScript** 的标签。

可以把它理解成：

```text
<script> = 告诉浏览器：这里要执行 JavaScript
```

例如：

```html
<script>
    alert("Hello");
</script>
```

浏览器看到 `<script>` 后，就知道里面是 JavaScript 代码。

***

#### 第一种：内联 JavaScript

代码中：

```html
<script>
    console.log("Hello,head标签的内联样式");
</script>
```

JavaScript 代码直接写在 HTML 的 `<script>` 标签里面。

这种方式叫：

> **内联 JavaScript**

结构就是：

```html
<script>
    JavaScript代码
</script>
```

例如：

```html
<script>
    alert("你好");
</script>
```

浏览器打开网页后，就会执行：

```javascript
alert("你好");
```

***

#### 第二种：外联 JavaScript

HTML 还有这一行：

```html
<script src="./js/myscript.js"></script>
```

这一行非常重要。

它表示：

> **不要直接在 HTML 中写 JavaScript，而是去加载一个外部&#x20;**`.js`**&#x20;文件。**

你的外部 JS 文件内容是：

```javascript
console.log('Hello,外联样式');
```

也就是说：

```text
HTML
 │
 │ <script src="...">
 ↓
myscript.js
 │
 ↓
console.log(...)
```

***

### 为什么要使用外联 JS？

假设你的网页有很多 JavaScript。

如果全部写在 HTML：

```html
<script>
    // 很多代码
    // 很多代码
    // 很多代码
    // 很多代码
</script>
```

HTML 就会变得非常乱。

所以可以把 JavaScript 单独放到：

```text
myscript.js
```

HTML：

```html
<script src="./js/myscript.js"></script>
```

JS：

```javascript
console.log("Hello,外联样式");
```

这样就实现了：

```text
HTML → 负责结构
CSS  → 负责样式
JS   → 负责行为
```

这也是实际开发中非常常见的组织方式。

***

### `console.log()` 是什么？

代码中多次出现：

```javascript
console.log("Hello,head标签的内联样式");
```

这里的：

```javascript
console.log()
```

是 JavaScript 中非常常用的一个方法。

作用：

> **向浏览器的控制台输出信息。**

例如：

```javascript
console.log("Hello");
```

打开浏览器开发者工具的 Console，就可以看到：

```text
Hello
```

***

### 为什么学习 JavaScript 经常使用 `console.log()`？

因为它非常适合**查看程序运行结果**。

例如：

```javascript
console.log(1 + 2);
```

控制台：

```text
3
```

再比如：

```javascript
console.log("JavaScript");
```

控制台：

```text
JavaScript
```

所以现在你可以简单记：

```text
console.log()
      ↓
输出信息到控制台
```

它一般不是显示在网页页面上的。

***

### `alert()` 是什么？

代码中还有：

```javascript
alert("Hello,内联样式弹窗");
```

`alert()` 的作用是：

> **弹出一个浏览器提示框。**

执行：

```javascript
alert("Hello");
```

浏览器会出现类似：

```text
┌─────────────────┐
│      Hello      │
│                 │
│       [确定]    │
└─────────────────┘
```

所以：

```javascript
console.log()
```

和：

```javascript
alert()
```

虽然都可以输出信息，但效果不同。

| JavaScript      | 作用    | 显示位置    |
| --------------- | ----- | ------- |
| `console.log()` | 输出信息  | 浏览器控制台  |
| `alert()`       | 弹出提示框 | 网页浏览器窗口 |

***

### `src` 是什么？

来看：

```html
<script src="./js/myscript.js"></script>
```

这里的：

```html
src
```

可以理解成：

> **告诉浏览器 JavaScript 文件在哪里。**

例如：

```html
<script src="myscript.js"></script>
```

意思就是：

```text
去当前目录寻找 myscript.js
```

而：

```html
<script src="./js/myscript.js"></script>
```

表示：

```text
当前目录
   ↓
js 文件夹
   ↓
myscript.js
```

所以项目结构应该类似：

```text
项目文件夹
│
├── js导入方式.html
│
└── js
    └── myscript.js
```

**注意：**&#x8DEF;径和文件名需要对应，否则浏览器找不到这个 JS 文件。

***

### 代码中 JS 的执行顺序

HTML 是：

```html
<head>

    <script>
        console.log("Hello,head标签的内联样式");
    </script>

    <script src="./js/myscript.js"></script>

</head>
```

然后 `body`：

```html
<body>

    <h1>JavaScript 导入方式</h1>

    <script>
        console.log("Hello,body标签的内联样式");
        alert("Hello,内联样式弹窗");
    </script>

</body>
```

浏览器解析 HTML 时，会按照代码出现的位置执行普通的 `<script>`。

因此大致可以理解为：

#### 第一步

执行：

```javascript
console.log("Hello,head标签的内联样式");
```

控制台输出：

```text
Hello,head标签的内联样式
```

#### 第二步

加载：

```html
<script src="./js/myscript.js"></script>
```

然后执行外部 JS：

```javascript
console.log('Hello,外联样式');
```

控制台输出：

```text
Hello,外联样式
```

#### 第三步

继续解析 `body`。

遇到：

```javascript
console.log("Hello,body标签的内联样式");
```

输出：

```text
Hello,body标签的内联样式
```

#### 第四步

执行：

```javascript
alert("Hello,内联样式弹窗");
```

浏览器弹出：

```text
Hello,内联样式弹窗
```

所以控制台大致会看到：

```text
Hello,head标签的内联样式
Hello,外联样式
Hello,body标签的内联样式
```

同时会出现一个 `alert` 弹窗。

***

### 为什么 `<script>` 可以放在 `head` 和 `body`？

代码正好演示了两种位置。

#### 放在 head

```html
<head>
    <script>
        console.log("...");
    </script>
</head>
```

#### 放在 body

```html
<body>
    <script>
        console.log("...");
    </script>
</body>
```

两种方式都可以使用。

不过需要注意：

普通 `<script>` 放在 `head` 中时，浏览器解析到它会先执行 JavaScript，再继续解析后面的 HTML。

因此实际开发中还会进一步学习：

```html
<script defer src="xxx.js"></script>
```

和：

```html
<script async src="xxx.js"></script>
```

它们可以控制 JavaScript 的加载和执行时机。

**但这部分不在当前这份代码里，可以等后面学习 JS 导入方式时再讲。**

***

### 把这份代码的知识点总结起来

这份代码实际上主要是在学习 **JavaScript 的导入方式**。

可以整理成：

```text
                 JavaScript
                      │
          ┌───────────┴───────────┐
          │                       │
       内联 JS                  外联 JS
          │                       │
     <script>                <script src="">
          │                       │
     直接写代码                引入 .js 文件
```

代码对应：

#### ① Head 中的内联 JS

```html
<script>
    console.log("Hello,head标签的内联样式");
</script>
```

#### ② 外联 JS

```html
<script src="./js/myscript.js"></script>
```

对应：

```javascript
console.log('Hello,外联样式');
```

#### ③ Body 中的内联 JS

```html
<script>
    console.log("Hello,body标签的内联样式");
    alert("Hello,内联样式弹窗");
</script>
```

***

### 最后记住这几个东西

| 代码              | 含义                             |
| --------------- | ------------------------------ |
| `<script>`      | 在 HTML 中编写/执行 JavaScript       |
| `src`           | 指定外部 JS 文件的位置                  |
| `console.log()` | 向控制台输出信息                       |
| `alert()`       | 弹出提示框                          |
| 内联 JS           | JS 直接写在 `<script>` 中           |
| 外联 JS           | JS 单独写在 `.js` 文件中，再通过 `src` 引入 |

***

## JavaScript 基础语法

**核心代码是：**

```javascript
var x;
let y = 5;
const PI = 3.14;

console.log(x, y, PI);

let name = '水鱼';
console.log(name);

let empty_value = null;
console.log(empty_value);
```

**代码主要涉及：**

1. 变量声明

2. `var`

3. `let`

4. `const`

5. 变量赋值

6. 字符串

7. `null`

8. `console.log()`

***

### 什么是变量？

在 JavaScript 中，我们经常需要**保存数据**。

比如：

```javascript
let y = 5;
```

可以理解成：

```text
变量 y
   ↓
保存
   ↓
5
```

以后我们就可以通过 `y` 来使用这个 `5`。

例如：

```javascript
let y = 5;

console.log(y);
```

控制台输出：

```text
5
```

所以可以简单理解：

> **变量就是用来存储数据的“容器”。**

***

### 变量的基本写法

JavaScript 中变量声明的基本形式：

```javascript
let 变量名 = 数据;
```

例如：

```javascript
let age = 18;
```

这里可以拆成：

```text
let     → 声明变量
age     → 变量名
=       → 赋值
18      → 数据
```

所以：

```javascript
let age = 18;
```

就是：

> 创建一个叫 `age` 的变量，并把 `18` 保存进去。

***

### 代码中的 `var`

代码：

```javascript
var x;
```

这里使用的是：

```javascript
var
```

`var` 也是 JavaScript 中声明变量的方式。

例如：

```javascript
var x;
```

这里实际上**只声明了变量&#x20;**`x`**，但是没有给它赋值**。

所以：

```javascript
console.log(x);
```

输出的是：

```text
undefined
```

***

### 什么是 `undefined`？

代码：

```javascript
var x;
```

虽然创建了变量 `x`，但是没有给它具体的数据。

所以 JavaScript 会给它一个特殊的值：

```javascript
undefined
```

可以理解成：

```text
x
↓
没有赋值
↓
undefined
```

因此：

```javascript
var x;

console.log(x);
```

结果：

```text
undefined
```

***

### `let`

代码中：

```javascript
let y = 5;
```

这里使用的是：

```javascript
let
```

它也是声明变量的方式。

例如：

```javascript
let y = 5;
```

意思是：

> 声明变量 `y`，并让它保存数字 `5`。

之后可以：

```javascript
console.log(y);
```

得到：

```text
5
```

***

### `let` 可以重新赋值

例如：

```javascript
let y = 5;

y = 10;

console.log(y);
```

结果：

```text
10
```

这里：

```javascript
y = 10;
```

并不是重新声明变量，而是**修改变量&#x20;**`y`**&#x20;保存的数据**。

所以：

```text
let y = 5
   ↓
y = 10
   ↓
y现在保存10
```

***

### `const`

代码：

```javascript
const PI = 3.14;
```

这里使用：

```javascript
const
```

`const` 用于声明**常量**。

例如：

```javascript
const PI = 3.14;
```

可以理解成：

> 创建一个叫 `PI` 的常量，并保存 `3.14`。

和 `let` 最大的区别之一是：

```text
let   → 可以重新赋值
const → 不能重新赋值
```

例如：

```javascript
let age = 18;
age = 20;
```

可以。

但是：

```javascript
const PI = 3.14;
PI = 3.14159;
```

不允许。

***

### 为什么 `PI` 使用 `const`？

代码：

```javascript
const PI = 3.14;
```

`PI` 表示数学中的圆周率。

圆周率是一个固定的概念，所以这里使用：

```javascript
const
```

表示这个值不应该被重新赋值。

因此在实际开发中：

> **不会改变的值，可以考虑使用&#x20;**`const`**。**

会改变的变量通常使用：

```javascript
let
```

***

### `var`、`let`、`const` 对比

你现在可以先记住最基础的区别：

| 关键字     | 作用   | 能否重新赋值 |
| ------- | ---- | ------ |
| `var`   | 声明变量 | 可以     |
| `let`   | 声明变量 | 可以     |
| `const` | 声明常量 | 不可以    |

例如：

```javascript
var a = 1;
a = 2;
```

可以。

```javascript
let b = 1;
b = 2;
```

也可以。

```javascript
const c = 1;
c = 2;
```

不可以。

**注意：**`var` 和 `let` 还有作用域、重复声明、提升等区别，不过这些不在你当前这份代码中，我们先不展开。

***

### 变量名

代码里有：

```javascript
let y = 5;
let name = '水鱼';
let empty_value = null;
```

这里：

```text
y
name
empty_value
```

都是**变量名**。

变量名可以自己定义，但是需要遵守一定的命名规则。

例如：

```javascript
let age = 18;
let username = "Tom";
let score = 100;
```

都是很常见的写法。

***

### 下划线 `_`

你的代码：

```javascript
let empty_value = null;
```

变量名中使用了：

```text
_
```

也就是下划线。

这是允许的。

所以：

```javascript
empty_value
```

是合法的变量名。

***

### JavaScript 中的字符串

代码：

```javascript
let name = '水鱼';
```

这里：

```javascript
'水鱼'
```

是一个**字符串**。

字符串就是一段文本。

例如：

```javascript
let name = '水鱼';
```

表示：

```text
name
 ↓
"水鱼"
```

***

### 字符串可以使用单引号

例如：

```javascript
let name = '水鱼';
```

也可以使用双引号：

```javascript
let name = "水鱼";
```

两者都可以表示字符串。

所以：

```javascript
'Hello'
```

和：

```javascript
"Hello"
```

都是字符串。

***

### 数字

代码：

```javascript
let y = 5;
```

这里的：

```javascript
5
```

是数字。

注意：

```javascript
5
```

和：

```javascript
'5'
```

是不一样的。

前者：

```javascript
5
```

是数字。

后者：

```javascript
'5'
```

是字符串。

可以理解成：

```text
5      → 数字
'5'    → 文本
```

这是 JavaScript 基础语法中非常重要的区别。

***

### `null`

代码：

```javascript
let empty_value = null;
```

这里出现了：

```javascript
null
```

`null` 表示：

> **空值，明确表示“这里没有值”。**

例如：

```javascript
let empty_value = null;
```

可以理解成：

```text
empty_value
     ↓
    null
     ↓
   空值
```

然后：

```javascript
console.log(empty_value);
```

控制台会输出：

```text
null
```

***

### `undefined` 和 `null` 的区别

这份代码刚好可以用：

```javascript
var x;
```

和：

```javascript
let empty_value = null;
```

来理解两者的区别。

### `undefined`

```javascript
var x;
```

没有给 `x` 赋值。

所以：

```text
x → undefined
```

### `null`

```javascript
let empty_value = null;
```

是**主动把变量设置为空值**。

所以：

```text
empty_value → null
```

简单记：

```text
undefined → 没有赋值
null      → 明确表示空
```

***

### `console.log()` 再复习一下

代码：

```javascript
console.log(x, y, PI);
```

这里一次输出了三个变量：

```javascript
x
y
PI
```

因为：

```javascript
x = undefined
y = 5
PI = 3.14
```

所以控制台大致会显示：

```text
undefined 5 3.14
```

后面：

```javascript
console.log(name);
```

输出：

```text
水鱼
```

最后：

```javascript
console.log(empty_value);
```

输出：

```text
null
```

***

### 把整个代码串起来理解

现在重新看代码：

```javascript
var x;
```

声明变量 `x`，但是没有赋值：

```text
x → undefined
```

然后：

```javascript
let y = 5;
```

声明变量 `y`：

```text
y → 5
```

然后：

```javascript
const PI = 3.14;
```

声明常量 `PI`：

```text
PI → 3.14
```

然后：

```javascript
console.log(x, y, PI);
```

把三个变量输出到控制台。

接着：

```javascript
let name = '水鱼';
```

创建变量 `name`，保存字符串：

```text
name → "水鱼"
```

最后：

```javascript
let empty_value = null;
```

创建变量 `empty_value`，并主动赋值为空：

```text
empty_value → null
```

***

### 这份代码涉及的知识点

可以整理成一张知识结构：

```text
JavaScript 基础语法
│
├── 变量
│   ├── var
│   ├── let
│   └── const
│
├── 数据
│   ├── 数字
│   │   └── 5
│   │
│   ├── 字符串
│   │   └── '水鱼'
│   │
│   ├── undefined
│   │   └── var x;
│   │
│   └── null
│       └── empty_value = null
│
└── 输出
    └── console.log()
```

#### **你现在最需要记住的就是**

```javascript
let age = 18;
```

**声明一个可以改变的变量**

```javascript
const PI = 3.14;
```

**声明一个不能重新赋值的常量**

```javascript
var x;
```

**声明变量但没有赋值 →&#x20;**`undefined`

```javascript
let value = null;
```

**主动表示这个变量是空值 →&#x20;**`null`

```javascript
console.log(value);
```

**把数据输出到浏览器控制台。**

***

## Java 控制语句

### 条件语句

条件语句是编程中常用的结构，用于基于不同的条件执行不同的代码块。

#### `if` 语句：用于执行一个代码块，当指定的条件为真（true）时执行。语法如下

```javascript
if (condition) {
    // 如果条件为真，执行这里的代码
}
```

***

#### `else` 语句：用于在上一个 `if` 和所有的 `else if` 都为假时执行的代码块。语法如下

```javascript
if (condition) {
    // 如果条件为真，执行这里的代码
} else {
    // 如果条件为假，执行这里的代码
}
```

***

#### else if 语句

用于在上一个 if 语句条件为假时，检查另一个条件。可以有多个 else if 语句。语法如下：

```text
if (condition1) {
    // 如果条件1为真，执行这里的代码
 } else if (condition2) {
    // 如果条件2为真，执行这里的代码
 } else {
    // 如果以上条件都为假，执行这里的代码
 }
```

***

### 循环语句

循环语句用于重复执行一段代码，直到指定的条件不再满足为止。

#### for 循环

是一种常见的循环结构，用于按照指定的条件重复执行代码块。语法如下：

```text
for（初始化表达式；循环条件；迭代器）{
    // 循环体，执行这里的代码
}
```

***

#### `while` 循环

会在指定的条件为真时执行代码块。语法如下：

```text
while (循环条件) {
    // 循环体，执行这里的代码
}
```

***

#### break 与 continue

循环关键字

* break 用于跳出循环，结束循环的执行。

* continue 用于跳过当前循环中的剩余代码，继续下一次循环。

***

## JavaScript 函数

`函数` 是一段可重复使用的代码块，它接受输入（参数）、执行特定任务，并返回输出。

```javascript
1 function function_name(参数1, 参数2, 参数3, ...) { // 参数可以不写，表示不传参
2     // 函数体，执行这里的代码
3     return 返回值; // 可选，返回值
4 }
```
