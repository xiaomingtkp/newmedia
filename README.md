# 新媒体图文编辑器

一个面向内容创作者的新媒体创作工作台，聚合了 `公众号编辑器`、`图文生成器`、`封面生成器` 三个核心模块，适合完成公众号排版、小红书图文生成、封面设计等常见内容生产流程。

项目强调“打开即用、所见即所得、主题化输出”的创作体验。你可以在同一套界面中整理飞书内容、完成公众号排版、生成多页图文卡片，并输出统一风格的封面图，减少在多个工具之间反复切换的成本。

整个站点基于原生 HTML / CSS / JavaScript 构建，无需构建工具与服务端依赖，适合作为个人创作工具、团队内部工作台，或直接以静态站点形式长期对外发布。

## 在线访问

- 正式域名：[https://editor.have-idea.com](https://editor.have-idea.com)
- GitHub Pages 备用地址：[https://xiaomingtkp.github.io/newmedia/](https://xiaomingtkp.github.io/newmedia/)

## 功能概览

### 1. 公众号编辑器

- 支持 Markdown 编辑与富文本粘贴
- 支持飞书内容粘贴后保留主要结构与样式
- 支持实时 HTML 预览
- 内置 `22` 套公众号排版主题
- 支持一键复制到公众号、复制到 X、导出 HTML
- 支持本地草稿保存与历史记录

入口：
- [公众号编辑器](https://editor.have-idea.com/views/md.html)

### 2. 图文生成器

- 支持 Markdown 输入
- 支持自动分页与手动分页
- 支持图片引用、批量导出与卡片化预览
- 内置 `13` 套图文样式
- 适合生成小红书风格图文内容

入口：
- [图文生成器](https://editor.have-idea.com/views/note.html)

### 3. 封面生成器

- 支持标题、副标题、日期、页数等元素配置
- 支持上传封面图与裁剪
- 支持快速套用视觉模板
- 内置 `9` 套封面主题
- 支持高清 JPG / PNG 导出

入口：
- [封面生成器](https://editor.have-idea.com/views/cover.html)

## 项目特色

- 纯静态架构：无服务端依赖，打开即可使用
- 多工作台整合：一个站点覆盖排版、图文、封面三类场景
- 本地优先：编辑状态保存在浏览器本地，开箱即用
- 主题化输出：可以快速切换不同内容风格
- 导出友好：兼顾公众号复制、图片导出与 HTML 导出

## 页面结构

```text
newmedia/
├── index.html                 # 首页 / 工作台入口
├── views/
│   ├── md.html                # 公众号编辑器
│   ├── note.html              # 图文生成器
│   └── cover.html             # 封面生成器
├── fonts/                     # 本地字体资源
├── og-cover.svg               # 分享封面
├── robots.txt
├── sitemap.xml
├── site.webmanifest
├── CNAME                      # 自定义域名
├── .github/workflows/
│   └── deploy-pages.yml       # GitHub Pages 自动部署
└── README.md
```

## 本地运行

这是一个纯静态项目，直接打开首页即可：

```bash
open index.html
```

如果你更习惯本地静态服务器，也可以使用任意简单服务，例如：

```bash
python3 -m http.server 8080
```

然后访问：

```text
http://localhost:8080
```

## 技术栈

- 原生 `HTML / CSS / JavaScript`
- `Tailwind CSS`（CDN）
- `Marked.js`
- `Turndown`
- `html-to-image`
- `JSZip`
- `FileSaver.js`
- `Lucide`

## 浏览器支持

- Chrome / Edge
- Safari
- Firefox

推荐使用最新版 Chrome 或 Edge，编辑和导出体验更稳定。

## 隐私与数据说明

- 项目不依赖服务端存储
- 编辑内容、样式配置、历史记录默认保存在浏览器本地 `localStorage`
- 适合个人创作场景，但在共享电脑上使用后建议手动清理本地数据

## 安全说明

- 项目已对粘贴 HTML 和 Markdown 渲染链路增加基础白名单清洗
- 仍建议不要在编辑器中粘贴不可信来源的复杂网页内容
- 如果用于长期公开运营，建议进一步将第三方 CDN 依赖改为固定版本并补充 SRI

## 补充说明

项目在整理与演进过程中，参考了网上部分开源编辑器的代码组织方式与页面样式思路，并结合当前的新媒体创作场景做了适配与扩展。

## License

MIT
