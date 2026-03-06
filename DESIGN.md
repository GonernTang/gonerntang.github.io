# Chen-qingyu 风格博客配置说明

本文档记录了为博客应用 chen-qingyu.github.io 相同设计风格所做的主要配置更改。

## 主要更改

### 1. 主题 Scheme
- **从**: Muse
- **改为**: Gemini
- Gemini scheme 提供了更现代的双栏布局，与 chen-qingyu 的设计一致

### 2. 深色模式
- **从**: `darkmode: true`（自动深色模式）
- **改为**: `darkmode: false`（手动控制深色模式）

### 3. 导航菜单
启用了以下菜单项：
- 首页 (`/`)
- 关于 (`/about/`)
- 分类 (`/categories/`)
- 归档 (`/archives/`)

### 4. 侧边栏
- 启用头像显示
- 社交链接仅显示图标（`icons_only: true`）
- 配置了 GitHub、Email 和 RSS 订阅链接

### 5. 目录（TOC）
- 关闭自动编号
- 启用展开所有目录项

### 6. 页脚
- 设置起始年份为 2025
- 启用心形图标动画
- 关闭 "Powered by Hexo & NexT"

### 7. 代码块
- 启用复制按钮
- 启用代码折叠（高度 500px）
- 主题：浅色 default，深色 stackoverflow-dark

### 8. 返回顶部
- 启用滚动百分比显示

### 9. 数学公式
- 所有页面启用 MathJax
- 支持数学公式渲染

### 10. 外部库
- **FancyBox**: 启用图片放大功能
- **Pjax**: 启用快速页面导航
- **Pangu**: 启用中英文自动空格
- **Canvas Ribbon**: 启用彩带动画效果

### 11. 统计功能
- 启用不蒜子统计
- 显示总访问量和总访客数

### 12. 本地搜索
- 启用本地搜索
- 自动触发搜索
- 预加载搜索数据

### 13. 创作共用许可
- 启用 CC BY-NC-SA 4.0 许可
- 侧边栏显示小型许可图标

## 已安装的依赖

```bash
npm install hexo-generator-searchdb hexo-filter-mathjax hexo-pangu --save
```

### 依赖说明
- **hexo-generator-searchdb**: 生成本地搜索数据库
- **hexo-filter-mathjax**: 渲染数学公式
- **hexo-pangu**: 自动在中英文之间添加空格

## 待完成的任务

### 1. 添加图片文件
在 `source/images/` 目录中添加以下文件：
- `avatar.gif` - 头像图片
- `favicon-16x16.png` - 16x16 图标
- `favicon-32x32.png` - 32x32 图标
- `apple-touch-icon.png` - Apple 触摸图标
- `safari-pinned-tab.svg` - Safari 固定标签图标

详细说明请参考 `source/images/README.md`

### 2. 自定义社交链接
在 `_config.next.yml` 中修改 `social` 部分：
```yaml
social:
  GitHub: https://github.com/gonernTang || fab fa-github
  E-Mail: mailto:yourname@gmail.com || fa fa-envelope
  订阅: /atom.xml || fa fa-rss
```

### 3. 创建"闪念"页面（可选）
chen-qingyu 有一个"闪念"页面，如果你想添加类似功能：
```bash
hexo new page idea
```

然后在菜单中添加：
```yaml
menu:
  闪念: /idea/ || fa fa-lightbulb
```

### 4. 配置评论系统（可选）
当前未启用评论系统，如需启用请配置以下任一系统：
- Gitalk
- Utterances
- Disqus

## 测试博客

运行以下命令启动本地服务器：
```bash
npm run server
```

访问 http://localhost:4000 查看效果。

## 构建和部署

```bash
# 生成静态文件
npm run build

# 部署到 GitHub Pages
npm run deploy
```

## 参考资源

- [NexT 主题文档](https://theme-next.js.org/)
- [Hexo 文档](https://hexo.io/zh-cn/docs/)
- [Chen-qingyu 的博客](https://chen-qingyu.github.io)
