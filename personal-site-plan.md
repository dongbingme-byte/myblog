# 🌿 个人网站规划方案

## 项目概述

一个极简而温暖的个人空间，承载日常、随笔、照片与画作。

---

## 📁 项目结构（GitHub 仓库）

```
my-personal-site/
├── README.md
├── index.html              # 首页
├── assets/
│   ├── css/
│   │   └── style.css
│   ├── js/
│   │   └── main.js
│   └── fonts/
├── pages/
│   ├── daily.html          # 日常动态
│   ├── essays.html         # 随笔文章
│   ├── photos.html         # 摄影集
│   └── art.html            # 画画作品
├── posts/                  # 内容文件夹（Markdown）
│   ├── daily/
│   ├── essays/
│   ├── photos/
│   └── art/
└── .github/
    └── workflows/
        └── deploy.yml      # 自动部署到 GitHub Pages
```

---

## 🗂 四大内容板块

| 板块 | 内容 | 展示形式 |
|------|------|---------|
| **日常** | 生活碎片、心情随记 | 时间线 / 卡片流 |
| **随笔** | 长文、思考、读书笔记 | 文章列表 + 阅读页 |
| **照片** | 摄影作品、生活记录 | 瀑布流相册 |
| **画作** | 手绘、插画、数字艺术 | 画廊网格 + 大图预览 |

---

## 🛠 技术选型

### 方案A：纯静态（最简单）
- **HTML + CSS + JS**：零依赖，直接托管 GitHub Pages
- 内容用 Markdown 写，JS 动态渲染
- 适合：技术基础一般，想快速上线

### 方案B：静态站点生成器（推荐）
- **Hugo** 或 **Astro**：自动将 Markdown 转成网页
- 主题丰富，性能极佳
- 适合：想长期维护，内容越来越多

### 方案C：现代框架
- **Next.js**：React 框架，支持 SSG
- 可扩展性强，适合将来加评论、搜索等功能
- 适合：有前端开发经验

---

## 🚀 GitHub Pages 部署流程

```yaml
# .github/workflows/deploy.yml
name: Deploy to GitHub Pages

on:
  push:
    branches: [ main ]

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - name: Deploy
        uses: peaceiris/actions-gh-pages@v3
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
          publish_dir: ./public
```

**步骤：**
1. 在 GitHub 新建仓库（如 `username.github.io` 或 `my-site`）
2. 推送代码到 `main` 分支
3. 在仓库 Settings → Pages → 选择 `gh-pages` 分支
4. 网站将在 `https://username.github.io` 上线

---

## ✨ 功能规划（分阶段）

### 第一阶段（MVP，1-2周）
- [x] 首页展示四大板块入口
- [x] 各板块内容列表页
- [x] 单篇内容详情页
- [x] 响应式移动端适配
- [x] GitHub Pages 自动部署

### 第二阶段（增强，1个月）
- [ ] 标签/分类系统
- [ ] 搜索功能
- [ ] 图片懒加载 + 灯箱效果
- [ ] 暗色模式切换
- [ ] RSS 订阅

### 第三阶段（精致化）
- [ ] 评论系统（utterances，基于 GitHub Issues）
- [ ] 阅读进度条
- [ ] 文章目录导航
- [ ] 站点统计（访客数）

---

## 📝 内容管理建议

- 写 **Markdown** 文件放入对应 `posts/` 文件夹
- 图片压缩后放入 `assets/images/`，或使用图床（如 Cloudinary）
- 每次更新推送到 GitHub，网站自动更新

---

## 🎨 设计建议

- **字体**：中文用「霞鹜文楷」或「LXGW Bright」，英文搭配 Playfair Display
- **配色**：温暖的米白底色 + 深墨绿/赭石点缀
- **风格**：类杂志排版，大量留白，有质感

---

*这是你的数字花园 🌱，慢慢种，慢慢长。*
