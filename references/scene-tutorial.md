# Scene: Tutorial / 教程型页面

> 适用于教程、科普、文档、知识分享、文章详情等「信息传递优先」的页面类型。

---

## 🎨 色板（方案A 焦糖奶茶）

| 变量名 | 色值 | 用途 | 比例 |
|--------|------|------|------|
| `--brown` | `#A67B5B` | 主色调、标题、链接、重点标记 | 60% |
| `--yellow` | `#F0C674` | 强调色、装饰、高亮、标签 | 30% |
| `--blue` | `#5B8BA0` | 点缀色、下划线、CTA、标签点缀 | 10% |
| `--bg-warm` | `#FDF8F0` | 暖底主背景 | — |
| `--bg-alt` | `#F5EDE0` | 交替/卡片背景（深奶底） | — |
| `--ink` | `#2D2420` | 墨色正文 | — |
| `--ink-light` | `#5C4D44` | 次要文字 | — |
| `--panel-dark` | `#1E1A16` | 暗色面板底色（仅全屏HTML） | — |

### CSS变量声明

```css
:root {
  --brown: #A67B5B;
  --yellow: #F0C674;
  --blue: #5B8BA0;
  --bg-warm: #FDF8F0;
  --bg-alt: #F5EDE0;
  --ink: #2D2420;
  --ink-light: #5C4D44;
  --panel-dark: #1E1A16;
}
```

---

## ✨ 气质关键词

设计出来的东西应该让人觉得：

- **温暖治愈** — 像一杯热茶，让人感到安心和放松
- **自由探索** — 有旅行的呼吸感，不拘束、不沉闷
- **元气满满** — 积极向上，有生命力和能量
- **潇洒酷帅** — 不拖泥带水，有态度有风格
- **体验感** — 不只是看，而是"感受到"那个场景
- **手绘彩铅感** — 有温度、有人味、有笔触的痕迹
- **不像AI** — 这是最高优先级的约束

---

## 📐 教程页特有结构

教程页面按"导览 → 正文 → 总结 → CTA"的节奏编排：

### 标准Section序列

1. **Hero** — 标题 + 一句话介绍 + 关键词标签
2. **概览/目录** — 用卡片或编号列出章节
3. **正文Section × N** — 每节一个核心知识点
4. **总结/要点回顾** — 用列表或卡片复述
5. **CTA/订阅** — 关注/收藏/下一篇文章

### 正文Section内部结构

每个教程Section建议包含：

```
[编号/图标] 标题
一句话概述（subtitle）
正文段落（2-4段，不要wall of text）
代码块 / 示意图 / 引用块（按需）
关键要点小结（1-2条）
```

---

## 🧩 教程页专属组件

### 步骤编号

```html
<span class="step-num" style="
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: 36px; height: 36px;
  border-radius: 50%;
  background: var(--brown);
  color: #FDF8F0;
  font-family: 'Fraunces', serif;
  font-style: italic;
  font-size: 1rem;
  font-weight: 700;
  margin-right: 12px;
  flex-shrink: 0;
">1</span>
```

### 关键词标签

```html
<span class="tag" style="
  display: inline-block;
  padding: 3px 12px;
  border-radius: 999px;
  font-size: 0.78rem;
  background: rgba(240,198,116,0.25);
  color: var(--ink-light);
  border: 1px solid rgba(240,198,116,0.4);
  margin-right: 6px;
  margin-bottom: 6px;
">关键词</span>
```

### 高亮标注（文字底部高亮）

```html
<span class="highlight" style="
  background: linear-gradient(180deg, transparent 50%, rgba(240,198,116,0.35) 50%);
">需要强调的内容</span>
```

### 提示框（Tip / Warning / Note）

```html
<div class="callout callout-tip" style="
  border-left: 4px solid var(--yellow);
  background: var(--bg-alt);
  padding: 20px 24px;
  border-radius: 0 8px 8px 0;
  margin: 28px 0;
  font-size: 0.92rem;
  color: var(--ink-light);
">
  <strong style="color: var(--brown);">💡 提示：</strong> 提示内容。
</div>
```

### 信息卡（定义/概念卡片）

```html
<div class="info-card" style="
  background: var(--bg-warm);
  border: 1px solid rgba(166,123,91,0.2);
  border-radius: 12px;
  padding: 28px;
  margin: 28px 0;
">
  <h4 style="margin-top: 0; color: var(--brown); font-family: 'Noto Serif SC', serif;">概念名称</h4>
  <p style="margin-bottom: 0; color: var(--ink-light);">概念说明内容。</p>
</div>
```

### 代码块

```html
<div class="code-block" style="
  background: var(--panel-dark);
  color: #F5EDE0;
  border-radius: 10px;
  padding: 24px;
  margin: 24px 0;
  font-family: 'Fira Code', monospace;
  font-size: 0.85rem;
  line-height: 1.7;
  overflow-x: auto;
">
<pre style="margin: 0;"><code>// 你的代码
const greeting = "Hello, Bubble!";
</code></pre>
</div>
```

