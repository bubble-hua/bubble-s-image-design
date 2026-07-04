# Components / 组件库

> 所有可用组件的完整代码。**硬规则：禁止使用HTML默认样式。** 所有引用块、列表、表格、卡片必须从这里选用。绝不允许浏览器默认渲染。

---

## CSS变量声明（所有组件共用）

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

## #01 步骤编号 (Step Number)

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
  flex-shrink: 0;
">1</span>
```

---

## #02 关键词标签 (Tag)

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

---

## #03 Badge (棕色)

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

---

## #04 Badge (黄色)

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

---

## #05 高亮标注 (Highlight)

```html
<span class="highlight" style="
  background: linear-gradient(180deg, transparent 55%, rgba(240,198,116,0.35) 55%);
  padding: 0 4px;
">需要强调的内容</span>
```

---

## #06 提示框 Tip

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
  <strong style="color: var(--brown);">提示：</strong> 提示内容。
</div>
```

---

## #07 警告框 Warning

```html
<div class="callout callout-warning" style="
  border-left: 4px solid var(--blue);
  background: rgba(91,139,160,0.08);
  padding: 20px 24px;
  border-radius: 0 8px 8px 0;
  margin: 28px 0;
  font-size: 0.92rem;
  color: var(--ink-light);
">
  <strong style="color: var(--blue);">注意：</strong> 警告内容。
</div>
```

---

## #08 信息卡 (Info Card)

```html
<div class="info-card" style="
  background: var(--bg-warm);
  border: 1px solid rgba(166,123,91,0.2);
  border-radius: 12px;
  padding: 28px;
  margin: 28px 0;
">
  <h4 style="
    margin: 0 0 10px 0;
    color: var(--brown);
    font-family: 'Noto Serif SC', serif;
  ">概念名称</h4>
  <p style="
    margin: 0;
    color: var(--ink-light);
    line-height: 1.6;
  ">概念说明内容。</p>
</div>
```

---

## #09 棕色高亮块 (Brown Highlight Block)

```html
<div class="highlight-block" style="
  background: rgba(166,123,91,0.08);
  border-left: 4px solid var(--brown);
  padding: 16px 20px;
  border-radius: 0 8px 8px 0;
  margin: 24px 0;
">
  <p style="
    margin: 0;
    color: var(--brown);
    font-size: 0.92rem;
    line-height: 1.6;
  ">棕色高亮块内容。</p>
</div>
```

---

## #10 代码块 (Code Block)

```html
<div class="code-block" style="
  background: var(--panel-dark);
  color: rgba(245,237,224,0.85);
  border-radius: 10px;
  padding: 24px;
  margin: 24px 0;
  font-family: 'Fira Code', monospace;
  font-size: 0.85rem;
  line-height: 1.7;
  overflow-x: auto;
">
<pre style="margin: 0;"><code>// 你的代码
const greeting = "Hello, Bubble!";</code></pre>
</div>
```

---

## #11 终端窗口 (Terminal)

```html
<div style="
  background: var(--panel-dark);
  border-radius: 10px;
  overflow: hidden;
  font-family: 'Fira Code', monospace;
  margin: 24px 0;
">
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
    <span style="margin-left: 12px; font-size: 0.72rem; color: rgba(255,255,255,0.4);">terminal</span>
  </div>
  <div style="padding: 20px 24px; font-size: 0.85rem; line-height: 1.8;">
    <div><span style="color: var(--green);">bubble@travel</span> <span style="color: rgba(255,255,255,0.6);">~</span> <span style="color: rgba(255,255,255,0.8);">$</span> <span style="color: rgba(255,255,255,0.7);">echo "Hello"</span></div>
    <div style="color: var(--yellow);">Hello</div>
  </div>
</div>
```

---

## #12 主CTA按钮 (Primary CTA)

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
  box-shadow: 0 2px 8px rgba(166,123,91,0.3);
">立即开始 →</a>
```

---

## #13 黄色CTA变体

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
">Follow 在下 花心泡</a>
```

---

## #14 次要CTA按钮 (Outline)

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
">了解更多</a>
```

---

## #15 黄色边框卡片 (Yellow Border Card)

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
    margin: 0;
    line-height: 1.6;
  ">描述文字。</p>
</div>
```

---

## #16 虚线圆圈装饰

```html
<div style="
  width: 280px; height: 280px;
  border: 2.5px dashed var(--yellow);
  border-radius: 50%;
  opacity: 0.3;
  pointer-events: none;
"></div>
```

---

## #17 渐变光晕

```html
<div style="
  width: 500px; height: 500px;
  background: radial-gradient(ellipse, rgba(240,198,116,0.15), transparent 70%);
  pointer-events: none;
"></div>
```

---

## #18 渐隐分割线

