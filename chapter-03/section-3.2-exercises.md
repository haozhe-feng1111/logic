# §3.2 自由出现和约束出现：习题 3.2.1–3.2.2

[返回习题目录](../README.md)

**教材依据：**郝兆宽、杨睿之、杨跃《数理逻辑：证明及其限度（第二版）》，第三章 §3.2，印刷页 70–72（本次 PDF 第 89–91 页）。自由出现及替换的递归定义见第 71 页；以下严格按书中定义 3.2.1 计算，不额外加入约束变元改名操作。

## 定义与记号

### $\varphi$ 表示什么

$\varphi$（phi）是元语言中代表整个公式的记号，本身不是公式内部的谓词符号或对象变元。例如，令

$$
\varphi=x\approx y\to\forall z(Rxz\land Ryz),
$$

以后写 $\varphi$ 就是在指这一整条公式。$x,y,z$ 是公式内部代表对象的变元；$\varphi,\psi$ 则是我们讨论公式时使用的占位记号。本节用 $\varphi_1,\varphi_2,\varphi_3$ 分别标记三个练习公式，下标只是为了区分它们。

### 自由出现与约束出现

教材用递归方式定义自由出现：

1. 原子公式中的变元出现都是自由出现。
2. 否定不改变内部变元出现的自由性。
3. 在 $\psi\to\gamma$ 中，来自两个子公式的自由出现仍为自由出现。
4. 在 $\forall v_i\psi$ 中，$x$ 的自由出现是 $\psi$ 中 $x$ 的自由出现，但要求 $x\ne v_i$。也就是说，新增的量词约束其辖域中原本自由的同名变元出现。

存在量词按通常缩写理解，判断约束范围的方法相同。某个变元出现若不是自由出现，就称为约束出现。判断时必须关注具体的出现位置；同一个变元可以在一个公式中既有自由出现，也有约束出现。

下面的表格逐个列出原子公式中的变元出现。量词后的变元符号用于标明约束对象，不另列入表格。用 $\mathrm{FV}(\varphi)$ 记公式中有自由出现的变元的集合。

### 替换记号及本书的约定

$\varphi_t^x$ 表示把 $\varphi$ 中 $x$ 的所有自由出现替换为项 $t$ 所得的公式：上标 $x$ 是被替换的变元，下标 $t$ 是换入的项。因此 $\varphi_y^x$ 是将自由的 $x$ 换成 $y$，不是将 $y$ 换成 $x$。

定义 3.2.1 对量词给出的规则是：

$$
(\forall u\psi)_t^x=
\begin{cases}
\forall u(\psi_t^x),&x\ne u;\\
\forall u\psi,&x=u.
\end{cases}
$$

对 $\exists u$ 有相同形式的规则，可从其缩写展开得到。遇到约束 $x$ 的量词时，不再向其辖域中替换；其他量词保持原样，继续递归替换。

**本书此处定义的是可以发生变元捕获的替换操作。** 定义没有要求先给约束变元改名，所以换入的 $y$ 或 $z$ 可能被原有同名量词约束。计算时只检查原式中 $x$ 的哪些出现是自由的，不要求换入的变元在结果中仍然自由。

<a id="exercise-321"></a>
## 3.2.1 找出各变元的自由出现和约束出现

### 题目

找出以下公式中每个变元的自由出现和约束出现：

$$
\begin{aligned}
\varphi_1&:=\forall x(Px\to\exists yQxy)\to\exists zRxyz;\\
\varphi_2&:=\forall x(x\approx z\to\neg\exists yRxy);\\
\varphi_3&:=x\approx y\to\forall z(Rxz\land Ryz).
\end{aligned}
$$

其中 $\approx$ 表示相等，$Px,Qxy,Rxyz$ 等采用教材省略谓词参数括号的写法。各小问分别讨论，其中 $R$ 的元数按该小问的公式确定。

### (1) $\varphi_1$

先把最外层蕴涵的两侧明确括起来：

$$
\underbrace{\forall x(Px\to\exists yQxy)}_{\text{前件}}
\quad\to\quad
\underbrace{\exists zRxyz}_{\text{后件}}.
$$

左边 $\forall x$ 的辖域是 $Px\to\exists yQxy$，不包括后件 $\exists zRxyz$。

| 原子公式 | 变元出现 | 性质与约束来源 |
| --- | --- | --- |
| $Px$ | $x$ | 约束出现，受前件的 $\forall x$ 约束 |
| $Qxy$ | $x$ | 约束出现，受前件的 $\forall x$ 约束 |
| $Qxy$ | $y$ | 约束出现，受 $\exists y$ 约束 |
| $Rxyz$ | $x$ | 自由出现 |
| $Rxyz$ | $y$ | 自由出现 |
| $Rxyz$ | $z$ | 约束出现，受后件的 $\exists z$ 约束 |

因此：

$$
\boxed{\mathrm{FV}(\varphi_1)=\{x,y\}.}
$$

这里 $x$ 和 $y$ 都既有自由出现，又有约束出现。左边出现过 $\forall x$ 或 $\exists y$，并不意味着它们能约束公式其他位置的一切同名变元。

### (2) $\varphi_2$

$$
\forall x\bigl(x\approx z\to\neg\exists yRxy\bigr).
$$

| 原子公式 | 变元出现 | 性质与约束来源 |
| --- | --- | --- |
| $x\approx z$ | $x$ | 约束出现，受 $\forall x$ 约束 |
| $x\approx z$ | $z$ | 自由出现 |
| $Rxy$ | $x$ | 约束出现，受 $\forall x$ 约束 |
| $Rxy$ | $y$ | 约束出现，受 $\exists y$ 约束 |

因此：

$$
\boxed{\mathrm{FV}(\varphi_2)=\{z\}.}
$$

