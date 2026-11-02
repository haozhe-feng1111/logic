# §3.1 一阶逻辑的语言：习题 3.1.1–3.1.5

[返回习题目录](../README.md)

**教材依据：**郝兆宽、杨睿之、杨跃《数理逻辑：证明及其限度（第二版）》，第三章 §3.1。题目依据本次复习提供的教材截图整理，答案与推导按讨论展开；对自然语言中有歧义的表述注明所采用的读法。

**记号约定：**$\approx$ 表示相等；$N(x)$、$I(x)$ 的含义在相应题目中指定。连续蕴涵按右结合理解。使用 $\land,\lor,\exists$ 等常用缩写，函数运算采用通常的中缀写法。

<a id="exercise-311"></a>
## 3.1.1 “存在着的鬼”与存在断言

### 题目

选择一阶逻辑语言，并将下列语句转换成一阶语句。你认为这些语句构成的推理有错误吗？为什么？

1. 如果存在存在着的鬼，则鬼存在；
2. 存在着的鬼当然存在；
3. 鬼存在。

### 语言与翻译

取一个一元谓词符号 $G$，$G(x)$ 表示“$x$ 是鬼”。存在由量词 $\exists$ 表达，无须另设“存在”谓词。令

$$
A:=\exists x\,G(x).
$$

将第 (2) 句理解为“若有存在着的鬼，那么鬼当然存在”，三个语句可分别形式化为：

$$
\begin{aligned}
(1)&\quad (\exists x\,G(x))\to(\exists x\,G(x));\\
(2)&\quad (\exists x\,G(x))\to(\exists x\,G(x));\\
(3)&\quad \exists x\,G(x).
\end{aligned}
$$

也就是从 $A\to A$、$A\to A$ 推出 $A$。

讨论中的关键认识：前两句都是重言式 $A\to A$，无论 $A$ 的真假都成立；第三句是 $A$ 本身，并不总为真。前提永远为真，不能保证结论也永远为真。

### 推理分析

推理无效。前两句只是条件命题，没有提供 $A$ 本身。要用分离规则从 $A\to A$ 得到 $A$，仍须先有 $A$，而这恰好是待证明的结论。

“存在着的鬼”这一名词短语，不能单凭字面上的“存在”就保证有对象满足它。

### 反例结构

取论域 $D=\{d\}$，令 $G$ 的解释为空集，即没有对象是鬼。则 $A$ 为假，而前两个 $A\to A$ 都为真。因此存在前提全真、结论为假的结构，推理无效。

这里使用的是非空论域；没有鬼不等于论域为空。

### 自然语言的歧义

如果把第 (2) 句直接理解为“确实有鬼存在”，就应翻译成 $A$。此时推出第 (3) 句当然有效，但结论已经被当作前提，并未独立证明鬼存在。

### 复习要点

- 区分“如果有满足某性质的对象，那么……”与“确实存在满足该性质的对象”。
- $A\to A$ 永远为真，但不保证 $A$ 为真。
- 证明推理无效，可以构造前提全真、结论为假的结构。

<a id="exercise-312"></a>
## 3.1.2 数、好玩与量词的范围

### 题目与语言

设一元谓词 $N(x)$ 表示“$x$ 是一个数”，$I(x)$ 表示“$x$ 好玩”；二元谓词 $<$ 表示“小于”；常数符号 $0$ 表示数学零。将下列中文语句翻译为公式。自然语言可能有歧义，以下采用逐字、明确量词范围的读法。

论域未被限定为只有数，因此量化时须用 $N$ 限制对象。

### (1) 零小于所有的数

$$
\forall x\bigl(N(x)\to 0<x\bigr).
$$

任取对象 $x$，如果它是数，那么零小于它。“所有的数”包括零（在 $N(0)$ 成立的通常解释下），所以该语句要求 $0<0$。在通常的数与严格小于关系的解释下，这句话为假；这不影响它是正确的翻译。不能自行把原句改成“零小于所有正数”。

