# Scene: Cards / 图文卡片

> 适用于小红书图文、文章转卡片、社交媒体图文、知识卡片等「3:4竖版卡片」场景。

---

## 🎨 色板（方案A 焦糖奶茶）

3:4卡片场景使用以下色值，**禁止深色底**：

| 变量名 | 色值 | 用途 |
|--------|------|------|
| `--brown` | `#A67B5B` | 主色调、标题、蓝色高亮块（替代原蓝色） |
| `--yellow` | `#F0C674` | 强调色、封面边框、装饰 |
| `--blue` | `#5B8BA0` | 点缀色、点缀标签 |
| `--bg-warm` | `#FDF8F0` | 暖底主背景 |
| `--bg-alt` | `#F5EDE0` | 交替/卡片背景 |
| `--ink` | `#2D2420` | 墨色正文 |
| `--ink-light` | `#5C4D44` | 次要文字 |
| `--panel-dark` | `#1E1A16` | ⚠️ 卡片场景禁止使用深色底 |

```css
:root {
  --brown: #A67B5B;
  --yellow: #F0C674;
  --blue: #5B8BA0;
  --bg-warm: #FDF8F0;
  --bg-alt: #F5EDE0;
  --ink: #2D2420;
  --ink-light: #5C4D44;
}
```

---

## 📐 卡片尺寸规范

### 小红书图文标准尺寸

| 尺寸 | 比例 | 适用场景 |
|------|------|----------|
| 1080×1440px | 3:4 | 标准图文卡片（推荐） |
| 1080×1080px | 1:1 | 方形卡片/封面 |
| 1080×1920px | 9:16 | 长图/信息图 |

### 卡片内边距

```css
.card {
  padding: clamp(40px, 5%, 64px);
  max-width: 1080px;
  aspect-ratio: 3 / 4;
}
```

---

## 🎴 卡片类型

### 封面卡片（Cover Card）

封面是整组图文的第一张，决定点击率。

```html
<div style="
  width: 100%;
  aspect-ratio: 3 / 4;
  background: var(--bg-warm);
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center;
  padding: 60px 48px;
  position: relative;
  overflow: hidden;
  border: 3px solid var(--yellow);
  border-radius: 16px;
">
  <!-- 装饰光晕 -->
  <div style="
    position: absolute;
    width: 400px; height: 400px;
    background: radial-gradient(ellipse, rgba(240,198,116,0.12), transparent 70%);
    top: -50px; left: -50px;
    pointer-events: none;
  "></div>

  <!-- 标签 -->
  <div style="
    font-size: 0.78rem;
    color: var(--blue);
    text-transform: uppercase;
    letter-spacing: 0.12em;
    margin-bottom: 20px;
    position: relative;
    z-index: 1;
  ">BUBBLE · TRAVEL NOTES</div>

  <!-- 大标题 -->
  <h1 style="
    font-family: 'Noto Serif SC', serif;
    font-size: clamp(2rem, 5vw, 3.2rem);
    color: var(--ink);
    line-height: 1.3;
    margin: 0 0 16px 0;
    position: relative;
    z-index: 1;
  ">
    在东京<br>寻找<span style="color: var(--brown);">治愈感</span>
  </h1>

  <!-- 副标题 -->
  <p style="
    font-size: 1rem;
    color: var(--ink-light);
    line-height: 1.6;
    max-width: 380px;
    margin: 0 0 32px 0;
    position: relative;
    z-index: 1;
  ">
    花心小泡泡 · 体验生活，感受体验，记录感受
  </p>

  <!-- CTA -->
  <div style="
    padding: 8px 24px;
    background: var(--brown);
    color: #FDF8F0;
    border-radius: 999px;
    font-size: 0.85rem;
    font-weight: 600;
    position: relative;
    z-index: 1;
  ">Follow 在下 花心泡</div>

  <!-- 底部装饰：虚线圆圈 -->
  <div style="
    width: 200px; height: 200px;
    border: 2px dashed var(--yellow);
    border-radius: 50%;
    opacity: 0.25;
    position: absolute;
    bottom: -60px; right: -60px;
    pointer-events: none;
  "></div>
</div>
```

