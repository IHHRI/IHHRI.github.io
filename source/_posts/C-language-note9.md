---
title: C_language_note9
date: 2021-04-18 11:56:40
tags:
---

## 运算符&

- 获得变量的地址，它的操作数必须是变量

  - ```
    int i; printf("%x", &i);
    ```

- 地址的大小是否与int相同取决于编译器

  - ```
    int i; printf("%p", &i);
    ```

    

- ```
  int main()
  {
  	int a[10];
  	
  	printf("%p\n", &a);
   	printf("%p\n", a);
   	printf("%p\n", &a[0]);
   	printf("%p\n", &a[1]);
   	
  	return 0;
  } 
  ```

  **&a，a，&a[0]**地址一样；每个元素之间相差4个字节

