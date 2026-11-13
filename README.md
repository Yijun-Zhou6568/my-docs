# my-docs

开源软件课程实践项目 2：用 MkDocs Material 搭建四页文档网站，通过 GitHub Actions 自动构建并部署到 GitHub Pages。

## 相关链接

- 网站地址：https://Yijun-Zhou6568.github.io/my-docs/
- 个人实验报告：[report/README.md](report/README.md)

## 仓库结构

```text
my-docs/
├── .github/workflows/deploy.yml   # 自动构建与部署工作流
├── docs/                          # 网站源码（四页 Markdown）
│   ├── index.md
│   ├── about.md
│   ├── guide.md
│   └── api.md
├── report/                        # 实验报告与过程截图
│   ├── README.md
│   └── images/
├── mkdocs.yml                     # 站点配置
├── requirements.txt               # 依赖版本范围
└── .gitignore
```

## 本地预览

```bash
python -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install -r requirements.txt
python -m mkdocs serve
```

浏览器打开终端显示的地址，通常为 http://127.0.0.1:8000/my-docs/ ，检查四页导航、表格与代码块，结束后 Ctrl + C 停止。

## 发布方式

修改 `docs/` 下的 Markdown 或相关配置后，推送到 `main` 分支即可。GitHub Actions 会自动执行安装、构建（`mkdocs build --strict`）和部署，无需手动上传网站文件，也不需要 `gh-pages` 分支。

## 自动更新验证

第二次文档推送已验证成功：[运行记录](https://github.com/Yijun-Zhou6568/my-docs/actions/runs/43345042522)。首页的“自动部署验证”一节与提交 e43cfb5 对应。