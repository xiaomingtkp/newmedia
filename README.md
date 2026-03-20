# 新媒体图文编辑器

一个面向内容创作者的纯静态编辑器站点，包含 3 个工作台：

- `公众号编辑器`：富文本粘贴、Markdown 编辑、主题排版、一键复制到公众号
- `图文生成器`：Markdown 转多页图文卡片，适合小红书等内容平台
- `封面生成器`：快速制作封面图、标题图和视觉头图

整个项目基于原生 HTML / CSS / JavaScript 构建，无需打包工具，适合直接部署到 GitHub Pages，生成对外可访问的网站。

## 本地使用

直接在浏览器中打开 [index.html](./index.html) 即可使用。

```bash
open index.html
```

## 页面结构

```text
newmedia/
├── index.html                 # 首页 / 功能导航
├── views/
│   ├── md.html                # 公众号编辑器
│   ├── note.html              # 图文生成器
│   └── cover.html             # 封面生成器
├── fonts/                     # 字体资源
├── favicon.svg
├── .github/workflows/
│   └── deploy-pages.yml       # GitHub Pages 自动部署
└── README.md
```

## 核心能力

### 公众号编辑器

- 支持 Markdown 编辑与实时 HTML 预览
- 支持粘贴飞书富文本并尽量保留结构
- 内置多套公众号排版主题
- 支持一键复制到公众号、复制到 X、导出 HTML
- 支持本地历史记录与草稿保存

### 图文生成器

- 支持 Markdown 输入与样式化卡片分页
- 支持自动分页与手动分页
- 支持主题切换、图片引用和批量导出
- 适合生成小红书风格图文内容

### 封面生成器

- 支持多种封面主题与布局模板
- 支持标题、副标题、日期、页数等元素配置
- 支持导出高清 JPG / PNG

## 技术栈

- 原生 `HTML / CSS / JavaScript`
- `Tailwind CSS`（CDN）
- `Marked.js`
- `Turndown`
- `html-to-image`
- `JSZip`
- `FileSaver.js`

## 部署到 GitHub Pages

项目已经包含 GitHub Pages 工作流。你只需要把代码推到 GitHub，然后开启 Pages。

### 1. 新建 GitHub 仓库

建议仓库名直接使用英文，例如 `newmedia-editor`。

### 2. 初始化并推送代码

在项目根目录执行：

```bash
git init
git add .
git commit -m "feat: initial site"
git branch -M main
git remote add origin https://github.com/<你的用户名>/<你的仓库名>.git
git push -u origin main
```

### 3. 在 GitHub 开启 Pages

进入仓库：

`Settings` -> `Pages` -> `Build and deployment`

选择：

- `Source`: `GitHub Actions`

仓库收到 `main` 或 `master` 分支更新后，会自动执行 `.github/workflows/deploy-pages.yml` 并发布网站。

### 4. 访问外部网址

部署成功后，默认地址通常是：

```text
https://<你的用户名>.github.io/<你的仓库名>/
```

如果你使用的是用户主页仓库 `<你的用户名>.github.io`，则地址会是：

```text
https://<你的用户名>.github.io/
```

## 自定义域名

如果后面你想绑定自己的域名，可以在仓库 `Settings -> Pages` 中配置 `Custom domain`，再按域名服务商要求添加 DNS 记录。

## 浏览器支持

- Chrome / Edge
- Safari
- Firefox

推荐使用最新版 Chrome 或 Edge，编辑与导出体验最稳定。

## 说明

- 项目根目录已加入 `.nojekyll`，避免 GitHub Pages 对静态目录做额外处理
- 当前站点是纯静态站，不依赖 Node.js 服务端
- 所有编辑数据默认保存在浏览器本地 `localStorage`

## License

MIT