```html
<hr style="
  border: none;
  height: 1px;
  background: linear-gradient(90deg, transparent, var(--yellow), transparent);
  margin: 48px 0;
">
```

---

## #19 大透明装饰数字

```html
<div style="
  font-family: 'Fraunces', serif;
  font-style: italic;
  font-size: clamp(3rem, 8vw, 7rem);
  color: var(--brown);
  opacity: 0.12;
  pointer-events: none;
  user-select: none;
  line-height: 1;
">03</div>
```

---

## #20 左侧色条

```html
<div style="
  border-left: 4px solid var(--yellow);
  padding-left: 20px;
  margin: 24px 0;
">
  <p style="margin: 0; color: var(--ink-light);">带有左侧色条标识的内容。</p>
</div>
```

---

## #21 机票/登机牌风格

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

---

## #22 邮票边框

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
    <div style="font-size: 0.7rem; color: var(--ink-light); text-align: center; letter-spacing: 0.1em;">POSTCARD</div>
    <div style="font-family: 'Caveat', cursive; font-size: 1.2rem; color: var(--brown); text-align: center; margin-top: 4px;">来自旅途的问候</div>
  </div>
</div>
```

---

## #23 拍立得风格

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

---

## #24 手账贴纸

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
">旅行日记</div>
```

---

## #25 地图定位点

```html
<div style="position: relative; display: inline-flex; align-items: center; gap: 8px;">
  <span style="
    display: inline-block;
    width: 14px; height: 14px;
    background: var(--blue);
    border-radius: 50%;
    border: 2px solid var(--bg-warm);
    box-shadow: 0 0 0 3px var(--blue);
    opacity: 0.8;
  "></span>
  <span style="font-family: 'Fira Code', monospace; font-size: 0.8rem; color: var(--ink-light);">
    35.6762° N, 139.6503° E
  </span>
</div>
```

---

## #26 条纹肌理分割

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

---

## #27 网格底纹

```html
<div style="
  background-image:
    linear-gradient(rgba(166,123,91,0.06) 1px, transparent 1px),
    linear-gradient(90deg, rgba(166,123,91,0.06) 1px, transparent 1px);
  background-size: 24px 24px;
  padding: 40px;
  border-radius: 12px;
">
  <p style="color: var(--ink-light);">带网格底纹的内容区</p>
</div>
```

---

## #28 水彩晕染光斑

```html
<div style="
  width: 300px; height: 300px;
  background:
    radial-gradient(ellipse at 30% 40%, rgba(240,198,116,0.12) 0%, transparent 50%),
    radial-gradient(ellipse at 70% 60%, rgba(91,139,160,0.08) 0%, transparent 50%),
    radial-gradient(ellipse at 50% 30%, rgba(166,123,91,0.06) 0%, transparent 50%);
  border-radius: 50%;
  pointer-events: none;
"></div>
```

---

## #29 彩铅笔触边框

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

---

## #30 状态指示器

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

## #31 进度条

```html
<div style="margin-bottom: 16px;">
  <div style="display: flex; justify-content: space-between; margin-bottom: 6px;">
    <span style="font-size: 0.8rem; color: var(--ink-light);">完成度</span>
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

## #32 删除按钮 (蓝色危险操作)

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
">删除</button>
```

---

## #33 危险确认面板

```html
<div style="
  background: var(--bg-warm);
  border: 1.5px solid var(--blue);
  border-radius: 10px;
  padding: 24px;
">
  <div style="display: flex; align-items: flex-start; gap: 12px; margin-bottom: 16px;">
    <span style="
      display: flex; align-items: center; justify-content: center;
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

## #34 统计卡片

```html
<div style="
  background: var(--bg-warm);
  border: 1px solid rgba(166,123,91,0.12);
  border-radius: 10px;
  padding: 20px;
">
  <div style="font-size: 0.75rem; color: var(--ink-light); text-transform: uppercase; letter-spacing: 0.05em; margin-bottom: 8px;">标题</div>
  <div style="font-family: 'Fraunces', serif; font-style: italic; font-size: 1.8rem; color: var(--brown);">128</div>
  <div style="font-size: 0.72rem; color: var(--green); margin-top: 4px;">↑ 12%</div>
</div>
```

---

## #35 项目列表行

```html
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
    <span style="color: var(--ink); font-size: 0.9rem;">项目名称</span>
  </div>
  <span style="color: var(--ink-light); font-size: 0.78rem;">2024.03</span>
