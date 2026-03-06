# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## 项目概述

这是一个基于 Hexo 的静态博客，使用 Next 主题，通过 GitHub Actions 自动部署到 GitHub Pages。

## 常用命令

### 开发与构建
```bash
# 创建新文章
hexo new "文章标题"

# 启动本地开发服务器（访问 http://localhost:4000）
npm run server

# 生成静态文件到 public/ 目录
npm run build

# 清除缓存和生成的文件
npm run clean

# 部署（需要先配置 deploy 设置）
npm run deploy
```

### 文章位置
- 所有文章存放在 `source/_posts/` 目录
- 文章使用 Markdown 格式，Front matter 格式参考 `scaffolds/post.md`

## 配置文件结构

### 主配置 (`_config.yml`)
Hexo 主配置文件，包含：
- 站点信息（标题、作者、语言等）
- URL 和永久链接设置
- 目录结构和文章生成设置
- 当前主题设置：`theme: next`

### 主题配置 (`_config.next.yml`)
NexT 主题配置文件，包含：
- 主题方案（Scheme）：Muse、Mist、Pisces、Gemini
- 深色模式设置：`darkmode: true`
- 菜单、侧边栏、社交链接等
- 自定义文件路径配置（在 `source/_data/` 目录）

**重要**：修改主题配置应编辑 `_config.next.yml`，不要直接修改 `node_modules/hexo-theme-next/_config.yml`

## GitHub Actions 自动部署

项目配置了 GitHub Pages 自动部署：
- 配置文件：`.github/workflows/pages.yml`
- 触发条件：推送到 `main` 分支
- 部署流程：
  1. 使用 Node.js 20
  2. 安装依赖（含缓存）
  3. 运行 `npm run build` 生成静态文件
  4. 部署 `public/` 目录到 GitHub Pages

## Hexo 目录结构

```
source/              # 源文件目录
  ├── _posts/        # 博客文章
  ├── _drafts/       # 草稿（如使用）
  └── _data/         # 自定义数据文件（用于主题自定义）

scaffolds/           # 文章模板
  ├── post.md        # 博客文章模板
  ├── page.md        # 页面模板
  └── draft.md       # 草稿模板

themes/              # 主题目录（当前使用 npm 安装的 Next 主题）

public/              # 生成的静态文件（由 hexo generate 生成，不要手动修改）
db.json              # Hexo 缓存数据库
```

## Front Matter 格式

文章默认使用以下 Front Matter（定义在 `scaffolds/post.md`）：
```yaml
---
title: 文章标题
date: 日期
tags:
---
```

## 注意事项

- 文章 URL 格式由 `permalink: :year/:month/:day/:title/` 决定
- 生成的 `public/` 目录和 `db.json` 不应手动修改或提交到 Git
- 主题通过 npm 安装，如需自定义主题，请使用 NexT 的自定义文件功能（`custom_file_path`）
