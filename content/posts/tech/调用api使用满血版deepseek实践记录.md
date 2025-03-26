---
title: "调用api使用满血版deepseek实践记录"
date: 2025-02-17T13:06:41+08:00
lastmod: 2025-02-17T13:06:41+08:00
author: ["Shanlong Yuan"]

categories:
- 技术

tags:
- AI


keywords:
- deepseek

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

本文仅针对 **Windows 11** 系统进行说明，其他设备的用户请参考原教程。目标是帮助用户在 **Windows 11** 上调用 **阿里云百炼大模型**，并通过 Cherry Studio 设置和使用满血版 DeepSeek。

原教程由小黑盒用户“这不是dd”提供，详细文章地址：[调用 API 使用满血版 DeepSeek](https://api.xiaoheihe.cn/v3/bbs/app/api/web/share?link_id=8fd36fd7f34b)。

------

## 一. 软件准备

### Cherry Studio

Cherry Studio 是一款开源软件，可以从 GitHub 下载：

- **下载链接**：[Cherry Studio GitHub](https://github.com/CherryHQ/cherry-studio)
- **安装版本**：下载 **Cherry-Studio-0.9.24-setup.exe** 安装版本
- **便携版**：下载 **Cherry-Studio-0.9.24-portable.exe**（无需安装）

安装完成后进入下一步。

------

## 二. API 调用

### DeepSeek

- 目前，DeepSeek 停止充值，因此暂时不考虑使用。
- 25年3月，在DeepSeek开放平台已开通充值，方法同下，官网：https://platform.deepseek.com/usage

### 硅基流动

- 目前也不考虑使用此服务。

### 阿里云百炼大模型

阿里云百炼大模型提供 180 天免费试用（100 万 Token），具体信息如下：

- **上下文长度**：65,792

- **最大输入**：57,344

- **最大输出**：32,768

- 每千 Token 成本

  - 输入：0.002 元（原价 0.004 元）
  - 输出：0.008 元（原价 0.016 元）

#### 活动信息

- **优惠活动**：DeepSeek-R1（671B）与 DeepSeek-V3 模型享五折优惠
- **活动时间**：**2025年02月12日18:00:00 ~ 2025年02月23日23:59:59**
- 活动结束后恢复原价。
- 免费额度用完会自动扣费，账单周期为 1 小时。

#### 开通阿里云百炼模型服务

1. **注册与认证**：完成阿里云注册、实名认证和账号安全设置。

2. 进入管理控制台

   - 访问链接：[阿里云百炼大模型服务平台](https://www.aliyun.com/product/bailian)
   - 点击 **管理控制台**，选择 **模型广场** > **DeepSeek-R1**，点击 **查看详细**。

3. 开通服务

   - 点击 **立即试用** 开通模型服务。
   - 点击 **查看我的 API-KEY**，复制 API 密钥。

4. 配置 Cherry Studio

   - 返回 **Cherry Studio** 页面，点击 **设置** > **模型服务** > **阿里云百炼**。
   - 在 **API 密钥** 方框中输入复制的 API 密钥，点击 **添加**。
   - 在 **模型 ID** 输入框中填写 `deepseek-r1`，点击 **添加模型**。
   - 启动阿里云百炼服务并测试 DeepSeek 是否正常运行。

------

## 三. 手机端调用 API

### 下载 ChatBox 软件

- **下载链接**：[Chatbox AI 官网](https://chatboxai.app/zh)

### 配置 API 设置

1. 打开 ChatBox 软件，选择添加 **自定义提供方**。
2. **设置提供方信息**：
   - **名称**：阿里云-DeepSeek-R1
   - **API 域名**：https://dashscope.aliyuncs.com/compatible-mode/v1
   - **API 路径**：/chat/completions
   - **API 密钥**：与上文相同
   - **模型**：deepseek-r1
3. 完成设置后保存，配置完成。
