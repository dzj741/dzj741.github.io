# LLM Wiki Schema

卡片 frontmatter 字段字典。所有字段列表，以及取值规范。

## 必填字段

| 字段 | 类型 | 取值 | 说明 |
|------|------|------|------|
| `id` | string | `{科目缩写}-{核心词} | 全库唯一标识，用于双向链接 |
| `title` | string | 卡片标题 | 一句话描述卡片内容 |
| `type` | enum | `concept` / `formula` / `problem` / `topic` / `example` | 卡片类型 |
| `exam` | string | `注册电气工程师-基础` | 考试名称 |
| `scope` | enum | `公共基础` / `专业基础` | 所属卷别 |
| `subject` | string | 见下方列表 | 所属一级科目 |
| `tags` | array[string] | 自定义 | 标签，用于检索和聚类 |
| `related` | array[string] | 其他卡片的 id | 双向链接目标 |
| `difficulty` | string | `★` / `★★` / `★★★` / `★★★★` | 难度星级 |
| `frequency` | enum | `高` / `中` / `低` | 考察频率 |
| `status` | enum | `seed` / `draft` / `reviewed` / `mastered` | 掌握状态 |
| `created` | date | `YYYY-MM-DD` | 创建日期 |
| `updated` | date | `YYYY-MM-DD` | 更新日期 |

## 可选字段

| 字段 | 类型 | 说明 |
|------|------|------|
| `formula` | string | 公式卡专用：主公式表达式 |
| `units` | string | 公式卡专用：量纲/单位 |
| `answer` | string | 真题/例题卡：正确答案 |
| `year` | number | 真题卡：年份 |
| `source` | string | 来源说明 |
| `prerequisites` | array[string] | 前置知识卡片 id |

## subject 取值列表

### 公共基础
- 高等数学
- 普通物理
- 普通化学
- 理论力学
- 材料力学
- 流体力学
- 计算机应用基础
- 电子电工技术
- 工程经济

### 专业基础
- 电路与电磁场
- 模拟电子技术
- 数字电子技术
- 电气工程基础

## status 流转

```
seed     → 种子卡，由系统/LLM生成，待人工核验
draft    → 草稿，人工编写中
reviewed → 已审核，内容可靠
mastered → 已掌握（用户自测通过）
```

## 双向链接规范

`related` 字段列出「这个卡链接出去的 id 列表。
维护时注意：
- 如果你在 A 卡 related 里加了 B，记得在 B 卡 related 里也加上 A（对称）
- 链接粒度相当：概念 ↔ 公式、概念 ↔ 真题，不跨太多层级
- 每卡 related 控制在 3~8 个为宜，过多说明卡太小