### 正文卡片（Content Card）

```html
<div style="
  width: 100%;
  aspect-ratio: 3 / 4;
  background: var(--bg-warm);
  padding: 56px 48px;
  position: relative;
  overflow: hidden;
  border-radius: 16px;
">
  <!-- 编号 -->
  <div style="
    font-family: 'Fraunces', serif;
    font-style: italic;
    font-size: clamp(3rem, 8vw, 7rem);
    color: var(--brown);
    opacity: 0.12;
    position: absolute;
    top: 20px; right: 30px;
    line-height: 1;
    pointer-events: none;
  ">01</div>

  <!-- 小标题 -->
  <div style="
    display: inline-flex;
    align-items: center;
    gap: 8px;
    margin-bottom: 20px;
  ">
    <span style="
      width: 8px; height: 8px;
      background: var(--yellow);
      border-radius: 50%;
    "></span>
    <span style="
      font-size: 0.78rem;
      color: var(--blue);
      letter-spacing: 0.08em;
    ">CHAPTER ONE</span>
  </div>

  <!-- 标题 -->
  <h2 style="
    font-family: 'Noto Serif SC', serif;
    font-size: clamp(1.8rem, 4vw, 2.4rem);
    color: var(--ink);
    line-height: 1.3;
    margin: 0 0 24px 0;
  ">
    清晨的<span style="
      background: linear-gradient(180deg, transparent 55%, rgba(240,198,116,0.35) 55%);
      padding: 0 4px;
    ">筑地市场</span>
  </h2>

  <!-- 正文 -->
  <p style="
    font-size: 1.05rem;
    color: var(--ink-light);
    line-height: 1.8;
    margin: 0 0 20px 0;
  ">
    凌晨五点的筑地市场已经热闹非凡。金枪鱼拍卖的吆喝声、刀具碰撞的清脆声、新鲜海产的咸腥味，构成了东京最真实的清晨。
  </p>

  <p style="
    font-size: 1.05rem;
    color: var(--ink-light);
    line-height: 1.8;
    margin: 0 0 28px 0;
  ">
    一碗热腾腾的海鲜丼，配上手打芥末，是最地道的东京味道。
  </p>

  <!-- 棕色高亮块（替代原蓝色） -->
  <div style="
    background: rgba(166,123,91,0.1);
    border-left: 4px solid var(--brown);
    padding: 16px 20px;
    border-radius: 0 8px 8px 0;
    margin-bottom: 24px;
  ">
    <p style="
      font-size: 0.9rem;
      color: var(--brown);
      margin: 0;
      line-height: 1.6;
    ">
      <strong>旅行小贴士：</strong>筑地市场周日和周三休市，建议早上6点前到达，避开游客高峰。
    </p>
  </div>

  <!-- 底部署名 -->
  <div style="
    position: absolute;
    bottom: 40px; left: 48px;
    font-size: 0.78rem;
    color: var(--ink-light);
  ">
    @ 花心小泡泡
  </div>
</div>
```

### 品牌三色比例卡（6:3:1）

展示品牌三色比例关系的卡片。

