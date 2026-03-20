# 新媒体图文编辑器

一个面向内容创作者的在线编辑器，聚合了 `公众号编辑器`、`图文生成器`、`封面生成器` 三个工作台，适合完成公众号排版、小红书图文生成、封面设计等新媒体创作流程。

项目为纯静态站点，基于原生 HTML / CSS / JavaScript 构建，无需构建工具，已经部署为公开网站，可直接访问使用。

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

- 纯静态部署：无服务端依赖，适合 GitHub Pages
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

## 部署说明

项目已内置 GitHub Pages 自动部署工作流。

### GitHub Pages

推送到 GitHub 后，在仓库中开启：

`Settings -> Pages -> Build and deployment -> Source: GitHub Actions`

工作流文件：

- [.github/workflows/deploy-pages.yml](./.github/workflows/deploy-pages.yml)

### 自定义域名

当前项目已配置自定义域名：

- `editor.have-idea.com`

仓库中对应文件：

- [CNAME](./CNAME)

如果你要迁移到自己的域名，需要修改两处：

1. 仓库根目录的 `CNAME`
2. 域名服务商后台的 DNS 记录

子域名常见配置示例：

```text
主机记录：editor
记录类型：CNAME
记录值：xiaomingtkp.github.io
```

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

## 参考

README 的组织方式参考了花生编辑器项目的开源展示思路：

- [alchaincyf/huasheng_editor](https://github.com/alchaincyf/huasheng_editor)

## License

MIT