### (2) 要是有数好玩的话，零就好玩

$$
\bigl(\exists x(N(x)\land I(x))\bigr)\to I(0).
$$

“有数好玩”是整个条件句的前件，表示存在至少一个既是数又好玩的对象。

### (3) 没有小于零的数

$$
\neg\exists x\bigl(N(x)\land x<0\bigr).
$$

等价地：

$$
\forall x\bigl(N(x)\to\neg(x<0)\bigr).
$$

这里写 $\neg(x<0)$，不额外引入语言中没有规定的 $\ge$ 符号。

### (4) 要是一个不好玩的数满足所有比它小的数都好玩这条性质，则它本身也好玩

$$
\forall x\left[
\left(N(x)\land\neg I(x)\land
\forall y\bigl((N(y)\land y<x)\to I(y)\bigr)\right)
\to I(x)
\right].
$$

外层任取一个对象 $x$。前件要求：它是数、它不好玩、所有比它小的数都好玩；后件说它好玩。结论与前件中的 $\neg I(x)$ 冲突，但公式仍然合式，表达的是不存在满足全部前件条件的对象，即不存在最小的不好玩的数（“最小”在此指所有更小的数都好玩）。

它在命题逻辑上等价于：

$$
\forall x\left[
\left(N(x)\land
\forall y\bigl((N(y)\land y<x)\to I(y)\bigr)\right)
\to I(x)
\right].
$$

这里是利用逻辑等价消去前件中的 $\neg I(x)$，而不是在逐字翻译时漏掉“不好玩”。

### (5) 不存在所有数都比它小的数

$$
\neg\exists x\left[
N(x)\land\forall y\bigl(N(y)\to y<x\bigr)
\right].
$$

先固定“它”指代的 $x$，再说所有数 $y$ 都小于 $x$，最后否定这样的数 $x$ 存在。注意 $y$ 也可以等于 $x$；原句没有排除自身，因此不能直接把它改写成“没有最大数”。

### (6) 不存在没有数不比它小的数

$$
\neg\exists x\left[
N(x)\land
\neg\exists y\bigl(N(y)\land\neg(y<x)\bigr)
\right].
$$

由内向外拆解：

1. $\neg(y<x)$：$y$ 不比它小。
2. $\exists y(N(y)\land\neg(y<x))$：有数不比它小。
3. 再取否定：没有数不比它小。
4. 最外层：不存在满足上述性质的数 $x$。

因为

$$
\neg\exists y\bigl(N(y)\land\neg(y<x)\bigr)
\iff
\forall y\bigl(N(y)\to y<x\bigr),
$$

所以按上述读法，第 (5)、(6) 问逻辑等价。

### 复习要点

- 所有数都满足 $P$：$\forall x(N(x)\to P(x))$。
- 有数满足 $P$：$\exists x(N(x)\land P(x))$。
- 没有数满足 $P$：$\neg\exists x(N(x)\land P(x))$。
- 翻译先保留原句含义，不为了使语句为真而补入“正数”“其他”等限制。
- 遇到多层否定，先固定代词指向的对象，再由内向外拆解。

<a id="exercise-313"></a>
## 3.1.3 将公式翻译成日常中文

### 题目

沿用 3.1.2 的语言，将下面的一阶语句转换成日常中文：

$$
\forall x\bigl(Nx\to Ix\to\neg\forall y(Ny\to Iy\to\neg(x<y))\bigr).
$$

其中 $N(x)$ 表示“$x$ 是数”，$I(x)$ 表示“$x$ 好玩”。要求使用日常中文，不把量词和符号逐字照搬。

### 答案

**每个好玩的数，都有一个比它更大的好玩的数。**

### 推导

按蕴涵右结合的约定，$A\to B\to C$ 表示 $A\to(B\to C)$，等价于 $(A\land B)\to C$。所以原式可写为：

$$
\forall x\left[
(N(x)\land I(x))\to
\neg\forall y\left((N(y)\land I(y))\to\neg(x<y)\right)
\right].
$$