```html
<div style="
  width: 100%;
  aspect-ratio: 3 / 4;
  background: var(--bg-warm);
  padding: 56px 48px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  border-radius: 16px;
">
  <div style="
    font-size: 0.78rem;
    color: var(--blue);
    letter-spacing: 0.08em;
    margin-bottom: 28px;
  ">BRAND COLORS</div>

  <!-- 棕色 60% -->
  <div style="
    display: flex;
    align-items: center;
    gap: 16px;
    margin-bottom: 16px;
  ">
    <div style="
      width: 60%;
      height: 48px;
      background: var(--brown);
      border-radius: 8px;
      display: flex;
      align-items: center;
      padding-left: 20px;
    ">
      <span style="color: #FDF8F0; font-family: 'Fira Code', monospace; font-size: 0.85rem;">#A67B5B</span>
    </div>
    <span style="font-size: 0.9rem; color: var(--ink-light);">60%</span>
  </div>

  <!-- 黄色 30% -->
  <div style="
    display: flex;
    align-items: center;
    gap: 16px;
    margin-bottom: 16px;
  ">
    <div style="
      width: 30%;
      height: 48px;
      background: var(--yellow);
      border-radius: 8px;
      display: flex;
      align-items: center;
      padding-left: 20px;
    ">
      <span style="color: var(--ink); font-family: 'Fira Code', monospace; font-size: 0.85rem;">#F0C674</span>
    </div>
    <span style="font-size: 0.9rem; color: var(--ink-light);">30%</span>
  </div>

  <!-- 蓝色 10% -->
  <div style="
    display: flex;
    align-items: center;
    gap: 16px;
    margin-bottom: 32px;
  ">
    <div style="
      width: 10%;
      height: 48px;
      background: var(--blue);
      border-radius: 8px;
      display: flex;
      align-items: center;
      padding-left: 12px;
    ">
      <span style="color: #FDF8F0; font-family: 'Fira Code', monospace; font-size: 0.78rem;">#5B8B</span>
    </div>
    <span style="font-size: 0.9rem; color: var(--ink-light);">10%</span>
  </div>

  <!-- 说明 -->
  <p style="
    font-size: 0.9rem;
    color: var(--ink-light);
    line-height: 1.6;
    margin: 0;
  ">
    主色60% · 强调色30% · 点缀色10%<br>
    点缀色永远是点缀，不做主色
  </p>
</div>
```

### 总结卡片（Summary Card）

整组图文的最后一张，用于总结和CTA。

```html
<div style="
  width: 100%;
  aspect-ratio: 3 / 4;
  background: var(--bg-alt);
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center;
  padding: 60px 48px;
  border-radius: 16px;
  position: relative;
  overflow: hidden;
">
  <!-- 水彩光斑 -->
  <div style="
    position: absolute;
    width: 300px; height: 300px;
    background:
      radial-gradient(ellipse at 30% 40%, rgba(240,198,116,0.1) 0%, transparent 50%),
      radial-gradient(ellipse at 70% 60%, rgba(166,123,91,0.06) 0%, transparent 50%);
    border-radius: 50%;
    top: -50px; right: -50px;
    pointer-events: none;
  "></div>

  <div style="position: relative; z-index: 1;">
    <div style="
      font-family: 'Fraunces', serif;
      font-style: italic;
      font-size: 2rem;
      color: var(--brown);
      margin-bottom: 16px;
    ">Bubble</div>

    <h2 style="
      font-family: 'Noto Serif SC', serif;
      font-size: 1.6rem;
      color: var(--ink);
      margin: 0 0 16px 0;
    ">感谢阅读</h2>

    <p style="
      font-size: 0.95rem;
      color: var(--ink-light);
      line-height: 1.7;
      max-width: 340px;
      margin: 0 0 28px 0;
    ">
      花心小泡泡 · 体验生活，感受体验，记录感受
    </p>

    <div style="
      display: inline-block;
      padding: 12px 32px;
      background: var(--brown);
      color: #FDF8F0;
      border-radius: 999px;
      font-size: 0.9rem;
      font-weight: 600;
      margin-bottom: 24px;
    ">Follow 在下 花心泡</div>

    <div style="
      font-size: 0.78rem;
      color: var(--ink-light);
      opacity: 0.7;
    ">更多旅行笔记，持续更新中</div>
  </div>
</div>
```

---

## 🖌️ 卡片排版手法

### 手法1：大标题居中 + 底部分割

```html
<div style="
  width: 100%;
  aspect-ratio: 3 / 4;
  background: var(--bg-warm);
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  padding: 48px;
  border-radius: 16px;
">
  <div style="text-align: center; flex: 1; display: flex; flex-direction: column; justify-content: center;">
    <h2 style="
      font-family: 'Noto Serif SC', serif;
      font-size: 2.2rem;
      color: var(--ink);
      line-height: 1.4;
      margin: 0;
    ">标题内容</h2>
    <p style="color: var(--ink-light); margin-top: 16px;">副标题说明</p>
  </div>
  <hr style="
    border: none;
    height: 1px;
    background: linear-gradient(90deg, transparent, var(--yellow), transparent);
  ">
  <div style="
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding-top: 16px;
    font-size: 0.78rem;
    color: var(--ink-light);
  ">
    <span>@ 花心小泡泡</span>
    <span>01/05</span>
  </div>
</div>
```

