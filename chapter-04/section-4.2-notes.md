# §4.2 推理和元定理：概念与例题笔记

[返回习题目录](../README.md)

**范围：**整理本次 §4.2 的讨论与习题所用工具。[习题 4.2.1–4.2.5 的完整解答](section-4.2-exercises.md)。依据用户提供的教材截图及既有公理笔记；下列解释与展开证明为复习整理。

## 这节在做什么：使证明方法有形式依据

原系统允许使用前提、逻辑公理与分离规则。§4.2 证明若干元定理，使我们能够合法地组织、压缩和转换证明。

内定理是系统中可证明的公式；元定理是关于公式、证明或形式系统的定理。例如，$A\to A$ 是对象语言公式，而演绎定理描述的是两种证明任务之间的关系。

因此，“暂时假设前件”“反证”“使用重言关系连接已有结论”都有展开成原始推演的依据。它们不是额外添加的原始规则。习题 4.2.1 禁止元定理，正是要求显式展开这些步骤。

## 引理 4.2.1：重言规则

若 $\Gamma\vdash\varphi_1,\ldots,\Gamma\vdash\varphi_n$，并且

$$
\varphi_1\to(\varphi_2\to\cdots\to(\varphi_n\to\psi))
$$

是一阶意义下的重言式，则 $\Gamma\vdash\psi$。

证明：由定理 4.1.1，该蕴涵链无前提可证，因而也可在前提集 $\Gamma$ 下使用。依次与 $\varphi_1,\ldots,\varphi_n$ 作 $n$ 次分离，即得 $\psi$。

蕴涵省略括号时通常约定向右结合。这只是书写约定，不能任意移动括号；$(A\to B)\to C$ 与 $A\to(B\to C)$ 一般不等价。取 $A$ 假、$B$ 真、$C$ 假，前者假而后者真。

## 复习概括定理：检查的是全部前提

$$
\Gamma\vdash\varphi,\quad x\notin\operatorname{FV}(\Gamma)
\quad\Longrightarrow\quad
\Gamma\vdash\forall x\varphi.
$$

这里 $\operatorname{FV}(\Gamma)$ 表示各前提的自由变元集合之并。它要求 $x$ 在每一个前提中都不自由出现，不要求 $x$ 在结论中不自由出现。

- 前提 $\forall xPx$ 中的 $x$ 被约束，不妨碍概括。
- 前提 $Px$ 中的 $x$ 自由，不能据此直接概括为 $\forall xPx$。
- 若 $\Gamma=\{\forall xPx,Qx\}$，虽第一个前提没有自由的 $x$，第二个有，所以条件不满足。
- 空前提集自动满足条件，因此 $\vdash\varphi$ 蕴涵 $\vdash\forall x\varphi$。

证明说明中的“取任意 $x$”属于元语言，不会自动改变公式的自由出现。$P(x)$ 中的 $x$ 仍自由；真正写成 $\forall xP(x)$ 后才被量词约束。“任意性”与“是否被量词约束”是两个问题。

证明概括定理时，对原推演各行归纳：公理行依靠公理的全称概括规定；前提行依靠第四组公理；分离行依靠第三组公理。习题 4.2.2 就是统计这三种转换的行数。

## 定理 4.2.3：演绎定理

$$
\Gamma\cup\{A\}\vdash B
\quad\Longleftrightarrow\quad
\Gamma\vdash A\to B.
$$

直观意思：要证明“如果 $A$，那么 $B$”，可以暂时假设 $A$，然后证明 $B$。最后借助演绎定理将额外假设 $A$ 撤去，形成蕴涵结论 $A\to B$。

这不是随意添加一个永远保留的前提，而是把两种证明任务相互转换。公式 $A\to B$ 在对象语言中；$\Gamma\cup\{A\}\vdash B$ 是元语言中的可证明性断言。演绎定理说明这两种可证明性任务等价，并不将对象语言的蕴涵符号与元语言的 $\vdash$ 当作同一个符号。

**证明骨架。**从右到左，将额外前提 $A$ 与 $A\to B$ 分离即可。从左到右，设原证明各行为 $\theta_i$，逐行证明 $\Gamma\vdash A\to\theta_i$：

1. 若 $\theta_i$ 是公理或属于 $\Gamma$，已有 $\Gamma\vdash\theta_i$，利用重言式 $\theta_i\to(A\to\theta_i)$。
2. 若 $\theta_i=A$，使用可证明的重言式 $A\to A$。
3. 若 $\theta_i$ 由 $\alpha$ 和 $\alpha\to\theta_i$ 分离得到，归纳假设给出 $A\to\alpha$ 与 $A\to(\alpha\to\theta_i)$，再用第二个命题公理或重言规则得到 $A\to\theta_i$。

最后一行即为 $\Gamma\vdash A\to B$。本书原始推理规则只有分离规则；概括在这里是已证明的定理，因此归纳中不需额外添加“原始概括规则”一类。

