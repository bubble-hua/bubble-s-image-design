# Scene: App / 应用型页面

> 适用于看板、书架、Canvas、Dashboard、终端风格等「功能型/工具型」页面类型。

---

## 🎨 色板（方案A 焦糖奶茶）

| 变量名 | 色值 | 用途 |
|--------|------|------|
| `--brown` | `#A67B5B` | Header/Badge主色、标题、导航 |
| `--yellow` | `#F0C674` | 强调色、边框高亮、装饰 |
| `--blue` | `#5B8BA0` | 危险操作、删除按钮、点缀 |
| `--bg-warm` | `#FDF8F0` | 暖底主背景 |
| `--bg-alt` | `#F5EDE0` | 交替/卡片背景 |
| `--ink` | `#2D2420` | 墨色正文 |
| `--ink-light` | `#5C4D44` | 次要文字 |
| `--panel-dark` | `#1E1A16` | 暗色面板底色（终端/全屏HTML） |
| `--green` | `#6B9E5A` | 终端绿（仅终端风格场景） |

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
  --green: #6B9E5A;
}
```

---

## 📐 App页面结构

App型页面注重"功能清晰 + 操作高效"：

### 标准布局

```
┌──────────────────────────────────┐
│  Header (棕色背景 + 白色文字)      │
├────────┬─────────────────────────┤
│ Sidebar│   Main Content          │
│ (导航) │                         │
│        │   ┌──────┬──────┬──────┐│
│        │   │ Card │ Card │ Card ││
│        │   ├──────┼──────┼──────┤│
│        │   │ Card │ Card │ Card ││
│        │   └──────┴──────┴──────┘│
│        │                         │
└────────┴─────────────────────────┘
```

---

## 🧩 App专属组件

### Header（棕色）

```html
<header style="
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 16px 32px;
  background: var(--brown);
  color: #FDF8F0;
">
  <div style="display: flex; align-items: center; gap: 12px;">
    <span style="
      font-family: 'Fraunces', serif;
      font-style: italic;
      font-size: 1.3rem;
      font-weight: 700;
    ">Bubble</span>
    <span style="
      font-size: 0.75rem;
      opacity: 0.7;
      background: rgba(255,255,255,0.15);
      padding: 2px 8px;
      border-radius: 4px;
    ">v1.0</span>
  </div>
  <nav style="display: flex; gap: 20px; align-items: center;">
    <a href="#" style="color: #FDF8F0; text-decoration: none; font-size: 0.9rem; opacity: 0.8;">首页</a>
    <a href="#" style="color: #FDF8F0; text-decoration: none; font-size: 0.9rem; opacity: 0.8;">项目</a>
    <a href="#" style="color: #FDF8F0; text-decoration: none; font-size: 0.9rem; opacity: 0.8;">关于</a>
  </nav>
</header>
```

### Badge（棕色）

```html
<span class="badge" style="
  display: inline-block;
  padding: 2px 10px;
  background: var(--brown);
  color: #FDF8F0;
  border-radius: 999px;
  font-size: 0.72rem;
  font-weight: 600;
  letter-spacing: 0.02em;
">NEW</span>
```

### 黄色Badge变体

```html
<span class="badge-yellow" style="
  display: inline-block;
  padding: 2px 10px;
  background: var(--yellow);
  color: var(--ink);
  border-radius: 999px;
  font-size: 0.72rem;
  font-weight: 600;
">HOT</span>
```

### 状态指示器

```html
<span class="status" style="
  display: inline-flex;
  align-items: center;
  gap: 6px;
  font-size: 0.8rem;
  color: var(--ink-light);
">
  <span style="
    display: inline-block;
    width: 8px; height: 8px;
    background: var(--green);
    border-radius: 50%;
  "></span>
  在线
</span>
```

---

## 🟡 强调/边框系统

### 黄色边框卡片

```html
<div style="
  background: var(--bg-warm);
  border: 2px solid var(--yellow);
  border-radius: 12px;
  padding: 24px;
  position: relative;
