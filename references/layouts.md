# Layouts / 布局库

> 16种布局模式，为每个Section分配不同布局。每个Section布局必须不同。

---

## CSS变量声明（所有布局共用）

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

## 布局1：Hero Split（左右分栏）

```html
<section style="
  display: flex;
  align-items: center;
  gap: clamp(40px, 6vw, 80px);
  min-height: 80vh;
  padding: clamp(60px, 10vh, 120px) clamp(20px, 4vw, 60px);
  background: var(--bg-warm);
  max-width: 1300px;
  margin: 0 auto;
">
  <div style="flex: 1;">
    <div style="
      font-size: 0.85rem;
      color: var(--blue);
      text-transform: uppercase;
      letter-spacing: 0.15em;
      margin-bottom: 16px;
    ">SUBTITLE</div>
    <h1 style="
      font-family: 'Noto Serif SC', serif;
      font-size: clamp(2.8rem, 7vw, 5.5rem);
      color: var(--ink);
      line-height: 1.15;
      margin: 0 0 20px 0;
    ">
      大标题<span style="color: var(--brown);">关键词</span>
    </h1>
    <p style="
      font-size: 1.05rem;
      color: var(--ink-light);
      line-height: 1.7;
      max-width: 480px;
      margin-bottom: 32px;
    ">副标题或描述文字。</p>
    <div style="display: flex; gap: 16px; flex-wrap: wrap;">
      <a href="#" style="
        display: inline-flex; align-items: center; gap: 8px;
        padding: 14px 32px;
        background: var(--brown);
        color: #FDF8F0;
        font-weight: 600;
        border-radius: 8px;
        text-decoration: none;
      ">CTA按钮 →</a>
    </div>
  </div>
  <div style="flex: 1; position: relative; min-height: 400px;">
    <div style="
      position: absolute;
      width: 500px; height: 500px;
      background: radial-gradient(ellipse, rgba(240,198,116,0.12), transparent 70%);
      top: -50px; right: -100px;
      pointer-events: none;
    "></div>
    <div style="
      width: 300px; height: 300px;
      border: 2.5px dashed var(--yellow);
      border-radius: 50%;
      opacity: 0.25;
      position: absolute;
      top: 10%; right: 5%;
    "></div>
  </div>
</section>
```

---

## 布局2：Hero Centered（居中）

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
    position: absolute;
    width: 600px; height: 600px;
    background: radial-gradient(ellipse, rgba(240,198,116,0.1), transparent 70%);
    top: -100px; left: 50%;
    transform: translateX(-50%);
    pointer-events: none;
  "></div>
  <div style="
    font-size: 0.85rem;
    color: var(--blue);
    text-transform: uppercase;
    letter-spacing: 0.15em;
    margin-bottom: 20px;
  ">SUBTITLE</div>
  <h1 style="
    font-family: 'Noto Serif SC', serif;
    font-size: clamp(2.8rem, 7vw, 5.5rem);
    color: var(--ink);
    line-height: 1.2;
    margin: 0 0 20px 0;
    max-width: 800px;
  ">
    大标题<br><span style="color: var(--brown);">关键词</span>
  </h1>
  <p style="
    font-size: 1.05rem;
    color: var(--ink-light);
    line-height: 1.7;
    max-width: 540px;
    margin-bottom: 36px;
  ">描述文字。</p>
  <a href="#" style="
    display: inline-flex; align-items: center; gap: 8px;
    padding: 16px 40px;
    background: var(--brown);
    color: #FDF8F0;
    font-size: 1.05rem;
    font-weight: 600;
    border-radius: 8px;
    text-decoration: none;
  ">CTA按钮 →</a>
</section>
```

---

## 布局3：Grid 2-Column Cards

```html
<section style="
  padding: clamp(80px, 12vh, 160px) clamp(20px, 4vw, 60px);
  background: var(--bg-alt);
  max-width: 1300px;
  margin: 0 auto;
