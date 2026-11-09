# 使用指南

## 日常修改流程

1. 修改 `docs` 目录中的 Markdown 文件。
2. 在本地预览并检查页面及链接。
3. 提交修改并推送到 `main` 分支。
4. 在 Actions 页面查看构建与部署状态。
5. 打开网站检查内容是否更新。

## 常用命令

在仓库根目录、已激活虚拟环境的终端中执行：

```bash
# 安装依赖
python -m pip install -r requirements.txt

# 本地预览，默认地址 http://127.0.0.1:8000/
python -m mkdocs serve

# 构建网站并严格检查警告
python -m mkdocs build --strict

# 预览结束后停止服务：Ctrl + C
```

`--strict` 的作用是把所有警告当成错误处理。本地构建能过，说明推送后云端构建大概率也能过。

## 各文件职责

| 路径 | 是否提交到仓库 | 说明 |
| --- | --- | --- |
| `docs/` | 提交 | 网站源码，四页 Markdown 都在这里 |
| `mkdocs.yml` | 提交 | 站点名称、主题、导航配置 |
| `requirements.txt` | 提交 | 锁定依赖版本范围，云端按它安装 |
| `.github/workflows/deploy.yml` | 提交 | 自动构建与部署的工作流定义 |
| `site/` | 不提交 | `mkdocs build` 生成的产物，已在 `.gitignore` 中忽略 |
| `.venv/` | 不提交 | 本地虚拟环境，同样被忽略 |

## 常见问题

| 现象 | 可能原因 | 处理方式 |
| --- | --- | --- |
| 导航里某一页打不开 | `nav` 里路径写成 `docs/index.md` | `nav` 中路径相对 `docs/`，应写 `index.md` |
| 构建报 YAML 错误 | 用了 Tab 缩进 | YAML 只能用空格缩进，改成两个空格 |
| 推送后工作流没触发 | 只改了 `report/` 或 `README.md` | 工作流只监听文档与配置路径，属正常行为 |
| 网站还是旧内容 | 浏览器缓存 | 强制刷新或无痕窗口访问 |

## 返回

- [回到首页](index.md)
- [API 参考](api.md)
