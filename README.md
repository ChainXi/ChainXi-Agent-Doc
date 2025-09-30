# ChainXi-Admin-Doc  [![visitors](https://visitor-badge.laobi.icu/badge?page_id=ChainXi/ChainXi-Admin-Doc)](https://chainxi.github.io/ChainXi-Admin-Doc/) [![Preview](https://img.shields.io/badge/Preview-在线预览-blue.svg)](https://chainxi.github.io/ChainXi-Admin-Doc/) [![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](#-license)

> 基于 VitePress 的文档站点，包含多语言、Algolia 搜索、Mermaid、评论系统(Giscus)、阅读数据统计、不蒜子 UV/PV、页面动效与丰富的自定义主题示例。

## ✨ 特性

- 🚀 基于 VitePress 1.x 与 Vue 3
- 🌓 深色模式 & 自定义主题样式
- 🔍 Algolia DocSearch 集成
- 💬 Giscus 评论系统
- 📊 不蒜子站点访问统计 (带加载动画)
- 🖼 图片中/大图放大 (medium-zoom)
- 📝 任务清单 / 自定义代码组图标
- 🧮 文章字数 / 阅读时长统计组件
- 🗺 永久链接（permalink）与多语言支持
- 🎉 五彩纸屑、鼠标特效、流体边框等动效示例
- 📈 Mermaid 流程图 / UML 支持

## 📦 目录结构 (简化)

```text
├─ docs/
│  ├─ .vitepress/
│  │  ├─ config.mts          # 站点配置
│  │  ├─ constants.ts        # 公共常量(如 BASE_PATH)
│  │  ├─ theme/              # 自定义主题与组件
│  │  │  ├─ components/      # 自定义组件
│  │  │  └─ index.ts         # 主题入口扩展
│  ├─ index.md               # 首页
│  ├─ preface.md             # 前言示例
│  └─ ... 其它文档
├─ public/                   # 站点静态资源
├─ docsearch.json            # Algolia DocSearch 爬虫配置
├─ package.json
└─ README.md
```

## 🚀 本地开发

```bash
# 安装依赖（推荐使用 pnpm / npm 均可）
npm install

# 启动开发服务器
npm run docs:dev

# 构建静态文件
npm run docs:build

# 本地预览构建产物
npm run docs:preview
```

## 🔧 技术栈

- VitePress
- Vue 3
- Mermaid
- Giscus
- Algolia DocSearch
- medium-zoom
- nprogress-v2
- busuanzi.pure.js

## 🛠 常量维护

公共路径等常量放在 `docs/.vitepress/constants.ts`，避免多处硬编码。

## 🗂 搜索配置

DocSearch 爬虫使用根目录 `docsearch.json`，若部署域名 / 基础路径变更，请同步更新：

- start_urls.url
- VitePress `base` (`config.mts`)

## 🤝 贡献

欢迎提交 Issue / PR 改进文档与功能示例。

## 📄 License

MIT License © 2023-2025 ChainXi

> 如果这个项目对你有帮助，欢迎 Star ⭐ 支持！
