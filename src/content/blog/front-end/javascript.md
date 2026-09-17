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
updated: 2026-09-17 18:24:40
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
> **CSS：负责网页的样式**\
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

## JavaScript 控制语句

**控制语句**就是用来控制代码“怎么执行”的语句。

正常情况下，JavaScript 是从上到下依次执行：

```javascript
console.log('第一句');
console.log('第二句');
console.log('第三句');
```

执行顺序就是：

```text
第一句
 ↓
第二句
 ↓
第三句
```

但是实际开发中，我们经常需要：

* **如果满足条件，就执行某段代码**

* **重复执行某段代码**

* **满足某个条件就跳过**

* **满足某个条件就停止**

这时候就需要使用**控制语句**。

***

我们来看这段代码：

```html
// let time=10;
        // if(time<12){
        //     alert('上午好');
        // }else if(time<18){
        //     alert('下午好');
        // }else{
        //     alert('晚上好');
        // }

        console.log('for循环');
        for(let i=1;i<=10;i++){
            console.log(i);
        }

        console.log('while循环');
        let count=1;
        while(count<=10){
            console.log(count);
            count++;
        }

        console.log('循环关键字');
        for(var i=0;i<7;i++){
            if(i==2){
                continue;
            }
            if(i==5){
                break;
            }
            console.log(i);
        }
```

这段代码主要涉及 JavaScript 中的 **控制语句**，可以分成三大类来理解：

1. **条件控制语句**：`if / else if / else`

2. **循环控制语句**：`for / while`

3. **循环关键字**：`continue / break`

下面直接结合代码讲。

***

### 条件语句

条件语句是编程中常用的结构，用于基于不同的条件执行不同的代码块。

代码最前面的部分：

```javascript
// let time=10;
// if(time<12){
//     alert('上午好');
// }else if(time<18){
//     alert('下午好');
// }else{
//     alert('晚上好');
// }
```

虽然现在被 `//` 注释掉了，但是它是非常典型的 `if` 条件语句。

#### `if` 语句：用于执行一个代码块，当指定的条件为真（true）时执行。语法如下

```javascript
if (condition) {
    // 如果条件为真，执行这里的代码
}
```

例如：

```javascript
let time = 10;

if(time < 12){
    alert('上午好');
}
```

程序会判断：

```text
time < 12 ?
```

因为：

```text
10 < 12
```

结果为：

```javascript
true
```

所以执行：

```javascript
alert('上午好');
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

例如：

```javascript
let age = 20;

if(age >= 18){
    console.log('成年人');
}else{
    console.log('未成年人');
}
```

执行过程：

```text
age >= 18？
   ↓
  是
   ↓
成年人
```

如果 `age = 15`：

```text
age >= 18？
   ↓
  否
   ↓
未成年人
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

例如：

```javascript
if(time < 12){
    alert('上午好');
}else if(time < 18){
    alert('下午好');
}else{
    alert('晚上好');
}
```

它可以处理**多个条件**。

假设：

```javascript
let time = 10;
```

程序从上往下判断。

### 第一次判断

```javascript
time < 12
```

也就是：

```text
10 < 12
```

成立，所以执行：

```javascript
alert('上午好');
```

然后整个条件结构结束，**不会继续判断后面的条件**。

***

如果：

```javascript
let time = 15;
```

那么：

```javascript
time < 12
```

不成立。

继续判断：

```javascript
time < 18
```

成立。

所以：

```text
下午好
```

***

如果：

```javascript
let time = 20;
```

前两个条件都不成立：

```javascript
20 < 12 ❌
20 < 18 ❌
```

最后执行：

```javascript
else{
    alert('晚上好');
}
```

所以可以总结成：

```text
time < 12      → 上午好
12 ≤ time < 18 → 下午好
time ≥ 18      → 晚上好
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

代码：

```javascript
console.log('for循环');

for(let i=1;i<=10;i++){
    console.log(i);
}
```

运行结果：

```text
for循环
1
2
3
4
5
6
7
8
9
10
```

`for` 是 JavaScript 中非常常用的循环语句。

基本格式：

```javascript
for(初始化; 条件; 更新){
    // 循环执行的代码
}
```

你的代码：

```javascript
for(let i=1; i<=10; i++){
    console.log(i);
}
```

可以拆成三部分：

```javascript
let i = 1
```

##### ① 初始化

第一次执行循环之前：

```javascript
let i = 1;
```

也就是：

```text
i = 1
```

***

##### ② 条件

```javascript
i <= 10
```

只要这个条件成立，就执行循环体。

***

##### ③ 更新

```javascript
i++
```

每执行一次循环：

```text
i = i + 1
```

所以执行过程是：

```text
i=1 → 输出1 → i++
i=2 → 输出2 → i++
i=3 → 输出3 → i++
...
i=10 → 输出10 → i++
i=11 → 11<=10 不成立 → 结束
```

***

##### for 循环的执行顺序

这个非常重要。

```javascript
for(let i=1; i<=3; i++){
    console.log(i);
}
```

执行过程：

```text
① let i=1
       ↓
② i<=3？
       ↓
③ console.log(i)
       ↓
④ i++
       ↓
⑤ i<=3？
       ↓
⑥ console.log(i)
       ↓