$z$ 虽然位于 $\forall x$ 的辖域中，但 $\forall x$ 只约束 $x$，不约束 $z$。否定号也不改变量词对 $y$ 的约束。

### (3) $\varphi_3$

$$
x\approx y\to\forall z(Rxz\land Ryz).
$$

| 原子公式 | 变元出现 | 性质与约束来源 |
| --- | --- | --- |
| $x\approx y$ | $x,y$ | 都是自由出现 |
| $Rxz$ | $x$ | 自由出现 |
| $Rxz$ | $z$ | 约束出现，受 $\forall z$ 约束 |
| $Ryz$ | $y$ | 自由出现 |
| $Ryz$ | $z$ | 约束出现，受 $\forall z$ 约束 |

因此：

$$
\boxed{\mathrm{FV}(\varphi_3)=\{x,y\}.}
$$

三个公式都有自由变元，因此都不是闭公式（语句）。

<a id="exercise-322"></a>
## 3.2.2 分别计算 $\varphi_y^x$ 与 $\varphi_z^x$

### 题目

令 $\varphi$ 为习题 3.2.1 中的某个公式，分别求出 $\varphi_y^x$ 和 $\varphi_z^x$。以下将上一题的三个公式全部计算。

### (1) 对 $\varphi_1$ 的替换

$$
\varphi_1=\forall x(Px\to\exists yQxy)\to\exists zRxyz.
$$

只有后件 $Rxyz$ 中的 $x$ 是自由出现；前件的 $x$ 均受 $\forall x$ 约束，整段前件保持不变。因此：

$$
\boxed{
(\varphi_1)_y^x=
\forall x(Px\to\exists yQxy)\to\exists zRyyz.
}
$$

$$
\boxed{
(\varphi_1)_z^x=
\forall x(Px\to\exists yQxy)\to\exists zRzyz.
}
$$

第一式中，$Ryyz$ 的两个 $y$ 都是自由出现；前件的 $\exists y$ 不管后件。第二式中，换入的第一个 $z$ 被后件原有的 $\exists z$ 捕获，$Rzyz$ 中两个 $z$ 都是约束出现。

### (2) 对 $\varphi_2$ 的替换

$$
\varphi_2=\forall x(x\approx z\to\neg\exists yRxy).
$$

此式没有 $x$ 的自由出现；按定义，遇到最外面的 $\forall x$ 就停止替换。因此两个结果都等于原式：

$$
\boxed{
(\varphi_2)_y^x=(\varphi_2)_z^x=
\forall x(x\approx z\to\neg\exists yRxy).
}
$$

式中有自由的 $z$，但本题要求替换的是自由的 $x$，所以这个 $z$ 不受影响。

### (3) 对 $\varphi_3$ 的替换

$$
\varphi_3=x\approx y\to\forall z(Rxz\land Ryz).
$$

等式左边的 $x$ 和 $Rxz$ 中的 $x$ 都是自由出现，必须全部替换：

$$
\boxed{
(\varphi_3)_y^x=
y\approx y\to\forall z(Ryz\land Ryz).
}
$$

$$
\boxed{
(\varphi_3)_z^x=
z\approx y\to\forall z(Rzz\land Ryz).
}
$$

第二式中，等式左边新换入的 $z$ 是自由出现，因为它不在 $\forall z$ 的辖域中；$Rzz$ 的第一个 $z$ 则被原有的 $\forall z$ 捕获。因此结果中同名的 $z$ 既有自由出现，也有约束出现。

## 为什么要定义替换

替换使我们能够把含自由变元的表达式应用到一个由项指称的对象上。项不仅可以是另一个变元，还可以是常数或由函数构造的复杂项。例如，对

$$
\psi(x):=x+0\approx x
$$

用 $S(0)$ 替换自由的 $x$，得到

$$
\psi_{S(0)}^x=S(0)+0\approx S(0).
$$

在自然数的通常解释下，这就是“$1$ 加零等于 $1$”。此例仅用于说明替换，使用的是相应的算术语言。

替换在推理中的典型用途，是把一般规律应用到具体对象。例如，令 $H(x)$ 表示“$x$ 是人”，$M(x)$ 表示“$x$ 会死”，常数 $s$ 指称苏格拉底。由

$$
\forall x\bigl(H(x)\to M(x)\bigr)
$$

可实例化得到

$$
H(s)\to M(s).
$$

这里是对量词后面的子公式 $H(x)\to M(x)$ 作替换；$x$ 在这个子公式中是自由的。若对包含最外层 $\forall x$ 的整个公式计算 $\varphi_s^x$，按本节定义，整个公式反而保持不变。取量词的实例与直接替换整个公式，需要区分。

本节先定义一个语法操作；不能因此认为任何这样的操作都自动成为合法的推理步骤。例如，按书中定义，

$$
\bigl(\exists y(x<y)\bigr)_y^x=\exists y(y<y).
$$

原式表示“有对象比 $x$ 大”；换入的 $y$ 被捕获后，结果却表示“有对象比自身大”。因此在推理或语义中使用替换时，还要检查相应的可代入条件，不能省略这一步。本题的任务只是按定义求出替换后的公式。

## 本节复习要点

1. 先找出量词辖域，再逐个判断变元出现；不能只看公式中是否出现过同名量词。
2. 量词只约束辖域中的同名变元，不会约束所有变元。
3. 自由与约束是某次出现的性质，同一个变元可以两种出现都有。
4. $\varphi_t^x$ 只替换原式中 $x$ 的自由出现；量词本身和约束出现保持不变。
5. 本题按教材定义 3.2.1 计算，允许换入变元被已有量词捕获，不自行改名来避免捕获。
6. 替换是公式的语法操作；把它用于一般规律的实例化时，还要检查相应条件。

整理日期：2026-11-02。
