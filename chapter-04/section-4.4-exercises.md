# §4.4 前束范式：规则证明与习题笔记

[返回习题目录](../README.md) · [§4.2 的证明工具](section-4.2-notes.md) · [§4.3 的等价替换](section-4.3-exercises.md#exercise-434)

**范围：**前束范式定理、六条量词操作规则，以及习题 4.4.1–4.4.2，共两道大题。规则与题目依据本次提供的教材截图整理；证明和解释为复习展开。

| 题号 | 内容 | 主要方法 |
| --- | --- | --- |
| [4.4.1](#exercise-441) | 证明 Q2b 和 Q3a | 量词与析取、逆否等价 |
| [4.4.2](#exercise-442) | 两个公式的前束化 | 约束变元改名、展开双条件、提取量词 |

## 一、这节的目标与记号

前束公式形如

$$
Q_1x_1\cdots Q_nx_n\,\theta,
$$

其中每个 $Q_i$ 为 $\forall$ 或 $\exists$，$\theta$ 不含量词，称为母式；允许量词前缀为空，也允许母式保留自由变元。

**定理 4.4.1（前束范式定理）。**对于任何公式，都可以找到与之语法等价的前束公式。

这里“语法等价”指可互相推导，也就是 $\vdash\alpha\leftrightarrow\beta$。下文用 $\alpha\equiv\beta$ 简写这种等价；等价链中的量词内部替换由 §4.3 的等价替换定理保证。

前束化的目标是把量词移到最前面，公式不一定变短。前束范式不唯一；不同种类的量词不能任意交换次序。

## 二、六条量词操作规则

| 编号 | 语法等价 | 条件 |
| --- | --- | --- |
| Q1a | $\neg\forall x\varphi\equiv\exists x\neg\varphi$ | 无额外条件 |
| Q1b | $\neg\exists x\varphi\equiv\forall x\neg\varphi$ | 无额外条件 |
| Q2a | $(\varphi\to\forall x\psi)\equiv\forall x(\varphi\to\psi)$ | $x\notin\operatorname{FV}(\varphi)$ |
| Q2b | $(\varphi\to\exists x\psi)\equiv\exists x(\varphi\to\psi)$ | $x\notin\operatorname{FV}(\varphi)$ |
| Q3a | $(\forall x\varphi\to\psi)\equiv\exists x(\varphi\to\psi)$ | $x\notin\operatorname{FV}(\psi)$ |
| Q3b | $(\exists x\varphi\to\psi)\equiv\forall x(\varphi\to\psi)$ | $x\notin\operatorname{FV}(\psi)$ |

记忆方法：量词穿过否定时翻转；从蕴涵后件提出时不变，从前件提出时翻转。变量条件保证提出后的量词不捕获另一部分原本自由的变元；有冲突时先对约束变元改名。

### 证明所用的已有工具

沿用本书的存在量词定义

$$
\exists x\alpha:=\neg\forall x\neg\alpha.
$$

下面使用全称实例化、概括定理、演绎定理、重言规则及已证的等价替换定理，不把“取存在见证”额外当成此系统的原始规则。

还要用到两个已有结论。

**量化不含自由 $x$ 的公式。**若 $x\notin\operatorname{FV}(C)$，则

$$
\forall xC\equiv C,\qquad \exists xC\equiv C.
$$

第一式由第四组公理 $C\to\forall xC$ 与全称实例化 $\forall xC\to C$ 得到。对 $\neg C$ 使用第一式，再由存在量词定义与双重否定消去，得到第二式。这沿用通常一阶逻辑的非空论域约定。

**存在量词与析取。**习题 4.2.5（1）已经证明

$$
(\exists x\alpha\lor\exists x\beta)
\equiv\exists x(\alpha\lor\beta).
$$

### Q1a：否定全称，变成存在否定

由双重否定消去及量词内的等价替换，

$$
\exists x\neg\varphi
=\neg\forall x\neg\neg\varphi
\equiv\neg\forall x\varphi.
$$

中间的等号是展开存在量词缩写，故得到所需等价。

直观理解：“并非所有对象都满足 $\varphi$”，即“存在不满足 $\varphi$ 的对象”。

### Q1b：否定存在，变成全称否定

直接展开定义并消去双重否定：

$$
\neg\exists x\varphi
=\neg\neg\forall x\neg\varphi
\equiv\forall x\neg\varphi.
$$

直观理解：“不存在满足 $\varphi$ 的对象”，即“所有对象都不满足 $\varphi$”。

### Q2a：从后件提出全称量词

假设 $x\notin\operatorname{FV}(\varphi)$。

**从左到右。**令 $H:=\varphi\to\forall x\psi$。在前提 $H,\varphi$ 下，先分离得到 $\forall x\psi$，再实例化得到 $\psi$。由演绎定理撤去 $\varphi$：

$$
H\vdash\varphi\to\psi.
$$

$x$ 不在前提 $H$ 中自由出现，所以可概括为

$$
H\vdash\forall x(\varphi\to\psi).
$$

**从右到左。**令 $K:=\forall x(\varphi\to\psi)$。在前提 $K,\varphi$ 下，实例化得到 $\varphi\to\psi$，分离得到 $\psi$。

由于 $x$ 在这两个前提中都不自由出现，可以概括为 $\forall x\psi$。再撤去临时假设 $\varphi$，得到

$$
K\vdash\varphi\to\forall x\psi.
$$

两个方向合并，即得 Q2a。变量条件正是保证这些概括合法的条件。

### Q2b：从后件提出存在量词

假设 $x\notin\operatorname{FV}(\varphi)$。利用上面的已有工具：

$$
\begin{aligned}
\varphi\to\exists x\psi
&\equiv\neg\varphi\lor\exists x\psi\\
&\equiv\exists x\neg\varphi\lor\exists x\psi\\
&\equiv\exists x(\neg\varphi\lor\psi)\\
&\equiv\exists x(\varphi\to\psi).
\end{aligned}
$$

依次使用蕴涵与析取的命题等价、$\exists x\neg\varphi\equiv\neg\varphi$、习题 4.2.5（1），以及量词内部的命题等价替换。

这条证明使用的是 §4.2 已经建立的量词与析取定理，没有预先假定待证的后件提取规则。

直观上，若 $\varphi$ 真，就由原式获得满足 $\psi$ 的对象；若 $\varphi$ 假，任意对象对应的条件句 $\varphi\to\psi$ 都真。这只是帮助理解，语法证明由上面的等价链给出。

### Q3a：从前件提出全称量词，变成存在量词

假设 $x\notin\operatorname{FV}(\psi)$。将蕴涵改成逆否形式，使量词进入后件，再使用已经证明的规则：

$$
\begin{aligned}
\forall x\varphi\to\psi
&\equiv\neg\psi\to\neg\forall x\varphi
&&\text{逆否等价}\\
&\equiv\neg\psi\to\exists x\neg\varphi
&&\text{Q1a}\\
&\equiv\exists x(\neg\psi\to\neg\varphi)
&&\text{Q2b}\\
&\equiv\exists x(\varphi\to\psi)
&&\text{逆否等价}.
\end{aligned}
$$

应用 Q2b 时，$x$ 不在 $\neg\psi$ 中自由出现，条件满足。

### Q3b：从前件提出存在量词，变成全称量词

同样假设 $x\notin\operatorname{FV}(\psi)$：

$$
\begin{aligned}
\exists x\varphi\to\psi
&\equiv\neg\psi\to\neg\exists x\varphi
&&\text{逆否等价}\\
&\equiv\neg\psi\to\forall x\neg\varphi
&&\text{Q1b}\\
&\equiv\forall x(\neg\psi\to\neg\varphi)
&&\text{Q2a}\\
&\equiv\forall x(\varphi\to\psi)
&&\text{逆否等价}.
\end{aligned}
$$

应用 Q2a 的自由变元条件同样满足。

**这两条证明的共同路线：**取逆否，把量词送入后件；否定穿过量词使其翻转；从后件提取量词；最后对内部条件句再取逆否。

即使暂时觉得日常语言解释绕，掌握这条推导路线也能准确证明和使用 Q3a、Q3b。注意逆否等价是 $(A\to B)\equiv(\neg B\to\neg A)$，不能只交换前后件。

## 三、前束范式定理的证明思路

对公式结构归纳。

1. 原子公式已经是前束公式，量词前缀为空。
2. 对否定公式，先把内部公式化为前束形式，再反复使用 Q1a、Q1b，让否定进入母式，所经过的每个量词翻转。
3. 对蕴涵公式，先把前件、后件分别化为前束形式，再给约束变元改名，排除双方的冲突。用 Q3 从前件逐个提取量词，用 Q2 从后件逐个提取量词；剩下的母式不含量词。
4. 对全称公式，先把内部公式化为前束形式，再把原有的全称量词接在最前面。

本书的其他联词与存在量词可以按缩写展开，因此这些基本构造已覆盖所有公式。各步的等价替换由 §4.3 的定理保证。

<a id="exercise-441"></a>
## 4.4.1 证明 Q2b 和 Q3a

**题目。**假设 $x$ 不在 $\varphi$ 中自由出现，证明

$$
\vdash(\varphi\to\exists x\psi)
\leftrightarrow\exists x(\varphi\to\psi),
$$

$$
\vdash(\forall x\psi\to\varphi)
\leftrightarrow\exists x(\psi\to\varphi).
$$

第一式正是上面已证的 Q2b。

第二式是 Q3a 的公式占位符互换后的写法。按逆否路线展开如下：

$$
\begin{aligned}
\forall x\psi\to\varphi
&\equiv\neg\varphi\to\neg\forall x\psi\\
&\equiv\neg\varphi\to\exists x\neg\psi\\
&\equiv\exists x(\neg\varphi\to\neg\psi)\\
&\equiv\exists x(\psi\to\varphi).
\end{aligned}
$$

因为 $x$ 不在 $\varphi$ 中自由出现，第三步的 Q2b 合法。每一行都是语法等价，故两式的双条件均为无前提可证的内定理。

<a id="exercise-442"></a>
## 4.4.2 找出语法等价的前束公式

### （1）$(\exists xAx\land\exists xBx)\to Cx$

**先识别自由变元。**两个存在量词各自只管自己的部分，$Cx$ 中的 $x$ 自由。必须保留这个自由出现；两处存在量词也不要求使用同一个见证。

把两处约束变元分别改成新变元 $y,z$：

$$
(\exists xAx\land\exists xBx)\to Cx
\equiv(\exists yAy\land\exists zBz)\to Cx.
$$

合取内部先整理为

$$
\exists yAy\land\exists zBz
\equiv\exists y\exists z(Ay\land Bz).
$$

这里使用独立变量的量词与合取等价：$\exists y(\alpha\land\beta)\equiv(\exists y\alpha)\land\beta$，其中 $y$ 不在 $\beta$ 中自由出现。它可由习题 4.2.5（5）同样的证明推广至任意公式；也可由 Q1、Q2、Q3 展开合取后推出。

再连续两次用 Q3b，从前件提出存在量词：

$$
\begin{aligned}
\bigl(\exists y\exists z(Ay\land Bz)\bigr)\to Cx
&\equiv\forall y\bigl((\exists z(Ay\land Bz))\to Cx\bigr)\\
&\equiv\forall y\forall z\bigl((Ay\land Bz)\to Cx\bigr).
\end{aligned}
$$

因此一个答案是

$$
\boxed{\forall y\forall z\bigl((Ay\land Bz)\to Cx\bigr).}
$$

**为什么“存在”变成“任意”？**原式说“只要存在一对满足 $Ay\land Bz$ 的对象，就有 $Cx$”；后式说“对任意一对对象，如果它们满足 $Ay\land Bz$，就有 $Cx$”。后式要求每一对都满足这个条件句，并没有要求每一对都满足其前件。

不能写成 $\exists y\exists z((Ay\land Bz)\to Cx)$：那样即使 $Cx$ 假，也可能仅靠选一对不满足前件的对象让公式成立，条件变弱了。

### （2）$\forall xAx\leftrightarrow\exists xBx$

双条件先展开成两个蕴涵的合取，再对各处约束变元分别改名：

$$
\forall xAx\leftrightarrow\exists xBx
\equiv
(\forall uAu\to\exists vBv)
\land
(\exists wBw\to\forall zAz).
$$

分别处理两个蕴涵：

$$
\begin{aligned}
\forall uAu\to\exists vBv
&\equiv\exists u(Au\to\exists vBv)\\
&\equiv\exists u\exists v(Au\to Bv),\\[4pt]
\exists wBw\to\forall zAz
&\equiv\forall w(Bw\to\forall zAz)\\
&\equiv\forall w\forall z(Bw\to Az).
\end{aligned}
$$

第一组依次使用 Q3a、Q2b；第二组依次使用 Q3b、Q2a。由于四个约束变元已经互不冲突，量词可以从合取两侧提出，得到

$$
\boxed{
\exists u\exists v\forall w\forall z
\bigl((Au\to Bv)\land(Bw\to Az)\bigr).
}
$$

此处量词跨过合取时不翻转，且每一步都满足“该变元不在另一合取项中自由出现”的条件。这是按提取过程得到的合法前缀，不是先得到任意量词前缀后再随意重排。

## 四、做题时的检查顺序

1. 找出必须保留的自由变元；必要时先给约束变元改名。
2. 双条件先展开，避免直接对 $\leftrightarrow$ 套用蕴涵规则。
3. 提取时判断量词经过的是否定、蕴涵前件、蕴涵后件还是合取，并检查自由出现条件。
4. 最后确认量词都在前缀中、母式不再含量词，且没有误绑定原来的自由出现。

本节最值得保留的证明技巧是用逆否等价处理蕴涵前件中的量词；熟悉后就不必每次重新靠日常语言判断量词如何翻转。

整理日期：2026-11-03。