">
  <div style="
    position: absolute;
    top: -1px; left: 24px;
    transform: translateY(-50%);
    background: var(--yellow);
    color: var(--ink);
    padding: 3px 12px;
    border-radius: 4px;
    font-size: 0.72rem;
    font-weight: 600;
  ">推荐</div>
  <h3 style="
    font-family: 'Noto Serif SC', serif;
    color: var(--ink);
    margin: 8px 0 12px 0;
  ">项目名称</h3>
  <p style="
    font-size: 0.88rem;
    color: var(--ink-light);
    margin: 0 0 16px 0;
    line-height: 1.6;
  ">项目描述内容，简短有力。</p>
  <div style="display: flex; gap: 8px;">
    <span style="
      font-size: 0.72rem;
      padding: 2px 8px;
      background: rgba(240,198,116,0.2);
      color: var(--ink-light);
      border-radius: 4px;
    ">标签A</span>
    <span style="
      font-size: 0.72rem;
      padding: 2px 8px;
      background: rgba(240,198,116,0.2);
      color: var(--ink-light);
      border-radius: 4px;
    ">标签B</span>
  </div>
</div>
```

### 强调色分割线

```html
<hr style="
  border: none;
  height: 2px;
  background: var(--yellow);
  margin: 32px 0;
  border-radius: 1px;
">
```

### 高亮选中行

```html
<div style="
  padding: 12px 16px;
  background: rgba(240,198,116,0.15);
  border-left: 3px solid var(--yellow);
  border-radius: 0 6px 6px 0;
  display: flex;
  align-items: center;
  justify-content: space-between;
">
  <span style="color: var(--ink); font-size: 0.9rem;">当前选中项目</span>
  <span style="color: var(--ink-light); font-size: 0.8rem;">活跃</span>
</div>
```

---

## 🔵 危险/删除操作（蓝色点缀）

### 删除按钮

```html
<button style="
  display: inline-flex;
  align-items: center;
  gap: 6px;
  padding: 8px 20px;
  background: transparent;
  color: var(--blue);
  border: 1.5px solid var(--blue);
  border-radius: 6px;
  font-size: 0.85rem;
  cursor: pointer;
  transition: background 0.2s ease, color 0.2s ease;
">
  删除
</button>
```

### 危险确认面板

```html
<div style="
  background: var(--bg-warm);
  border: 1.5px solid var(--blue);
  border-radius: 10px;
  padding: 24px;
">
  <div style="
    display: flex;
    align-items: flex-start;
    gap: 12px;
    margin-bottom: 16px;
  ">
    <span style="
      display: flex;
      align-items: center;
      justify-content: center;
      width: 32px; height: 32px;
      background: rgba(91,139,160,0.15);
      color: var(--blue);
      border-radius: 50%;
      font-size: 1rem;
      flex-shrink: 0;
    ">!</span>
    <div>
      <strong style="color: var(--blue); display: block; margin-bottom: 4px;">确认删除</strong>
      <span style="color: var(--ink-light); font-size: 0.85rem;">此操作不可撤销，确定要继续吗？</span>
    </div>
  </div>
  <div style="display: flex; gap: 10px; justify-content: flex-end;">
    <button style="
      padding: 8px 20px;
      background: transparent;
      color: var(--ink-light);
      border: 1px solid rgba(0,0,0,0.15);
      border-radius: 6px;
      font-size: 0.85rem;
      cursor: pointer;
    ">取消</button>
    <button style="
      padding: 8px 20px;
      background: var(--blue);
      color: #fff;
      border: none;
      border-radius: 6px;
      font-size: 0.85rem;
      cursor: pointer;
    ">确认删除</button>
  </div>
</div>
```

---

## 🟢 终端风格（绿色 `#6B9E5A`）

终端风格仅适用于终端/命令行场景。

### 终端窗口

