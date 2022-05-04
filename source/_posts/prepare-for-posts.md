---
layout: posts
title: prepare_for_posts
date: 2020-12-27 17:58:16
tags:
---

## 本地 PART

1. 装**npm，nodejs**

```
curl -sL https://deb.nodesource.com/setup_10.x -o nodesource_setup.sh
sudo bash nodesource_setup.sh
sudo apt install nodejs
```

```
npm -v	//查看nmp版本
nodejs -v	//查看nodejs版本
```

2. 装**gcc，g++ make**

```
sudo apt-get install gcc g++ make
```

3. 设**npm，proxy**代理，方便安装博客框架

```
npm config set proxy http://127.0.0.1:1081
npm config set https-proxy http://127.0.0.1:1081
```

```
npm config list		//查看npm的配置文件
```

4. 设**git**代理

```
git config --global http.proxy http://127.0.0.1:1081
git config --global https.proxy http://127.0.0.1:1081
```

5. 用**npm**这个**nodejs**的包管理器，安装博客框架**hexo**

```
npm install hexo --save -g
```

6. 在D盘新建个code并在路面新建仓库目录

```
mkdir -p /mnt/d/code/IHHRI.github.io
```

7. 用**hexo**初始化这个目录框架内容

```
cd /mnt/d/code/IHHRI.github.io
hexo init
```

8. **git init**把当前目录准备成一个代码仓库

```
git init
```

9. 切换并新建一个**gh-pages**分支（用作储存代码）

```
git checkout -b gh-pages
```

```
git remote -v	//检查当前目录关联的仓库地址
git remote add origin https://github.com/IHHRI/IHHRI.github.io.git
```

10. 新建文件并保存密码

    ```
    touch ~/.git-credentials
    vim ~/.git-credentials
    ```

11. 添加内容

    ```
    https://{username}:{passwd}@github.com
    ```

​	![https://github.com/IHHRI/picture](https://github.com/IHHRI/picture/blob/main/%E5%BE%AE%E4%BF%A1%E6%88%AA%E5%9B%BE_20220424232901.png?raw=true)

![https://github.com/IHHRI/picture](https://github.com/IHHRI/picture/blob/main/%E5%BE%AE%E4%BF%A1%E6%88%AA%E5%9B%BE_20220424232933.png?raw=true)

12.添加git配置

```
git config --global credential.helper store
```

13.查看～/.gitconfig文件变化

```
cat ～/.gitconfig
```

14.然后在尝试一下git push不再在需要密码了

## GitHub PART

1. 注册GitHub

将钥匙地址放到**GitHub**中的**ssh keys**

![https://github.com/IHHRI/picture/main](https://raw.githubusercontent.com/IHHRI/picture/main/_20210116200658_LI.jpg)![https://github.com/IHHRI/picture/main](https://raw.githubusercontent.com/IHHRI/picture/main/_20210116201043_LI.jpg)

2. 将**gh-pages**设为本地上游

```
git push --set-upsream origin gh-pages
```

3. 新建个**travis**来自动编译博客代码

```
touch .travis.yml
```

4. 用**nano**编辑它

```
nano .travis.yml
```

再填入![https://github.com/IHHRI/picture/main](https://raw.githubusercontent.com/IHHRI/picture/main/_20210116214107.png)

创建travis账号，用github账号登录

## 用Ubuntu推送博文

1. 进入IHHRI.github.io

   ```
   cd /mnt/d/code/IHHRI.github.io 
   ```

2. 添加所有文件（若想单一想添加可：git add fileA，git add fileB...）

   ```
   git add .
   ```

3. 将本地修改过的文件提交到本地库中

   ```
   git commit -m “名字”
   ```

4. 将最新信息发送给远程库（"git status"查看现在所在的分支）

   ```
   git push origin gh-pages
   ```

补充：创建新POST  “hexo new posts 博文标题”

