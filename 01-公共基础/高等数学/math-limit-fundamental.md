---
id: math-limit-fundamental
title: 两个重要极限
type: formula
exam: 注册电气工程师-基础
scope: 公共基础
subject: 高等数学
tags: [极限, 重要公式]
related: [math-l-hospital]
difficulty: ★★
frequency: 高
status: seed
created: 2026-07-20
updated: 2026-07-20
---

# 两个重要极限

## 第一个重要极限

$$
\boxed{\lim_{x \to 0} \frac{\sin x}{x} = 1}
$$

**推广形式**：只要 $\alpha(x) \to 0$，就有

$$
\lim \frac{\sin \alpha(x)}{\alpha(x)} = 1
$$

**直觉**：当 $x$ 非常小时，$\sin x \approx x$，两者是等价无穷小。从单位圆上看，弧长、弦长、切线长在极限情况下相等。

## 第二个重要极限

$$
\boxed{\lim_{x \to \infty} \left(1 + \frac{1}{x}\right)^x = e}
$$

**等价形式**：

$$
\lim_{x \to 0} (1 + x)^{\frac{1}{x}} = e
$$

**推广形式**：只要 $\alpha(x) \to 0$，就有

$$
\lim \left[1 + \alpha(x)\right]^{\frac{1}{\alpha(x)}} = e
$$

**直觉**：复利模型——年利率 100%，无限次复利，本金 1 元，年末就是 $e$ 元。

## 适用条件

| 重要极限 | 适用形式 | 注意 |
|----------|----------|------|
| $\frac{\sin x}{x}$ | $\frac{0}{0}$ 型，且分子含 sin/tan/arcsin/arctan | 必须是 sin(无穷小) / 无穷小 |
| $(1+1/x)^x$ | $1^\infty$ 型，幂指函数 | 必须是 (1+无穷小)^(无穷大的倒数) |

## 量纲

无量纲（纯数）。$e \approx 2.71828\ldots$

## 推导 / 记忆方法

**第一个**：用单位圆面积法。夹逼准则证：
$S_\text{三角形} < S_\text{扇形} < S_\text{大三角形}$
→ $\frac{1}{2}\sin x < \frac{1}{2}x < \frac{1}{2}\tan x$
→ 两边除以 $\sin x$ 取倒数，用夹逼得结论。

**第二个**：用二项式定理展开 + 单调有界定理证。

**记忆口诀**：
- "正弦比自一，零极限为一"
- "一加无穷小，幂指无穷倒，极限等于 e"

## 典型题

**题**：求 $\lim_{x \to 0} \frac{\tan 2x}{\sin 3x}$

**解**：
方法一（重要极限）：
$$
\frac{\tan 2x}{\sin 3x} = \frac{\sin 2x}{\cos 2x \cdot \sin 3x} = \frac{\sin 2x}{2x} \cdot \frac{3x}{\sin 3x} \cdot \frac{2}{3} \cdot \frac{1}{\cos 2x}
$$
取极限：$1 \cdot 1 \cdot \frac{2}{3} \cdot \frac{1}{1} = \frac{2}{3}$

方法二（等价无穷小）：$x\to0$ 时 $\tan 2x \sim 2x$，$\sin 3x \sim 3x$，
$$
\lim_{x\to0} \frac{2x}{3x} = \frac{2}{3}
$$

**答案**：$\boxed{\dfrac{2}{3}}$

## 关联知识点

- [[math-l-hospital]] 洛必达法则 — 另一种处理不定式极限的工具
- [[math-equivalent-infinitesimal]] 等价无穷小替换 — 重要极限的推论，更便捷