---

## 🖼️ 装饰元素

### 标准装饰手法

#### 虚线圆圈

```html
<div style="
  width: 280px; height: 280px;
  border: 2.5px dashed var(--yellow);
  border-radius: 50%;
  opacity: 0.3;
  position: absolute;
  top: -80px; right: -100px;
  pointer-events: none;
"></div>
```

#### 渐变光晕背景

```html
<div style="
  position: absolute;
  width: 500px; height: 500px;
  background: radial-gradient(ellipse, rgba(240,198,116,0.15), transparent 70%);
  top: -100px; left: -150px;
  pointer-events: none;
  z-index: 0;
"></div>
```

#### 分割线（渐隐线）

```html
<hr style="
  border: none;
  height: 1px;
  background: linear-gradient(90deg, transparent, var(--yellow), transparent);
  margin: 48px 0;
">
```

#### 高亮标记（文字底部色块）

```html
<span style="
  background: linear-gradient(180deg, transparent 55%, rgba(240,198,116,0.4) 55%);
  padding: 0 4px;
">被标记的文字</span>
```

#### 大透明装饰数字

```html
<div style="
  font-family: 'Fraunces', serif;
  font-style: italic;
  font-size: clamp(3rem, 8vw, 7rem);
  color: var(--brown);
  opacity: 0.12;
  position: absolute;
  top: -20px; right: 20px;
  pointer-events: none;
  user-select: none;
">03</div>
```

#### 左侧色条

```html
<div style="
  border-left: 4px solid var(--yellow);
  padding-left: 20px;
  margin: 24px 0;
">
  <p style="margin: 0; color: var(--ink-light);">带有左侧色条标识的内容。</p>
</div>
```

### 旅行主题装饰

#### 机票/登机牌风格

```html
<div class="boarding-pass" style="
  background: var(--bg-warm);
  border: 2px solid var(--yellow);
  border-radius: 12px;
  padding: 24px 28px;
  position: relative;
  overflow: hidden;
  max-width: 400px;
">
  <!-- 虚线撕纸边 -->
  <div style="
    position: absolute;
    left: 0; top: 50%;
    width: 100%;
    height: 0;
    border-top: 2px dashed var(--yellow);
    opacity: 0.4;
  "></div>
  <div style="display: flex; justify-content: space-between; align-items: flex-start;">
    <div>
      <div style="font-size: 0.7rem; color: var(--ink-light); text-transform: uppercase; letter-spacing: 0.1em;">Boarding Pass</div>
      <div style="font-family: 'Fraunces', serif; font-size: 1.8rem; font-style: italic; color: var(--brown); margin-top: 4px;">目的地</div>
    </div>
    <div style="text-align: right;">
      <div style="font-size: 0.7rem; color: var(--ink-light);">GATE</div>
      <div style="font-family: 'Fira Code', monospace; font-size: 1.5rem; color: var(--blue);">B12</div>
    </div>
  </div>
  <div style="margin-top: 20px; display: flex; gap: 24px; font-size: 0.75rem; color: var(--ink-light);">
    <span>FROM: 出发点</span>
    <span>TO: 目的地</span>
    <span>DATE: 日期</span>
  </div>
</div>
```

#### 邮票边框

```html
<div class="stamp-frame" style="
  display: inline-block;
  padding: 8px;
  background: var(--bg-alt);
  position: relative;
">
  <div style="
    padding: 20px;
    border: 3px solid var(--yellow);
    outline: 2px solid var(--yellow);
    outline-offset: -8px;
    position: relative;
  ">
    <!-- 锯齿效果通过outline + outline-offset模拟 -->
    <div style="font-size: 0.7rem; color: var(--ink-light); text-align: center; letter-spacing: 0.1em;">POSTCARD</div>
    <div style="font-family: 'Caveat', cursive; font-size: 1.2rem; color: var(--brown); text-align: center; margin-top: 4px;">来自旅途的问候</div>
  </div>
</div>
```

#### 地图元素

```html
<div class="map-marker" style="
  position: relative;
  padding: 20px 24px;
  background: var(--bg-warm);
  border-radius: 8px;
  border: 1px solid rgba(166,123,91,0.15);
">
  <!-- 定位点 -->
  <span style="
    display: inline-block;
    width: 14px; height: 14px;
    background: var(--blue);
    border-radius: 50%;
    border: 2px solid var(--bg-warm);
    box-shadow: 0 0 0 3px var(--blue);
    opacity: 0.8;
    margin-right: 8px;
  "></span>
  <span style="font-family: 'Fira Code', monospace; font-size: 0.8rem; color: var(--ink-light);">
    35.6762° N, 139.6503° E
  </span>
  <!-- 路径虚线 -->
  <div style="
    position: absolute;
    left: 27px; top: 100%;
    width: 0;
    height: 30px;
    border-left: 2px dashed var(--yellow);
    opacity: 0.5;
  "></div>
</div>
```