</div>
```

---

## #36 高亮选中行

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

## #37 终端标签

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

## #38 时间线节点

```html
<div style="position: relative; padding-left: 32px; margin-bottom: 40px;">
  <div style="
    position: absolute;
    left: 5px; top: 4px;
    width: 14px; height: 14px;
    background: var(--brown);
    border-radius: 50%;
    border: 3px solid var(--bg-warm);
    box-shadow: 0 0 0 3px var(--brown);
  "></div>
  <div style="font-size: 0.78rem; color: var(--blue); margin-bottom: 4px;">日期</div>
  <h4 style="
    font-family: 'Noto Serif SC', serif;
    color: var(--ink);
    margin: 0 0 8px 0;
  ">标题</h4>
  <p style="color: var(--ink-light); font-size: 0.92rem; line-height: 1.6; margin: 0;">描述内容。</p>
</div>
```

---

## #39 引用/金句

```html
<div style="text-align: center; padding: 40px 20px;">
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
    margin: 0 0 20px 0;
  ">引用的金句内容。</blockquote>
  <div style="font-size: 0.9rem; color: var(--ink-light);">— 署名</div>
</div>
```

---

## #40 封面卡片 (Cover Card)

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
  <div style="
    position: absolute;
    width: 400px; height: 400px;
    background: radial-gradient(ellipse, rgba(240,198,116,0.12), transparent 70%);
    top: -50px; left: -50px;
    pointer-events: none;
  "></div>

  <div style="
    font-size: 0.78rem;
    color: var(--blue);
    text-transform: uppercase;
    letter-spacing: 0.12em;
    margin-bottom: 20px;
    position: relative;
    z-index: 1;
  ">BUBBLE · TRAVEL NOTES</div>

  <h1 style="
    font-family: 'Noto Serif SC', serif;
    font-size: clamp(2rem, 5vw, 3.2rem);
    color: var(--ink);
    line-height: 1.3;
    margin: 0 0 16px 0;
    position: relative;
    z-index: 1;
  ">大标题<br><span style="color: var(--brown);">关键词</span></h1>

  <p style="
    font-size: 1rem;
    color: var(--ink-light);
    line-height: 1.6;
    max-width: 380px;
    margin: 0 0 32px 0;
    position: relative;
    z-index: 1;
  ">花心小泡泡 · 体验生活，感受体验，记录感受</p>

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
</div>
```

---

## #41 正文卡片 (Content Card)

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

  <div style="display: inline-flex; align-items: center; gap: 8px; margin-bottom: 20px;">
    <span style="width: 8px; height: 8px; background: var(--yellow); border-radius: 50%;"></span>
    <span style="font-size: 0.78rem; color: var(--blue); letter-spacing: 0.08em;">CHAPTER ONE</span>
  </div>

  <h2 style="
    font-family: 'Noto Serif SC', serif;
    font-size: clamp(1.8rem, 4vw, 2.4rem);
    color: var(--ink);
    line-height: 1.3;
    margin: 0 0 24px 0;
  ">标题</h2>

  <p style="font-size: 1.05rem; color: var(--ink-light); line-height: 1.8; margin: 0 0 20px 0;">正文内容。</p>
</div>
```

---

## #42 总结卡片 (Summary Card)

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
    ">花心小泡泡 · 体验生活，感受体验，记录感受</p>

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

    <div style="font-size: 0.78rem; color: var(--ink-light); opacity: 0.7;">更多旅行笔记，持续更新中</div>
  </div>
</div>
```

---

## #43 签名档 (Signature Block)

```html
<div class="signature" style="
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 8px;
  padding: 24px;
  text-align: center;
">
  <div style="
    font-family: 'Fraunces', serif;
    font-style: italic;
    font-size: 1.4rem;
    color: var(--brown);
  ">花心小泡泡 / Bubble</div>
  <div style="
    font-size: 0.85rem;
    color: var(--ink-light);
    line-height: 1.5;
  ">花心小泡泡 · 体验生活，感受体验，记录感受</div>
  <div style="
    display: inline-block;
    margin-top: 8px;
    padding: 6px 20px;
    background: var(--brown);
    color: #FDF8F0;
    border-radius: 999px;
    font-size: 0.8rem;
    font-weight: 600;
  ">Follow 在下 花心泡</div>
</div>
```

---

## #44 品牌三色比例展示

```html
<div style="display: flex; flex-direction: column; gap: 12px; max-width: 400px;">
  <div style="display: flex; align-items: center; gap: 12px;">
    <div style="
      width: 60%; height: 36px;
      background: var(--brown);
      border-radius: 6px;
      display: flex; align-items: center;
      padding-left: 16px;
    "><span style="color: #FDF8F0; font-family: 'Fira Code', monospace; font-size: 0.8rem;">#A67B5B</span></div>
    <span style="font-size: 0.85rem; color: var(--ink-light);">60%</span>
  </div>
  <div style="display: flex; align-items: center; gap: 12px;">
    <div style="
      width: 30%; height: 36px;
      background: var(--yellow);
      border-radius: 6px;
      display: flex; align-items: center;
      padding-left: 16px;
    "><span style="color: var(--ink); font-family: 'Fira Code', monospace; font-size: 0.8rem;">#F0C674</span></div>
    <span style="font-size: 0.85rem; color: var(--ink-light);">30%</span>
  </div>
  <div style="display: flex; align-items: center; gap: 12px;">
    <div style="
      width: 10%; height: 36px;
      background: var(--blue);
      border-radius: 6px;
      display: flex; align-items: center;
      padding-left: 10px;
    "><span style="color: #FDF8F0; font-family: 'Fira Code', monospace; font-size: 0.72rem;">#5B8B</span></div>
    <span style="font-size: 0.85rem; color: var(--ink-light);">10%</span>
  </div>
</div>
```

