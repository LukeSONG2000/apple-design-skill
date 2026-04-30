# Apple Design Language — Frontend Skill

将 Apple 设计语言（Apple.com + HIG）应用到前端开发的 AI Skill。平台无关的 Design Token、组件模式和布局方案，适用于 Web、React Native、Flutter、SwiftUI 等任何前端技术栈。

## 数据来源

本 Skill 的设计 Token 提取自以下**公开资源**，仅供学习与参考：

| 来源 | 说明 |
|---|---|
| [Apple.com 主 CSS](https://www.apple.com) | 从公开样式表中提取的色值、字号、间距等数值 |
| [Human Interface Guidelines (HIG)](https://developer.apple.com/cn/design/) | Apple 官方设计原则和组件规范 |
| [Apple Style Guide](https://support.apple.com/zh-cn/guide/applestyleguide/welcome/web) | Apple 官方编辑与排版规范 |
| Apple.com 页面结构 | 布局模式、间距规律的逆向分析 |

> **注意**：Apple、Apple Logo、Human Interface Guidelines 等为 Apple Inc. 的商标或版权内容。本项目仅作为设计学习与参考用途，不隶属于 Apple Inc.，也未获得其endorsement。

## 快速使用

### Claude Code

将本目录放入项目的 `.claude/commands/` 下即可作为 slash command 使用：

```bash
# 复制到项目
cp -r apple-design /your-project/.claude/commands/
```

### Codex (agentskills.io)

将 `SKILL.md` 和 `references/` 放入 Codex 的全局 skills 目录即可。

## 内容结构

```
apple-design/
├── SKILL.md                    # Skill 主文件（Design Token + 组件模式）
├── references/                 # 详细实现参考
│   ├── 00-philosophy.md        # 设计哲学、HIG 六原则
│   ├── 01-tokens.md            # 色彩、排版、间距、断点、圆角、阴影、毛玻璃、动效
│   ├── 02-components.md        # 按钮、导航栏、卡片、表单、模态框、Toast、页脚
│   ├── 03-patterns.md          # Hero 区、双栏、三栏、图文区等页面布局模式
│   ├── 04-accessibility.md     # 色彩对比度、Focus 管理、ARIA、屏幕阅读器
│   └── 05-tailwind-config.md   # Tailwind CSS 配置、CSS 变量版
```

## Design Token 速查

### 色彩

| 用途 | 值 | 深色模式 |
|---|---|---|
| 正文 | `#1D1D1F` | `#F5F5F7` |
| 次要文字 | `#6E6E73` | `#A1A1A6` |
| 背景 | `#FFFFFF` | `#000000` |
| 链接/主交互 | `#0071E3` | `#2997FF` |

### 核心设计签名

1. **大留白** — 内容不超过 980px 宽
2. **毛玻璃** — 72% 不透明度 + 180% 饱和度 + 20px 模糊
3. **品牌蓝仅交互** — `#0071E3` 只用于链接和按钮
4. **聚焦环** — 键盘导航时显示，鼠标/触屏时隐藏
5. **渐进式信息** — 大标题 → 副标题 → 正文

## 许可证

MIT License — 本项目仅供学习参考，Apple 相关设计资产版权归 Apple Inc. 所有。
