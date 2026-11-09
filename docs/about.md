# 关于本项目

## 项目目标

实现从 Markdown 文档到公开网站的自动化发布。我在本地只负责写内容，构建和部署全部交给 GitHub 的云端机器完成。

## 技术组成

| 工具 | 作用 |
| --- | --- |
| Markdown | 编写文档内容 |
| MkDocs Material | 将文档构建成静态网站 |
| GitHub Actions | 自动执行安装、构建和部署 |
| GitHub Pages | 托管并提供网站访问地址 |

## 一次推送发生了什么

1. 我把改动 `git push` 到 `main` 分支。
2. GitHub 检测到 `docs/`、`mkdocs.yml`、`requirements.txt` 或工作流文件发生变化，触发 `Deploy MkDocs to GitHub Pages` 工作流。
3. `build` 任务在 `ubuntu-latest` 上安装依赖，执行 `mkdocs build --strict`，把生成的 `site/` 目录打包成 artifact 上传。
4. `deploy` 任务拿到 artifact，发布到 `github-pages` 环境，网站地址被写回本次运行记录。

## 我对这套机制的理解

以前做课程作业时，静态页面靠手工拖动文件上传，谁改了哪一版说不清楚。这套流程把“内容”和“网站”分开：`docs/` 是源头，`site/` 是一次性的产物，随时可以重新生成。产物不进版本库，也就不会出现源码和产物互相冲突的情况。

## 返回

- [回到首页](index.md)
- [查看使用指南](guide.md)
