---
layout: posts
title: prepare_for_posts
date: 2020-12-27 17:58:16
tags:
---

## 本地PART

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
git remote add origin https://github.com/IHHRI.github.io.git
```

10. 拿公钥

```
ssh-keygen -N "" -C 用户名@密钥场景（wsl）
```

```
cat /root/.ssh/id_rsa.pub		//查询公钥
```

![https://github.com/IHHRI/picture/main](https://raw.githubusercontent.com/IHHRI/picture/main/_20210116195749.png)

## GitHub PART

1. 注册GitHub

将钥匙地址放到**GitHub**中的**ssh keys**

![https://github.com/IHHRI/picture/main](https://raw.githubusercontent.com/IHHRI/picture/main/_20210116200658.png)![https://github.com/IHHRI/picture/main](https://raw.githubusercontent.com/IHHRI/picture/main/_20210116201043.png)

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

