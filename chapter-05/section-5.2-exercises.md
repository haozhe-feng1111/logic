# §5.2 可定义性：习题与复习笔记

[返回习题目录](../README.md)

**范围：**习题 5.2.1–5.2.4，共四道。依据本次提供的教材截图整理题目与解答；附可定义性的两种方向、配对构造，以及量词次序的易错点。默认结构的论域非空，等词 $\approx$ 解释为实际相等。

## 本节概念

### 结构、模型与结构类

结构 $\mathcal A$ 包含非空论域 $|\mathcal A|$，以及语言中各个非逻辑符号的解释。同一个论域，配上不同的符号解释，可以得到不同的结构。这里 $|\mathcal A|$ 表示论域集合，不是元素个数。

$$
\mathcal A\models\tau
\quad\text{表示结构 }\mathcal A\text{ 满足语句 }\tau;
\qquad
\operatorname{Mod}\tau=\{\mathcal A:\mathcal A\models\tau\}.
$$

$\operatorname{Mod}$ 来自 model（模型）。$\operatorname{Mod}\Sigma$ 表示同时满足语句集 $\Sigma$ 中每个语句的所有结构组成的类。

- **初等类（EC）：**存在一个语句 $\tau$，使 $\mathcal K=\operatorname{Mod}\tau$。
- **广义初等类（$\mathrm{EC}_{\Delta}$）：**存在一个语句集 $\Sigma$，使 $\mathcal K=\operatorname{Mod}\Sigma$。

若 $\Sigma=\{\sigma_1,\ldots,\sigma_n\}$ 有限且非空，可以令 $\tau=\sigma_1\land\cdots\land\sigma_n$，于是

$$
\operatorname{Mod}\Sigma
=\operatorname{Mod}\tau
=\bigcap_{i=1}^{n}\operatorname{Mod}\sigma_i.
$$

空语句集对应所有结构，也可用语句 $\forall x(x\approx x)$ 描述。因此，有限语句集定义的结构类总是初等类。

例如严格线序的三条要求是传递性、任意不同元素可比较、非对称性。每一条单独定义一个结构类，三条合取后才定义严格线序结构组成的类。“严格”意味着元素不与自身有序关系；非对称性比反对称性更强，两者不要混淆。

### 固定结构中的可定义性

另一种方向是固定结构 $\mathcal A$，用公式挑出论域内部的元素或元素组。若 $\varphi(v_1,\ldots,v_k)$ 的所有自由变元都已列出，则

$$
\mathcal A\models\varphi[a_1,\ldots,a_k]
$$

表示给 $v_i$ 赋值为 $a_i$ 后公式成立。其他变元的外部赋值不影响结果。方括号是满足关系的简写，不是把实际对象当成语言中的项来替换。

在不使用额外参数的意义下，关系 $R\subseteq|\mathcal A|^k$ 可定义，是指存在原语言中的公式 $\varphi(v_1,\ldots,v_k)$，使

$$
R=\{(a_1,\ldots,a_k)\in|\mathcal A|^k:
\mathcal A\models\varphi[a_1,\ldots,a_k]\}.
$$

$k=1$ 时就是定义一个子集；$k=2$ 时就是定义一个二元关系。给论域元素添加常数名字会扩充语言；使用这些名字时，要区分原语言可定义与带参数可定义。

## 习题目录