">
  <h2 style="
    text-align: center;
    font-family: 'Noto Serif SC', serif;
    font-size: clamp(1.6rem, 4vw, 2.6rem);
    color: var(--ink);
    margin: 0 0 clamp(40px, 6vw, 80px) 0;
  ">Section<span style="color: var(--brown);">标题</span></h2>

  <div style="
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: clamp(24px, 3vw, 48px);
  ">
    <div style="
      background: var(--bg-warm);
      border-radius: 12px;
      padding: clamp(28px, 3vw, 44px);
      border: 1px solid rgba(166,123,91,0.12);
    ">
      <h3 style="
        font-family: 'Noto Serif SC', serif;
        color: var(--brown);
        margin: 0 0 12px 0;
      ">卡片标题</h3>
      <p style="color: var(--ink-light); line-height: 1.7; margin: 0;">卡片内容描述。</p>
    </div>
    <div style="
      background: var(--bg-warm);
      border-radius: 12px;
      padding: clamp(28px, 3vw, 44px);
      border: 1px solid rgba(166,123,91,0.12);
    ">
      <h3 style="
        font-family: 'Noto Serif SC', serif;
        color: var(--brown);
        margin: 0 0 12px 0;
      ">卡片标题</h3>
      <p style="color: var(--ink-light); line-height: 1.7; margin: 0;">卡片内容描述。</p>
    </div>
  </div>
</section>
```

---

## 布局4：Grid 3-Column Cards

```html
<section style="
  padding: clamp(80px, 12vh, 160px) clamp(20px, 4vw, 60px);
  background: var(--bg-warm);
  max-width: 1300px;
  margin: 0 auto;
">
  <h2 style="
    text-align: center;
    font-family: 'Noto Serif SC', serif;
    font-size: clamp(1.6rem, 4vw, 2.6rem);
    color: var(--ink);
    margin: 0 0 clamp(40px, 6vw, 80px) 0;
  ">Section<span style="color: var(--brown);">标题</span></h2>

  <div style="
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: clamp(24px, 3vw, 48px);
  ">
    <div style="
      background: var(--bg-alt);
      border-radius: 12px;
      padding: clamp(28px, 3vw, 44px);
      text-align: center;
    ">
      <div style="
        width: 48px; height: 48px;
        background: rgba(240,198,116,0.25);
        border-radius: 12px;
        display: flex; align-items: center; justify-content: center;
        margin: 0 auto 20px;
        font-size: 1.4rem;
      ">①</div>
      <h3 style="
        font-family: 'Noto Serif SC', serif;
        color: var(--brown);
        margin: 0 0 12px 0;
      ">标题</h3>
      <p style="color: var(--ink-light); line-height: 1.6; margin: 0; font-size: 0.92rem;">描述文字。</p>
    </div>
    <div style="
      background: var(--bg-alt);
      border-radius: 12px;
      padding: clamp(28px, 3vw, 44px);
      text-align: center;
    ">
      <div style="
        width: 48px; height: 48px;
        background: rgba(240,198,116,0.25);
        border-radius: 12px;
        display: flex; align-items: center; justify-content: center;
        margin: 0 auto 20px;
        font-size: 1.4rem;
      ">②</div>
      <h3 style="
        font-family: 'Noto Serif SC', serif;
        color: var(--brown);
        margin: 0 0 12px 0;
      ">标题</h3>
      <p style="color: var(--ink-light); line-height: 1.6; margin: 0; font-size: 0.92rem;">描述文字。</p>
    </div>
    <div style="
      background: var(--bg-alt);
      border-radius: 12px;
      padding: clamp(28px, 3vw, 44px);
      text-align: center;
    ">
      <div style="
        width: 48px; height: 48px;
        background: rgba(240,198,116,0.25);
        border-radius: 12px;
        display: flex; align-items: center; justify-content: center;
        margin: 0 auto 20px;
        font-size: 1.4rem;
      ">③</div>
      <h3 style="
        font-family: 'Noto Serif SC', serif;
        color: var(--brown);
        margin: 0 0 12px 0;
      ">标题</h3>
      <p style="color: var(--ink-light); line-height: 1.6; margin: 0; font-size: 0.92rem;">描述文字。</p>
    </div>
  </div>
</section>
```

---

## 布局5：Alternating Rows（交替行）

```html
<section style="
  padding: clamp(80px, 12vh, 160px) clamp(20px, 4vw, 60px);
  background: var(--bg-warm);
  max-width: 1300px;
  margin: 0 auto;
  display: flex;
  flex-direction: column;
  gap: clamp(40px, 6vw, 100px);
