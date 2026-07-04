# Scene: Landing / 落地页

> 适用于活动页、产品介绍、分享会页面、个人主页、作品集首页等「转化导向」的页面类型。

---

## 🎨 色板（方案A 焦糖奶茶）

所有Landing页面统一使用以下色值：

| 变量名 | 色值 | 用途 |
|--------|------|------|
| `--brown` | `#A67B5B` | 主色调、标题、CTA按钮主色、链接 |
| `--yellow` | `#F0C674` | 强调色、装饰、品牌黄底、CTA黄色变体 |
| `--blue` | `#5B8BA0` | 点缀色、点缀标签、下划线 |
| `--bg-warm` | `#FDF8F0` | 暖底主背景 |
| `--bg-alt` | `#F5EDE0` | 交替/卡片背景 |
| `--ink` | `#2D2420` | 墨色正文 |
| `--ink-light` | `#5C4D44` | 次要文字 |
| `--panel-dark` | `#1E1A16` | 暗色面板底色（全屏HTML可用） |

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

## 📐 Landing页结构

Landing页面按"吸引 → 信任 → 行动"的漏斗式节奏：

### 标准Section序列

1. **Hero** — 大标题 + 副标题 + CTA按钮（首屏核心）
2. **价值主张** — 3-4个核心卖点卡片
3. **内容展示** — 核心内容/功能/作品展示
4. **信任背书** — 数据、评价、合作方logo
5. **再次CTA** — 强化行动号召
6. **Footer** — 署名 + 签名档 + 链接

---

## 🔘 CTA按钮系统

Landing页的CTA是核心转化元素，必须醒目但不刺眼。

### 主CTA按钮（棕色）

```html
<a href="#" class="cta-primary" style="
  display: inline-flex;
  align-items: center;
  gap: 8px;
  padding: 14px 32px;
  background: var(--brown);
  color: #FDF8F0;
  font-family: 'Noto Sans SC', sans-serif;
  font-size: 1rem;
  font-weight: 600;
  border: none;
  border-radius: 8px;
  text-decoration: none;
  cursor: pointer;
  transition: transform 0.2s ease, box-shadow 0.2s ease;
  box-shadow: 0 2px 8px rgba(166,123,91,0.3);
">
  立即开始
  <span style="font-size: 1.1rem;">→</span>
</a>
```

### CTA悬停效果

```css
.cta-primary:hover {
  transform: translateY(-2px);
  box-shadow: 0 4px 16px rgba(166,123,91,0.4);
}
```

### CTA黄色变体

```html
<a href="#" class="cta-yellow" style="
  display: inline-flex;
  align-items: center;
  gap: 8px;
  padding: 14px 32px;
  background: var(--yellow);
  color: var(--ink);
  font-family: 'Noto Sans SC', sans-serif;
  font-size: 1rem;
  font-weight: 600;
  border: none;
  border-radius: 8px;
  text-decoration: none;
  cursor: pointer;
  transition: transform 0.2s ease, box-shadow 0.2s ease;
">
  Follow 在下 花心泡
</a>
```

### 次要CTA按钮（outline）

```html
<a href="#" class="cta-outline" style="
  display: inline-flex;
  align-items: center;
  gap: 8px;
  padding: 13px 32px;
  background: transparent;
  color: var(--brown);
  font-family: 'Noto Sans SC', sans-serif;
  font-size: 1rem;
  font-weight: 600;
  border: 2px solid var(--brown);
  border-radius: 8px;
  text-decoration: none;
  cursor: pointer;
  transition: background 0.2s ease, color 0.2s ease;
">
  了解更多
</a>
```

---

## 🎯 Hero区域

### Hero Split（图文左右）

