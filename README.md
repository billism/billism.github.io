# Achso!

基于 [Hugo](https://gohugo.io/) 的极简静态站点，源码即本仓库。

## 本地预览

```bash
hugo server   # http://localhost:1313
```

## 写文章

```bash
hugo new content posts/my-post/index.md
```

- 文章是 page bundle：`posts/<slug>/index.md` + 同目录图片，图片用普通 Markdown 语法 `![alt](src)` 引用
- frontmatter 字段：

| 字段 | 说明 |
|---|---|
| `draft` | `true` 时不会在站点上公开 |
| `toc` | `true` 显示可折叠的目录 |
| `math` | `true` 加载 MathJax<br>行内公式 `\(...)`，块级公式 `$$…$$` 或 `\[…\]` |
| `description` | 文章摘要， 会写入`<meta name="description">` |

## 记读书目录

```bash
hugo new content reading/<书名-slug>.md
```

- 每本书一个小文件，`date` 填当天即可（页面只显示年-月），`pages` 选填（页数）
- archetype 自动带上 `[build] render = 'never'`：书目只出现在 Reading 列表里，不生成独立页面
- Reading 页按年分组，复用与 Posts 相同的列表样式

## 排版约定

- 导航、日期、页脚、代码等是等宽字体
- 正文是系统无衬线
- 亮/暗主题跟随系统，右上角按钮可手动切换并记忆（localStorage）
- 首页简介写在 `content/_index.md` 正文里，留空文件则不显示，支持 Markdown
- 诗歌居中用 shortcode：

```
{{< poem title="静夜思" author="唐 · 李白" >}}
床前明月光，
疑是地上霜。
{{< /poem >}}
```

- 带图注的图用 `{{< figure src="…" alt="…" caption="…" >}}`

## 部署

推送到 GitHub 后，在仓库 **Settings → Pages → Source** 选 **GitHub Actions**，`.github/workflows/hugo.yml` 会自动构建并发布；`baseURL` 由 Pages 配置自动派生，无需改代码。

## 目录结构

```
├── archetypes/    # 新文章模板（hugo new 生成 frontmatter）
├── assets/css/    # 全部样式 (包含 github/github-dark 两套代码高亮配色)
├── content/       # 文章（Markdown + 图片 page bundle）
├── layouts/       # 极简主题（模板、渲染钩子、shortcode）
└── static/        # 静态文件（比如 favicon）
```

---

© Ye · *So long, and thanks for all the fish.*
