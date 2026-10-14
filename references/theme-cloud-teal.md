# 公众号排版组件库 —— 云舞者青

> **使用说明**：本组件库为「云舞者青」主题，所有组件使用**内联样式**，可直接复制粘贴到微信公众号编辑器。
>
> **设计风格**：云舞者青主题（冷静清晰 + 现代自然）。柔和暖白底、深青绿锚点、浅青下划线。适合深度思考、科技观察、方法论、个人随笔。
>
> **公众号平台限制须知**：
> - ❌ 不支持 `<style>`/`<script>`、CSS class/id、`position:fixed/absolute`、`float`、`@media`/`@keyframes`、`display:grid`
> - ✅ 支持内联 `style`、`display:flex`（有限）、`linear-gradient`（可渲染但有暗色模式检测风险，文字背景默认用纯色）、`border-radius`、`box-shadow`、`<section>/<p>/<span>/<strong>/<img>` 等基础标签
>
> **WeChat 兼容铁律**（本主题组件全部已按此写好，改动时必须遵守）：
> - 所有"装饰性空元素"（青绿渐变分割线、END 短线、光晕竖条、数据卡分隔）**必须在内部放 `<span leaf=""><br></span>` 占位**，否则微信会剥掉样式
> - **不要把 `font-size`/`border-bottom` 打在 `<strong>` 上**，也不要在同一个 `<p>` 里混多个不同 `font-size`——微信编辑器会自动"纠正"导致样式被重写。正确做法：拆成多个 `<p>`，每个 `<p>` 只有一个字号；高亮样式统一挂在外层 `<span>` 上
> - 不用 `position:absolute` 做划线/高亮，删除线用 `text-decoration:line-through`
> - 结构化区域（如引言卡右下署名、图片说明）没有内容时**整块删掉**，不留空 section

---

## 设计变量速查表

```
主色调：       #2F6F6A（深青绿）
主色调深：     #1E4A47（深青绿）
主色调浅：     #A8D5D0（浅青绿）
主色调极浅：   #E8F3F2（极浅青）
主色调背景：   #F5FBFB（极浅青底）
淡青标记色：   #A8D5D0（下划线/左竖条专用）
标题色：       #1C1917（近黑）
正文色：       #2C3338（深灰）
辅助文字色：   #9CA3AF（中灰）
分割线色：     #E5E7EB
灰竖条：       #D6D3D1（灰底引用左竖条）
正文字号：     15px（不可改）
行高：         1.8
字间距：       0.5px
最大宽度：     677px
内容区边距：   0 10px（左右各 10px）
```

字体栈：`-apple-system,BlinkMacSystemFont,'PingFang SC','Hiragino Sans GB','Microsoft YaHei',sans-serif`

---

## 组件 1 全局容器

```html
<section style="max-width:677px;margin:0 auto;background:#ffffff;font-family:-apple-system,BlinkMacSystemFont,'PingFang SC','Hiragino Sans GB','Microsoft YaHei',sans-serif;color:#2C3338;line-height:1.75;letter-spacing:0.5px;overflow-x:hidden;">

  <!-- 所有组件放在这里 -->

</section>
```

---

## 组件 6 正文段落

> **关键规则**：每段主动识别 1~3 个关键短语，用**浅青下划线（7d）**标记——这是本风格的核心视觉特征，让读者快速扫到每段重点。

**带关键词下划线标记的段落**（推荐默认）：

```html
<p style="margin-bottom:20px;font-size:15px;line-height:1.8;text-align:justify;">
  <span leaf="">{{ 前半句 }}</span>
  <span style="background:linear-gradient(#A8D5D0,#A8D5D0) no-repeat;background-size:100% 2px;background-position:0 100%;font-weight:600;padding-bottom:2px;"><span leaf="">{{ 需要强调的关键短语 }}</span></span>
  <span leaf="">{{ 后半句 }}</span>
</p>
```

### 7d. 浅青下划线（最常用，本风格标志性标记）

```html
<span style="background:linear-gradient(#A8D5D0,#A8D5D0) no-repeat;background-size:100% 2px;background-position:0 100%;font-weight:600;padding-bottom:2px;"><span leaf="">浅青下划线关键词</span></span>
```

---

完整组件库其余部分（组件 2-5、8-16、骨架、配方表、映射规则）保持原样，下划线已全部替换为 background 模拟方案。