```html
<section style="
  display: flex;
  align-items: center;
  gap: clamp(40px, 6vw, 80px);
  min-height: 80vh;
  padding: clamp(60px, 10vh, 120px) clamp(20px, 4vw, 60px);
  background: var(--bg-warm);
  position: relative;
  overflow: hidden;
">
  <!-- 左侧文字 -->
  <div style="flex: 1; position: relative; z-index: 1;">
    <div style="
      font-size: 0.85rem;
      color: var(--blue);
      text-transform: uppercase;
      letter-spacing: 0.15em;
      margin-bottom: 16px;
    ">BUBBLE DESIGN SYSTEM</div>
    <h1 style="
      font-family: 'Noto Serif SC', serif;
      font-size: clamp(2.8rem, 7vw, 5.5rem);
      color: var(--ink);
      line-height: 1.15;
      margin: 0 0 20px 0;
    ">
      用设计<br>记录每一次<span style="color: var(--brown);">旅行</span>
    </h1>
    <p style="
      font-size: 1.05rem;
      color: var(--ink-light);
      line-height: 1.7;
      max-width: 480px;
      margin-bottom: 32px;
    ">
      花心小泡泡 · 体验生活，感受体验，记录感受
    </p>
    <div style="display: flex; gap: 16px; flex-wrap: wrap;">
      <!-- CTA按钮 -->
      <a href="#" style="
        display: inline-flex; align-items: center; gap: 8px;
        padding: 14px 32px;
        background: var(--brown);
        color: #FDF8F0;
        font-weight: 600;
        border-radius: 8px;
        text-decoration: none;
        box-shadow: 0 2px 8px rgba(166,123,91,0.3);
      ">开始探索 →</a>
      <a href="#" style="
        display: inline-flex; align-items: center; gap: 8px;
        padding: 13px 32px;
        background: transparent;
        color: var(--brown);
        font-weight: 600;
        border: 2px solid var(--brown);
        border-radius: 8px;
        text-decoration: none;
      ">了解更多</a>
    </div>
  </div>

  <!-- 右侧装饰 -->
  <div style="flex: 1; position: relative; min-height: 400px;">
    <!-- 光晕背景 -->
    <div style="
      position: absolute;
      width: 500px; height: 500px;
      background: radial-gradient(ellipse, rgba(240,198,116,0.15), transparent 70%);
      top: -50px; right: -100px;
      pointer-events: none;
    "></div>
    <!-- 虚线圆圈 -->
    <div style="
      width: 300px; height: 300px;
      border: 2.5px dashed var(--yellow);
      border-radius: 50%;
      opacity: 0.3;
      position: absolute;
      top: 10%; right: 5%;
    "></div>
    <!-- IP形象或头像 -->
    <div style="
      position: absolute;
      top: 50%; left: 50%;
      transform: translate(-50%, -50%);
      width: 260px; height: 260px;
      border-radius: 50%;
      background: var(--bg-alt);
      display: flex;
      align-items: center;
      justify-content: center;
    ">
      <span style="color: var(--brown); font-family: 'Fraunces', serif; font-style: italic; font-size: 1.5rem;">Bubble</span>
    </div>
  </div>
</section>
```

### Hero Centered（居中）

```html
<section style="
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center;
  min-height: 85vh;
  padding: clamp(60px, 10vh, 120px) clamp(20px, 4vw, 60px);
  background: var(--bg-warm);
  position: relative;
  overflow: hidden;
">
  <div style="
    font-size: 0.85rem;
    color: var(--blue);
    text-transform: uppercase;
    letter-spacing: 0.15em;
    margin-bottom: 20px;
  ">花心小泡泡 · 个人品牌</div>
  <h1 style="
    font-family: 'Noto Serif SC', serif;
    font-size: clamp(2.8rem, 7vw, 5.5rem);
    color: var(--ink);
    line-height: 1.2;
    margin: 0 0 20px 0;
    max-width: 800px;
  ">
    体验生活<br>感受<span style="color: var(--brown);">体验</span>
  </h1>
  <p style="
    font-size: 1.05rem;
    color: var(--ink-light);
    line-height: 1.7;
    max-width: 540px;
    margin-bottom: 36px;
  ">
    温暖治愈、自由探索、元气满满、潇洒酷帅 — 
    用设计和文字记录每一次旅程。
  </p>
  <a href="#" style="
    display: inline-flex; align-items: center; gap: 8px;
    padding: 16px 40px;
    background: var(--brown);
    color: #FDF8F0;
    font-size: 1.05rem;
    font-weight: 600;
    border-radius: 8px;
    text-decoration: none;
    box-shadow: 0 2px 12px rgba(166,123,91,0.3);
  ">Follow 在下 花心泡 →</a>
</section>
```

---

## 🃏 价值主张卡片

