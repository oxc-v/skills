# HTML Artifact Style Guide

设计受 `The unreasonable effectiveness of HTML` 启发的 artifact 时，使用这份 reference。

## 标志性布局

- Masthead 包含小号 mono/uppercase eyebrow、大号 editorial title、简洁 intro，以及右侧可选 visual metaphor。
- Pill TOC 直接放在 intro 下方；包含 section names 和小型 counts 或 numbers。
- Sections 使用 `idx + h2 + count/status`，后接一段简短 intro paragraph。
- Card grids 用于 examples、approaches、decisions、files、risks 或 milestones。
- Footer 放一条简短说明，交代 artifact 与 source/context。

## 默认 Tokens

```css
:root {
  --ivory: #FAF9F5;
  --paper: #FFFFFF;
  --slate: #141413;
  --clay: #D97757;
  --clay-d: #B85C3E;
  --oat: #E3DACC;
  --olive: #788C5D;
  --g100: #F0EEE6;
  --g200: #E6E3DA;
  --g300: #D1CFC5;
  --g500: #87867F;
  --g700: #3D3D3A;
  --serif: ui-serif, Georgia, "Times New Roman", Times, serif;
  --sans: system-ui, -apple-system, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
  --mono: ui-monospace, "SF Mono", Menlo, Monaco, Consolas, monospace;
}
```

可根据用户要求的品牌方向调整 accents，但要保持对比度和克制感。

## Artifact 模式

### 探索 / 规划（Exploration / Planning）
使用并排 cards。每张 card 应包含：方案标题（approach title）、适用时机（when to use）、trade-offs、implementation notes，以及 recommendation marker。

### Code Review / 理解
使用 annotated diffs、severity badges、file map、call graph 或 hot path diagram。先放 findings，再放 summary。

### Design System / 组件
使用 swatches、type scale、spacing examples、component contact sheets、states 和 copyable tokens。

### Prototype / 交互
使用聚焦的 sandbox 和 controls。让用户能感受到 motion、timing、ordering 或 click-through。

### 研究 / 概念讲解（Research / Concept Explainer）
使用 TL;DR、interactive model、step-by-step path、comparison table、glossary、FAQ 和 gotchas。

### 报告 / 事故（Reports / Incidents）
使用 status strip、timeline、impact cards、chart、action items、owners 和 open risks。

### 自定义编辑器（Custom Editors）
使用面向任务的 UI，并提供 export。不要构建完整 app；只做足够的 controls，让 feedback loop 闭合。

## 文案风格

- 优先使用具体 labels，而不是泛化 labels：如 “Keys moved”、“Risk map”、“Reviewer focus”、“Open questions”。
- 使用短段落；把细节移入 cards 或 expandable blocks。
- 当目标是比较时，明确命名 recommendation。
- 交互发生时，说明视觉上发生了什么变化。

## 避免

- 泛化的 SaaS landing pages。
- 用户没有要求时，不使用默认紫色 gradient。
- 避免巨大 hero area 把真正的 artifact 推到首屏以下。
- 避免 placeholder text、无意义的装饰性 charts，或不会改变用户理解的 interactions。
- 需要自包含文件时，避免 external fonts/assets。