固定 $x$，处理里面的否定：

$$
\begin{aligned}
&\neg\forall y\left((N(y)\land I(y))\to\neg(x<y)\right)\\
\iff{}&\exists y\,\neg\left((N(y)\land I(y))\to\neg(x<y)\right)\\
\iff{}&\exists y\left(N(y)\land I(y)\land x<y\right).
\end{aligned}
$$

用到 $\neg\forall y\,\varphi\iff\exists y\,\neg\varphi$ 以及 $\neg(P\to Q)\iff P\land\neg Q$。

因此原式等价于：

$$
\forall x\left[
(N(x)\land I(x))\to
\exists y\left(N(y)\land I(y)\land x<y\right)
\right],
$$

即每个好玩的数都有一个更大的好玩的数。

### 复习要点

- 连续蕴涵先补出括号，再合并前件。
- “并非所有……都……”可改写为“存在一个……不……”。
- 否定一个蕴涵，要求前件真、后件假。
- 原句本身不保证有好玩的数；如果没有好玩的数，外层条件句仍然成立。
- 在通常的严格线性序解释下，可简述为“好玩的数没有最大值”，但“每个都有更大的”保留了原式完整含义，不依赖额外的序公理。

<a id="exercise-314"></a>
## 3.1.4 整数中的奇数与平方和

### 题目与语言

二元函数符号 $+$、$\cdot$ 分别表示加法、乘法；常数符号 $1,2,3,4$ 分别表示对应整数。所有变量的取值均为整数。$\approx$ 表示相等。

### (1) 将公式转换成中文语句

$$
\forall x\left[
\exists m(x\approx 2\cdot m+1)
\to
\exists n(x\cdot x\approx 2\cdot n+1)
\right].
$$

**答案：每个奇数的平方都是奇数。**

- $\exists m(x\approx 2\cdot m+1)$ 表示整数 $x$ 可以写成 $2m+1$，即 $x$ 是奇数。
- $\exists n(x\cdot x\approx 2\cdot n+1)$ 表示 $x$ 的平方可以写成 $2n+1$，即它也是奇数。
- 外层量词和蕴涵把两者连成“任意整数若为奇数，其平方也是奇数”。

核对：若 $x=2m+1$，则 $x^2=2(2m^2+2m)+1$，取整数 $n=2m^2+2m$ 即可。此处幂记号仅用于解释；正式公式用 $x\cdot x$ 表示平方。

### (2) 将“没有形如 $4k+3$ 的整数是平方和”转换成公式

这里把“平方和”理解为“两个整数的平方和”。原句没有明确写出项数，因此需说明这一读法。

$$
\boxed{
\neg\exists k\exists a\exists b\,
\left(4\cdot k+3\approx a\cdot a+b\cdot b\right)
}
$$

等价地：

$$
\forall k\forall a\forall b\,
\neg\left(4\cdot k+3\approx a\cdot a+b\cdot b\right).
$$

即不存在三个整数 $k,a,b$，使 $4k+3=a^2+b^2$。

核对：整数平方除以 $4$ 的余数只能是 $0$ 或 $1$，两个平方之和的余数只能是 $0,1,2$，不可能是 $3$。

如果“平方和”允许任意多个平方相加，原句在通常整数解释下就不成立，例如 $3=1^2+1^2+1^2$。上述公式明确表达的是两个平方之和。

### 复习要点

- 先确定变量的取值范围。本题论域是整数，无须额外加入 $N(x)$。
- “形如 $2m+1$”用存在量词表达，而不是把 $m$ 当作某个预先固定的整数。
- 翻译存在性命题时要约束全部辅助变量，避免遗漏量词。
- 正式公式只能使用题目给定的符号；平方可用同一项的乘积表示。
- 自然语言省略了必要条件时，应说明所采用的读法。

<a id="exercise-315"></a>
## 3.1.5 否定量词命题：极限与线性无关

### 题目