## 推论 4.2.4：逆否命题

$$
\Gamma\cup\{\varphi\}\vdash\neg\psi
\quad\Longleftrightarrow\quad
\Gamma\cup\{\psi\}\vdash\neg\varphi.
$$

由左侧出发，演绎定理给出 $\Gamma\vdash\varphi\to\neg\psi$。再用重言式

$$
(\varphi\to\neg\psi)\to(\psi\to\neg\varphi),
$$

得到 $\Gamma\vdash\psi\to\neg\varphi$。演绎定理再将 $\psi$ 移到前提侧，即得右侧。交换 $\varphi,\psi$，得到反方向。

直观上，$\varphi\to\neg\psi$ 表达二者不能同时成立；因此任意一方成立都能排除另一方。

## 推论 4.2.5：反证法

若 $\Gamma\cup\{A\}$ 不一致，则 $\Gamma\vdash\neg A$。

“不一致”表示存在 $B$，使该前提集既能推出 $B$，又能推出 $\neg B$。分别用演绎定理得到

$$
\Gamma\vdash A\to B,\qquad\Gamma\vdash A\to\neg B.
$$

再用重言式 $(A\to B)\to((A\to\neg B)\to\neg A)$，得到所求。

若目标是证明 $A$，也可先假设 $\neg A$，推出矛盾后得到 $\neg\neg A$，最后用重言规则消去双重否定。

## 做题时怎样选择工具

| 题型或目标 | 优先考虑 |
| --- | --- |
| 公式是否为某条公理的实例 | 对照模板，检查替换和自由出现条件 |
| $\Gamma\vdash A\to B$ | 演绎定理：将 $A$ 暂时移到前提侧 |
| $\Gamma\vdash A\leftrightarrow B$ | 分别证明两个方向 |
| $\Gamma\vdash A\land B$ | 分别得到两个合取项，再用重言规则合并 |
| $\Gamma\vdash\neg A$ | 假设 $A$，尝试推出矛盾 |
| $\Gamma\vdash\forall xA$ | 先检查全部前提中有无自由的 $x$，再考虑证明 $A$ 并概括 |
| 前提含 $\forall xA$ | 考虑哪个全称实例有用，检查无冲突替换 |
| 目标含 $\exists$ 或量词外否定 | 用 $\exists xA:=\neg\forall x\neg A$，配合反证法和重言规则 |
| 关于替换、自由变元的普遍结论 | 对公式结构归纳 |
| 关于推演转换、推演长度的结论 | 对推演各行归纳 |

重言规则用于连接已证明的公式，不只是化简某个公式。量词内部的变化还需要量词公理和相应条件。特别地，有 $\exists xA$ 并不允许直接把当前任意变元 $x$ 当成满足者，写下 $A$。

## 例 4.2.7：把最外层前件变成临时假设

要证明

$$
\varnothing\vdash\forall x(\varphi\to\psi)\to(\exists x\varphi\to\exists x\psi).
$$

令

$$
A:=\forall x(\varphi\to\psi),\qquad B:=\exists x\varphi\to\exists x\psi.
$$

目标就是 $\varnothing\vdash A\to B$。演绎定理取 $\Gamma=\varnothing$，告诉我们只需完成

$$
\{A\}\vdash B,
$$

即

$$
\forall x(\varphi\to\psi)\vdash\exists x\varphi\to\exists x\psi.
$$

左边单写一个公式表示以前提集 $\{\forall x(\varphi\to\psi)\}$ 为前提。移到左侧的是整个最外层前件 $\forall x(\varphi\to\psi)$，不是其中的 $\varphi$。

结论仍有一个蕴涵，还可以再次使用演绎定理，将任务化为

$$
\{\forall x(\varphi\to\psi),\ \exists x\varphi\}\vdash\exists x\psi.
$$

直观上就是：假设所有对象满足“有性质 $\varphi$ 就有性质 $\psi$”，又假设存在满足 $\varphi$ 的对象，证明存在满足 $\psi$ 的对象。

也可以直接在前提 $A=\forall x(\varphi\to\psi)$ 下完成证明：

1. 全称实例化得到 $A\vdash\varphi\to\psi$。
2. 重言规则给出 $A\vdash\neg\psi\to\neg\varphi$。
3. 前提 $A$ 中无自由的 $x$，因此概括并使用第三组公理，得到 $A\vdash\forall x\neg\psi\to\forall x\neg\varphi$。
4. 逆否后得到 $A\vdash\neg\forall x\neg\varphi\to\neg\forall x\neg\psi$，即 $A\vdash\exists x\varphi\to\exists x\psi$。
5. 最后用演绎定理撤去 $A$，得到原目标。

**注意：**原始任务没有额外前提；过程中的假设是临时的，最后须用演绎定理逐一撤去，得到无额外前提的蕴涵结论。

整理日期：2026-11-03。
