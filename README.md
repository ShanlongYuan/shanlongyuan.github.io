# 我的Hugo博客

这是一个使用Hugo和PaperMod主题构建的个人博客。

## 部署说明

本博客使用GitHub Pages进行部署。我已经设置了GitHub Actions工作流来自动构建和部署网站。

### 部署流程

1. 将更改推送到main分支
2. GitHub Actions会自动运行工作流程（在`.github/workflows/hugo.yml`中定义）
3. 工作流程会构建Hugo网站并将其部署到GitHub Pages

### 本地开发

要在本地运行此博客：

```bash
# 安装Hugo（如果尚未安装）
# 克隆仓库后运行
hugo server -D
```

然后在浏览器中访问 http://localhost:1313

## 常见问题解决

### 404错误

如果网站显示404错误，请检查以下几点：

1. 确保GitHub Pages设置正确（在仓库设置中）
2. 确保GitHub Actions工作流成功运行
3. 确保`hugo.yml`中的baseURL设置正确（当前为`https://shanlongyuan.github.io/`）

## 文件结构

- `content/`: 博客内容
- `static/`: 静态资源（图片等）
- `themes/`: 博客主题
- `layouts/`: 自定义布局
- `public/`: 生成的静态网站（不应手动修改）

## 许可证

[MIT](https://opensource.org/licenses/MIT)