### 手法2：左文右图（左右分栏）

```html
<div style="
  width: 100%;
  aspect-ratio: 3 / 4;
  background: var(--bg-warm);
  display: flex;
  padding: 0;
  border-radius: 16px;
  overflow: hidden;
">
  <!-- 左侧文字 -->
  <div style="
    flex: 1;
    padding: 48px 36px;
    display: flex;
    flex-direction: column;
    justify-content: center;
  ">
    <h3 style="
      font-family: 'Noto Serif SC', serif;
      font-size: 1.5rem;
      color: var(--ink);
      margin: 0 0 16px 0;
    ">标题</h3>
    <p style="
      font-size: 0.95rem;
      color: var(--ink-light);
      line-height: 1.7;
      margin: 0;
    ">内容描述文字，简洁有力地传达核心信息。</p>
  </div>
  <!-- 右侧图片/色块 -->
  <div style="
    flex: 1;
    background: var(--bg-alt);
    display: flex;
    align-items: center;
    justify-content: center;
    position: relative;
  ">
    <div style="
      width: 120px; height: 120px;
      border: 2px dashed var(--yellow);
      border-radius: 50%;
      opacity: 0.4;
    "></div>
  </div>
</div>
```

### 手法3：编号列表 + 左侧色条

```html
<div style="
  width: 100%;
  aspect-ratio: 3 / 4;
  background: var(--bg-warm);
  padding: 48px;
  border-radius: 16px;
">
  <h2 style="
    font-family: 'Noto Serif SC', serif;
    font-size: 1.6rem;
    color: var(--ink);
    margin: 0 0 32px 0;
  ">三步开启<span style="color: var(--brown);">旅程</span></h2>

  <div style="display: flex; flex-direction: column; gap: 24px;">
    <div style="
      display: flex;
      align-items: flex-start;
      gap: 16px;
    ">
      <span style="
        display: flex;
        align-items: center;
        justify-content: center;
        width: 36px; height: 36px;
        background: var(--brown);
        color: #FDF8F0;
        border-radius: 50%;
        font-family: 'Fraunces', serif;
        font-style: italic;
        font-size: 1rem;
        font-weight: 700;
        flex-shrink: 0;
      ">1</span>
      <div style="
        border-left: 3px solid var(--yellow);
        padding-left: 16px;
      ">
        <strong style="display: block; color: var(--ink); margin-bottom: 4px;">选择目的地</strong>
        <span style="font-size: 0.85rem; color: var(--ink-light);">从愿望清单中挑选你的下一站</span>
      </div>
    </div>

    <div style="
      display: flex;
      align-items: flex-start;
      gap: 16px;
    ">
      <span style="
        display: flex;
        align-items: center;
        justify-content: center;
        width: 36px; height: 36px;
        background: var(--brown);
        color: #FDF8F0;
        border-radius: 50%;
        font-family: 'Fraunces', serif;
        font-style: italic;
        font-size: 1rem;
        font-weight: 700;
        flex-shrink: 0;
      ">2</span>
      <div style="
        border-left: 3px solid var(--yellow);
        padding-left: 16px;
      ">
        <strong style="display: block; color: var(--ink); margin-bottom: 4px;">规划路线</strong>
        <span style="font-size: 0.85rem; color: var(--ink-light);">用地图标记想去的每一个角落</span>
      </div>
    </div>

    <div style="
      display: flex;
      align-items: flex-start;
      gap: 16px;
    ">
      <span style="
        display: flex;
        align-items: center;
        justify-content: center;
        width: 36px; height: 36px;
        background: var(--brown);
        color: #FDF8F0;
        border-radius: 50%;
        font-family: 'Fraunces', serif;
        font-style: italic;
        font-size: 1rem;
        font-weight: 700;
        flex-shrink: 0;
      ">3</span>
      <div style="
        border-left: 3px solid var(--yellow);
        padding-left: 16px;
      ">
        <strong style="display: block; color: var(--ink); margin-bottom: 4px;">出发记录</strong>
        <span style="font-size: 0.85rem; color: var(--ink-light);">带上相机和笔记本，记录每一个瞬间</span>
      </div>
    </div>
  </div>
</div>
```

