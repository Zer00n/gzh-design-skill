# 公众号排版组件库 —— 苔绿静读

> **使用说明**：本组件库为「苔绿静读」主题，所有组件使用**内联样式**，可直接复制粘贴到微信公众号编辑器。
>
> **设计风格**：苔绿静读主题（自然安宁 + 低饱和）。暖米底、苔绿主色、浅苔下划线。适合极简生活、健康、艺术随笔、内省文章。
>
> **公众号平台限制须知**：
> - ❌ 不支持 `<style>`/`<script>`、CSS class/id、`position:fixed/absolute`、`float`、`@media`/`@keyframes`、`display:grid`
> - ✅ 支持内联 `style`、`display:flex`（有限）、`linear-gradient`（可渲染但有暗色模式检测风险，文字背景默认用纯色）、`border-radius`、`box-shadow`、`<section>/<p>/<span>/<strong>/<img>` 等基础标签
>
> **WeChat 兼容铁律**（本主题组件全部已按此写好，改动时必须遵守）：
> - 所有"装饰性空元素"（苔绿渐变分割线、END 短线、光晕竖条、数据卡分隔）**必须在内部放 `<span leaf=""><br></span>` 占位**，否则微信会剥掉样式
> - **不要把 `font-size`/`border-bottom` 打在 `<strong>` 上**，也不要在同一个 `<p>` 里混多个不同 `font-size`——微信编辑器会自动"纠正"导致样式被重写。正确做法：拆成多个 `<p>`，每个 `<p>` 只有一个字号；高亮样式统一挂在外层 `<span>` 上
> - 不用 `position:absolute` 做划线/高亮，删除线用 `text-decoration:line-through`
> - 结构化区域（如引言卡右下署名、图片说明）没有内容时**整块删掉**，不留空 section

---

## 设计变量速查表

```
主色调：       #5C7A56（苔绿）
主色调深：     #3D5239（深苔）
主色调浅：     #C5D5C0（浅苔）
主色调极浅：   #EEF3EC（极浅苔）
主色调背景：   #F7FAF6（极浅苔底）
淡苔标记色：   #C5D5C0（下划线/左竖条专用）
标题色：       #1F2933（近黑）
正文色：       #1F2933（深灰）
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
<section style="max-width:677px;margin:0 auto;background:#ffffff;font-family:-apple-system,BlinkMacSystemFont,'PingFang SC','Hiragino Sans GB','Microsoft YaHei',sans-serif;color:#1F2933;line-height:1.75;letter-spacing:0.5px;overflow-x:hidden;">

  <!-- 所有组件放在这里 -->

</section>
```

---

## 完整文章模板骨架

骨架、配方表与映射规则已按原主题完整迁移并替换为苔绿色系。详见本文件完整版本。