1. 已知数学分析中的极限定义，写出 $\lim_{x\to a}f(x)\ne l$ 的定义，即否定“$f(x)$ 在 $x\to a$ 时以 $l$ 为极限”。
2. 已知向量组线性相关的定义：存在一组不全为零的实系数，使线性组合等于零向量。写出向量组 $\mathbf x_1,\ldots,\mathbf x_n$ 线性无关的定义。

教材说明本题作为数学练习；下面分别给出原定义、否定过程和整理后的结论。

### 通用规则

$$
\neg\forall x\,P(x)\iff\exists x\,\neg P(x),\qquad
\neg\exists x\,P(x)\iff\forall x\,\neg P(x).
$$

$$
\neg(P\to Q)\iff P\land\neg Q,\qquad
\neg(P\land Q)\iff\neg P\lor\neg Q.
$$

否定受限量词时保持取值范围，例如 $\neg\forall\epsilon>0$ 变为 $\exists\epsilon>0$。

### (1) 极限不等于指定值的定义

已知

$$
\lim_{x\to a}f(x)=l
\iff
(\forall\epsilon>0)(\exists\delta>0)(\forall x\in\mathbb R)
\left[0<|x-a|<\delta\to|f(x)-l|<\epsilon\right].
$$

对整个条件取否定。量词前缀 $\forall\epsilon\exists\delta\forall x$ 变为 $\exists\epsilon\forall\delta\exists x$；蕴涵的否定要求前件成立、后件不成立。因此“不以 $l$ 为极限”的定义为：

$$
\boxed{
(\exists\epsilon>0)(\forall\delta>0)(\exists x\in\mathbb R)
\left[0<|x-a|<\delta\land|f(x)-l|\ge\epsilon\right]
}
$$

日常表述：存在一个固定的正误差标准 $\epsilon$，无论邻域半径 $\delta$ 取得多小，总能在该去心邻域中找到一个点 $x$，使函数值与 $l$ 的距离至少为 $\epsilon$。

注意：$\epsilon$ 先选定，$x$ 可以随 $\delta$ 改变。结论是每个邻域都有一个不达标点，不是每个点都不达标。这里否定的是“以 $l$ 为极限”，包含极限不存在的情形，并不保证另一个不同的极限存在。

### (2) 线性无关的定义

设 $\mathbf x_1,\ldots,\mathbf x_n$ 是实向量空间中的向量。线性相关表示：

$$
\exists c_1\in\mathbb R\cdots\exists c_n\in\mathbb R
\left[
\neg(c_1=0\land\cdots\land c_n=0)
\land
\sum_{i=1}^{n}c_i\mathbf x_i=\mathbf 0
\right].
$$

线性无关是否定上述存在断言：不存在一组不全为零的系数，使线性组合为零向量。

翻转量词并应用德摩根律，得到：

$$
\forall c_1\in\mathbb R\cdots\forall c_n\in\mathbb R
\left[
(c_1=0\land\cdots\land c_n=0)
\lor
\sum_{i=1}^{n}c_i\mathbf x_i\ne\mathbf 0
\right].
$$

等价的标准写法是：

$$
\boxed{
\forall c_1\in\mathbb R\cdots\forall c_n\in\mathbb R
\left[
\sum_{i=1}^{n}c_i\mathbf x_i=\mathbf 0
\to
(c_1=0\land\cdots\land c_n=0)
\right]
}
$$

日常表述：只有所有系数都为零，才能使这些向量的线性组合等于零向量，即该齐次向量方程只有零解。

不能写成“对所有系数，线性组合都不为零”，因为全零系数总会给出零向量。

### 复习要点

- 否定整个命题时，沿量词从外向内翻转 $\forall$ 与 $\exists$，保持原有顺序。
- 量词后的条件也必须否定，不能只改量词。
- $<$ 的否定是 $\ge$，不能漏掉等号。
- “不全为零”的否定是“全为零”，不是“全不为零”。
- 区分实数零与零向量，证明中分别写作 $0$ 和 $\mathbf 0$。
