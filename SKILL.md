---
name: apple-design
version: 1.0.0
description: Apply Apple Design Language (from Apple.com & HIG) to frontend development — platform-agnostic design tokens, component patterns, and layout recipes.
category: productivity
tags:
  - frontend
  - docs
  - planning
  - analysis

namespace: "@LukeSONG2000"
description_zh: 将 Apple 设计语言（Apple.com + HIG）应用到前端开发——平台无关的 Design Token、组件模式和布局方案。
author: LukeSONG2000
license: MIT
homepage: https://github.com/LukeSONG2000/apple-design-skill

ide_config:
  claude:
    auto_activate: false
---

# Apple Design Language — Frontend Skill

将 Apple 设计语言应用到前端开发。本 skill 提供平台无关的 Design Token 和组件模式，适用于 Web、React Native、Flutter、SwiftUI 等任何前端技术栈。完整的 CSS/Tailwind 实现参考见 [references/](references/) 目录。

## 数据来源

本 skill 的设计 Token 提取自以下公开资源：

- **Apple.com 主 CSS**（公开样式表中提取的色值、字号、间距等数值）
- **[Human Interface Guidelines](https://developer.apple.com/cn/design/)**（Apple 官方设计原则和组件规范）
- **[Apple Style Guide](https://support.apple.com/zh-cn/guide/applestyleguide/welcome/web)**（Apple 官方编辑与排版规范）
- **Apple.com 页面结构分析**（布局模式、间距规律的逆向分析）

## 触发条件

当用户要求构建具有 Apple 风格的界面、参考 Apple 设计规范、或使用 Apple 视觉语言时触发。

## 设计 Token

### 色彩

| 用途 | 值 | 深色模式 |
|---|---|---|
| 正文 | `#1D1D1F` | `#F5F5F7` |
| 次要文字 | `#6E6E73` | `#A1A1A6` |
| 辅助文字 | `#86868B` | `#6E6E73` |
| 背景 | `#FFFFFF` | `#000000` |
| 次要背景 | `#F5F5F7` | `#1D1D1F` |
| 链接/主交互 | `#0071E3` | `#2997FF` |
| 链接悬停 | `#0077ED` | `#547EAE` |

品牌蓝（`#0071E3`）只用于链接和按钮，不用于装饰。

### 排版

- 字重：300（大标题）/ 400（正文）/ 600（小标题、标签）
- 标题字间距：`-0.015em` ~ `-0.022em`
- 行高：英文 1.33，中文 1.8
- 基础字号 17px
- 字体栈按平台选择（Web: SF Pro → Helvetica Neue → Arial；中文: PingFang SC → Noto Sans SC）

### 间距与尺寸

- 区块间距 ≥ 40px，Hero 区间距 ≥ 80px
- 标题 → 副标题 12px，副标题 → 正文 16px，正文 → CTA 20px
- 圆角：按钮 8px / 卡片 12px / 大面板 20px / 药丸形 980px
- 断点：320 / 735 / 1068 / 1441px

### 动效

- 微交互（hover、toggle）：100ms linear
- 标准过渡（展开、切换）：200ms ease
- 大幅动画（页面进入、揭示）：600ms ease
- 必须尊重用户减少动画偏好

### 毛玻璃

背景 72% 不透明度 + 180% 饱和度 + 20px 模糊。

## 核心设计签名

1. **大留白** — 元素间大量呼吸空间，内容不超过 980px 宽
2. **毛玻璃** — 半透明 + 模糊，用于导航栏和遮罩层
3. **品牌蓝仅交互** — 蓝色只出现在链接和按钮上
4. **聚焦环** — 键盘导航时显示 2px 蓝色轮廓，鼠标/触屏时隐藏
5. **渐进式信息** — 大标题 → 副标题 → 正文，层次分明，一眼扫到重点

## 组件模式

### 按钮

- 主要：品牌蓝填充 + 白字 + 药丸形圆角 + 内边距 8×16px
- 次要：品牌蓝文字 + 右箭头 → + 无边框无背景
- 深色背景上：白字 + 白色 1px 边框

### 导航栏

固定顶部 / 高 44px / 毛玻璃背景 / 文字 12px + 透明度 0.8 → 悬停 1.0

### Hero 区

文字居中 / 标题 48–96px 字重 300 / 副标题 21–28px / 产品图居中 / 大量留白

### 卡片

圆角 20px / 悬停：scale 1.02 + 阴影 / 深色浅色背景可交替

## 无障碍

- 正文对比度 ≥ 4.5:1
- 支持深色模式、减少动画、增强对比度偏好
- 键盘完整可导航 + 聚焦环可见

## 参考资料

详细实现（CSS 代码、Tailwind 配置、完整组件规范）见 references 目录：

| 文件 | 内容 |
|---|---|
| [00-philosophy.md](references/00-philosophy.md) | 设计哲学、HIG 六原则、设计签名 |
| [01-tokens.md](references/01-tokens.md) | 色彩、排版、间距、断点、圆角、阴影、毛玻璃、动效 |
| [02-components.md](references/02-components.md) | 按钮、导航栏、卡片、表单、模态框、Toast、页脚 |
| [03-patterns.md](references/03-patterns.md) | Hero 区、双栏、三栏、图文区等页面布局模式 |
| [04-accessibility.md](references/04-accessibility.md) | 色彩对比度、Focus 管理、动画减弱、ARIA |
| [05-tailwind-config.md](references/05-tailwind-config.md) | Tailwind CSS 配置、CSS 变量版、使用示例 |
