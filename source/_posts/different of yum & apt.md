---
title: different of yum & apt
date: 2021-05-11 09:18:09
tags:
---

## yum（仓库地址，调用的包管理器，软件包的格式，运行的os）

- **命令**

  - 安装

    ```
    yum install package1 //安装指定的安装包package1
    ```

  - 查找

    ```
    yum info package1 //显示安装包信息package1
    ```

    模糊查找

    ```
    yum list|grep package1//查找出含有package1的软件包
    ```

  - 删除软件

    ```
    yum remove package1
    ```

  - 显示软件包依赖关系

    ```
    yum deplist package1
    ```

- **调用的包管理器**

  基于rpm管理机制，能够从指定的服务器自动下载rpm包并安装，可以处理依赖性关系，并且一次安装所有依赖的软件包，无须繁琐地一次次下载、安装。

- **仓库地址（yum配置文件路径：/etc/yum.repos.d/仓库名）**

  ![https://github.com/IHHRI/picture](https://raw.githubusercontent.com/IHHRI/picture/main/image-20210528183712987.png)

- **软件包的格式**

  rpm

- **运行的os**

  运行在基于RPM包管理的的Linux操作系统（例如RedHat、CentOS、Suse等）。

## apt（会咨询软件仓库，是在线安装）

- **命令**

  - 安装

    ```
    apt install package1
    ```

  - 查找

    ```
    apt show package1 //显示安装包信息package1
    ```

    模糊查找

    ```
    apt list |grep package1//查找出含有package1的软件包
    ```

  - 删除

    ```
    apt remove package1
    ```

- **仓库地址**

  ```
  /etc/apt/sources.list
  ```

- **调用的包管理器**

  调用dpkg包管理程序

- **软件包的格式**

  deb

- **运行的os**

  Ubuntu 系统、Debian系统、deepin系统、红旗Linux