">
  <!-- 行1：文字左 + 图片右 -->
  <div style="
    display: flex;
    align-items: center;
    gap: clamp(40px, 6vw, 80px);
  ">
    <div style="flex: 1;">
      <span style="
        display: inline-block;
        padding: 3px 12px;
        background: rgba(240,198,116,0.2);
        color: var(--ink-light);
        border-radius: 999px;
        font-size: 0.78rem;
        margin-bottom: 12px;
      ">步骤 01</span>
      <h3 style="
        font-family: 'Noto Serif SC', serif;
        font-size: 1.5rem;
        color: var(--ink);
        margin: 0 0 12px 0;
      ">标题</h3>
      <p style="color: var(--ink-light); line-height: 1.7; margin: 0;">描述文字。</p>
    </div>
    <div style="
      flex: 1;
      height: 320px;
      background: var(--bg-alt);
      border-radius: 12px;
      display: flex; align-items: center; justify-content: center;
    ">
      <span style="color: var(--ink-light);">[图片/插图]</span>
    </div>
  </div>

  <!-- 行2：图片左 + 文字右 -->
  <div style="
    display: flex;
    align-items: center;
    gap: clamp(40px, 6vw, 80px);
    flex-direction: row-reverse;
  ">
    <div style="flex: 1;">
      <span style="
        display: inline-block;
        padding: 3px 12px;
        background: rgba(240,198,116,0.2);
        color: var(--ink-light);
        border-radius: 999px;
        font-size: 0.78rem;
        margin-bottom: 12px;
      ">步骤 02</span>
      <h3 style="
        font-family: 'Noto Serif SC', serif;
        font-size: 1.5rem;
        color: var(--ink);
        margin: 0 0 12px 0;
      ">标题</h3>
      <p style="color: var(--ink-light); line-height: 1.7; margin: 0;">描述文字。</p>
    </div>
    <div style="
      flex: 1;
      height: 320px;
      background: var(--bg-alt);
      border-radius: 12px;
      display: flex; align-items: center; justify-content: center;
    ">
      <span style="color: var(--ink-light);">[图片/插图]</span>
    </div>
  </div>
</section>
```

---

## 布局6：Full-width Text（全宽文字）

```html
<section style="
  padding: clamp(80px, 12vh, 160px) clamp(20px, 4vw, 60px);
  background: var(--bg-warm);
  max-width: 800px;
  margin: 0 auto;
">
  <h2 style="
    font-family: 'Noto Serif SC', serif;
    font-size: clamp(1.6rem, 4vw, 2.6rem);
    color: var(--ink);
    margin: 0 0 24px 0;
  ">
    Section<span style="color: var(--brown);">标题</span>
  </h2>
  <p style="
    font-size: 1.05rem;
    color: var(--ink-light);
    line-height: 1.9;
    margin: 0 0 20px 0;
  ">正文段落内容，保持适当的行距和段落间距，让长文本阅读起来舒适。</p>
  <p style="
    font-size: 1.05rem;
    color: var(--ink-light);
    line-height: 1.9;
    margin: 0;
  ">第二段正文内容。</p>
</section>
```

---

## 布局7：Split Code + Preview（代码+预览）

```html
<section style="
  padding: clamp(80px, 12vh, 160px) clamp(20px, 4vw, 60px);
  background: var(--bg-alt);
  max-width: 1300px;
  margin: 0 auto;
">
  <div style="
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: clamp(24px, 3vw, 48px);
  ">
    <!-- 代码块 -->
    <div style="
      background: var(--panel-dark);
      border-radius: 12px;
      padding: 28px;
      font-family: 'Fira Code', monospace;
      font-size: 0.85rem;
      line-height: 1.7;
      color: rgba(245,237,224,0.85);
      overflow-x: auto;
    ">
<pre style="margin: 0;"><code>// 代码示例
function hello() {
  console.log("Hello, Bubble!");
}</code></pre>
    </div>
    <!-- 预览 -->
    <div style="
      background: var(--bg-warm);
      border-radius: 12px;
      padding: 28px;
      display: flex;
      align-items: center;
      justify-content: center;
      border: 1px solid rgba(166,123,91,0.12);
    ">
      <span style="color: var(--ink-light);">[预览区域]</span>
    </div>
  </div>
</section>
```

---

## 布局8：Stats Row（数据行）

```html
<section style="
  padding: clamp(80px, 12vh, 160px) clamp(20px, 4vw, 60px);
  background: var(--bg-warm);
  max-width: 1300px;
  margin: 0 auto;