```html
<div style="
  background: var(--panel-dark);
  border-radius: 10px;
  overflow: hidden;
  font-family: 'Fira Code', monospace;
">
  <!-- 标题栏 -->
  <div style="
    display: flex;
    align-items: center;
    gap: 8px;
    padding: 10px 16px;
    background: rgba(0,0,0,0.3);
  ">
    <span style="width: 12px; height: 12px; background: #ff5f57; border-radius: 50%;"></span>
    <span style="width: 12px; height: 12px; background: #febc2e; border-radius: 50%;"></span>
    <span style="width: 12px; height: 12px; background: #28c840; border-radius: 50%;"></span>
    <span style="margin-left: 12px; font-size: 0.72rem; color: rgba(255,255,255,0.4);">terminal — bash</span>
  </div>
  <!-- 内容 -->
  <div style="padding: 20px 24px; font-size: 0.85rem; line-height: 1.8;">
    <div><span style="color: var(--green);">bubble@travel</span> <span style="color: rgba(255,255,255,0.6);">~</span> <span style="color: rgba(255,255,255,0.8);">$</span> <span style="color: rgba(255,255,255,0.7);">ls -la</span></div>
    <div style="color: rgba(255,255,255,0.5); margin-top: 4px;">
      drwxr-xr-x  bubble  staff  .notes<br>
      drwxr-xr-x  bubble  staff  .photos<br>
      -rw-r--r--  bubble  staff  travel-log.md
    </div>
    <div style="margin-top: 12px;"><span style="color: var(--green);">bubble@travel</span> <span style="color: rgba(255,255,255,0.6);">~</span> <span style="color: rgba(255,255,255,0.8);">$</span> <span style="color: rgba(255,255,255,0.7);">cat travel-log.md</span></div>
    <div style="color: var(--yellow); margin-top: 4px;">
      # 花心小泡泡 · 体验生活，感受体验，记录感受
    </div>
    <div style="margin-top: 8px;"><span style="color: var(--green);">bubble@travel</span> <span style="color: rgba(255,255,255,0.6);">~</span> <span style="color: rgba(255,255,255,0.8);">$</span> <span style="display: inline-block; width: 8px; height: 16px; background: rgba(255,255,255,0.6); animation: blink 1s step-end infinite; vertical-align: text-bottom;"></span></div>
  </div>
</div>
```

### 终端标签

```html
<span style="
  display: inline-block;
  padding: 2px 8px;
  background: rgba(107,158,90,0.15);
  color: var(--green);
  border: 1px solid rgba(107,158,90,0.3);
  border-radius: 4px;
  font-family: 'Fira Code', monospace;
  font-size: 0.75rem;
">status: ok</span>
```

---

## 📊 数据看板组件

### 统计卡片

```html
<div style="
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
  gap: 16px;
">
  <!-- 统计卡片 -->
  <div style="
    background: var(--bg-warm);
    border: 1px solid rgba(166,123,91,0.12);
    border-radius: 10px;
    padding: 20px;
  ">
    <div style="font-size: 0.75rem; color: var(--ink-light); text-transform: uppercase; letter-spacing: 0.05em; margin-bottom: 8px;">笔记数</div>
    <div style="font-family: 'Fraunces', serif; font-style: italic; font-size: 1.8rem; color: var(--brown);">128</div>
    <div style="font-size: 0.72rem; color: var(--green); margin-top: 4px;">↑ 12%</div>
  </div>

  <div style="
    background: var(--bg-warm);
    border: 1px solid rgba(166,123,91,0.12);
    border-radius: 10px;
    padding: 20px;
  ">
    <div style="font-size: 0.75rem; color: var(--ink-light); text-transform: uppercase; letter-spacing: 0.05em; margin-bottom: 8px;">城市</div>
    <div style="font-family: 'Fraunces', serif; font-style: italic; font-size: 1.8rem; color: var(--brown);">37</div>
    <div style="font-size: 0.72rem; color: var(--green); margin-top: 4px;">↑ 5</div>
  </div>

  <div style="
    background: var(--bg-warm);
    border: 1px solid rgba(166,123,91,0.12);
    border-radius: 10px;
    padding: 20px;
  ">
    <div style="font-size: 0.75rem; color: var(--ink-light); text-transform: uppercase; letter-spacing: 0.05em; margin-bottom: 8px;">照片</div>
    <div style="font-family: 'Fraunces', serif; font-style: italic; font-size: 1.8rem; color: var(--brown);">2.4k</div>
    <div style="font-size: 0.72rem; color: var(--blue); margin-top: 4px;">↓ 3%</div>
  </div>
</div>
```