---

## 📊 组件场景索引

| 组件编号 | 名称 | 教程页 | Landing | App | 卡片 |
|----------|------|--------|---------|-----|------|
| #01 | 步骤编号 | ✅ | — | — | ✅ |
| #02 | 关键词标签 | ✅ | ✅ | ✅ | ✅ |
| #03 | Badge 棕色 | ✅ | ✅ | ✅ | — |
| #04 | Badge 黄色 | ✅ | ✅ | ✅ | ✅ |
| #05 | 高亮标注 | ✅ | ✅ | — | ✅ |
| #06 | 提示框 Tip | ✅ | ✅ | — | ✅ |
| #07 | 警告框 Warning | ✅ | — | ✅ | — |
| #08 | 信息卡 | ✅ | ✅ | ✅ | ✅ |
| #09 | 棕色高亮块 | ✅ | ✅ | — | ✅ |
| #10 | 代码块 | ✅ | — | ✅ | — |
| #11 | 终端窗口 | ✅ | — | ✅ | — |
| #12 | 主CTA按钮 | ✅ | ✅ | ✅ | — |
| #13 | 黄色CTA变体 | ✅ | ✅ | ✅ | ✅ |
| #14 | 次要CTA按钮 | ✅ | ✅ | ✅ | — |
| #15 | 黄色边框卡片 | ✅ | ✅ | ✅ | ✅ |
| #16 | 虚线圆圈 | ✅ | ✅ | ✅ | ✅ |
| #17 | 渐变光晕 | ✅ | ✅ | ✅ | ✅ |
| #18 | 渐隐分割线 | ✅ | ✅ | ✅ | ✅ |
| #19 | 大透明数字 | ✅ | ✅ | ✅ | ✅ |
| #20 | 左侧色条 | ✅ | ✅ | ✅ | ✅ |
| #21 | 机票/登机牌 | ✅ | ✅ | — | ✅ |
| #22 | 邮票边框 | ✅ | ✅ | — | ✅ |
| #23 | 拍立得 | ✅ | ✅ | — | ✅ |
| #24 | 手账贴纸 | ✅ | ✅ | — | ✅ |
| #25 | 地图定位点 | ✅ | ✅ | — | ✅ |
| #26 | 条纹肌理 | ✅ | ✅ | ✅ | ✅ |
| #27 | 网格底纹 | ✅ | ✅ | ✅ | ✅ |
| #28 | 水彩晕染 | ✅ | ✅ | ✅ | ✅ |
| #29 | 彩铅笔触 | ✅ | ✅ | ✅ | ✅ |
| #30 | 状态指示器 | — | — | ✅ | — |
| #31 | 进度条 | ✅ | ✅ | ✅ | — |
| #32 | 删除按钮 | — | — | ✅ | — |
| #33 | 危险确认面板 | — | — | ✅ | — |
| #34 | 统计卡片 | ✅ | ✅ | ✅ | — |
| #35 | 项目列表行 | ✅ | ✅ | ✅ | — |
| #36 | 高亮选中行 | — | — | ✅ | — |
| #37 | 终端标签 | ✅ | — | ✅ | — |
| #38 | 时间线节点 | ✅ | ✅ | ✅ | — |
| #39 | 引用/金句 | ✅ | ✅ | — | ✅ |
| #40 | 封面卡片 | — | — | — | ✅ |
| #41 | 正文卡片 | — | — | — | ✅ |
| #42 | 总结卡片 | — | — | — | ✅ |
| #43 | 签名档 | ✅ | ✅ | ✅ | ✅ |
| #44 | 品牌三色比例 | ✅ | ✅ | ✅ | ✅ |

---

## ⚠️ 硬规则提醒

- **禁止使用HTML默认样式**：所有引用块、列表、表格必须从这里选用组件
- 如果在components.md里找不到合适的，可以自行设计一个符合brand-dna规范的组件
- 但绝不能用浏览器默认样式（默认blockquote、默认border-left引用、默认ul/ol、默认table）

---

*Components are the flesh. Pick and fill into layouts from layouts.md.*