```html
<section style="
  padding: clamp(80px, 12vh, 160px) clamp(20px, 4vw, 60px);
  background: var(--bg-alt);
">
  <h2 style="
    text-align: center;
    font-family: 'Noto Serif SC', serif;
    font-size: clamp(1.6rem, 4vw, 2.6rem);
    color: var(--ink);
    margin: 0 0 48px 0;
  ">品牌<span style="color: var(--brown);">基因</span></h2>

  <div style="
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
    gap: clamp(24px, 3vw, 48px);
    max-width: 1300px;
    margin: 0 auto;
  ">
    <!-- 卡片1 -->
    <div style="
      background: var(--bg-warm);
      border-radius: 12px;
      padding: 36px 28px;
      border: 1px solid rgba(166,123,91,0.12);
    ">
      <div style="
        width: 48px; height: 48px;
        background: rgba(240,198,116,0.25);
        border-radius: 12px;
        display: flex; align-items: center; justify-content: center;
        margin-bottom: 20px;
      ">
        <span style="font-size: 1.4rem;">☕</span>
      </div>
      <h3 style="
        font-family: 'Noto Serif SC', serif;
        font-size: 1.2rem;
        color: var(--brown);
        margin: 0 0 12px 0;
      ">温暖治愈</h3>
      <p style="
        font-size: 0.92rem;
        color: var(--ink-light);
        line-height: 1.6;
        margin: 0;
      ">像一杯热茶，让人感到安心和放松的设计语言。</p>
    </div>

    <!-- 卡片2 -->
    <div style="
      background: var(--bg-warm);
      border-radius: 12px;
      padding: 36px 28px;
      border: 1px solid rgba(166,123,91,0.12);
    ">
      <div style="
        width: 48px; height: 48px;
        background: rgba(240,198,116,0.25);
        border-radius: 12px;
        display: flex; align-items: center; justify-content: center;
        margin-bottom: 20px;
      ">
        <span style="font-size: 1.4rem;">✈️</span>
      </div>
      <h3 style="
        font-family: 'Noto Serif SC', serif;
        font-size: 1.2rem;
        color: var(--brown);
        margin: 0 0 12px 0;
      ">自由探索</h3>
      <p style="
        font-size: 0.92rem;
        color: var(--ink-light);
        line-height: 1.6;
        margin: 0;
      ">有旅行的呼吸感，不拘束、不沉闷的视觉节奏。</p>
    </div>

    <!-- 卡片3 -->
    <div style="
      background: var(--bg-warm);
      border-radius: 12px;
      padding: 36px 28px;
      border: 1px solid rgba(166,123,91,0.12);
    ">
      <div style="
        width: 48px; height: 48px;
        background: rgba(240,198,116,0.25);
        border-radius: 12px;
        display: flex; align-items: center; justify-content: center;
        margin-bottom: 20px;
      ">
        <span style="font-size: 1.4rem;">🎨</span>
      </div>
      <h3 style="
        font-family: 'Noto Serif SC', serif;
        font-size: 1.2rem;
        color: var(--brown);
        margin: 0 0 12px 0;
      ">手绘彩铅感</h3>
      <p style="
        font-size: 0.92rem;
        color: var(--ink-light);
        line-height: 1.6;
        margin: 0;
      ">有温度、有人味、有笔触痕迹的质感设计。</p>
    </div>
  </div>
</section>
```

---

## 🌙 暗色面板

暗色面板仅在全屏HTML页面中使用，3:4图文卡片场景禁止深色底。

```html
<section style="
  padding: clamp(80px, 12vh, 160px) clamp(20px, 4vw, 60px);
  background: var(--panel-dark);
  color: #F5EDE0;
  position: relative;
  overflow: hidden;
">
  <!-- 光晕 -->
  <div style="
    position: absolute;
    width: 400px; height: 400px;
    background: radial-gradient(ellipse, rgba(240,198,116,0.08), transparent 70%);
    top: -50px; right: -100px;
    pointer-events: none;
  "></div>

  <div style="
    max-width: 1300px;
    margin: 0 auto;
    position: relative;
    z-index: 1;
  ">
    <h2 style="
      font-family: 'Noto Serif SC', serif;
      font-size: clamp(1.6rem, 4vw, 2.6rem);
      color: #F5EDE0;
      margin: 0 0 20px 0;
    ">
      暗色面板中的<span style="color: var(--yellow);">内容</span>
    </h2>
    <p style="
      font-size: 1rem;
      color: rgba(245,237,224,0.7);
      line-height: 1.7;
      max-width: 600px;
      margin-bottom: 36px;
    ">
      花心小泡泡 · 体验生活，感受体验，记录感受
    </p>
    <a href="#" style="
      display: inline-flex; align-items: center; gap: 8px;
      padding: 14px 32px;
      background: var(--yellow);
      color: var(--ink);
      font-weight: 600;
      border-radius: 8px;
      text-decoration: none;
    ">Follow 在下 花心泡 →</a>
  </div>
</section>
```

---

## 🟡 品牌黄底区块

```html
<section style="
  padding: clamp(60px, 8vh, 100px) clamp(20px, 4vw, 60px);
  background: var(--yellow);
  text-align: center;
">
  <h2 style="
    font-family: 'Noto Serif SC', serif;
    font-size: clamp(1.6rem, 4vw, 2.6rem);
    color: var(--ink);
    margin: 0 0 16px 0;
  ">
    准备好开始<span style="color: var(--brown);">旅程</span>了吗？
  </h2>
  <p style="
    font-size: 1rem;
    color: var(--ink-light);
    margin-bottom: 32px;
  ">
    花心小泡泡 · 体验生活，感受体验，记录感受
  </p>
  <a href="#" style="
    display: inline-flex; align-items: center; gap: 8px;
    padding: 14px 32px;
    background: var(--ink);
    color: var(--yellow);
    font-weight: 600;
    border-radius: 8px;
    text-decoration: none;
    box-shadow: 0 2px 8px rgba(0,0,0,0.15);
  ">Follow 在下 花心泡 →</a>
</section>
```