⑦ i++
       ↓
...
```

所以 `for` 循环可以理解为：

> **设置初始值 → 判断条件 → 执行代码 → 修改变量 → 再判断条件 → ……**

***

#### `while` 循环

会在指定的条件为真时执行代码块。语法如下：

```text
while (循环条件) {
    // 循环体，执行这里的代码
}
```

代码：

```javascript
console.log('while循环');

let count=1;

while(count<=10){
    console.log(count);
    count++;
}
```

运行结果同样是：

```text
while循环
1
2
3
4
5
6
7
8
9
10
```

`while` 的基本格式：

```javascript
while(条件){
    // 循环执行的代码
}
```

你的代码：

```javascript
while(count <= 10){
    console.log(count);
    count++;
}
```

意思是：

> **只要&#x20;**`count <= 10`**，就一直执行循环。**

***

##### while 循环的执行过程

开始：

```javascript
let count = 1;
```

然后判断：

```javascript
count <= 10
```

成立：

```text
输出 1
count++
```

此时：

```text
count = 2
```

再次判断：

```text
2 <= 10
```

成立。

继续：

```text
输出 2
count++
```

一直到：

```text
count = 10
```

输出：

```text
10
```

然后：

```javascript
count++;
```

变成：

```text
count = 11
```

判断：

```text
11 <= 10
```

不成立。

循环结束。

***

#### for 和 while 的区别

你这里的两个循环实际上完成了相同的事情：

**for**

```javascript
for(let i=1;i<=10;i++){
    console.log(i);
}
```

**while**

```javascript
let count=1;

while(count<=10){
    console.log(count);
    count++;
}
```

都可以输出：

```text
1 2 3 4 5 6 7 8 9 10
```

区别主要在于使用场景。

| 循环      | 特点                     |
| ------- | ---------------------- |
| `for`   | 通常用于**循环次数比较明确**的情况    |
| `while` | 通常用于**满足某个条件就一直循环**的情况 |

例如：

```javascript
for(let i=1;i<=100;i++){
    console.log(i);
}
```

非常适合表示：

> 循环 100 次。

而：

```javascript
while(password != '123456'){
    // 继续输入密码
}
```

更加符合：

> 只要密码不正确，就继续。

***

#### 循环关键字

你的第三部分：

```javascript
console.log('循环关键字');

for(var i=0;i<7;i++){
    if(i==2){
        continue;
    }

    if(i==5){
        break;
    }

    console.log(i);
}
```

这里主要学习两个非常重要的关键字：

```javascript
continue
break
```

**break 与 continue**

循环关键字

* break 用于跳出循环，结束循环的执行。

* continue 用于跳过当前循环中的剩余代码，继续下一次循环。

***

##### continue：跳过本次循环

代码：

```javascript
if(i==2){
    continue;
}
```

`continue` 的作用：

> **跳过当前这一次循环，直接进入下一次循环。**

例如：

```javascript
for(var i=0;i<7;i++){
    if(i==2){
        continue;
    }

    console.log(i);
}
```

正常情况下应该输出：

```text
0
1
2
3
4
5
6
```

但是当：

```javascript
i == 2
```

时：

```javascript
continue;
```

执行。

于是 `2` 这一轮不会执行：

```javascript
console.log(i);
```

所以结果：

```text
0
1
3
4
5
6
```

可以把 `continue` 理解成：

> **“这次先跳过，下一次继续。”**

***

##### break：直接结束循环

代码：

```javascript
if(i==5){
    break;
}
```

`break` 和 `continue` 最大的区别：

```text
continue → 跳过本次循环
break    → 结束整个循环
```

例如：

```javascript
for(var i=0;i<7;i++){
    if(i==5){
        break;
    }

    console.log(i);
}
```

执行：

```text
i=0 → 输出0
i=1 → 输出1
i=2 → 输出2
i=3 → 输出3
i=4 → 输出4
i=5 → break
```

所以结果：

```text
0
1
2
3
4
```

`6` 不会执行。

***

#### 完整代码到底输出什么？

重点看：

```javascript
for(var i=0;i<7;i++){
    if(i==2){
        continue;
    }

    if(i==5){
        break;
    }

    console.log(i);
}
```

我们一步一步来看：

| `i` | `i==2` | `i==5` | 执行结果          |
| --- | ------ | ------ | ------------- |
| 0   | ❌      | ❌      | 输出 `0`        |
| 1   | ❌      | ❌      | 输出 `1`        |
| 2   | ✅      | —      | `continue`，跳过 |
| 3   | ❌      | ❌      | 输出 `3`        |
| 4   | ❌      | ❌      | 输出 `4`        |
| 5   | ❌      | ✅      | `break`，结束循环  |
| 6   | —      | —      | 不执行           |

最终：

```text
0
1
3
4
```

***

#### 三个控制语句放在一起理解

你可以记成：

##### `if`

**判断**

```javascript
if(age >= 18){
    console.log('成年人');
}
```

> 如果条件成立，就执行。

***

##### `for / while`

**重复**

```javascript
for(let i=0;i<5;i++){
    console.log(i);
}
```

> 重复执行一段代码。

***

##### `continue`

**跳过**

```javascript
if(i == 2){
    continue;
}
```

> 当前这一次不执行，下一次继续。

***

##### `break`

**停止**

```javascript
if(i == 5){
    break;
}
```

> 直接结束整个循环。

***

#### 可以用一个流程图记忆

```text
                开始
                  ↓
             判断条件？
             ↙       ↘
           是         否
           ↓          ↓
        执行代码      结束
           ↓
     是否 continue？
       ↙       ↘
     是         否
     ↓          ↓
   下一轮     是否 break？
              ↙      ↘
            是        否
            ↓         ↓
           结束      下一轮
