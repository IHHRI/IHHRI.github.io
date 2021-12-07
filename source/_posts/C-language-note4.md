---
layout: posts
title: C_language_note4
date: 2021-03-16 09:14:52
tags:
---

# 逃逸字符

<u>用来表达无法印出来的控制字符或特殊字符，它由一个反斜杠“\”开头，后面跟上另个字符，这两个字符合起来，组成了一个字符</u>

**不同的终端对不同的控制字符（尤其是特殊的控制字符）有不同的反应**

```
\b	回退一格
\"	双引号
\t	到下一个表格位 （“Tab”是行当中的固定位置而不是固定大小）
\'	单引号
\n	换行
\\	反斜杠本身
\r	回车
```



# 整数的范围

- char：1字节：-128~127


```
	char c = 128;
	c = c - 1;
	printf("c=%d, i=%d\n", c, i); 
	return 0;
```

若超出**char**范围，结果如下：

```
    c=127, i=255

    --------------------------------
    Process exited after 0.0121 seconds with return value 0
    请按任意键继续. . .

```

![https://github.com/IHHRI/picture//blob/main](https://raw.githubusercontent.com/IHHRI/picture/main/%E5%BE%AE%E4%BF%A1%E6%88%AA%E5%9B%BE_20210319211523.png)

- short：2字节：-32768~32767

- int：取决于编译器（CPU）

- long：4字节

- long long：8字节

**<u>计算机内部是二进制</u>**

# 整数的输入输出（有两种形式：int或long long）

- %d：int
- %u：unsigned
- %ld：long long
- %lu：unsigned long long