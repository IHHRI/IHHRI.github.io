---
layout: posts
title: C_language_note3
date: 2021-01-11 22:18:54
tags:
---

1. <u>case用法：</u>

   ```
   do {
   		int d = x / mask;
   		switch ( d ) {
   			case 0: printf("ling"); break;
   			case 1: printf("yi"); break;
   			case 2: printf("er"); break;
   			case 3: printf("san"); break;
   			case 4: printf("si"); break;
   			case 5: printf("wu"); break;
   			case 6: printf("liu"); break;
   			case 7: printf("ba"); break;
   			case 8: printf("qi"); break;
   			case 9: printf("jiu"); break;
   		}
   		if ( mask > 9 ) printf(" ");
   ```

   输出与**d**的值相关，与**case**后的值相对应来输出

2. <u>浮点运算的精度</u>

   ```
   f1 == f2 //可能失败
   ```

   ```
   fabs（f1-f2）<le-12	//**le-12**:1x10^-12
   ```

   （注意：1.带小数点的字面是**double**而非**float**，而**float**需要用**f**或**F**后缀表明身份；2.没特别需要，浮点数类型用**double**）

3. <u>变量定义用法需注意</u>

   - 若在后面定义a,**b**为**double**，前面则不能在定义**a**,**b**为**double**，否则会出现错误

   ```
   double a,b;
   
   scanf("%d %d", &a, &b);
   
   printf("%.9lf",(double)a/b);
   ```

   正确为

   ```
   int a,b;
   	
   scanf("%d %d", &a, &b);
   
   printf("%.9lf",(double)a/b);
   ```

   