```

#### 最后记忆口诀

> **if 是“判断”，for/while 是“重复”，continue 是“跳过”，break 是“停止”。**

这段代码其实已经覆盖了 JS 控制语句最核心的基础内容。学习顺序可以记成：

```text
条件
 ↓
if
 ↓
if...else
 ↓
if...else if...else
 ↓
循环
 ↓
for
 ↓
while
 ↓
continue / break
```

这几个掌握之后，再往后就是 `switch`**&#x20;条件语句、嵌套循环、三元运算符** 等内容。

***

## JavaScript 函数

`函数` 是一段可重复使用的代码块，它接受输入（参数）、执行特定任务，并返回输出。

```javascript
1 function function_name(参数1, 参数2, 参数3, ...) { // 参数可以不写，表示不传参
2     // 函数体，执行这里的代码
3     return 返回值; // 可选，返回值
4 }
```

***

主要讲**JavaScript 函数的 4 个核心知识点**：

1. 什么是函数

2. 函数的调用

3. 参数和返回值

4. 作用域（全局变量、局部变量）

下面按照代码里的顺序讲。

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>JavaScript 函数</title>
</head>
<body>
    <script>
        function hello(){
            console.log('Hello,world!');
        }
        hello();

        function hello_with_return(){
            return 'Hello,world! - 返回值'
        }
        let a = hello_with_return();
        console.log(a);
        console.log(hello_with_return());
        
        function hello_with_parms(name){
            console.log('hello,'+name);
        }
        hello_with_parms('如花');
        hello_with_parms('Alice');

        //作用域
        let global_var = '全局变量';
        function local_var_function(){
            let local_var ='局部变量';
            console.log('函数内打印全局变量:'+global_var);
            console.log('函数内打印局部变量:'+local_var);
        }
        local_var_function();
        console.log('全局打印全局变量:'+global_var);
        console.log('全局打印局部变量:'+local_var);
    </script>
</body>
</html>
```

***

### 什么是函数？

函数可以简单理解为：

> **把一段可以重复执行的代码封装起来，需要的时候直接调用。**

代码中的第一个函数：

```javascript
function hello(){
    console.log('Hello,world!');
}

hello();
```

这里：

```javascript
function hello(){
```

是在**定义函数**。

其中：

* `function`：声明函数的关键字

* `hello`：函数名

* `()`：参数列表，目前没有参数

* `{}`：函数体，里面放需要执行的代码

所以：

```javascript
function hello(){
    console.log('Hello,world!');
}
```

可以理解成：

> 创建了一个叫 `hello` 的函数，这个函数的功能是输出 `Hello,world!`。

**但是定义函数并不会自动执行**

真正让它执行的是：

```javascript
hello();
```

这叫做**函数调用**。

所以执行过程是：

```text
定义函数
   ↓
function hello(){...}
   ↓
调用函数
   ↓
hello()
   ↓
执行 console.log()
   ↓
输出 Hello,world!
```

代码正是这样体现的。

***

### 函数返回值 `return`

接下来代码：

```javascript
function hello_with_return(){
    return 'Hello,world! - 返回值'
}

let a = hello_with_return();
console.log(a);
```

这里出现了一个非常重要的概念：

`return`**&#x20;—— 返回值**

```javascript
return 'Hello,world! - 返回值'
```

意思是：

> 执行这个函数之后，把这个字符串返回出去。

所以：

```javascript
let a = hello_with_return();
```

执行过程可以理解成：

```text
hello_with_return()
       ↓
执行 return
       ↓
返回 'Hello,world! - 返回值'
       ↓
赋值给 a
```

最终：

```javascript
a
```

里面保存的是：

```text
Hello,world! - 返回值
```

所以：

```javascript
console.log(a);
```

就会输出：

```text
Hello,world! - 返回值
```

***

### `return` 和 `console.log` 有什么区别？

这是学习函数时非常容易混淆的地方。

#### `console.log()`

```javascript
function hello(){
    console.log('Hello');
}
```

它主要是：

> **把内容打印到控制台。**

#### `return`

```javascript
function hello(){
    return 'Hello';
}
```

它主要是：

> **把结果返回给调用这个函数的地方。**

例如：

```javascript
let a = hello();
```

这里 `a` 可以接收到 `return` 返回的值。

代码中还直接这样写：

```javascript
console.log(hello_with_return());
```

意思就是：

```text
调用函数
 ↓
得到返回值
 ↓
console.log()打印返回值
```

这部分代码正好演示了函数返回值的两种使用方式。

***

### 函数参数

接下来是：

```javascript
function hello_with_parms(name){
    console.log('hello,'+name);
}

hello_with_parms('如花');
hello_with_parms('Alice');
```

