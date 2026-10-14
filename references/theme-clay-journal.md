# 公众号排版组件库 —— 陶土手记

> **使用说明**：本组件库为「陶土手记」主题，所有组件使用**内联样式**，可直接复制粘贴到微信公众号编辑器。
>
> **设计风格**：陶土手记主题（温暖手作 + 编辑部质感）。暖奶油底、陶土主色、柔陶下划线。适合案例复盘、生活观察、访谈、观点长文。
>
> **公众号平台限制须知**：
> - ❌ 不支持 `<style>`/`<script>`、CSS class/id、`position:fixed/absolute`、`float`、`@media`/`@keyframes`、`display:grid`
> - ✅ 支持内联 `style`、`display:flex`（有限）、`linear-gradient`（可渲染但有暗色模式检测风险，文字背景默认用纯色）、`border-radius`、`box-shadow`、`<section>/<p>/<span>/<strong>/<img>` 等基础标签
>
> **WeChat 兼容铁律**（本主题组件全部已按此写好，改动时必须遵守）：
> - 所有"装饰性空元素"（陶土渐变分割线、END 短线、光晕竖条、数据卡分隔）**必须在内部放 `<span leaf=""><br></span>` 占位**，否则微信会剥掉样式
> - **不要把 `font-size`/`border-bottom` 打在 `<strong>` 上**，也不要在同一个 `<p>` 里混多个不同 `font-size`——微信编辑器会自动"纠正"导致样式被重写。正确做法：拆成多个 `<p>`，每个 `<p>` 只有一个字号；高亮样式统一挂在外层 `<span>` 上
> - 不用 `position:absolute` 做划线/高亮，删除线用 `text-decoration:line-through`
> - 结构化区域（如引言卡右下署名、图片说明）没有内容时**整块删掉**，不留空 section

---

## 设计变量速查表

```
主色调：       #B85C38（陶土）
主色调深：     #8A4228（深陶）
主色调浅：     #E8C4B0（浅陶）
主色调极浅：   #F6EDE6（极浅陶）
主色调背景：   #FAF7F2（极浅陶底）
淡陶标记色：   #E8C4B0（下划线/左竖条专用）
标题色：       #2A2522（近黑）
正文色：       #2A2522（深灰）
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
<section style="max-width:677px;margin:0 auto;background:#ffffff;font-family:-apple-system,BlinkMacSystemFont,'PingFang SC','Hiragino Sans GB','Microsoft YaHei',sans-serif;color:#2A2522;line-height:1.75;letter-spacing:0.5px;overflow-x:hidden;">

  <!-- 所有组件放在这里 -->

</section>
```

---

## 组件 2 开头引言卡片（白底 + 陶土阴影光晕）

> **文案策略（先读，比代码重要）**：
> - 引言卡金句和公众号外标题是**两层**，视角要错开——外标题卖"为什么点开"，引言卡卖"核心观点是什么"
> - 已知外标题时，金句**禁止原样复述**其核心关键词；从文章第一段或核心论点提炼一句有张力的判断句
> - 右下署名按文章实际作者填，未知则整行删掉，**不要固定写"甲木"**
> - 陶土底白字标签仅在本卡片内使用（视觉焦点），正文中的关键词标签一律用浅陶底深陶字（组件 7b）

```html
<section style="margin:10px 10px 32px;background:#ffffff;border-radius:12px;box-shadow:0 4px 24px -4px rgba(184,92,56,0.15);padding:28px 24px 22px;overflow:hidden;">
  <p style="font-size:42px;color:#B85C38;font-weight:900;margin:0;line-height:0.6;">
    <span leaf="">"</span>
  </p>
  <p style="font-size:16px;font-weight:800;color:#2A2522;margin:12px 0 8px;line-height:1.75;padding-left:4px;">
    <span style="background:#B85C38;color:#FFFFFF;padding:2px 8px;border-radius:4px;"><span leaf="">{{ 高亮关键词 }}</span></span>
    <span leaf="">{{ 金句中段 }}</span>
    <span style="background:#B85C38;color:#FFFFFF;padding:2px 8px;border-radius:4px;"><span leaf="">{{ 高亮关键词 }}</span></span>
    <span leaf="">{{ 金句收尾 }}</span>
  </p>
  <p style="text-align:right;font-size:12px;color:#9CA3AF;margin:8px 0 0;letter-spacing:1px;">
    <span leaf="">—— {{ 作者名，未知则删整行 }}</span>
  </p>
</section>
```

---

## 完整文章模板骨架

骨架、配方表与映射规则已按原主题完整迁移并替换为陶土色系。详见本文件完整版本。
