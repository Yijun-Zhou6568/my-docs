# my-docs

开源软件课程实践项目 2：用 MkDocs Material 搭建四页文档网站，通过 GitHub Actions 自动构建并部署到 GitHub Pages。

## 相关链接

- 网站地址：https://Yijun-Zhou6568.github.io/my-docs/
- 个人实验报告：[report/README.md](report/README.md)

## 仓库结构

```text
my-docs/
├── .github/workflows/deploy.yml         # 自动构建与部署工作流
├── docs/                                # 网站源码（四页 Markdown）
│   ├── index.md
│   ├── about.md
│   ├── guide.md
│   └── api.md
├── report/                              # 开源软件实践项目2 报告与截图
│   ├── README.md
│   └── images/
├── practice-1-pi-agent/                 # 系统分析与设计 实践课1：安装与基础使用
├── practice-2-pi-agent-fork/            # 实践课2：组织建仓与源码分析
├── practice-3-pi-agent-source-build/    # 实践课3：源码安装与编译
├── practice-4-pi-agent-run/             # 实践课4：模型调用与运行流程
├── mkdocs.yml                           # 站点配置
├── requirements.txt                     # 依赖版本范围
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

## 系统分析与设计实践课报告

四次实践课的报告各自独立成目录，均放在仓库根目录，命名统一为 `practice-N-主题`。截图与报告同目录（实践课1 用建目录时的 `evidence/`，其余用 `images/`），报告内引用一律为相对路径，可单独打开阅读。

| 实践课 | 主题 | 报告 |
| --- | --- | --- |
| 实践课1 | Pi Agent 安装与基础使用 | [practice-1-pi-agent/实践报告.md](practice-1-pi-agent/实践报告.md) |
| 实践课2 | 组织建仓与源码分析 | [practice-2-pi-agent-fork/report.md](practice-2-pi-agent-fork/report.md) |
| 实践课3 | Pi Agent 源码安装与编译 | [practice-3-pi-agent-source-build/report.md](practice-3-pi-agent-source-build/report.md) |
| 实践课4 | Pi Agent 模型调用与运行流程 | [practice-4-pi-agent-run/report.md](practice-4-pi-agent-run/report.md) |

> 目录位置自实践课1 起保持不变（`practice-1-pi-agent/`、`practice-2-pi-agent-fork/`），已提交的 Issue 链接继续有效。