这里出现了**参数**。

定义函数的时候：

```javascript
function hello_with_parms(name)
```

这里的 `name` 就叫做**形参**。

可以把它理解成一个变量：

```javascript
name
```

它等待调用函数的时候接收数据。

***

### 调用的时候传入参数

第一次：

```javascript
hello_with_parms('如花');
```

相当于：

```javascript
name = '如花'
```

所以：

```javascript
console.log('hello,'+name);
```

最终就是：

```javascript
console.log('hello,'+'如花');
```

输出：

```text
hello,如花
```

第二次：

```javascript
hello_with_parms('Alice');
```

此时：

```javascript
name = 'Alice'
```

输出：

```text
hello,Alice
```

我的代码正是通过连续调用两次来展示**同一个函数可以接收不同的数据**。

***

### 形参和实参

这里可以顺便记住两个概念。

**形参**

定义函数时的参数：

```javascript
function hello_with_parms(name)
```

`name` 是**形参**。

**实参**

调用函数时真正传入的数据：

```javascript
hello_with_parms('如花');
```

`'如花'` 是**实参**。

再比如：

```javascript
function add(a,b){
    return a+b;
}

add(10,20);
```

这里：

```text
a、b     → 形参
10、20   → 实参
```

***

### 函数可以同时有多个参数

比如：

```javascript
function add(a,b){
    return a+b;
}

let result = add(10,20);

console.log(result);
```

执行：

```text
add(10,20)
   ↓
a = 10
b = 20
   ↓
return 10 + 20
   ↓
返回 30
   ↓
result = 30
```

最终：

```text
30
```

所以函数参数的作用就是：

> **让函数可以接收外部传进来的数据。**

***

### 函数作用域

代码后面专门演示了**作用域**：

```javascript
let global_var = '全局变量';

function local_var_function(){
    let local_var ='局部变量';

    console.log('函数内打印全局变量:'+global_var);
    console.log('函数内打印局部变量:'+local_var);
}
```

这里需要理解两个概念：

* 全局变量

* 局部变量

***

#### 1. 全局变量

```javascript
let global_var = '全局变量';
```

它定义在函数外面。

所以它属于**全局作用域**。

例如：

```javascript
function local_var_function(){
    console.log(global_var);
}
```

函数内部可以访问它。

代码就是这样：

```javascript
console.log('函数内打印全局变量:'+global_var);
```

能够正常使用 `global_var`。

***

#### 局部变量

再看：

```javascript
function local_var_function(){
    let local_var ='局部变量';
}
```

`local_var` 定义在函数里面。

所以它属于这个函数的**局部作用域**。

也就是说：

```javascript
function local_var_function(){
    let local_var ='局部变量';

    console.log(local_var); // 可以
}
```

但是函数外：

```javascript
console.log(local_var);
```

就不能正常访问。

你的代码最后就是专门演示这个区别：

```javascript
local_var_function();

console.log('全局打印全局变量:'+global_var);
console.log('全局打印局部变量:'+local_var);
```

其中：

```javascript
global_var
```

可以在函数外使用。

而：

```javascript
local_var
```

不能在函数外使用，因为它是在函数内部定义的。

***

### 把整个文件串起来

这个代码实际上是在逐步学习：

```text
                    JavaScript 函数
                         │
        ┌────────────────┼────────────────┐
        ↓                ↓                ↓
     定义函数          参数             返回值
        │                │                │
 function hello()    name            return
        │                │                │
        ↓                ↓                ↓
     hello()        传入数据          接收结果
                         │
                         ↓
                      作用域
                         │
                ┌────────┴────────┐
                ↓                 ↓
             全局变量          局部变量
```

***

### 你现在最应该记住的语法

#### ① 无参数、无返回值

```javascript
function hello(){
    console.log('Hello');
}

hello();
```

***

#### ② 有返回值

```javascript
function getName(){
    return 'Alice';
}

let name = getName();
console.log(name);
```

***

#### ③ 有参数

```javascript
function hello(name){
    console.log('Hello,' + name);
}

hello('Alice');
```

***

#### ④ 有参数 + 有返回值

这个是非常常见的形式：

```javascript
function add(a,b){
    return a+b;
}

let result = add(10,20);

console.log(result);
```

可以记成：

> **参数负责“传进去”，return 负责“传出来”。**

***

### 和前面学的 JS 控制语句联系起来

前面学了：

```javascript
if
else
for
while
```

这些是**控制程序执行流程**的。

而函数是：

> **把代码组织、封装起来。**

例如：

```javascript
function checkAge(age){

    if(age >= 18){
        return '成年人';
    }else{
        return '未成年人';
    }

}

console.log(checkAge(20));
```

这里就把之前学的：

```text
函数
 +
参数
 +
if...else
 +
return
```

结合起来了。

这也是为什么 **函数是 JavaScript 基础语法中非常重要的一部分**。

***

## JavaScript 事件

简单来说：

> **事件 = 用户对网页进行的某种操作，或者网页发生的某种事情。**

事件

事件是文档或浏览器窗口中发生的特定瞬间，例如用户的点击、键盘的按下、页面的加载等。常见的事件如下：