### 手法4：引用/金句卡片

```html
<div style="
  width: 100%;
  aspect-ratio: 3 / 4;
  background: var(--bg-warm);
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center;
  padding: 60px 48px;
  border-radius: 16px;
  position: relative;
">
  <!-- 大引号装饰 -->
  <div style="
    font-family: 'Fraunces', serif;
    font-size: 8rem;
    color: var(--brown);
    opacity: 0.1;
    line-height: 1;
    position: absolute;
    top: 40px; left: 40px;
    pointer-events: none;
  ">"</div>

  <blockquote style="
    font-family: 'Noto Serif SC', serif;
    font-size: clamp(1.4rem, 3vw, 1.8rem);
    color: var(--ink);
    line-height: 1.6;
    margin: 0 0 24px 0;
    position: relative;
    z-index: 1;
  ">
    旅行不是为了到达目的地，<br>
    而是为了在路上<span style="
      background: linear-gradient(180deg, transparent 55%, rgba(240,198,116,0.35) 55%);
      padding: 0 4px;
    ">发现自己</span>。
  </blockquote>

  <div style="
    font-size: 0.85rem;
    color: var(--ink-light);
    position: relative;
    z-index: 1;
  ">— 花心小泡泡</div>
</div>
```

### 手法5：大透明数字 + 文字叠加

```html
<div style="
  width: 100%;
  aspect-ratio: 3 / 4;
  background: var(--bg-warm);
  padding: 48px;
  position: relative;
  overflow: hidden;
  border-radius: 16px;
">
  <!-- 超大透明数字 -->
  <div style="
    font-family: 'Fraunces', serif;
    font-style: italic;
    font-size: 12rem;
    color: var(--brown);
    opacity: 0.08;
    line-height: 0.8;
    position: absolute;
    bottom: -30px; right: -20px;
    pointer-events: none;
  ">03</div>

  <div style="position: relative; z-index: 1;">
    <h2 style="
      font-family: 'Noto Serif SC', serif;
      font-size: 1.8rem;
      color: var(--ink);
      margin: 0 0 20px 0;
    ">第三章</h2>
    <p style="
      font-size: 1rem;
      color: var(--ink-light);
      line-height: 1.8;
      margin: 0;
    ">正文内容区域，与背景数字形成层次对比。</p>
  </div>
</div>
```

---

## 🎯 卡片页面自检清单

### P0（必须过）
- [ ] 3:4比例正确
- [ ] **禁止深色底**（`#1E1A16` 不可用于卡片场景）
- [ ] 三色比例正确（棕60% + 黄30% + 蓝10%）
- [ ] 封面边框使用黄色 `#F0C674`
- [ ] 棕色高亮块使用 `#A67B5B`（替代原蓝色）
- [ ] 署名：花心小泡泡
- [ ] CTA：Follow 在下 花心泡
- [ ] 签名档：花心小泡泡 · 体验生活，感受体验，记录感受

### P1（应过）
- [ ] 每张卡片使用不同的排版手法
- [ ] 有封面卡 + 正文卡 + 总结卡的完整结构
- [ ] 文字字号对比极端
- [ ] 有至少一种装饰元素

### P2（加分）
- [ ] 有品牌三色比例展示卡
- [ ] 有金句/引用卡
- [ ] 有旅行主题装饰（机票/邮票/拍立得）
- [ ] 有手绘彩铅感装饰
- [ ] 整体看起来不像AI生成的

---

## 📝 品牌信息

- **署名**: 花心小泡泡 / Bubble
- **签名档**: 花心小泡泡 · 体验生活，感受体验，记录感受
- **CTA**: Follow 在下 花心泡

---

*This scene file builds on top of brand-dna.md. Always reference brand-dna.md for the full brand specification.*
