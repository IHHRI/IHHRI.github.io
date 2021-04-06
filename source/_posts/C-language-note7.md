---
layout: posts
title: C_language_note7
date: 2021-04-06 16:28:50
tags:
---

## 调用函数

### 类型不匹配：

1. 调用函数时给的值与参数的类型不匹配是C语言传统上最大的漏洞

2. 编译器总是悄悄替你把类型转换好，但是这很可能不是你所期望的

   

   ![https://github.com/IHHRI/picture](https://raw.githubusercontent.com/IHHRI/picture/main/%E5%BE%AE%E4%BF%A1%E6%88%AA%E5%9B%BE_20210406164256.png)

### 逗号运算符 OR 标点符号

- **f(a,b)** 圆括号里的逗号是标点符号
- **f((a,b))** 此时圆括号里的逗号是运算符