#### 胶片/拍立得

```html
<div class="polaroid" style="
  display: inline-block;
  background: var(--bg-warm);
  padding: 12px 12px 36px 12px;
  box-shadow: 3px 4px 12px rgba(0,0,0,0.08);
  transform: rotate(-1.5deg);
">
  <div style="
    width: 200px; height: 160px;
    background: var(--bg-alt);
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 0.8rem;
    color: var(--ink-light);
  ">[ 照片 ]</div>
  <div style="
    margin-top: 10px;
    font-family: 'Caveat', cursive;
    font-size: 1rem;
    color: var(--ink);
    text-align: center;
  ">旅途中的美好瞬间</div>
</div>
```

#### 手账贴纸感

```html
<div class="sticker" style="
  display: inline-block;
  background: rgba(240,198,116,0.2);
  padding: 6px 14px;
  border-radius: 4px;
  transform: rotate(2deg);
  font-size: 0.8rem;
  color: var(--brown);
  box-shadow: 1px 2px 4px rgba(0,0,0,0.06);
  border: 1px dashed var(--yellow);
  font-family: 'Caveat', cursive;
">旅行日记 ✈️</div>
```

### 材质/肌理

#### 条纹肌理分割

```html
<div style="
  height: 12px;
  background: repeating-linear-gradient(
    -45deg,
    transparent,
    transparent 4px,
    rgba(240,198,116,0.2) 4px,
    rgba(240,198,116,0.2) 8px
  );
  margin: 40px 0;
  border-radius: 2px;
"></div>
```

#### 网格底纹

```html
<div style="
  background-image:
    linear-gradient(rgba(166,123,91,0.06) 1px, transparent 1px),
    linear-gradient(90deg, rgba(166,123,91,0.06) 1px, transparent 1px);
  background-size: 24px 24px;
  padding: 40px;
  border-radius: 12px;
">
  <p>带网格底纹的内容区</p>
</div>
```

#### 彩铅笔触（虚线模拟）

```html
<div style="
  padding: 24px;
  border: 2px dashed var(--brown);
  border-radius: 8px;
  opacity: 0.7;
  background: rgba(166,123,91,0.03);
">
  <p style="margin: 0; color: var(--ink-light);">彩铅手绘感边框的内容块</p>
</div>
```

#### 水彩晕染光斑

```html
<div style="
  position: absolute;
  width: 300px; height: 300px;
  background:
    radial-gradient(ellipse at 30% 40%, rgba(240,198,116,0.12) 0%, transparent 50%),
    radial-gradient(ellipse at 70% 60%, rgba(91,139,160,0.08) 0%, transparent 50%),
    radial-gradient(ellipse at 50% 30%, rgba(166,123,91,0.06) 0%, transparent 50%);
  border-radius: 50%;
  pointer-events: none;
  z-index: 0;
"></div>
```

---

## 📐 教程页布局推荐

| Section | 推荐布局 | 说明 |
|---------|----------|------|
| Hero | Hero Split / Hero Centered | 大标题 + 一句话 + 标签 |
| 概览/目录 | Grid 3-col cards / Numbered list | 章节导航 |
| 正文 | Main content + sidebar / Full width text | 内容为主 |
| 代码示例 | Split code+preview | 左右对照 |
| 总结 | Card grid / Horizontal timeline | 要点回顾 |
| CTA | Banner / Centered CTA | 行动号召 |

---

## 🎯 教程页自检清单

### P0（必须过）
- [ ] 三色使用正确（棕60% + 黄30% + 蓝10%）
- [ ] 背景为暖底 `#FDF8F0` 或 `#F5EDE0`
- [ ] 正文用墨色 `#2D2420`，非纯黑
- [ ] 所有组件从components.md选用，无浏览器默认样式
- [ ] 至少有一种手绘/彩铅感装饰元素
- [ ] 字号对比极端（Hero大 + 辅助小）

### P1（应过）
- [ ] 每个Section布局不同
- [ ] 有旅行主题装饰元素（机票/邮票/地图/拍立得/贴纸至少1种）
- [ ] 有材质肌理感（条纹/网格/水彩晕染至少1种）
- [ ] 步骤编号用棕色圆形badge
- [ ] 代码块使用暗色面板底色

### P2（加分）
- [ ] 有渐变光晕做section背景
- [ ] 使用了虚线圆圈装饰
- [ ] 有渐隐分割线
- [ ] 大透明数字做section装饰
- [ ] 整体截图不会被说"又是AI做的"
- [ ] 一眼能认出是花心小泡泡的品牌

---

## 📝 品牌信息

- **署名**: 花心小泡泡 / Bubble
- **签名档**: 花心小泡泡 · 体验生活，感受体验，记录感受
- **CTA**: Follow 在下 花心泡

---

*This scene file builds on top of brand-dna.md. Always reference brand-dna.md for the full brand specification.*
