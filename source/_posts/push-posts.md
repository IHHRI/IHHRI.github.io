---
layout: posts
title: push_posts
date: 2020-12-27 17:06:17
tags:
---

# 用Ubuntu推送博文

1. 添加所有文件（若想单一想添加可：git add fileA，git add fileB...）

```
git add .
```

2. 将本地修改过的文件提交到本地库中

```
git commit
```

3. 将最新信息发送给远程库（"git status"查看现在所在的分支）

```
git push origin gh-pages
```

补充：创建新POST  “hexo new posts 博文标题”