# Jiagebiao Frontend Design Skill
**Language**: [English](#english) | [中文](#chinese)

<a id="english"></a>
## English

This repository contains the AI coding agent skill for the **Jiagebiao (Price List System) Frontend Design**. 
It defines the modern UI/UX design specifications, specifically built for Vue 3 + Element Plus, ensuring consistency when building new features or modules.

### Key Features
- **Glassmorphism**: Translucent backgrounds with deep blurs for cards, sidebars, and dialogs.
- **Spring Physics**: Bouncy, natural animations for button clicks and hover states.
- **Mobile-First Data UI**: Auto-switching from desktop sidebars to mobile bottom navigation. Data grids and complex inline editing tables are smoothly transformed into staggered, animated `.mobile-card` and `.mobile-item-list` flows for optimal touch usability.
- **Responsive Forms**: Smart layout degrading for complex forms, scaling from multi-column grids down to touch-friendly mobile layouts dynamically.
- **Element Plus Overrides**: Highly customized Element Plus components (rounded borders, gradient buttons, inner-shadow inputs).

### How to Use
For AI Agents: Place this folder inside your workspace's `.agents/skills/` or global `.gemini/config/skills/` directory to automatically apply these design rules during code generation.

---

<a id="chinese"></a>
## 中文

本仓库包含了 **价格表系统 (Jiagebiao)** 前端设计的 AI 编程代理专属技能 (Skill) 配置文件。
该规范提炼了针对 Vue 3 + Element Plus 的现代 UI/UX 设计标准，可确保在生成新代码时自动保持一致的高级感和设计风格。

### 核心特性
- **毛玻璃效果 (Glassmorphism)**：卡片、侧边栏和弹窗统一采用半透明背景及深度背景模糊。
- **弹簧物理动效 (Spring Physics)**：为按钮点击、悬浮等交互提供真实且 Q 弹的物理动画反馈。
- **极致的移动端数据交互 (Mobile-First Data UI)**：不仅实现了基础响应式，对于极难适配的复杂数据表格及“多行内联编辑”功能，本规范定义了将其无缝转换为带入场动画的 `.mobile-card` 及 `.mobile-item-list`（流式内嵌表单）标准，保障了优秀的移动端触控和录入体验。
- **智能响应式表单 (Responsive Forms)**：规范了复杂表单的多列响应式降维降级处理。
- **Element Plus 深度定制**：大圆角、渐变色按钮、内阴影输入框等组件覆写规范。

### 如何使用
对于 AI 编程助手：将此文件夹放置于您的工作区 `.agents/skills/` 目录或全局 `.gemini/config/skills/` 目录下，AI 即可在后续生成前端代码时自动加载并遵循本设计规范。
