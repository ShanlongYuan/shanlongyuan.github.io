---
title: "Hugo常用命令"
date: 2025-03-26T22:05:08+08:00
lastmod: 2025-03-26T22:05:08+08:00
author: ["Shanlong Yuan"]

categories:
- 技术

tags:
- Hugo

keywords:
- Hugo命令

description: "" # 文章描述，与搜索优化相关
summary: "" # 文章简单描述，会展示在主页
weight: # 输入1可以顶置文章，用来给文章展示排序，不填就默认按时间排序
slug: ""
draft: false # 是否为草稿
comments: true
showToc: true # 显示目录
TocOpen: true # 自动展开目录
autonumbering: true # 目录自动编号
hidemeta: false # 是否隐藏文章的元信息，如发布日期、作者等
disableShare: true # 底部不显示分享栏
searchHidden: false # 该页面可以被搜索到
showbreadcrumbs: true #顶部显示当前路径
mermaid: true
cover:
    image: ""
    caption: ""
    alt: ""
    relative: false
---

本文记录了使用Hugo框架搭建博客时常用的命令行操作，方便日后查阅。

## 创建新文章

```bash
# 在posts目录下创建新文章
hugo new posts/文章名称.md

# 创建到指定目录
hugo new posts/tech/文章名称.md
```

## 本地预览

```bash
# 启动开发服务器（包含草稿）
hugo server -D

# 不包含草稿
hugo server

# 指定端口启动
hugo server -p 1314
```

## 构建静态文件

```bash
# 构建静态文件（包含草稿）
hugo -D

# 不包含草稿构建
hugo

# 清理public目录后构建
hugo --cleanDestinationDir
```

## 主题管理

```bash
# 更新主题
git submodule update --remote --merge

# 初始化并拉取主题
git submodule update --init --recursive
```

## 常见问题处理

1. 如果本地预览时提示端口被占用，可以使用`-p`参数指定其他端口：
```bash
hugo server -p 1314
```

2. 如果构建后发现内容未更新，可以先清理缓存：
```bash
hugo --cleanDestinationDir
```

3. 本地预览时支持实时重载，修改文件后会自动刷新页面。
