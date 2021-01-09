---
layout: posts
title: note2
date: 2020-12-27 17:03:04
tags:
---

# 循环：1.do-while；2.while（if）；3.for

**do-while**

先做循环内的句子再判断条件

**while (if)**

**for**<u>对于的意思</u>（ 初始动作【可省略】**；**循环继续条件**；**循环每轮要做的动作【可省略】）

循环控制变量**i**只在循环里被使用，在循环外面没有任何用处，可以把变量**i**的定义写到for语句里面。eg.

```
for ( int=1; int<=n; i++ )//only c99
```

读成：对于一开始的**int=1**，当**int<=n**时，重复做循环体，每轮循环在做完循环体内语句后，使得**i++**。

**总结：**

1. for==while

2. 如有固定次数，用for

3. 如果必须执行一次，用do_while

4. 其他用while

5. 跳出循环：

   1）break（一层一层的跳出）

   ```
   #include <stdio.h>
   
   int main()
   {
   	int x;
   	int one, two, five;
   	int exit = 0;
   	//scanf("%d", &x);
   	x = 2;
   	for ( one = 1; one < x*10; one++ ) {
   		for ( two = 1; two < x*10/2; two++ ) {
   			for ( five = 1; five < x*10/5; five++ ) {
   				if ( one + two*2 + five*5 == x*10 ) {
   					printf("可以用%d个1角加%d个2角加%d个五角得到%d元\n",
   						one, two, five, x);
   					exit = 1;
   					break; 
   				}
   			}
   			if ( exit ==1 ) break;
   		}
   		if ( exit ==1 ) break;
   	}
   	return 0;
   }
   ```

   2）goto <u>out</u> （直接跳出，out可用其他代码代替。tips：**尽量在多重循环跳出到最外层使用**）

   ```
   #include <stdio.h>
   
   int main()
   {
   	int x;
   	int one, two, five;
   	int exit = 0;
   	//scanf("%d", &x);
   	x = 2;
   	for ( one = 1; one < x*10; one++ ) {
   		for ( two = 1; two < x*10/2; two++ ) {
   			for ( five = 1; five < x*10/5; five++ ) {
   				if ( one + two*2 + five*5 == x*10 ) {
   					printf("可以用%d个1角加%d个2角加%d个五角得到%d元\n",
   						one, two, five, x);
   						goto out; 
   				}
   			}
   		}
   	}
   out:
   	return 0;
   }
   ```

   3）continue	(跳过循环这一轮剩下的语句进入下一轮)

## 浮点运算的精度（注意：带小数点的字面是double而非float，而float需要用f或F后缀表明身份）

1. **le-12**:1x10^-12

```
f1 == f2 //可能失败
```

```
fabs（f1-f2）<le-12
```

2. 没特别需要，浮点数类型用**double**