">
  <div style="
    display: flex;
    justify-content: center;
    gap: clamp(40px, 8vw, 100px);
    flex-wrap: wrap;
    text-align: center;
  ">
    <div>
      <div style="
        font-family: 'Fraunces', serif;
        font-style: italic;
        font-size: clamp(2.5rem, 5vw, 3.5rem);
        color: var(--brown);
        line-height: 1;
      ">128</div>
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
      ">37</div>
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

## 布局9：Timeline（时间线）

```html
<section style="
  padding: clamp(80px, 12vh, 160px) clamp(20px, 4vw, 60px);
  background: var(--bg-warm);
  max-width: 800px;
  margin: 0 auto;
">
  <h2 style="
    text-align: center;
    font-family: 'Noto Serif SC', serif;
    font-size: clamp(1.6rem, 4vw, 2.6rem);
    color: var(--ink);
    margin: 0 0 clamp(40px, 6vw, 80px) 0;
  ">时间<span style="color: var(--brown);">线</span></h2>

  <div style="position: relative; padding-left: 32px;">
    <!-- 竖线 -->
    <div style="
      position: absolute;
      left: 11px; top: 0; bottom: 0;
      width: 2px;
      background: linear-gradient(180deg, var(--yellow), var(--brown), var(--blue));
    "></div>

    <!-- 节点1 -->
    <div style="position: relative; margin-bottom: 40px;">
      <div style="
        position: absolute;
        left: -27px; top: 4px;
        width: 14px; height: 14px;
        background: var(--brown);
        border-radius: 50%;
        border: 3px solid var(--bg-warm);
        box-shadow: 0 0 0 3px var(--brown);
      "></div>
      <div style="font-size: 0.78rem; color: var(--blue); margin-bottom: 4px;">2024.03</div>
      <h3 style="
        font-family: 'Noto Serif SC', serif;
        color: var(--ink);
        margin: 0 0 8px 0;
      ">东京之旅</h3>
      <p style="color: var(--ink-light); font-size: 0.92rem; line-height: 1.6; margin: 0;">描述内容。</p>
    </div>

    <!-- 节点2 -->
    <div style="position: relative; margin-bottom: 40px;">
      <div style="
        position: absolute;
        left: -27px; top: 4px;
        width: 14px; height: 14px;
        background: var(--yellow);
        border-radius: 50%;
        border: 3px solid var(--bg-warm);
        box-shadow: 0 0 0 3px var(--yellow);
      "></div>
      <div style="font-size: 0.78rem; color: var(--blue); margin-bottom: 4px;">2024.06</div>
      <h3 style="
        font-family: 'Noto Serif SC', serif;
        color: var(--ink);
        margin: 0 0 8px 0;
      ">京都漫步</h3>
      <p style="color: var(--ink-light); font-size: 0.92rem; line-height: 1.6; margin: 0;">描述内容。</p>
    </div>

    <!-- 节点3 -->
    <div style="position: relative;">
      <div style="
        position: absolute;
        left: -27px; top: 4px;
        width: 14px; height: 14px;
        background: var(--blue);
        border-radius: 50%;
        border: 3px solid var(--bg-warm);
        box-shadow: 0 0 0 3px var(--blue);
      "></div>
      <div style="font-size: 0.78rem; color: var(--blue); margin-bottom: 4px;">2024.12</div>
      <h3 style="
        font-family: 'Noto Serif SC', serif;
        color: var(--ink);
        margin: 0 0 8px 0;
      ">北海道之冬</h3>
      <p style="color: var(--ink-light); font-size: 0.92rem; line-height: 1.6; margin: 0;">描述内容。</p>
    </div>
  </div>
</section>
```

---

## 布局10：Banner（横幅CTA）

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
  ">准备好开始<span style="color: var(--brown);">旅程</span>了吗？</h2>
  <p style="
    font-size: 1rem;
    color: var(--ink-light);
    margin-bottom: 32px;
  ">花心小泡泡 · 体验生活，感受体验，记录感受</p>
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

## 布局11：Dark Panel（暗色面板）

```html
<section style="
  padding: clamp(80px, 12vh, 160px) clamp(20px, 4vw, 60px);
  background: var(--panel-dark);
  color: #F5EDE0;
  position: relative;
  overflow: hidden;
">
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
    ">描述文字在暗色背景中呈现。</p>
    <a href="#" style="
      display: inline-flex; align-items: center; gap: 8px;
      padding: 14px 32px;
      background: var(--yellow);
      color: var(--ink);
      font-weight: 600;
      border-radius: 8px;
      text-decoration: none;
    ">行动按钮 →</a>
  </div>
</section>
```