---

## 📊 数据展示（信任背书）

```html
<section style="
  padding: clamp(80px, 12vh, 160px) clamp(20px, 4vw, 60px);
  background: var(--bg-warm);
">
  <div style="
    display: flex;
    justify-content: center;
    gap: clamp(40px, 8vw, 100px);
    flex-wrap: wrap;
    max-width: 1300px;
    margin: 0 auto;
    text-align: center;
  ">
    <div>
      <div style="
        font-family: 'Fraunces', serif;
        font-style: italic;
        font-size: clamp(2.5rem, 5vw, 3.5rem);
        color: var(--brown);
        line-height: 1;
      ">100+</div>
      <div style="
        font-size: 0.85rem;
        color: var(--ink-light);
        margin-top: 8px;
      ">旅行笔记</div>
    </div>
    <div>
      <div style="
        font-family: 'Fraunces', serif;
        font-style: italic;
        font-size: clamp(2.5rem, 5vw, 3.5rem);
        color: var(--brown);
        line-height: 1;
      ">50+</div>
      <div style="
        font-size: 0.85rem;
        color: var(--ink-light);
        margin-top: 8px;
      ">城市足迹</div>
    </div>
    <div>
      <div style="
        font-family: 'Fraunces', serif;
        font-style: italic;
        font-size: clamp(2.5rem, 5vw, 3.5rem);
        color: var(--brown);
        line-height: 1;
      ">10k+</div>
      <div style="
        font-size: 0.85rem;
        color: var(--ink-light);
        margin-top: 8px;
      ">读者伙伴</div>
    </div>
  </div>
</section>
```

---

## 📋 Footer

```html
<footer style="
  padding: clamp(60px, 8vh, 100px) clamp(20px, 4vw, 60px);
  background: var(--panel-dark);
  color: #F5EDE0;
  text-align: center;
">
  <div style="
    font-family: 'Fraunces', serif;
    font-style: italic;
    font-size: 1.8rem;
    color: var(--yellow);
    margin-bottom: 12px;
  ">Bubble</div>
  <p style="
    font-size: 0.9rem;
    color: rgba(245,237,224,0.6);
    margin: 0 0 20px 0;
  ">
    花心小泡泡 · 体验生活，感受体验，记录感受
  </p>
  <div style="
    display: flex;
    justify-content: center;
    gap: 24px;
    flex-wrap: wrap;
  ">
    <a href="#" style="color: rgba(245,237,224,0.5); text-decoration: none; font-size: 0.85rem;">关于</a>
    <a href="#" style="color: rgba(245,237,224,0.5); text-decoration: none; font-size: 0.85rem;">联系</a>
    <a href="#" style="color: rgba(245,237,224,0.5); text-decoration: none; font-size: 0.85rem;">Follow 在下 花心泡</a>
  </div>
</footer>
```

---

## 📐 Landing页布局推荐

| Section | 推荐布局 | 说明 |
|---------|----------|------|
| Hero | Hero Split / Hero Centered | 大标题 + CTA |
| 价值主张 | Grid 3-col cards | 卖点展示 |
| 内容展示 | Alternating rows / Masonry | 作品/功能展示 |
| 数据背书 | Stats row / Logo grid | 信任建立 |
| 二次CTA | Banner / Centered CTA | 强化转化 |
| Footer | Footer dark | 署名 + 链接 |

---

## 🎯 Landing页自检清单

### P0（必须过）
- [ ] 三色比例正确（棕60% + 黄30% + 蓝10%）
- [ ] CTA按钮使用棕色 `#A67B5B`
- [ ] CTA黄色变体使用 `#F0C674` + 墨色字
- [ ] 品牌黄底使用 `#F0C674` 背景 + 墨色字
- [ ] 暗色面板底色 `#1E1A16`（仅全屏HTML）
- [ ] 署名和签名档正确

### P1（应过）
- [ ] Hero区域有视觉冲击力
- [ ] 每个Section布局不同
- [ ] 有数据或信任元素
- [ ] CTA按钮有hover效果

### P2（加分）
- [ ] 有暗色面板区块制造节奏变化
- [ ] 有品牌黄底全宽区块
- [ ] 使用了旅行主题装饰元素
- [ ] Footer有完整的品牌信息
- [ ] 截图不会被说"又是AI做的"

---

## 📝 品牌信息

- **署名**: 花心小泡泡 / Bubble
- **签名档**: 花心小泡泡 · 体验生活，感受体验，记录感受
- **CTA**: Follow 在下 花心泡

---

*This scene file builds on top of brand-dna.md. Always reference brand-dna.md for the full brand specification.*
