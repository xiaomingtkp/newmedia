# 新媒体图文编辑器

一个面向内容创作者的新媒体创作工作台，集成 `公众号编辑器`、`图文生成器`、`封面生成器` 三个核心模块。适合完成公众号排版、小红书图文拆页、封面设计、内容预览与发布前整理等常见工作。

项目强调“打开即用、所见即所得、主题化输出”。你可以把 Markdown、飞书富文本或普通文章内容放进编辑器，快速套用适合公众号和新媒体平台的排版样式，再复制、导出或生成图片。

整站基于原生 HTML / CSS / JavaScript 构建，不依赖服务端，适合作为个人创作工具、团队内部工作台，或静态网站长期公开访问。

## 在线访问

- 正式域名：[https://editor.have-idea.com](https://editor.have-idea.com)
- GitHub Pages 备用地址：[https://xiaomingtkp.github.io/newmedia/](https://xiaomingtkp.github.io/newmedia/)

## 功能模块

### 公众号编辑器

面向公众号排版和富文本发布，核心目标是把编辑内容转换成更适合微信公众号后台粘贴的 HTML 样式。

- 支持 Markdown 内容编辑、实时预览与 HTML 源码微调
- 支持飞书等富文本内容粘贴，保留主要结构、表格和格式
- 支持 GFM 表格、任务列表、提示块、代码块和图片滑动组
- 内置 `32` 套公众号主题，其中包含多套 WeMD 风格主题
- 右侧主题会影响中间预览和复制到公众号的实际样式
- 支持一键复制到公众号、复制到 X Articles、导出 HTML / Markdown / Word / PDF
- 支持本地历史记录、图片压缩、图片库和图片引用

入口：[公众号编辑器](https://editor.have-idea.com/views/md.html)

### 图文生成器

面向小红书、图文笔记和内容卡片拆页，核心目标是把长文拆成多张统一风格的图片。

- 支持 Markdown 输入和富文本转 Markdown 清洗
- 支持自动分页、手动分页和卡片化预览
- 支持表格转 Markdown，尽量保留飞书文档结构
- 支持图片粘贴、图片引用和图片库管理
- 内置 `13` 套图文样式
- 支持单张导出与批量 JPG 导出

入口：[图文生成器](https://editor.have-idea.com/views/note.html)

### 封面生成器

面向封面图、头图和标题图制作，核心目标是快速生成统一视觉风格的封面。

- 支持标题、副标题、日期、作者/标签等元素配置
- 支持封面图上传、裁剪、显示开关和布局调整
- 支持主题配色、字体、字号、间距和对齐设置
- 内置 `9` 套封面主题
- 支持快捷键、清空配置和高清 JPG / PNG 导出

入口：[封面生成器](https://editor.have-idea.com/views/cover.html)

## 项目特色

| 特性 | 说明 |
|---|---|
| 纯静态架构 | 无服务端依赖，适合 GitHub Pages 等静态托管 |
| 一体化工作台 | 覆盖公众号排版、图文拆页、封面生成三类场景 |
| 主题化输出 | 主题不只是改颜色，会影响标题、正文、引用、表格、图片和代码块 |
| 复制友好 | 公众号编辑器会在复制前做 HTML 归一化，提高微信后台保留样式的概率 |
| 本地优先 | 草稿、历史记录、图片库等数据默认保存在浏览器本地 |
| 快速导出 | 支持 HTML、Markdown、Word、PDF、JPG/PNG 等常见输出方式 |

## 页面结构

```text
newmedia/
├── index.html                 # 首页 / 工作台入口
├── views/
│   ├── md.html                # 公众号编辑器
│   ├── note.html              # 图文生成器
│   └── cover.html             # 封面生成器
├── assets/styles/             # 本地静态 CSS
├── fonts/                     # 本地字体资源
├── og-cover.svg               # 分享封面
├── robots.txt
├── sitemap.xml
├── site.webmanifest
├── CNAME                      # 自定义域名
└── README.md
```

## 本地运行

这是一个纯静态项目，可以直接打开首页：

```bash
open index.html
```

也可以使用本地静态服务器：

```bash
python3 -m http.server 8080
```

然后访问：

```text
http://localhost:8080
```

## 技术栈

- 原生 `HTML / CSS / JavaScript`
- 本地静态 CSS
- `Marked.js`
- `Turndown` / `turndown-plugin-gfm`
- `html-to-image`
- `JSZip`
- `FileSaver.js`
- `Lucide`
- `localStorage` / `IndexedDB`

## 浏览器支持

- Chrome / Edge
- Safari
- Firefox

推荐使用最新版 Chrome 或 Edge，图片导出、富文本粘贴和剪贴板复制体验更稳定。

## 隐私与数据

- 项目不依赖服务端存储
- 编辑内容、主题配置、历史记录默认保存在浏览器本地
- 图片库使用浏览器本地 IndexedDB 保存
- 在共享电脑上使用后，建议手动清理浏览器本地数据

## 安全说明

- 项目对粘贴 HTML、Markdown 渲染和复制链路做了基础白名单清洗
- 外部脚本依赖已尽量使用固定版本
- 不建议粘贴不可信来源的复杂网页代码
- 如果用于长期公开运营，后续可以继续把第三方脚本本地化或补充 SRI 校验

## 补充说明

项目在整理与演进过程中，参考了网上部分开源编辑器的代码组织方式与页面样式思路，并结合当前的新媒体创作场景做了适配与扩展。

## License

MIT
