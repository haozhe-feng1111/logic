# §4.5 自然推演：规则与习题笔记

[返回习题目录](../README.md) · [§3.2 自由出现与替换](../chapter-03/section-3.2-exercises.md)

**范围：**习题 4.5.1–4.5.2，共两道，附本节记号与证明方法。题目和规则依据教材印刷页 84–87；证明按复习需要展开。4.5.2 中的实例记号与 §3.2 的机械替换须作区分，详见该题末尾。

| 题号 | 内容 | 主要方法 |
| --- | --- | --- |
| [4.5.1](#exercise-451) | 弱化定理的弱形式 | 对证明树高度归纳、全称规则的特征变元改名 |
| [4.5.2](#exercise-452) | 全称公式的实例化 | 公理′、存在规则、弱化、切割；区分无捕获实例与机械替换 |

## 一、本节记号与推理规则

### 公式集与逗号

本节的 $\vdash\Gamma$ 表示公式集 $\Gamma$ 有一个自然推演。若 $\Gamma=\{A,B\}$，则 $\Gamma,\varphi$ 简写 $\Gamma\cup\{\varphi\}$，整体按 $A\lor B\lor\varphi$ 理解。这里的逗号作析取式理解；它不同于前几节 $\Gamma\vdash\varphi$ 中共同使用的前提集。

大括号表示集合，不表示合取。将 $\{A,B,C\}$ 写成 $\{A,B\},C$ 只是转写，记作 $(rw)$；公式集没有改变。

规则横线上方是已经有证明的结果，下方是应用规则得到的结果。若上方有两个分支，两个分支都须有证明；每一行内部的逗号仍按析取理解。

### 公理和规则

原始公理为包含一对互相否定的原子公式的有限公式集：

$$
\Gamma,P(v_{i_1},\ldots,v_{i_k}),\overline P(v_{i_1},\ldots,v_{i_k}).
$$

例 4.5.1 将它推广到任意公式，得到以后可直接使用的“公理′”：

$$
\vdash\Gamma,\varphi,\neg\varphi.
$$

因此 $\varphi$ 和 $\neg\varphi$ 是两个析取选项，不是在断言它们同时成立。这里讨论的无额外假设的证明树以公理为叶子；这只是本节所用系统的组织方式，其他自然推演系统也可以有临时假设及其撤销规则。

本节各规则为：

$$
\frac{\Gamma,\varphi_i}{\Gamma,\varphi_0\lor\varphi_1}\;(\lor),\qquad i=0,1;
$$

$$
\frac{\Gamma,\varphi_0\qquad\Gamma,\varphi_1}
{\Gamma,\varphi_0\land\varphi_1}\;(\land);
$$

$$
\frac{\Gamma,\varphi(y)}{\Gamma,\exists x\varphi(x)}\;(\exists);
\qquad
\frac{\Gamma,\varphi(y)}{\Gamma,\forall x\varphi(x)}\;(\forall),
\quad y\notin\operatorname{FV}(\Gamma);
$$

$$
\frac{\Gamma,\varphi\qquad\Gamma,\neg\varphi}{\Gamma}\;(\text{切割}).
$$

其中 $\operatorname{FV}(\Gamma)$ 是 $\Gamma$ 中各公式的自由变元集合之并；量词规则中的实例按避免捕获的方式理解。全称规则中的 $y$ 称为特征变元，表达所取对象的任意性。否定与量词满足本节的定义约定：

$$
\neg\forall x\varphi(x)=\exists x\neg\varphi(x),\qquad
\neg\exists x\varphi(x)=\forall x\neg\varphi(x).
$$

### 对证明树归纳时如何阅读

例 4.5.3 已知 $\vdash\Gamma,\varphi_0\land\varphi_1$，要构造 $\vdash\Gamma,\varphi_0$ 和 $\vdash\Gamma,\varphi_1$ 的证明。原证明的存在是题设，可以查看它的最后一步；这不是把推理规则倒着使用。

例如，若原证明最后一步是

$$
\frac{\Gamma',\psi_0}{\Gamma',\psi_0\lor\psi_1},
$$

则同一个最终公式集有两种写法：

$$
\Gamma'\cup\{\psi_0\lor\psi_1\}
=\Gamma\cup\{\varphi_0\land\varphi_1\}.
$$

$\Gamma'$ 是该规则不改动的背景，$\Gamma$ 是题目中除目标合取外的背景，两者不能混同。分析时向上查看已有证明的结构，构造新证明时仍沿规则从上向下进行。

<a id="exercise-451"></a>
## 4.5.1 弱化定理的弱形式

### 题目与思路

对所有有穷公式集 $\Gamma$ 和公式 $\varphi$，证明：

$$
\vdash\Gamma\quad\Longrightarrow\quad\vdash\Gamma,\varphi.
$$

按析取理解，增加一个选项使断言变弱，所以称为“弱化”。形式证明是在原证明的各行加入 $\varphi$；全称规则须额外检查特征变元条件。

### 新变元改名的准备

量词规则的特征变元可以改为一个全新的变元，同时在它上方的子证明中一致地改动相应自由出现，避免捕获。原子公理仍含有互否的一对，规则的形式与条件也保持，证明树高度不变。全称规则的背景没有该特征变元的自由出现，因此背景不变。

每棵证明树有限，可以选到在原证明及待加入公式中都不出现的新变元。这里只改相关自由出现，不把同名约束出现一并机械替换。

### 证明

对原证明 $\mathcal D$ 的高度归纳，归纳命题对所有 $\Gamma$ 和 $\varphi$ 同时成立。

**基础情形。**若高度为 $1$，$\Gamma$ 是公理，包含一对互相否定的原子公式。$\Gamma,\varphi$ 仍包含这对公式，故也为公理。

**归纳步骤。**假设结论对高度不超过 $k$ 的证明成立。考虑高度为 $k+1$ 的证明，按最后一步分类。

**（1）析取规则。**最后一步为

$$
\frac{\Gamma',\psi_i}{\Gamma',\psi_0\lor\psi_1},
\qquad\Gamma=\Gamma'\cup\{\psi_0\lor\psi_1\}.
$$

由归纳假设有 $\vdash\Gamma',\varphi,\psi_i$，再用析取规则得到 $\vdash\Gamma',\varphi,\psi_0\lor\psi_1$，即 $\vdash\Gamma,\varphi$。

**（2）合取规则。**对两个较矮的分支分别使用归纳假设，再补回合取规则：

$$
\frac{\Gamma',\varphi,\psi_0\qquad\Gamma',\varphi,\psi_1}
{\Gamma',\varphi,\psi_0\land\psi_1}.
$$

其中 $\Gamma=\Gamma'\cup\{\psi_0\land\psi_1\}$，故下方为 $\Gamma,\varphi$。

**（3）存在规则。**若最后一步由 $\Gamma',\psi(y)$ 得到 $\Gamma',\exists x\psi(x)$，先用归纳假设得到 $\vdash\Gamma',\varphi,\psi(y)$，再用同一个存在规则即可。

**（4）全称规则。**设最后一步为

$$
\frac{\Gamma',\psi(y)}{\Gamma',\forall x\psi(x)},
\qquad y\notin\operatorname{FV}(\Gamma').
$$

原有条件并不保证 $y\notin\operatorname{FV}(\varphi)$，所以不能直接在原规则背景中加入 $\varphi$。先按前述改名方法，将特征变元改为原证明和 $\varphi$ 中都不出现的新变元 $z$，得到同样高度的上方证明：

$$
\vdash\Gamma',\psi(z).
$$

由归纳假设，$\vdash\Gamma',\varphi,\psi(z)$。现在 $z\notin\operatorname{FV}(\Gamma'\cup\{\varphi\})$，故可以推出

$$
\frac{\Gamma',\varphi,\psi(z)}
{\Gamma',\varphi,\forall x\psi(x)}\;(\forall).
$$

这就是 $\vdash\Gamma,\varphi$。

**（5）切割规则。**若最后一步由 $\Gamma,\psi$ 和 $\Gamma,\neg\psi$ 切割得到 $\Gamma$，由归纳假设，两个分支可分别加入 $\varphi$。以 $\Gamma,\varphi$ 为共同背景再次切割：

$$
\frac{\Gamma,\varphi,\psi\qquad\Gamma,\varphi,\neg\psi}
{\Gamma,\varphi}.
$$

所有情况成立，故归纳完成。

**易错点。**不能把“在每行加入 $\varphi$”作为不加检查的完整证明；关键是全称规则可能因新背景中的自由变元而失效，须先改名。若 $\varphi\in\Gamma$，结论与原公式集相同，无须改造。

<a id="exercise-452"></a>
## 4.5.2 全称公式的实例化

### 题目

若 $\vdash\Gamma,\forall x\varphi(x)$，则对于任意项 $t$（在简化的语言中只有变元 $v_i$），有

$$
\vdash\Gamma,\varphi(t).
$$

为什么这里没有“$t$ 可以在 $\varphi$ 中无冲突地替换 $x$”的条件？

### 证明

以下将 $\varphi(t)$ 理解为必要时先给约束变元改名、再代入得到的无捕获实例；与 §3.2 的区别见下一小节。

由公理′，

$$
\vdash\Gamma,\varphi(t),\neg\varphi(t).
$$

以 $\Gamma,\varphi(t)$ 为背景，对最后的 $\neg\varphi(t)$ 使用存在规则：

$$
\frac{\Gamma,\varphi(t),\neg\varphi(t)}
{\Gamma,\varphi(t),\exists x\neg\varphi(x)}\;(\exists).
$$

由于 $\exists x\neg\varphi(x)=\neg\forall x\varphi(x)$，得到

$$
\vdash\Gamma,\varphi(t),\neg\forall x\varphi(x).
$$

另一方面，对已知的 $\vdash\Gamma,\forall x\varphi(x)$ 使用习题 4.5.1，加入 $\varphi(t)$，得到

$$
\vdash\Gamma,\varphi(t),\forall x\varphi(x).
$$

以 $\Gamma,\varphi(t)$ 为共同背景，对 $\forall x\varphi(x)$ 进行切割：

$$
\frac{
\Gamma,\varphi(t),\forall x\varphi(x)
\qquad
\Gamma,\varphi(t),\neg\forall x\varphi(x)
}{\Gamma,\varphi(t)}\;(\text{切割}).
$$

因此 $\boxed{\vdash\Gamma,\varphi(t)}$。

### 无冲突条件与实例记号

不能因为简化语言中的项只有变元，就说替换不会冲突。例如取

$$
\varphi(x)=\exists yR(x,y),\qquad t=y.
$$

直接按 §3.2 的机械替换定义计算，会得到 $\exists yR(y,y)$，换入的 $y$ 被内部量词捕获。若要取无捕获实例，先将约束变元改名为新的 $z$，再代入：

$$
\exists yR(x,y)\ \leadsto\ \exists zR(x,z)
\ \leadsto\ \exists zR(y,z).
$$

两种结果不能混同。后一种才表达“以 $y$ 所指的对象代入自由的 $x$”。

因此，若 $\varphi(t)$ 约定表示无捕获实例，则可通过约束变元改名处理任意 $t$，无需把可代入条件另列为对 $t$ 的限制。若将它严格理解成 §3.2 允许捕获的机械替换 $\varphi_t^x$，则仍须附加无冲突条件。

这一点有实质区别：把 $R$ 解释为两元素论域中的“不相等”关系，则 $\forall x\exists yR(x,y)$ 为真，而 $\exists yR(y,y)$ 为假，捕获后的公式不能充当合法实例。

**记号边界。**本笔记采用无捕获实例的解释来给出上述证明。所给 §4.5 页面未明确写出它与 §3.2 机械替换记号的衔接约定，因此不能把“教材已明确改用此约定”写成已核实的事实；若要求严格按旧替换定义作答，需保留无冲突条件。这道题不能解释为允许变元捕获。

## 三、复习要点

1. $\vdash\Gamma$ 的公式集按析取理解；增加公式是弱化，不是增加必须共同满足的前提。
2. 对证明高度归纳时，先查看已有证明的最后一步，再对上方较矮的证明使用归纳假设；构造新证明仍正向使用规则。
3. 保留教材的 $\Gamma'$、$\Gamma$ 等记号，区分规则背景与题目背景；转写只改变集合的展示方式。
4. 全称规则须检查特征变元是否在全部背景公式中自由出现；必要时先选新变元改名。
5. 4.5.2 的切割公式是 $\forall x\varphi(x)$，切割后的共同背景为 $\Gamma,\varphi(t)$。
6. 机械替换、无捕获实例、约束变元改名是不同操作，不能用本题覆盖 §3.2 原有的替换定义。

整理日期：2026-11-03。
