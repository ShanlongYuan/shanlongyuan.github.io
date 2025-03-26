---
title: "Hugo PaperMod博客搭建教程"
date: 2025-03-13T21:51:55+08:00
lastmod: 2025-03-13T21:51:55+08:00
author: ["Shanlong Yuan"]

categories:
- 博客搭建
- 技术


tags:
- 博客搭建
- 博客主题

keywords:


description: "" # 文章描述，与搜索优化相关
summary: "" # 文章简单描述，会展示在主页
weight: # 输入1可以顶置文章，用来给文章展示排序，不填就默认按时间排序
slug: ""
draft: true # 是否为草稿
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

<!-- more -->

我来帮您使用 Hugo 搭建一个使用 PaperMod 主题的博客。以下是具体步骤：

1. 首先安装 Hugo（如果尚未安装）。打开 PowerShell 或命令提示符，使用以下命令：

```bash
winget install Hugo.Hugo.Extended
```

2. 创建新的 Hugo 站点：

```bash
hugo new site . --force
```

3. 初始化 Git 仓库并添加 PaperMod 主题：

```bash
git init
```

```bash
git submodule add --depth=1 https://github.com/adityatelange/hugo-PaperMod.git themes/PaperMod
```

4. 如果出现错误需要先清理残留的 Git 配置。以下是针对 Windows PowerShell 的完整修复步骤：

   1. 删除残留的 Git 配置：

   ```bash
   Remove-Item -Force -Recurse .git
   Remove-Item -Force themes/PaperMod -Recurse -ErrorAction SilentlyContinue
   Remove-Item -Force .gitmodules -ErrorAction SilentlyContinue
   ```

   2. 重新初始化 Git 仓库：

   ```bash
   git init
   ```

   3. 添加 PaperMod 主题子模块：

   ```bash
   git submodule add --depth=1 https://github.com/adityatelange/hugo-PaperMod.git themes/PaperMod
   ```

   

4. 创建基础配置文件。我们需要创建一个 `config.yml` 文件：