---

## 布局12：Masonry Grid（瀑布流）

```html
<section style="
  padding: clamp(80px, 12vh, 160px) clamp(20px, 4vw, 60px);
  background: var(--bg-warm);
  max-width: 1300px;
  margin: 0 auto;
">
  <h2 style="
    text-align: center;
    font-family: 'Noto Serif SC', serif;
    font-size: clamp(1.6rem, 4vw, 2.6rem);
    color: var(--ink);
    margin: 0 0 clamp(40px, 6vw, 80px) 0;
  ">作品<span style="color: var(--brown);">展示</span></h2>

  <div style="
    column-count: 3;
    column-gap: clamp(20px, 3vw, 32px);
  ">
    <div style="
      break-inside: avoid;
      margin-bottom: clamp(20px, 3vw, 32px);
      background: var(--bg-alt);
      border-radius: 12px;
      padding: 28px;
      border: 1px solid rgba(166,123,91,0.12);
    ">
      <h3 style="
        font-family: 'Noto Serif SC', serif;
        color: var(--brown);
        margin: 0 0 8px 0;
      ">卡片1</h3>
      <p style="color: var(--ink-light); font-size: 0.9rem; line-height: 1.6; margin: 0;">内容描述。</p>
    </div>
    <div style="
      break-inside: avoid;
      margin-bottom: clamp(20px, 3vw, 32px);
      background: var(--bg-alt);
      border-radius: 12px;
      padding: 28px;
      border: 1px solid rgba(166,123,91,0.12);
    ">
      <h3 style="
        font-family: 'Noto Serif SC', serif;
        color: var(--brown);
        margin: 0 0 8px 0;
      ">卡片2</h3>
      <p style="color: var(--ink-light); font-size: 0.9rem; line-height: 1.6; margin: 0;">较长的内容描述，展示瀑布流的高度差异。</p>
    </div>
    <div style="
      break-inside: avoid;
      margin-bottom: clamp(20px, 3vw, 32px);
      background: var(--bg-alt);
      border-radius: 12px;
      padding: 28px;
      border: 1px solid rgba(166,123,91,0.12);
    ">
      <h3 style="
        font-family: 'Noto Serif SC', serif;
        color: var(--brown);
        margin: 0 0 8px 0;
      ">卡片3</h3>
      <p style="color: var(--ink-light); font-size: 0.9rem; line-height: 1.6; margin: 0;">内容描述。</p>
    </div>
  </div>
</section>
```

---

## 布局13：Sidebar + Content（侧边栏+内容）

```html
<section style="
  padding: clamp(80px, 12vh, 160px) clamp(20px, 4vw, 60px);
  background: var(--bg-warm);
  max-width: 1300px;
  margin: 0 auto;
  display: flex;
  gap: clamp(40px, 6vw, 80px);
">
  <!-- 侧边栏 -->
  <aside style="
    width: 240px;
    flex-shrink: 0;
  ">
    <div style="
      background: var(--bg-alt);
      border-radius: 12px;
      padding: 24px;
      position: sticky;
      top: 24px;
    ">
      <h4 style="
        font-family: 'Noto Serif SC', serif;
        color: var(--brown);
        margin: 0 0 16px 0;
      ">目录</h4>
      <nav style="display: flex; flex-direction: column; gap: 10px;">
        <a href="#" style="
          color: var(--ink);
          text-decoration: none;
          font-size: 0.9rem;
          padding: 6px 10px;
          border-radius: 6px;
          background: rgba(240,198,116,0.15);
        ">第一章</a>
        <a href="#" style="
          color: var(--ink-light);
          text-decoration: none;
          font-size: 0.9rem;
          padding: 6px 10px;
          border-radius: 6px;
        ">第二章</a>
        <a href="#" style="
          color: var(--ink-light);
          text-decoration: none;
          font-size: 0.9rem;
          padding: 6px 10px;
          border-radius: 6px;
        ">第三章</a>
      </nav>
    </div>
  </aside>

  <!-- 主内容 -->
  <main style="flex: 1; min-width: 0;">
    <article>
      <h2 style="
        font-family: 'Noto Serif SC', serif;
        font-size: clamp(1.6rem, 4vw, 2.6rem);
        color: var(--ink);
        margin: 0 0 24px 0;
      ">文章<span style="color: var(--brown);">标题</span></h2>
      <p style="
        font-size: 1.05rem;
        color: var(--ink-light);
        line-height: 1.9;
        margin: 0 0 20px 0;
      ">正文内容...</p>
    </article>
  </main>
</section>
```