| 事件          | 描述       |
| ----------- | -------- |
| onClick     | 点击事件     |
| onMouseOver | 鼠标经过     |
| onMouseOut  | 鼠标移出     |
| onChange    | 文本内容改变事件 |
| onSelect    | 文本框选中    |
| onFocus     | 光标聚集     |
| onBlur      | 移开光标     |

JavaScript 可以**监听这些事件，并在事件发生时执行对应的函数**。

***

### 事件绑定

JavaScript 绑定事件的方法有三种：

1. `HTML` 属性

2. `DOM` 属性

3. `addEventListener` 方法

***

来看代码：

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>事件处理</title>
</head>
<body>
    <button onclick="click_event()">这是一个点击事件按钮</button>
    <input type="text" onfocus="focus_event()" onblur="blur_event()">
    <script>
        //点击事件
        function click_event(){
            alert('点击事件触发了');
        }
        //聚焦事件
        function focus_event(){
            console.log('获取焦点');
        }
        //失去焦点事件
        function blur_event(){
            console.log('失去焦点');
        }
    </script>
</body>
</html>
```

这个代码主要有 3 个事件：

| 事件        | 含义   | 代码中的作用       |
| --------- | ---- | ------------ |
| `onclick` | 点击事件 | 点击按钮时执行      |
| `onfocus` | 获取焦点 | 点击输入框准备输入时执行 |
| `onblur`  | 失去焦点 | 离开输入框时执行     |

***

### 点击事件 `onclick`

先看代码：

```html
<button onclick="click_event()">这是一个点击事件按钮</button>
```

这里有两个重要部分：

```html
onclick="click_event()"
```

可以拆开理解：

```text
onclick       → 点击事件
click_event() → 点击后要执行的函数
```

也就是说：

> **当用户点击这个按钮时，就执行&#x20;**`click_event()`**&#x20;函数。**

下面定义了这个函数：

```javascript
function click_event(){
    alert('点击事件触发了');
}
```

### 执行过程

用户点击按钮：

```text
点击按钮
   ↓
触发 onclick
   ↓
执行 click_event()
   ↓
执行 alert()
   ↓
