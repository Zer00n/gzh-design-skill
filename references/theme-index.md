# 主题索引与选择决策表

本表是主题信息的**单一来源**。工作流第 1 步据此向用户展示选项，第 2 步据"组件库文件"列读取对应库，下划线标记时据"正文下划线 CSS"列取值。

每个主题的**英文标识**（用于产物命名 `{ 中文名 }({ 标识 }).html`、Agent 引用）= "组件库文件"列去掉 `theme-` 前缀与 `.md` 后缀。展示给用户仍用中文名。

## 已注册主题

| 主题 | 主色 | 适用场景 | 组件库文件 | 正文下划线 CSS |
|------|------|--------- |-----------|---------------|
| 摸鱼绿 | `#059669` emerald | 教程、测评、清单、工具盘点（卡片丰富、信息密度高，默认推荐） | `references/theme-moyu-green.md` | `background:linear-gradient(#A7F3D0,#A7F3D0) no-repeat;background-size:100% 2px;background-position:0 100%;font-weight:600;padding-bottom:2px;` |
| 红白色系 | `#DC2626` 正红 | 深度分析、观点、力量感话题（经典编辑风，编号章节+引言卡+签名区，红色克制点睛） | `references/theme-red-white.md` | `background:linear-gradient(#FECACA,#FECACA) no-repeat;background-size:100% 2px;background-position:0 100%;font-weight:600;padding-bottom:2px;` |
| 石墨极简风 | `#52525B` 石墨灰 | 设计、科技评论、专业观点、高端品牌（极简克制、留白理性、全灰阶） | `references/theme-graphite-minimal.md` | `background:linear-gradient(#52525B,#52525B) no-repeat;background-size:100% 2px;background-position:0 100%;font-weight:600;padding-bottom:2px;` |
| 留白禅意风 | `#4A5D52` 墨绿 | 禅意冥想、极简生活、深度随笔、艺术留白（呼吸感最强） | `references/theme-zen-whitespace.md` | `background:linear-gradient(#B5C8BC,#B5C8BC) no-repeat;background-size:100% 1.5px;background-position:0 100%;font-weight:500;padding-bottom:2px;` |
| 摸鱼票据风 | `#059669` emerald | 测评、工具对比、创意评测（票据/门票视觉隐喻，星级评分+编号+硬阴影卡片） | `references/theme-moyu-ticket.md` | `background:linear-gradient(#A7F3D0,#A7F3D0) no-repeat;background-size:100% 2px;background-position:0 100%;font-weight:600;padding-bottom:2px;` |
| 橄榄手记 | `#1e1f23` 墨黑（配橙 `#ed7b2f`） | 内刊手记、深度评测、案例复盘、系统性说明文档（编辑部内刊质感，分节形式多样，信息密度偏高） | `references/theme-olive-journal.md` | `background:linear-gradient(#ed7b2f,#ed7b2f) no-repeat;background-size:100% 2px;background-position:0 100%;font-weight:600;padding-bottom:2px;` |
| 云舞者青 | `#2F6F6A` transformative teal | 深度思考、科技观察、方法论、个人随笔（冷静清晰、现代自然、Cloud Dancer + Teal） | `references/theme-cloud-teal.md` | `background:linear-gradient(#A8D5D0,#A8D5D0) no-repeat;background-size:100% 2px;background-position:0 100%;font-weight:600;padding-bottom:2px;` |
| 陶土手记 | `#B85C38` terracotta | 案例复盘、生活观察、访谈、观点长文（温暖手作、编辑部质感） | `references/theme-clay-journal.md` | `background:linear-gradient(#E8C4B0,#E8C4B0) no-repeat;background-size:100% 2px;background-position:0 100%;font-weight:600;padding-bottom:2px;` |
| 苔绿静读 | `#5C7A56` moss sage | 极简生活、健康、艺术随笔、内省文章（自然安宁、低饱和） | `references/theme-sage-quiet.md` | `background:linear-gradient(#C5D5C0,#C5D5C0) no-repeat;background-size:100% 1.5px;background-position:0 100%;font-weight:500;padding-bottom:2px;` |
| 李子墨 | `#6B3A4A` deep plum | 文化评论、人物特稿、深度观点（精致内敛、微奢） | `references/theme-plum-ink.md` | `background:linear-gradient(#E0C8D0,#E0C8D0) no-repeat;background-size:100% 2px;background-position:0 100%;font-weight:600;padding-bottom:2px;` |

## 选择建议

- **用户选择制**：用户没指定主题时，把本表全部主题列给用户选（中文名 + 适用场景），不替用户定；最贴合题材的主题可标"（推荐）"放第一位。
- 全自动模式（用户明说"直接排"）才自动选：默认第一行主题，题材明显契合其它主题时选契合项并在交付时说明理由。
- 同一篇文章只用一套主题，不混搭。

## 下划线色值的权威性

正文关键词下划线一律用上表"正文下划线 CSS"列的值。组件库里可能有浅色下划线变体，那是可选样式；**正文关键词标记以本表为单一权威来源**，避免双轨。

## 新主题登记流程

1. 把主题组件库写入 `references/theme-{ 英文标识 }.md`（格式要求见 SKILL.md「添加新主题的规范」）。
2. 在上表登记一行；首个/最常用主题放第一行作为默认推荐。
3. 跑 `python3 scripts/component_lint.py .` 确认 0 ERROR。

> 用户想要全新风格时，可走 `references/theme-generator.md` 的自定义主题生成流程：按偏好/参考图生成区块库（预览存 `assets/theme-previews/`），确认后转标准主题库并按上面流程登记。
