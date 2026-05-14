---
name: html-artifact-designer
description: "创建精致、自包含的单文件 HTML artifact，风格参考 thariqs.github.io/html-effectiveness：适用于编辑化技术讲解、作品集/索引页、对比页、PR/评审摘要、实施计划、报告、图表、原型和小型自定义编辑器。用户要求制作美观、高质量、有设计感的 HTML 文件、HTML artifact、交互式讲解、可视化技术文档、演示页，或受 The unreasonable effectiveness of HTML 启发的可复用布局时使用。"
---

# HTML Artifact Designer

创建一个可在浏览器中打开的 `.html` artifact，将密集文本转化为结构化、可视化、可选交互的文档。优先采用 `html-effectiveness` 的设计语言：编辑化结构、温暖纸感表面、编号章节、胶囊导航、卡片网格、inline SVG、克制动效，以及足够具体、有实际用途的文案。

## 工作流程

1. **定义 artifact 任务**：判断输出应是画廊/索引页（gallery/index）、概念讲解、对比页、PR review、实施计划、报告、图表、prototype，还是 tiny editor。
2. **先定结构，再做样式**：
   - 画廊/索引页（Gallery/index）：masthead、pill TOC、编号章节、card grid、SVG thumbnails。
   - 单页讲解（Single explainer）：紧凑 masthead、侧边/章节导航、interactive model、comparison cards、specs/FAQ。
   - 评审/报告（Review/report）：summary strip、severity/risk map、annotated blocks、timeline、next actions。
   - 编辑器/工具（Editor/tool）：聚焦 workspace、controls、live preview/state、明确的 export/copy button。
3. **写成自包含文件**：inline CSS、inline JS、inline SVG；不需要 build step。除非用户明确要求，否则避免外部依赖。
4. **让内容像人为撰写，而不是泛化模板**：使用具体数据、标签、取舍、风险和示例。不要使用 lorem ipsum 或 placeholder filler。
5. **交付前验证**：确认文件存在、JS 引用的 IDs 存在、inline JS 能解析、首屏有意义，且 desktop/mobile 布局可读。

## 视觉方向

除非用户给出更明确的品牌方向，否则使用以下默认风格：

- 背景：暖象牙色或浅灰色，搭配白色纸面卡片。
- 配色：slate/ink 正文，clay 或 blue 强调色，muted olive/green 辅助色，oat/light gray 边框。
- 排版：大标题使用 editorial serif；正文使用 clean sans；索引、文件名、计数和标签使用 mono。
- 布局：max-width container，间距充足但不浪费，层级清晰，章节标题带编号。
- 组件：pill TOC、card grids、risk/status badges、comparison columns、timelines、inline SVG diagrams，以及必要时的 copy/export controls。
- 动效：只使用轻微 hover lift 和有目的的 reveal/transition；避免花哨动画。
- 响应式：在 tablet 以下宽度清晰折叠 grids 和 sidebars。

需要更细的风格语法和可复用模式时，读取 `references/style-guide.md`。需要起始骨架时，复制并改造 `assets/starter.html`。

## 内容规则

- 将大段 Markdown 转化为空间结构：sections、cards、diagrams、callouts、timelines、tabs 或 controls。
- 当用户需要在多个方案间选择时，把 trade-offs 并排展示。
- 默认使用 inline SVG 绘制 diagrams 和 thumbnails，而不是 raster images。
- 当 artifact 用于解释或决策时，包含 “why this matters” 和 “what to do next”。
- 对 custom editors，提供将用户编辑内容导出为 Markdown、JSON、diff、prompt text 或其他有用纯文本格式的方法。
- 保持生成文件易于检查和提交：一个 `.html` 文件、可读 CSS、不做 minification。

## 实现标准

- 使用 semantic HTML：`header`、`nav`、`main`、`section`、`article`、`aside`、`footer`。
- 在 `:root` 中定义 CSS variables；component classes 保持描述性。
- 布局优先使用 CSS Grid，局部对齐使用 Flexbox。
- JS 保持小而有边界；demo data 放在使用它的 script 附近。
- 在相关场景为 nav、controls、diagrams 和 live metrics 添加 ARIA labels。
- 避免复制真实网站的专有 assets、logo 或源码。借鉴 design language，不复刻 trademarked identity。

## 验证清单

可行时运行或模拟这些检查：

- 页面有非平凡 JavaScript 时，对抽取出的 inline JS 运行 `node --check`。
- 搜索 JS selectors 引用但不存在的 IDs。
- 有 browser 或 thumbnail renderer 时，在本地 render/open 页面。
- 检查首屏：应说明 artifact 的目的，并提供清晰导航或交互入口。
- 检查窄屏视口，或确认 media queries 覆盖 mobile。

## 输出

完成后只报告文件路径、改了什么、为什么该结构适合请求，以及验证结果。如果某项验证无法执行，明确说明未验证的内容。