弹出“点击事件触发了”
```

所以：

```javascript
alert('点击事件触发了');
```

就是点击之后真正执行的代码。

***

### `function` 是什么？

这里顺便复习一下函数：

```javascript
function click_event(){
    alert('点击事件触发了');
}
```

基本结构：

```javascript
function 函数名(){
    // 要执行的代码
}
```

所以：

```javascript
function click_event(){
```

表示定义一个叫：

```text
click_event
```

的函数。

而：

```javascript
click_event()
```

表示：

> **调用这个函数。**

例如：

```javascript
function hello(){
    console.log('你好');
}

hello();
```

运行：

```text
你好
```

所以代码中的：

```html
onclick="click_event()"
```

本质上就是：

> 点击按钮 → 调用 `click_event()`。

***

### 聚焦事件 `onfocus`

再看输入框：

```html
<input type="text" onfocus="focus_event()" onblur="blur_event()">
```

这里同时设置了两个事件：

```html
onfocus="focus_event()"
```

和：

```html
onblur="blur_event()"
```

先看 `onfocus`。

代码：

```javascript
function focus_event(){
    console.log('获取焦点');
}
```

### 什么叫“获取焦点”？

例如页面上有一个输入框：

```text
┌────────────────────┐
│                    │
└────────────────────┘
```

当你点击输入框：

```text
┌────────────────────┐
│ |                  │
└────────────────────┘
```

光标进入输入框，这个输入框就**获得了焦点**。

于是：

```html
onfocus="focus_event()"
```

被触发。

然后执行：

```javascript
focus_event()
```

最后：

```javascript
console.log('获取焦点');
```

在浏览器控制台输出：

```text
获取焦点
```

***

### 失去焦点事件 `onblur`

代码：

```javascript
function blur_event(){
    console.log('失去焦点');
}
```

当输入框原本是：

```text
┌────────────────────┐
│ hello|             │
└────────────────────┘
```

此时输入框有焦点。

如果你点击其他地方：

```text
输入框
   ↓
点击页面其他位置
   ↓
输入框失去焦点
   ↓
触发 blur
   ↓
执行 blur_event()
```

于是控制台：

```text
失去焦点
```

***

### focus 和 blur 是一对

这两个事件特别容易理解成一对：

```text
          点击输入框
              ↓
        ┌──────────┐
        │  focus   │
        │ 获取焦点 │
        └──────────┘
              ↓
           输入内容
              ↓
        点击其他地方
              ↓
        ┌──────────┐
        │   blur   │
        │ 失去焦点 │
        └──────────┘
```

所以：

```javascript
onfocus
```

就是：

> **进来**

而：

```javascript
onblur
```

就是：

> **出去**

***

### 三个事件放在一起看

这份代码的核心其实就是下面这张表：

| HTML 事件    | 什么时候触发  | 执行的函数           |
| --------- | ------- | --------------- |
| `onclick` | 点击按钮    | `click_event()` |
| `onfocus` | 输入框获得焦点 | `focus_event()` |
| `onblur`  | 输入框失去焦点 | `blur_event()`  |

对应代码：

```html
<button onclick="click_event()">
    这是一个点击事件按钮
</button>

<input 
    type="text"
    onfocus="focus_event()"
    onblur="blur_event()"
>
```

然后 JavaScript：

```javascript
function click_event(){
    alert('点击事件触发了');
}

function focus_event(){
    console.log('获取焦点');
}

function blur_event(){
    console.log('失去焦点');
}
```

***

### 事件最重要的思维方式

学习 JS 事件时，你可以记住一个公式：

> **发生什么事情 → 触发什么事件 → 执行什么函数**

例如：

#### ① 点击按钮

```text
点击
 ↓
click
 ↓
click_event()
```

#### ② 点击输入框

```text
获得焦点
 ↓
focus
 ↓
focus_event()
```

#### ③ 离开输入框

```text
失去焦点
 ↓
blur
 ↓
blur_event()
```

***

### `alert` 和 `console.log` 有什么区别？

代码里还出现了两个常见的 JS 方法：

#### `alert()`

```javascript
alert('点击事件触发了');
```

会直接弹出浏览器提示框：

```text
┌─────────────────────┐
│ 点击事件触发了       │
│                     │
│        [确定]        │
└─────────────────────┘
```

#### `console.log()`

```javascript
console.log('获取焦点');
```

不会弹窗，而是把内容输出到浏览器的**开发者工具 Console 控制台**。

所以可以简单记：

```text
alert()
  ↓
弹窗

console.log()
  ↓
控制台输出
```

***

### “事件绑定”

代码使用的是一种比较直观的写法：

```html
onclick="click_event()"
```

也就是直接把事件写在 HTML 标签里面。

例如：

```html
<button onclick="click_event()">按钮</button>
```

这种方式叫做**内联事件处理**。

对于刚开始学习 JavaScript 来说非常直观：

```text
HTML
 ↓
发生事件
 ↓
调用 JS 函数
```

后面学习 DOM 之后，还会接触另一种更常见的写法：

```javascript
button.addEventListener('click', function(){
    alert('点击事件');
});
```

这里的：

```javascript
addEventListener()
```

就是专门用来**给元素添加事件监听器**的。

现在可以先把它理解成：

> **“如果这个元素发生某个事件，就执行指定的代码。”**

***

### 最后浓缩成 4 句话

**① 事件是什么？**

> 用户操作或者网页发生的事情。

**②&#x20;**`onclick`**？**

> 点击元素时触发。

**③&#x20;**`onfocus`**&#x20;/&#x20;**`onblur`**？**

> 分别表示获得焦点和失去焦点。

**④ 事件处理的核心？**

```text
事件发生
   ↓
触发事件
   ↓
调用函数
   ↓
执行 JavaScript
```

这份代码就是用 **按钮点击 + 输入框获取焦点 + 输入框失去焦点**，来演示 JavaScript 最基础的事件处理机制。

***

## DOM(JavaScript 事件)

在 Web 开发中，DOM 通常与 JavaScript 一起使用。

当网页被加载时，浏览器会创建页面的文档对象模型，也就是 DOM（Document Object Model）。

每个 HTML 或 XML 文档都可以被视为一个文档树，文档树是整个文档的层次结构表示。

文档节点是整个文档树的根节点。

DOM 为这个文档树提供了一个编程接口，开发者可以使用 JavaScript 来操作这个树状结构。

***

### DOM 对象常用方法

| 方法                  | 描述                |
| ------------------- | ----------------- |
| `appendChild()`     | 把新的子节点添加到指定节点。    |
| `removeChild()`     | 删除子节点。            |
| `replaceChild()`    | 替换子节点。            |
| `insertBefore()`    | 在指定的子节点前面插入新的子节点。 |
| `createAttribute()` | 创建属性节点。           |
| `createElement()`   | 创建元素节点。           |
| `createTextNode()`  | 创建文本节点。           |
| `getAttribute()`    | 返回指定的属性值。         |

***

主要是讲 **JavaScript 如何通过 DOM 获取 HTML 元素、修改元素内容、修改 CSS，以及给元素绑定事件**。

```javascript
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>JavaScript DOM</title>
</head>
<body>
    <div id="box1">这是一个ID选择器标签</div>
    <div class="box2">这是一个类选择器标签</div>
    <div>普通的div标签</div>

    <button>点击按钮</button>

    <script>
        var element_id = document.getElementById('box1');
        console.log(element_id);
        
        var element_class = document.getElementsByClassName('box2')[0];
        console.log(element_class);

        var element_tag = document.getElementsByTagName('div')[2];
        console.log(element_tag);
        
        element_id.innerHTML = '<a href="#">跳转链接</a>';
        element_class.innerText = '<a href="#">跳转链接</a>';

        element_tag.style.color = 'red';
        element_tag.style.fontSize= '20px';

        //DOM属性绑定事件
        var button_element = document.getElementsByTagName('button')[0];
        console.log(button_element);

        // button_element.onclick = function(){
        //     alert('DOM 属性按键触发');
        // }

        button_element.addEventListener('click',click_event);
        function click_event(){
            alert('通过addEventListener 触发按键');
        }
    </script>
</body>
</html>
```

### 什么是 DOM？

**DOM（Document Object Model，文档对象模型）**，可以简单理解成：

> JavaScript 把 HTML 页面变成了一棵“对象树”，然后我们可以通过 JavaScript 找到 HTML 元素，并对它进行修改。

比如代码的 HTML：

```html
<div id="box1">这是一个ID选择器标签</div>
<div class="box2">这是一个类选择器标签</div>
<div>普通的div标签</div>
<button>点击按钮</button>
```

浏览器会把它理解成类似这样的结构：

```text
document
│
├── html
│   ├── head
│   │
│   └── body
│       ├── div#box1
│       ├── div.box2
│       ├── div
│       └── button
```

JavaScript 中的：

```javascript
document
```

就代表当前的 **HTML 文档**。

所以 DOM 操作的基本思路就是：

```text
document
   ↓
找到 HTML 元素
   ↓
修改元素
   ↓
页面发生变化
```

***

### DOM 获取元素

这个代码主要演示了 3 种获取元素的方法。

***

#### 1. `getElementById()`

代码：

```javascript
var element_id = document.getElementById('box1');
console.log(element_id);
```

对应 HTML：

```html
<div id="box1">这是一个ID选择器标签</div>
```

**作用**

通过 HTML 元素的 `id` 获取元素。

格式：

```javascript
document.getElementById('id名称');
```

例如：

```javascript
document.getElementById('box1');
```

就是：

> 找到 `id="box1"` 的 HTML 元素。

因此：

```javascript
var element_id = document.getElementById('box1');
```

可以理解成：

```text
找到 box1
   ↓
把这个元素交给 element_id
```

所以：

```javascript
console.log(element_id);
```

控制台打印出来的就是：

```html
<div id="box1">这是一个ID选择器标签</div>
```

你的代码中这一部分就是演示通过 ID 获取 DOM 元素。

#### 注意

`id` 一般应该是唯一的：

```html
<div id="box1"></div>
```

因此：

```javascript
getElementById()
```

通常直接得到一个元素。

***

#### 通过 class 获取元素

代码：

```javascript
var element_class = document.getElementsByClassName('box2')[0];
console.log(element_class);
```

对应：

```html
<div class="box2">这是一个类选择器标签</div>
```

***

#### `getElementsByClassName()`

作用：

> 根据 `class` 获取元素。

格式：

```javascript
document.getElementsByClassName('类名');
```

例如：

```javascript
document.getElementsByClassName('box2');
```

这里有一个非常重要的地方：

***它返回的是一组元素***

例如：

```html
<div class="box2">第一个</div>
<div class="box2">第二个</div>
<div class="box2">第三个</div>
```

那么：

```javascript
document.getElementsByClassName('box2')
```

得到的不是单独一个元素，而是一组元素：

```text
box2
├── 第一个
├── 第二个
└── 第三个
```

所以我们需要使用下标：

```javascript
[0]
```

表示第一个。

```javascript
document.getElementsByClassName('box2')[0]
```

就是：

> 获取 class 为 `box2` 的第一个元素。

代码正是这么做的。

***

### 通过标签名获取元素

代码：

```javascript
var element_tag = document.getElementsByTagName('div')[2];
console.log(element_tag);
```

作用：

> 根据 HTML 标签名称获取元素。

例如：

```javascript
document.getElementsByTagName('div');
```

意思就是：

> 找到页面中所有的 `div`。

HTML 有三个 `div`：

```html
<div id="box1">这是一个ID选择器标签</div>

<div class="box2">这是一个类选择器标签</div>

<div>普通的div标签</div>
```

它们的下标分别是：

```text
[0] → 第一个 div
[1] → 第二个 div
[2] → 第三个 div
```

所以：

```javascript
document.getElementsByTagName('div')[2]
```

获取的就是：

```html
<div>普通的div标签</div>
```

代码中就是通过这种方式取得第三个 `div`。

***

### 三个 DOM 获取方法总结

可以直接记这个表：

| 方法                         | 根据什么找 | 返回特点 |
| -------------------------- | ----- | ---- |
| `getElementById()`         | id    | 一个元素 |
| `getElementsByClassName()` | class | 一组元素 |
| `getElementsByTagName()`   | 标签名   | 一组元素 |

例如：

```javascript
// 根据 id
document.getElementById('box1');

// 根据 class
document.getElementsByClassName('box2')[0];

// 根据标签
document.getElementsByTagName('div')[2];
```

***

### DOM 修改 HTML 内容

找到元素之后，我们就可以修改它。

代码：

```javascript
element_id.innerHTML = '<a href="#">跳转链接</a>';
```

这里的：

```javascript
innerHTML
```

表示：

> 修改元素里面的 HTML 内容。

原本：

```html
<div id="box1">这是一个ID选择器标签</div>
```

执行：

```javascript
element_id.innerHTML = '<a href="#">跳转链接</a>';
```

之后变成：

```html
<div id="box1">
    <a href="#">跳转链接</a>
</div>
```

也就是说：

```text
原来的文字
↓
被替换
↓
<a>跳转链接</a>
```

代码就是利用 `innerHTML` 把 `box1` 里面的内容替换成了一个 `<a>` 标签。

***

### `innerHTML` 和 `innerText` 的区别

这个是这份代码里**非常重要的知识点**。

代码：

```javascript
element_id.innerHTML = '<a href="#">跳转链接</a>';

element_class.innerText = '<a href="#">跳转链接</a>';
```

看起来很像，但结果完全不同。

***

#### `innerHTML`

```javascript
element_id.innerHTML = '<a href="#">跳转链接</a>';
```

会把字符串当成 **HTML 代码**。

最终页面显示：

> 跳转链接

并且它实际上创建了一个 `<a>` 标签。

***

#### `innerText`

```javascript
element_class.innerText = '<a href="#">跳转链接</a>';
```

会把内容当成 **普通文字**。

页面会直接显示：

```text
<a href="#">跳转链接</a>
```

而不会把它当成超链接。

正好通过这两句代码展示了二者的区别。

可以这样记：

```text
innerHTML
↓
把内容当 HTML

innerText
↓
把内容当文字
```

***

### DOM 修改 CSS

找到 HTML 元素之后，还可以直接修改 CSS。

代码：

```javascript
element_tag.style.color = 'red';
element_tag.style.fontSize = '20px';
```

这里：

```javascript
style
```

表示：

> 修改这个 HTML 元素的 CSS 样式。

***

#### 修改字体颜色

```javascript
element_tag.style.color = 'red';
```

相当于 CSS：

```css
color: red;
```

所以第三个 `div` 的文字会变成红色。

***

#### 修改字体大小

```javascript
element_tag.style.fontSize = '20px';
```

相当于：

```css
font-size: 20px;
```

这里有一个小知识：

CSS：

```css
font-size
```

JavaScript：

```javascript
fontSize
```

因为 JavaScript 属性不能直接这样写：

```javascript
style.font-size
```

所以 CSS 中的：

```text
font-size
```

在 JS 中通常写成：

```text
fontSize
```

这叫做 **驼峰命名法**。

例如：

```css
background-color
```

JS：

```javascript
style.backgroundColor
```

CSS：

```css
margin-top
```

JS：

```javascript
style.marginTop
```

***

### DOM 绑定事件

接下来就是代码中最后一部分，也是 DOM 很重要的用途。

HTML：

```html
<button>点击按钮</button>
```

首先找到按钮：

```javascript
var button_element = document.getElementsByTagName('button')[0];
```

意思：

> 找到页面上的第一个 button。

代码就是这样取得按钮 DOM 元素的。

***

#### 方式一：DOM 属性绑定事件

代码中把这种方法注释掉了：

```javascript
// button_element.onclick = function(){
//     alert('DOM 属性按键触发');
// }
```

它的意思是：

```javascript
button_element.onclick = function(){
    alert('DOM 属性按键触发');
}
```

可以理解成：

```text
点击 button
    ↓
执行 function
    ↓
弹出 alert
```

所以：

```javascript
onclick
```

就是：

> 点击事件。

***

#### 方式二：`addEventListener()`

实际使用的是：

```javascript
button_element.addEventListener('click',click_event);
```

这里是 DOM 事件监听最重要的写法之一。

基本格式：

```javascript
元素.addEventListener('事件类型', 函数);
```

代码：

```javascript
button_element.addEventListener('click', click_event);
```

拆开来看：

```text
button_element
      ↓
监听事件
      ↓
click
      ↓
发生点击
      ↓
执行 click_event
```

然后：

```javascript
function click_event(){
    alert('通过addEventListener 触发按键');
}
```

所以点击按钮之后就会弹出：

```text
通过addEventListener 触发按键
```

***

### 为什么 `addEventListener` 后面不加括号？

这里特别容易搞错。

正确：

```javascript
button_element.addEventListener('click', click_event);
```

错误：

```javascript
button_element.addEventListener('click', click_event());
```

因为我们这里需要的是：

> **把函数交给事件监听器，等点击的时候再执行。**

所以：

```javascript
click_event
```

表示：

> 这个函数。

而：

```javascript
click_event()
```

表示：

> 现在马上执行这个函数。

所以事件监听一般写：

```javascript
addEventListener('click', click_event);
```

***

### 把整个代码串起来

你这份代码实际上是在演示一个非常完整的 DOM 操作流程：

```text
             HTML 页面
                 ↓
              document
                 ↓
        ┌────────┼────────┐
        ↓        ↓        ↓
       ID      class     标签
        ↓        ↓        ↓
 getElement  getElements getElements
  ById       ByClassName ByTagName
        ↓        ↓        ↓
        └────────┼────────┘
                 ↓
              找到元素
                 ↓
       ┌─────────┼──────────┐
       ↓         ↓          ↓
   修改内容    修改样式    添加事件
       ↓         ↓          ↓
 innerHTML     style     addEventListener
 innerText
```

所以可以把 **DOM** 理解成一句话：

> **JavaScript 通过 DOM 找到 HTML 元素，然后对 HTML 元素进行“增、删、改、查”和事件操作。**

而现在这份代码重点学的是：

#### ① 查——获取元素

```javascript
document.getElementById()
document.getElementsByClassName()
document.getElementsByTagName()
```

#### ② 改——修改内容

```javascript
element.innerHTML
element.innerText
```

#### ③ 改——修改 CSS

```javascript
element.style.color
element.style.fontSize
```

#### ④ 事件——监听用户操作

```javascript
element.addEventListener()
```

这几个是 **DOM 入门代码的核心知识点**。