---

## 布局14：Gallery / 画廊

```html
<section style="
  padding: clamp(80px, 12vh, 160px) clamp(20px, 4vw, 60px);
  background: var(--bg-alt);
  max-width: 1300px;
  margin: 0 auto;
">
  <div style="
    display: grid;
    grid-template-columns: 2fr 1fr 1fr;
    grid-template-rows: 200px 200px;
    gap: 16px;
  ">
    <div style="
      grid-row: span 2;
      background: var(--bg-warm);
      border-radius: 12px;
      display: flex; align-items: center; justify-content: center;
      border: 2px solid var(--yellow);
    "><span style="color: var(--ink-light);">大图</span></div>
    <div style="
      background: var(--bg-warm);
      border-radius: 12px;
      display: flex; align-items: center; justify-content: center;
      border: 1px solid rgba(166,123,91,0.12);
    "><span style="color: var(--ink-light);">图片2</span></div>
    <div style="
      background: var(--bg-warm);
      border-radius: 12px;
      display: flex; align-items: center; justify-content: center;
      border: 1px solid rgba(166,123,91,0.12);
    "><span style="color: var(--ink-light);">图片3</span></div>
    <div style="
      grid-column: span 2;
      background: var(--bg-warm);
      border-radius: 12px;
      display: flex; align-items: center; justify-content: center;
      border: 1px solid rgba(166,123,91,0.12);
    "><span style="color: var(--ink-light);">图片4</span></div>
  </div>
</section>
```

---

## 布局15：Testimonial / 引用

```html
<section style="
  padding: clamp(80px, 12vh, 160px) clamp(20px, 4vw, 60px);
  background: var(--bg-warm);
  max-width: 800px;
  margin: 0 auto;
  text-align: center;
">
  <div style="
    font-family: 'Fraunces', serif;
    font-size: 6rem;
    color: var(--brown);
    opacity: 0.15;
    line-height: 1;
    margin-bottom: -30px;
  ">"</div>
  <blockquote style="
    font-family: 'Noto Serif SC', serif;
    font-size: clamp(1.2rem, 2.5vw, 1.6rem);
    color: var(--ink);
    line-height: 1.7;
    margin: 0 0 24px 0;
  ">
    旅行不是为了到达目的地，<br>
    而是为了在路上<span style="
      background: linear-gradient(180deg, transparent 55%, rgba(240,198,116,0.35) 55%);
      padding: 0 4px;
    ">发现自己</span>。
  </blockquote>
  <div style="
    font-size: 0.9rem;
    color: var(--ink-light);
  ">— 花心小泡泡</div>
</section>
```

---

## 布局16：Footer（页脚）

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
    <a href="#" style="
      color: rgba(245,237,224,0.5);
      text-decoration: none;
      font-size: 0.85rem;
    ">关于</a>
    <a href="#" style="
      color: rgba(245,237,224,0.5);
      text-decoration: none;
      font-size: 0.85rem;
    ">联系</a>
    <a href="#" style="
      color: rgba(245,237,224,0.5);
      text-decoration: none;
      font-size: 0.85rem;
    ">Follow 在下 花心泡</a>
  </div>
</footer>
```

---

## 📊 布局选择指南

| 场景类型 | 推荐布局组合 |
|----------|-------------|
| 教程页 | Hero Split → Sidebar+Content → Full-width Text → Split Code+Preview → Banner |
| Landing页 | Hero Centered → Grid 3-col → Alternating Rows → Stats Row → Dark Panel → Footer |
| App页 | Sidebar+Content → Grid 2-col → Timeline → Gallery → Footer |
| 作品集 | Hero Split → Masonry Grid → Gallery → Testimonial → Footer |
| 卡片组 | 每个卡片使用不同手法（参考 scene-cards.md） |

---

## ⚠️ 关键原则

- **每个Section必须使用不同布局**
- 布局1-16可以自由组合，但相邻Section不能重复
- 所有布局共用 `:root` CSS变量
- 响应式通过 `clamp()` 和 `grid-template-columns: repeat(auto-fit, ...)` 实现
- 移动端是"重新排列"不是"缩小"

---

*Layouts are the skeleton. Fill them with components from components.md.*
