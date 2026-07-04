# Bubble Design System

> 花心小泡泡个人品牌设计系统 — 温暖治愈、自由探索、元气满满、潇洒酷帅的设计语言。

---

## 快速开始

### 首次使用前必须完成配置

1. 品牌色已配置为花心小泡泡的棕/黄/蓝三色。如需调整，修改 `brand-dna.md` 中的三色色值
2. 头像已放入 `assets/avatar.jpg`
3. IP形象已放入 `assets/character.png`
4. 模板中的作者名/签名档已替换为花心小泡泡
5. 气质关键词和禁忌清单已根据花心小泡泡品牌调性配置

### 使用方式（7步工作流）

1. **澄清需求** — 确认类型、受众、Section数、素材、硬约束
2. **读规范** — 必读 `brand-dna.md`，按需读场景文件
3. **拷模板** — 从 `assets/` 选择对应模板作为起点
4. **选布局组合** — 从 `references/layouts.md` 选取3~5种布局
5. **选组件填充** — 从 `references/components.md` 选取组件
6. **自检** — 对照 `references/checklist.md` 逐条检查
7. **交付** — 输出最终HTML文件

---

## 品牌基因速览

### 三色（方案A 焦糖奶茶）

| 颜色 | 色值 | 比例 |
|------|------|------|
| 主色（棕） | `#A67B5B` | 60% |
| 强调色（黄） | `#F0C674` | 30% |
| 点缀色（蓝） | `#5B8BA0` | 10% |

### 背景与文字

| 用途 | 色值 |
|------|------|
| 暖底背景 | `#FDF8F0` |
| 交替背景（深奶底） | `#F5EDE0` |
| 墨色正文 | `#2D2420` |
| 次要文字 | `#5C4D44` |
| 暗色面板（仅全屏HTML） | `#1E1A16` |

### 字体

| 用途 | 字体 |
|------|------|
| 中文标题 | 汇文明朝体 / Noto Serif SC |
| 中文正文 | Noto Sans SC |
| 英文装饰 | Fraunces italic |
| 手写/注释 | Caveat |
| 代码/终端 | Fira Code |

### 气质关键词

温暖治愈 · 自由探索 · 元气满满 · 潇洒酷帅 · 体验感 · 手绘彩铅感 · 不像AI

### 禁忌

蓝紫渐变 · glassmorphism · neon · bounce · 颜色过渡失调 · 小家子气 · Inter/Roboto · 所有 section 居中 · HTML 默认样式 · 看起来像 AI 生成的通用模板

---

## 文件结构

```
bubble-design-system/
├── README.md                          # 本文件
├── brand-dna.md                       # 品牌底层规范（必读）
├── SKILL.md                           # Skill入口文件
├── .gitignore
├── assets/
│   ├── avatar.jpg                     # 头像（600×600px）
│   ├── character.png                  # IP形象（Q版三视图）
│   ├── template-tutorial.html         # 教程型模板
│   ├── template-landing.html          # Landing模板
│   ├── template-app.html              # App型模板
│   └── template-cards.html           # 图文卡片模板
└── references/
    ├── scene-tutorial.md              # 教程型场景规范
    ├── scene-landing.md               # Landing场景规范
    ├── scene-app.md                   # App型场景规范
    ├── scene-cards.md                 # 图文卡片场景规范
    ├── layouts.md                     # 16种布局库
    ├── components.md                  # 44个组件库
    └── checklist.md                   # 自检清单
```

---

## 场景类型速查

| 类型 | 场景文件 | 模板 |
|------|----------|------|
| 教程型/介绍型/科普型 | `references/scene-tutorial.md` | `assets/template-tutorial.html` |
| 活动页/分享会/Landing | `references/scene-landing.md` | `assets/template-landing.html` |
| App型/功能型 | `references/scene-app.md` | `assets/template-app.html` |
| 图文卡片/小红书图文 | `references/scene-cards.md` | `assets/template-cards.html` |

---

## 关键原则

- **从模板开始改，不从零写** — 模板已内置品牌变量和基础结构
- **每个 Section 布局必须不同** — 避免单调重复，从 layouts.md 选不同模式
- **做完必须跑 checklist** — P0 全过才能交付
- **禁止使用 HTML 默认样式** — 所有组件从 components.md 选用
- **三色比例**：主色60% + 强调色30% + 点缀色10%
- **不像AI** — 最高优先级的约束

---

## Demo

> Demo链接待补充

---

## 品牌信息

- **署名**: 花心小泡泡 / Bubble
- **签名档**: 花心小泡泡 · 体验生活，感受体验，记录感受
- **CTA**: Follow 在下 花心泡

---

## 自检问题

做完设计后问自己：
1. 这个页面截图发到社交媒体，会不会被人评论"又是AI做的"？
2. 能不能一眼认出这是花心小泡泡的品牌？
3. 有没有哪个部分让你觉得"见过很多次了"？

---

*Bubble Design System — 温暖治愈的个人品牌设计系统。*
