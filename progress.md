# WeMD 图文编辑器优化进度

## 已完成
1. 已克隆并阅读 WeMD README 与核心源码。
2. 已定位 WeMD 关键模块：
   - packages/core/src/MarkdownParser.ts
   - packages/core/src/ThemeProcessor.ts
   - apps/web/src/services/wechatCopyService.ts
   - apps/web/src/services/wechatCopyNormalizer.ts
   - apps/web/src/services/wechatTableRenderer.ts
   - apps/web/src/services/image/imageUploadFlow.ts
   - apps/web/src/store/historyDb.ts
3. 已对照本项目 views/md.html 的现有能力，确认第一阶段应优先优化公众号编辑器。

## 待确认
1. Mermaid 与深色模式预览默认放入第二阶段。

## 开发步骤
/// 1. 在 md 页面补 Markdown 轻量扩展：任务列表、提醒块、图片滑动组。
/// 2. 优化复制到公众号的 HTML 归一化，重点保护根容器留白、背景、文本颜色和表格。
/// 3. 统一 md 预览与复制里的表格容器，避免宽表格撑破预览/公众号页面。
/// 4. 增加 md 本地历史快照，最近 30 条可恢复。
/// 5. 本地静态校验后提交推送。

## 进行中
1. 等待提交与推送。

## 未开始
1. OpenSpec archive 归档。

## 已验证
1. 已确认 views/note.html 没有遗留改动。
2. 已对 views/md.html 的内联脚本做语法解析检查。
3. 已确认第一阶段改动集中在 views/md.html。

## 说明
1. 当前仓库没有可用的 /opsx:archive 命令或 OpenSpec 配置，归档步骤只能在本次记录中说明，不能执行真实命令。
