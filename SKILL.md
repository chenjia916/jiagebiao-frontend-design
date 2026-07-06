---
name: jiagebiao-frontend-design
description: "应用价格表系统 (Price List System) 的现代毛玻璃 UI 设计规范。适用于 Vue 3 + Element Plus 项目，包含色彩、排版、组件覆写、移动端自适应及复杂表单录入标准。"
---

# 价格表系统前端设计规范 (Vue 3 + Element Plus)

本技能 (Skill) 提炼自“价格表系统”，用于在构建新项目或新模块时，保持极其现代、高级且一致的 UI/UX 体验。

## 1. 核心视觉与背景
- **毛玻璃质感 (Glassmorphism):** 容器（卡片、侧边栏、弹窗）必须使用半透明背景 `rgba(255, 255, 255, 0.75)`，辅以 `backdrop-filter: blur(24px)` 和半透明发光边框 `rgba(255, 255, 255, 0.5)`。
- **弥散渐变 (Mesh Gradient):** `body` 采用浅冷灰白 `var(--bg)`，叠加固定的蓝色、紫色、绿色径向渐变 (Radial Gradient) 作为底层背景。
- **阴影层次:** 摒弃生硬的边框，大量使用柔和的多层阴影 `var(--shadow-sm)` 和悬浮阴影 `var(--shadow-lg)`。

## 2. 色彩与排版 (Typography)
- **品牌色:** 亮眼的皇家蓝 `#2563EB`，主要按钮使用对角线渐变 `linear-gradient(135deg, #3B82F6, #2563EB)`。
- **字体搭配:** 
  - 标题及重点展示数字：使用 `Outfit` 字体（几何无衬线体），尽显现代感。
  - 正文：使用 `Inter` 字体。
- **数字对齐:** 金额和数据必须使用等宽变体 `font-variant-numeric: tabular-nums`（或 `.tabular-nums` 类），防止数字跳动和不对齐。

## 3. 组件级覆写 (Element Plus)
- **按钮 (Buttons):** 10px 圆角，摒弃默认的点击效果，改为真实的弹簧缩放反馈 `transform: scale(0.94)`。
- **卡片 (Cards):** 16px 圆角，默认毛玻璃状态，鼠标悬浮时触发 `translateY(-2px)` 的上浮及阴影加深效果。
- **弹窗 (Dialogs):** 高度圆角化 (24px)，彻底去除原生生硬感，配合弹簧动画的出入场。
- **输入框 (Inputs):** 10px 圆角，使用内阴影 `box-shadow: inset` 替代传统边框，获取焦点时渐变过渡到品牌色边框和纯白背景。

## 4. 响应式布局与移动端优化 (Mobile-First)
- **悬浮式布局 (Desktop):** 电脑端采用 `Floating Sidebar` (悬浮侧边栏，不贴边) 和 `Floating Header`。
- **移动端导航:** 屏幕缩小后，侧边栏转为 `Drawer` 抽屉，同时底部固定显示毛玻璃质感的 **底部导航栏 (Bottom Nav)**。
- **响应式表单 (Responsive Forms):** 针对多列内联表单，使用 `.responsive-form-item` 类，并在移动端 (`@media (max-width: 768px)`) 强制 `width: 100% !important; margin-right: 0`，实现平滑降级。
- **移动端只读卡片流 (`.mobile-card-list`):** 在移动端，坚决避免显示臃肿的数据表格，必须转换为交错动画出场的卡片列表。
- **移动端复杂数据录入 (`.mobile-item-list`):** 移动端录入明细（如多行产品编辑）时，禁用表格内编辑，改为卡片内嵌表单流 `.mobile-item-list` > `.mobile-card` > `.form-row`。左侧 Label 统一浅灰色定宽 (`width: 70px; color:#909399`)，右侧放输入控件，保证移动端极佳的录入体验。
- **悬浮操作按钮 (FAB):** 移动端主操作（如新建）统一使用位于右下角的悬浮按钮 `.mobile-fab`，并带按压倾斜动画。
- **触控优化:** 移动端输入框和按钮的最小高度必须强制保证在 `44px` 以上，防误触。

## 5. 动效设计 (Animations)
- **弹簧物理引擎:** 核心过渡动画必须使用 `cubic-bezier(0.34, 1.56, 0.64, 1)`，使所有悬浮、点击操作具有真实的弹性物理反馈。
- **级联入场:** 列表项 (如 `.mobile-card`) 需要使用 `@keyframes cardEnter` 搭配递增的 `animation-delay` (0ms, 50ms, 100ms...)，实现瀑布式的丝滑加载。

## 💡 开发硬性规则
1. **绝不使用大面积纯白背景**，所有主容器必须套用毛玻璃效果。
2. **严禁出现直角**。小型控件 10px，普通卡片 16px，大弹窗 24px。
3. **新增功能必须考虑移动端形态**，无法放入表格的数据必须设计为移动端卡片，复杂录入必须降级为移动卡片流式表单。