```yaml:c:\User\Dev\Active\my-blog\config.yml
baseURL: https://www.shanlongyuan.github.io # 绑定的域名
title: Shanlong Yuan
pagination:
  pagerSize: 10    # 首页每页显示的文章数
theme: PaperMod # 主题名称，和themes文件夹下的一致
languageCode: zh-cn # en-us

hasCJKLanguage: true # 自动检测是否包含中文日文韩文,如果文章中使用了很多中文引号的话可以开启
enableInlineShortcodes: true
enableEmoji: true # 允许使用 Emoji 表情，建议 true
enableRobotsTXT: true
buildDrafts: false
buildFuture: false
buildExpired: false
enableEmoji: true
pygmentsUseClasses: true
# googleAnalytics: UA-123-45


minify:
    disableXML: true
    # minifyOutput: true

permalinks:
  post: "/:title/"
  # post: "/:year/:month/:day/:title/"

defaultContentLanguage: zh # 最顶部首先展示的语言页面
defaultContentLanguageInSubdir: true

languages:
    zh:
      languageName: "Chinese"
      # contentDir: content/english
      weight: 1
      profileMode:
        enabled: true
        title: 独立之精神，自由之思想
        subtitle: "👏🏼欢迎光临寒舍</br>👇联系方式"
        imageUrl: "img/favicon.ico"
        imageTitle:
        imageWidth: 150
        imageHeight: 150
        buttons:
          - name: 👨🏻‍💻技术
            url: posts/tech
          - name: 📕阅读
            url: posts/read
          - name: 🏖生活
            url: posts/life

      menu:
        main:
          - identifier: search
            name: 🔍搜索
            url: search
            weight: 1
          - identifier: home
            name: 🏠主页
            url: /
            weight: 2
          - identifier: posts
            name: 📚文章
            url: /posts
            weight: 3
          - identifier: archives
            name: ⏱时间轴
            url: /archives
            weight: 20
          # - identifier: categories
          #   name: 🧩分类
          #   url: categories
          #   weight: 30
          - identifier: tags
            name: 🔖标签
            url: /tags
            weight: 40
          - identifier: about
            name: 🙋🏻‍♂️关于
            url: /about
            weight: 50
          # - identifier: links
          #   name: 🤝友链
          #   url: links
          #   weight: 60

outputs:
    home:
        - HTML
        - RSS
        - JSON

params:
    env: production # to enable google analytics, opengraph, twitter-cards and schema.
    description: "这是一个纯粹的博客......"
    author: Shanlong Yuan
    # author: ["Me", "You"] # multiple authors


    defaultTheme: auto  # defaultTheme: light or  dark
    disableThemeToggle: false
    DateFormat: "2006-01-02"
    ShowShareButtons: true
    ShowReadingTime: true
    # disableSpecialistPost: true
    displayFullLangName: true
    ShowPostNavLinks: true
    ShowBreadCrumbs: true
    ShowCodeCopyButtons: true
    hideFooter: false # 隐藏页脚
    ShowWordCounts: true
    VisitCount: true

    ShowLastMod: true #显示文章更新时间

    ShowToc: true # 显示目录
    TocOpen: true # 自动展开目录

    comments: true

    socialIcons:
        - name: github
          url: "https://github.com/ShanlongYuan"
          icon: "img/github.png"
        - name: bilibili
          url: "https://space.bilibili.com/3546769587701963?spm_id_from=333.1007.0.0"
        - name: email
          url: "mailto:shanlong.yuan@hotmail.com"
        #- name: RSS
       #   url: "index.xml"
        # - name: facebook
        #   url: "https://www.facebook.com/profile.php?id=100027782410997"
        # - name: instagram
        #   url: "img/instagram.png"
        # - name: QQ
        #   url: "img/qq.png"
        # - name: Phone
        #   url: "img/phone.png"


    # editPost:
    #     URL: "https://github.com/adityatelange/hugo-PaperMod/tree/exampleSite/content"
    #     Text: "Suggest Changes" # edit text
    #     appendFilePath: true # to append file path to Edit link

    # label:
    #     text: "Home"
    #     icon: icon.png
    #     iconHeight: 35

    # analytics:
    #     google:
    #         SiteVerificationTag: "XYZabc"

    assets:
        favicon: "img/logo.gif"
        favicon16x16: "img/logo.gif"
        favicon32x32: "img/logo.gif"
        apple_touch_icon: "logo.gif"
        safari_pinned_tab: "logo.gif"

    # cover:
    #     hidden: true # hide everywhere but not in structured data
    #     hiddenInList: true # hide on list pages and home
    #     hiddenInSingle: true # hide on single page

    fuseOpts:
        isCaseSensitive: false
        shouldSort: true
        location: 0
        distance: 1000
        threshold: 1
        minMatchCharLength: 0
        keys: ["title", "permalink", "summary"]

    twikoo:
      version: 1.141.0

taxonomies:
    category: categories
    tag: tags
    series: series

markup:
    goldmark:
        renderer:
            unsafe: true # HUGO 默认转义 Markdown 文件中的 HTML 代码，如需开启的话
    highlight:
        # anchorLineNos: true
        codeFences: true
        guessSyntax: true
        lineNos: true
        # noClasses: false
        # style: monokai
        style: darcula

        # codeFences：代码围栏功能，这个功能一般都要设为 true 的，不然很难看，就是干巴巴的-代码文字，没有颜色。
        # guessSyntax：猜测语法，这个功能建议设置为 true, 如果你没有设置要显示的语言则会自动匹配。
        # hl_Lines：高亮的行号，一般这个不设置，因为每个代码块我们可能希望让高亮的地方不一样。
        # lineNoStart：行号从编号几开始，一般从 1 开始。
        # lineNos：是否显示行号，我比较喜欢显示，所以我设置的为 true.
        # lineNumbersInTable：使用表来格式化行号和代码,而不是 标签。这个属性一般设置为 true.
        # noClasses：使用 class 标签，而不是内嵌的内联样式

privacy:
    vimeo:
        disabled: false
        simple: true

    twitter:
        disabled: false
        enableDNT: true
        simple: true

    instagram:
        disabled: false
        simple: true

    youtube:
        disabled: false
        privacyEnhanced: true

services:
    instagram:
        disableInlineCSS: true
    twitter:
        disableInlineCSS: true


```

5. 创建第一篇文章：

```bash
hugo new posts/my-first-post.md
```

这将在 `content/posts` 目录下创建一个新的 Markdown 文件。

6. 启动 Hugo 开发服务器：

```bash
hugo server -D
```

现在您可以在浏览器中访问 `http://localhost:1313` 查看您的博客了。

