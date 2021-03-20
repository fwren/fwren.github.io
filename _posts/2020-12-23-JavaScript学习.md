---
layout: post #使用的布局（不需要改）
title: JavaScript 学习 # 标题
subtitle: 不定期更新 #副标题
date: 2020-12-23 # 时间
author: fwren # 作者
header-img: #这篇文章的背景图片
catalog: true #是否归档
tags: #标签
  - JavaScript
---

# **1. JavaScript 准备条件**

## **1.1 开发工具**

### **1.1.1 浏览器**

- Chrome 浏览器和 Firefox 浏览器

### **1.1.2 编辑器**

- WebStorm
- VS Code
- HBuilder
- 等等

## **1.2 要求**

- **HTML 和 CSS 相关知识**

# **2. JavaScript 介绍**

## **2.1 JavaScript**

JavaScript 是一种轻量级的脚本语言，同时也是一种**嵌入式**，**对象模型**的语言，简称**JS**。

核心语法部分很精简

> - 基础语法部分
> - 标准库

实现其他复杂功能需要依靠**宿主环境**（运行环境）提供 API，目前 JavaScript 常见的宿主环境有浏览器，和服务器环境（操作系统）。

## **2.2 JavaScript 应用场景**

- 网页特效\*
- 服务端开发（Node.js）\*
- 桌面应用程序（Electron）
- APP
- 游戏开发

## **2.3 JavaScript组成部分**

- ECMAScript

  ECMAScript 是由 ECMA 国际（原欧洲计算机制造商协会）进行标准化的一门编程语言   
  ECMAScript 是一套标准，规定了基本语法、数据类型、关键字、具体 API 的设计规范等，与具体实现无关

- DOM（文档对象模型）

  **文档对象模型**（Document Object Model，简称 DOM），是 W3C 组织推荐的处理可拓展标记语言的**标准编程接口**。通过 DOM 提供的接口可对页面上的各种元素进行操作（大小、位置、颜色等）

- BOM（浏览器对象模型）

  **BOM**（Browser Object Model，简称 BOM）是指浏览器对象模型，它提供了独立于内容的、可以与浏览器窗口进行互动的对象结构。通过 BOM 可以操作浏览器窗口，比如弹出框、控制浏览器跳转、获取分辨率等

## **2.4 JavaScript 与 HTML、CSS**

> - HTML：提供网页的结构和内容
> - CSS：样式排版、美化页面
> - JavaScript：控制网页内容，给页面添加动态效果

## **2.5 浏览器执行JavaScript**

浏览器分为两个部分：渲染引擎和JS引擎

- **渲染引擎**：用来解析 HTML和CSS，俗称内核，比如chrome浏览器的blink，老版本的webkit
- **JS引擎**：也成为JS解释器。用来读取网页中的JavaScript代码，对其处理后运行，比如chrome浏览器的V8

> 浏览器本身并不会执行 JS 代码，而是通过内置的 JavaScript 引擎（解释器）来执行 JS 代码，JS 引擎执行代码时逐行解释每一句源码（转换为机器语言），然后由计算机去执行，所以 JavaScript 语言归为脚本语言，会逐行解释执行

# **3. JavaScript语法基础**

## **3.1 书写简单的 JavaScript 代码**

- **（1）书写在 HTML 文件行内**

```html
<input type="button" value="按钮" onclick="alert(123)" />
```

- **（2）书写在`<script>`标签中**

```html
<script>
  alert(456);
</script>
```

- **（3）引用外部 JS 文件**

```html
<script src="/JS/demo.js"></script>
```

> 注意：使用`<script>`标签引用外部 js 文件时，将不会执行写在`<script>`标签内部的 js 代码

## **3.2 变量**

### **3.2.1 变量是什么**

- 什么是变量

  变量是计算机内存中存储数据的标识符，根据变量名称可以获取到内存中存储的数据。

- 为什么使用变量

  使用变量可以方便获取或修改内存中数据

### **3.2.2 如何使用变量**

  > 声明一个变量并且给它赋值，称为变量的初始化

- **声明变量**

  ```javascript
  //单个变量声明
  var a;
  let c;

  //多个变量声明
  var a, b;
  let c, d;
  ```
  > **声明方式 var 、let 、const 的区别**

  > | 声明方式 | 变量提升 | 暂时性死区 | 重复声明 | 初始值 |  作用域  |
  > | :-----: | :------: | :-------: | :-----: | :----: | :----: |
  > |   var   |   允许   |   不存在   |   允许  |  不需要 | 除块级 |
  > |   let   |  不允许  |    存在    |  不允许 |  不需要 |  块级  |
  > |  const  |  不允许  |    存在    |  不允许 |   需要  |  块级  |

- **为变量赋值**

  ```javascript
  var a;
  a = 10;
  ```

  ```javascript
  //声明单个变量并赋值
  var a = 10;

  //声明多个变量并赋值
  var b = 10, c = 5, d = 20;
  ```

- **变量命名规则**

  - 变量的名字必须是**数字**、**字母**、**下划线 _** 、和$组成
  - 变量名字不能以数字开头
  - 变量的名字不能是关键字
  - 变量名字要有意义，如
    ```javascript
    var name = "李华";
    var age = 18;
    ```
  - 变量命名区分大小写，如 `name` 和 `Name` 是两个变量
  - 变量命名尽量采用**驼峰法**，例如 `userName`

- **更新变量**

  一个变量被重新赋值后，它原有的值就会被覆盖，变量值将以最后一次赋的值为准。
  
- **同时声明多个变量**

```javascript
  var name = 'lihua', age = 18, sex = '男'
```

## **3.3 注释**

- 单行注释
  ```javascript
  // 这是单行注释
  ```

- 多行注释
  ```javascript
  /*
  这是多行
  注释
  */
  ```

## **3.4 JavaScript 输入输出语句**

为了方便信息的输入输出，JS 中提供了一些输入输出语句，其常用的语句格式如下：

|  方法  |  说明  |  归属  |
| :----: | :----: | :----: |
| alert(message) | 浏览器弹出警示框 | 浏览器 |  
| console.log(message) | 浏览器控制台打印输出信息 | 浏览器 |
| prompt(message) | 浏览器弹出输入框，用户可以输入 | 浏览器 |

## **3.5数据类型**

### 3.5.1 typeof操作符

对一个值使用typeof操作符会返回下列字符串之一

> - underfined：表示值未定义
> - boolean：表示值为布尔值
> - string：表示值为字符串
> - number：表示值为数值
> - object：表示值为对象（而不是函数）或null
> - function：表示值为函数
> - symbol：表示值为符号