| 题号 | 内容 | 主要方法 |
| --- | --- | --- |
| [5.2.1](#exercise-521) | 结合律与左右方程可解推出群 | 从局部单位元推广到全局单位元 |
| [5.2.2](#exercise-522) | 有任意正偶数大小的模型，无奇数大小的有限模型 | 无不动点的对合、两两配对 |
| [5.2.3](#exercise-523) | 在自然数加乘结构中定义零、一、后继与小于 | 用性质代替缺少的符号 |
| [5.2.4](#exercise-524) | 描述二元素论域、函数与一一对应 | 存在性、唯一性、入箭头与出箭头 |

<a id="exercise-521"></a>
## 5.2.1 方程可解性与群

### 题目与思路

证明满足下列语句的结构为一个群：

$$
\begin{aligned}
&\forall x\forall y\forall z\,
\bigl(x\circ(y\circ z)\approx(x\circ y)\circ z\bigr);\\
&\forall x\forall y\exists z\,(x\circ z\approx y);\\
&\forall x\forall y\exists z\,(z\circ x\approx y).
\end{aligned}
$$

后两条分别表示任意方程 $xz=y$、$zx=y$ 可解。结合律已经给出；需要构造双侧单位元和双侧逆元。下面在元语言推导中把 $\circ$ 省略，并把相等写成 $=$。

### 证明

设论域为非空集合 $G$，固定 $a\in G$。

**（1）构造右单位元。**由第二条，存在 $r\in G$ 使 $ar=a$。对任意 $x\in G$，由第三条，存在 $t\in G$ 使 $ta=x$。利用结合律，

$$
xr=(ta)r=t(ar)=ta=x.
$$

所以同一个 $r$ 对所有 $x$ 都满足 $xr=x$，是右单位元。

**（2）构造左单位元，并证明二者相同。**由第三条，存在 $l\in G$ 使 $la=a$。对任意 $x\in G$，由第二条，存在 $s\in G$ 使 $as=x$。于是

$$
lx=l(as)=(la)s=as=x.
$$

所以 $l$ 是左单位元。由 $r$ 的右单位性质及 $l$ 的左单位性质，

$$
l=lr=r.
$$

记这个共同元素为 $e$，则对所有 $x\in G$ 都有 $xe=ex=x$。

**（3）构造双侧逆元。**任取 $x\in G$。由后两条，存在 $b,c\in G$ 使 $bx=e$、$xc=e$。于是

$$
b=be=b(xc)=(bx)c=ec=c.
$$

故 $b=c$ 是 $x$ 的双侧逆元。结合律、双侧单位元和双侧逆元均已具备，因此 $(G,\circ)$ 是群。

### 为什么任取了 $a$，还要再引入 $x$

由方程可解性，只能直接得到

$$
\forall a\exists r\,(ar=a),
$$

其中 $r$ 可能依赖 $a$；右单位元却要求

$$
\exists r\forall x\,(xr=x).
$$

不能直接交换量词。证明先固定一个 $a$，选出一个 $r$，再保持这个 $r$ 不变，验证它对所有 $x$ 都有效。引入 $x$ 正是为了完成这一步。

**如何想到：**已知 $ar=a$，目标是 $xr=x$。尝试把任意 $x$ 写成含有固定元素 $a$ 的形式。题设允许 $x=ta$，结合律便把目标接到已知等式上。

### 与初等类的联系

在只有等词和二元运算符号的语言中，三条语句的合取就描述了群结构组成的类。语言里不必预先给出单位元常数和逆元函数符号：公理可以保证它们存在。

反过来，群中 $xz=y$ 可取 $z=x^{-1}y$，$zx=y$ 可取 $z=yx^{-1}$，因此群也满足题设三条语句。

<a id="exercise-522"></a>
## 5.2.2 只有偶数大小的有限模型

### 题目与思路

找出一个语句 $\sigma$，使得对任何正整数 $n$，$\sigma$ 都有一个恰好具有 $2n$ 个元素的模型，并且没有恰好具有奇数个元素的有限模型。语言中含有等词，可以自行选择其他符号。

把“元素数是偶数”转化为“所有元素能两两配对”。选择一元函数符号 $f$，把 $f(x)$ 看作 $x$ 的搭档。

### 解答与验证

选取语言 $\mathcal L=\{\approx,f\}$，令

$$
\boxed{\sigma=\forall x\bigl(f(f(x))\approx x\land\neg(f(x)\approx x)\bigr).}
$$

两个条件分别表示“搭档的搭档是自己”和“不能与自己配对”，即 $f$ 是一个无不动点的对合。

**（1）构造任意正偶数大小的模型。**给定正整数 $n$，取论域 $A=\{1,2,\ldots,2n\}$，定义

$$
f^{\mathcal A}(2k-1)=2k,\qquad
f^{\mathcal A}(2k)=2k-1\quad(1\le k\le n).
$$

这使元素按 $1\leftrightarrow2,3\leftrightarrow4,\ldots,2n-1\leftrightarrow2n$ 配对，显然 $\mathcal A\models\sigma$。

**（2）排除奇数大小的有限模型。**设有限结构 $\mathcal A\models\sigma$，以下简写其函数解释为 $f$。对每个 $a$，集合 $B_a=\{a,f(a)\}$ 恰有两个元素，且 $B_{f(a)}=B_a$。若 $B_a$ 与 $B_b$ 相交，取交点 $c$，便有 $B_a=B_c=B_b$。因此这些二元素集合构成论域的一个划分。

若共有 $k$ 组，则论域元素数为 $2k$，不可能为奇数。

**易错点：**仅要求 $f(x)\ne x$ 不够，有限集合上仍可能出现三元循环。还需要 $f(f(x))=x$，才能把循环限制成二元配对。

<a id="exercise-523"></a>
## 5.2.3 在自然数加乘结构中定义集合与关系

### 题目

语言中含有等词和两个二元函数符号 $+$、$\times$。分别找出在结构 $(\mathbb N,+,\times)$ 中定义下列集合与关系的公式：

1. $\{0\}$；
2. $\{1\}$；
3. $\{(m,n):n\text{ 是 }m\text{ 在 }\mathbb N\text{ 中的后继}\}$；
4. $\{(m,n):m<n\}$，其中 $<$ 是自然数上的自然序。

这里 $\mathbb N$ 包含 $0$。下面的公式只使用等词、加法和乘法，不引入额外常数名字或参数。

### 解答

**（1）零。**自然数中只有 $0$ 满足加上自己仍等于自己，因此取

$$
\boxed{\varphi_0(x):\quad x+x\approx x.}
$$

**（2）一。**利用乘法单位元的性质，取

$$
\boxed{\varphi_1(x):\quad\forall z\,(x\times z\approx z).}
$$

$1$ 显然满足；反过来，若 $a$ 满足该公式，在结构中令 $z$ 取实际自然数 $1$，便得 $a\times1=1$，故 $a=1$。这里是在元语言中选取赋值，不是在对象语言公式中加入常数符号 $1$。

**（3）后继。**用满足 $\varphi_1$ 的元素代替 $1$，取

$$
\boxed{\varphi_S(x,y):\quad
\exists u\Bigl(\forall z\,(u\times z\approx z)\land y\approx x+u\Bigr).}
$$

其中 $u$ 被限定为 $1$，因此公式恰好表示 $y=x+1$。

**（4）小于。**$m<n$ 当且仅当存在非零自然数 $u$，使 $m+u=n$。利用（1），取

$$
\boxed{\varphi_{<}(x,y):\quad
\exists u\Bigl(x+u\approx y\land\neg(u+u\approx u)\Bigr).}
$$

公式中的非零条件排除了 $u=0$；若删除这一条件，定义出来的是 $m\le n$。

### 关键思路

语言里没有给一个元素或关系起名字，不代表无法定义它。先用已有运算识别 $0$、$1$，再把这些识别条件嵌入更复杂的公式。定义必须相对于指定结构理解；这些公式的正确性用到了自然数加乘运算的性质。

<a id="exercise-524"></a>
## 5.2.4 二元素论域、函数与一一对应

### 题目

设语言含有等词和二元谓词符号 $P$。对以下条件分别找出语句 $\sigma$，使得结构 $\mathcal A=(|\mathcal A|,P^{\mathcal A})$ 满足 $\sigma$ 当且仅当该条件成立：

1. $|\mathcal A|$ 有且仅有两个元素；
2. $P^{\mathcal A}$ 是从 $|\mathcal A|$ 到自身的函数；
3. $P^{\mathcal A}$ 是从 $|\mathcal A|$ 到自身的一一对应。

三问分别作答，不要求把前一问的条件全部带入后一问。第二、三问把二元关系理解成函数的图像，$P(x,y)$ 表示输入 $x$ 对应输出 $y$。

### 解答

**（1）恰好两个元素。**存在两个不同元素，且所有元素都是它们之一：

$$
\boxed{\sigma_1=\exists x\exists y\Bigl(
\neg(x\approx y)\land\forall z\,(z\approx x\lor z\approx y)
\Bigr).}
$$

不同保证至少两个；全称条件保证至多两个。关系 $P^{\mathcal A}$ 无需满足额外要求。

**（2）函数。**每个输入恰好有一个输出：

$$
\boxed{\sigma_2=\forall x\exists y\Bigl(
P(x,y)\land\forall z\,(P(x,z)\to z\approx y)
\Bigr).}
$$

$\exists yP(x,y)$ 保证输出存在；后半句保证任何输出都等于这个 $y$，即输出唯一。由于 $P^{\mathcal A}\subseteq|\mathcal A|^2$，输出自动属于同一论域。

**（3）一一对应。**既要求每个输入恰好有一个输出，也要求每个输出恰好有一个原像：

$$
\boxed{
\begin{aligned}
\sigma_3={}&
\forall x\exists y\Bigl(P(x,y)\land
\forall z\,(P(x,z)\to z\approx y)\Bigr)\\
&\land\forall y\exists x\Bigl(P(x,y)\land
\forall z\,(P(z,y)\to z\approx x)\Bigr).
\end{aligned}
}
$$

第一部分保证函数性。第二部分中的原像存在保证满射，原像唯一保证单射，因此恰好描述一一对应。

### 直观记法与易错点

把 $P(x,y)$ 画成箭头 $x\to y$：函数要求每个点恰好有一条出箭头；一一对应还要求每个点恰好有一条入箭头。允许自环。

不要把“每个输入的输出唯一”和“每个输出的原像唯一”混淆，前者是函数的要求，后者是单射的要求。$P$ 是关系符号，不能直接当成函数项写成 $P(x)$。

整理日期：2026-11-03。