### 进度条

```html
<div style="margin-bottom: 16px;">
  <div style="display: flex; justify-content: space-between; margin-bottom: 6px;">
    <span style="font-size: 0.8rem; color: var(--ink-light);">旅行计划完成度</span>
    <span style="font-size: 0.8rem; color: var(--brown); font-weight: 600;">75%</span>
  </div>
  <div style="
    height: 6px;
    background: var(--bg-alt);
    border-radius: 3px;
    overflow: hidden;
  ">
    <div style="
      height: 100%;
      width: 75%;
      background: linear-gradient(90deg, var(--brown), var(--yellow));
      border-radius: 3px;
    "></div>
  </div>
</div>
```

---

## 📋 列表组件

### 项目列表

```html
<div style="display: flex; flex-direction: column; gap: 4px;">
  <div style="
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 14px 16px;
    background: var(--bg-warm);
    border-radius: 8px;
    border: 1px solid rgba(166,123,91,0.08);
  ">
    <div style="display: flex; align-items: center; gap: 12px;">
      <span style="
        width: 10px; height: 10px;
        background: var(--yellow);
        border-radius: 2px;
      "></span>
      <span style="color: var(--ink); font-size: 0.9rem;">东京游记</span>
    </div>
    <span style="color: var(--ink-light); font-size: 0.78rem;">2024.03</span>
  </div>

  <div style="
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 14px 16px;
    background: var(--bg-warm);
    border-radius: 8px;
    border: 1px solid rgba(166,123,91,0.08);
  ">
    <div style="display: flex; align-items: center; gap: 12px;">
      <span style="
        width: 10px; height: 10px;
        background: var(--brown);
        border-radius: 2px;
      "></span>
      <span style="color: var(--ink); font-size: 0.9rem;">京都漫步</span>
    </div>
    <span style="color: var(--ink-light); font-size: 0.78rem;">2024.04</span>
  </div>

  <div style="
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 14px 16px;
    background: var(--bg-warm);
    border-radius: 8px;
    border: 1px solid rgba(166,123,91,0.08);
  ">
    <div style="display: flex; align-items: center; gap: 12px;">
      <span style="
        width: 10px; height: 10px;
        background: var(--blue);
        border-radius: 2px;
      "></span>
      <span style="color: var(--ink); font-size: 0.9rem;">北海道之冬</span>
    </div>
    <span style="color: var(--ink-light); font-size: 0.78rem;">2024.12</span>
  </div>
</div>
```

---

## 📐 App页面布局推荐

| Section | 推荐布局 | 说明 |
|---------|----------|------|
| Header | Full-width header | 棕色背景 |
| Sidebar | Fixed sidebar + content | 导航 + 内容 |
| Dashboard | Grid cards | 数据统计 |
| 内容区 | Grid / List / Table | 功能展示 |
| 终端区 | Terminal panel | 暗色面板 |
| Footer | Compact footer | 状态信息 |

---

## 🎯 App页面自检清单

### P0（必须过）
- [ ] Header使用棕色 `#A67B5B`
- [ ] Badge使用棕色 `#A67B5B`
- [ ] 强调/边框使用黄色 `#F0C674`
- [ ] 危险操作使用蓝色 `#5B8BA0`
- [ ] 终端绿仅用于终端场景 `#6B9E5A`
- [ ] 暗色面板仅用于全屏HTML
- [ ] 三色比例正确

### P1（应过）
- [ ] 功能分区清晰
- [ ] 状态指示明确
- [ ] 交互元素有hover/active反馈
- [ ] 数据展示有对比（上升/下降）

### P2（加分）
- [ ] 有终端风格区块
- [ ] 有进度条或图表元素
- [ ] 有项目列表或数据表格
- [ ] 操作确认有二次确认面板
- [ ] 截图有工具感但不冰冷

---

## 📝 品牌信息

- **署名**: 花心小泡泡 / Bubble
- **签名档**: 花心小泡泡 · 体验生活，感受体验，记录感受
- **CTA**: Follow 在下 花心泡

---

*This scene file builds on top of brand-dna.md. Always reference brand-dna.md for the full brand specification.*
