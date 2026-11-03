# §5.1 一阶语言的结构：习题与复习笔记

[返回习题目录](../README.md)

**范围：**习题 5.1.1–5.1.12，共十二道。保留题号与题意，证明按复习需要整理；附结构、赋值、语义蕴涵的说明及反例构造方法。蕴涵按右结合理解。

## 本节概念

### 结构、赋值和项的值

以语言中有二元谓词符号 $P$、一元函数符号 $f$ 和常数符号 $c$ 为例：

$$
\mathcal A=(\mathbb N,\le,S,0),\qquad S(n)=n+1.
$$

这里 $\mathcal A$ 是整个结构；$|\mathcal A|=\mathbb N$ 是非空论域；$P^{\mathcal A}$、$f^{\mathcal A}$、$c^{\mathcal A}$ 分别把符号解释成“小于等于”、后继函数和自然数 $0$。上标表示在该结构中的解释，不是乘方。

二元关系 $P^{\mathcal A}$ 是有序对的集合：$(a,b)\in P^{\mathcal A}$ 表示 $aPb$ 成立。可以把论域看成点的集合，把关系看成箭头的集合。

赋值 $s:V\to|\mathcal A|$ 给所有变元指定对象，它不包含在结构中。$s_d^x$ 表示仅把 $x$ 的取值改成 $d$，其他变元保持不变。

$\bar s$ 把 $s$ 扩展到所有项：

$$
\bar s(x)=s(x),\qquad
\bar s(c)=c^{\mathcal A},\qquad
\bar s(f(t_1,\ldots,t_n))
=f^{\mathcal A}(\bar s(t_1),\ldots,\bar s(t_n)).
$$

例如在上述结构中，若 $s(v_i)=i-1$，则 $\bar s(ffv_3)=4$、$\bar s(ffc)=2$。项的值是对象；公式才有真假。

### 满足、语义蕴涵与普遍有效

- $(\mathcal A,s)\models\varphi$：在这个结构和赋值下，公式为真。
- $\mathcal A\models\sigma$：句子 $\sigma$ 在该结构中为真。句子没有自由变元，因此真假不依赖赋值。
- $\Gamma\models\varphi$：对所有结构 $\mathcal A$ 和赋值 $s$，只要 $\Gamma$ 中的公式全真，$\varphi$ 就真。
- $\models\varphi$：对所有结构和所有赋值，$\varphi$ 都真，即普遍有效。

语义蕴涵等价于“不存在前提全真、结论假的结构与赋值”。它不保证前提能够同时为真。例如 $\{\alpha,\neg\alpha\}\models\psi$ 对任意 $\psi$ 都成立。

语义证明中的“任取 $(\mathcal A,s)$，假设它满足前提”，是在证明一个条件句，并没有先断言满足前提的结构一定存在。

### 自由变元和约束变元

在 $\forall v_1Pv_2v_1$ 中，$v_2$ 是自由的，按 $s(v_2)$ 取值；$v_1$ 受量词约束，要遍历论域。判断全称公式时，不能只检查最初的 $s(v_1)$。

同一个变元符号在不同位置可以有不同作用。例如

$$
\forall v_1Qv_1\models Qv_1
$$

左边的出现受约束，右边的出现自由。也可以把左边改名为 $\forall xQx\models Qv_1$，含义不变。

## 习题目录

| 题号 | 内容 | 主要方法 |
| --- | --- | --- |
| [5.1.1](#exercise-511) | 或、且、存在量词的语义 | 展开缩写 |
| [5.1.2](#exercise-512) | 全称蕴涵存在 | 非空论域提供见证 |
| [5.1.3](#exercise-513) | 固定结构中的真假与普遍有效 | 单元素、二元素结构 |
| [5.1.4](#exercise-514) | 语义版演绎定理 | 两方向证明、蕴涵真值 |
| [5.1.5](#exercise-515) | 普遍有效性的双条件与语义等价 | 两个都不普遍有效的公式 |
| [5.1.6](#exercise-516) | 三个语句互不被其余两个蕴涵 | 三个有限反例结构 |
| [5.1.7](#exercise-517) | 对象参数与常数解释 | 展开新记号与满足定义 |
| [5.1.8](#exercise-518) | 全称公式下的分离规则 | 在同一修改赋值下使用前提 |
| [5.1.9](#exercise-519) | 对非自由变元全称化 | 自由变元赋值一致性 |
| [5.1.10](#exercise-5110) | 相等对象在函数和关系中的替换 | 项的解释、相同有序对 |
| [5.1.11](#exercise-5111) | 普遍有效与全称闭合一步 | 所有赋值与修改赋值 |
| [5.1.12](#exercise-5112) | 存在一个对象使全称蕴涵成立 | 全部满足或存在反例对象 |

<a id="exercise-511"></a>
## 5.1.1 或、且与存在量词的语义

### 题目与思路

$\varphi\lor\psi$、$\varphi\land\psi$、$\exists x\varphi$ 分别是 $(\neg\varphi)\to\psi$、$\neg(\varphi\to\neg\psi)$、$\neg\forall x\neg\varphi$ 的缩写。根据定义解释它们的满足条件。

只需使用：否定翻转真假；蕴涵只有在前件真、后件假时为假。

### 解答

**（1）或。**$\varphi\lor\psi$ 为假当且仅当 $\neg\varphi$ 真而 $\psi$ 假，即 $\varphi,\psi$ 都假。因此

$$
(\mathcal A,s)\models\varphi\lor\psi
\iff
(\mathcal A,s)\models\varphi\ \text{或}\ (\mathcal A,s)\models\psi.
$$

这里的“或”包含两者都真的情况。

**（2）且。**$\neg(\varphi\to\neg\psi)$ 为真当且仅当内部蕴涵为假，即 $\varphi$ 真、$\neg\psi$ 假。因此

$$
(\mathcal A,s)\models\varphi\land\psi
\iff
(\mathcal A,s)\models\varphi\ \text{且}\ (\mathcal A,s)\models\psi.
$$

**（3）存在。**$\neg\forall x\neg\varphi$ 表示“并非每个对象都使 $\varphi$ 为假”，因此

$$
(\mathcal A,s)\models\exists x\varphi
\iff
\text{存在 }d\in|\mathcal A|,\quad(\mathcal A,s_d^x)\models\varphi.
$$

存在量词要求找到一个合适对象，不要求原赋值 $s(x)$ 就是这个对象。

<a id="exercise-512"></a>
## 5.1.2 全称蕴涵存在与非空论域

### 题目与思路

证明 $\models\forall x\varphi(x)\to\exists x\varphi(x)$，指出何处用到了论域非空。

“所有人都会游泳”能保证“有人会游泳”，需要至少有一个人。

### 证明

任取结构 $\mathcal A$ 和赋值 $s$。若全称前件为假，整个蕴涵为真。若

$$
(\mathcal A,s)\models\forall x\varphi(x),
$$

则对每个 $d\in|\mathcal A|$，都有 $(\mathcal A,s_d^x)\models\varphi(x)$。**由论域非空，选取 $d_0\in|\mathcal A|$**，便有 $(\mathcal A,s_{d_0}^x)\models\varphi(x)$，故 $(\mathcal A,s)\models\exists x\varphi(x)$。

因此该蕴涵普遍有效。非空条件用于选取见证 $d_0$。若另行允许空论域，并按通常量词语义理解，“所有对象都满足”会空泛为真，“存在对象满足”则为假；本课程的定义排除了空论域。

<a id="exercise-513"></a>
## 5.1.3 固定结构中的真假与普遍有效

### 题目

固定一阶语言 $\mathcal L$，判断并证明或举反例：

1. 对任意 $\mathcal L$-结构 $\mathcal A$ 和语句 $\sigma$，或者 $\mathcal A\models\sigma$，或者 $\mathcal A\models\neg\sigma$。
2. 对任意语句 $\sigma$，或者 $\models\sigma$，或者 $\models\neg\sigma$。

### 解答

**（1）正确。**句子的真假不依赖赋值。固定结构后，$\sigma$ 有确定真值；若为真，则 $\mathcal A\models\sigma$；若为假，由否定的语义，$\mathcal A\models\neg\sigma$。两者恰好一个成立。

**（2）错误。**取

$$
\sigma=\forall x\forall y(x\approx y).
$$

它表示论域只有一个元素。在单元素结构中为真，在二元素结构中为假。语言中的其他非逻辑符号可作任意合法解释，不影响这个句子的真假。因此 $\not\models\sigma$ 且 $\not\models\neg\sigma$。

**易错点：**$\not\models\sigma$ 表示“有结构使它假”，$\models\neg\sigma$ 表示“所有结构都使它假”，两者不同。

<a id="exercise-514"></a>
## 5.1.4 语义版演绎定理

### 题目与思路

证明

$$
\Gamma\cup\{\varphi\}\models\psi
\iff
\Gamma\models(\varphi\to\psi).
$$

左边把 $\varphi$ 作为额外前提，右边把它写成结论中蕴涵的前件。

### 证明

**正向。**假设 $\Gamma\cup\{\varphi\}\models\psi$。任取 $\mathcal A,s$，假设它们满足 $\Gamma$ 中的所有公式。

- 若 $\varphi$ 假，则 $\varphi\to\psi$ 真。
- 若 $\varphi$ 真，则 $\Gamma\cup\{\varphi\}$ 中的公式全真，由最开始的语义蕴涵假设，$\psi$ 真，所以 $\varphi\to\psi$ 真。

故 $\Gamma\models(\varphi\to\psi)$。

**反向。**假设 $\Gamma\models(\varphi\to\psi)$。任取满足 $\Gamma\cup\{\varphi\}$ 的 $\mathcal A,s$。由其满足 $\Gamma$ 及假设，$\varphi\to\psi$ 真；又有 $\varphi$ 真，故 $\psi$ 真。因此 $\Gamma\cup\{\varphi\}\models\psi$。

**易错点：**证明中的“假设满足 $\Gamma$”不承诺这种结构与赋值存在。若没有这样的结构与赋值，就不存在前提全真、结论假的反例，语义蕴涵仍成立。

<a id="exercise-515"></a>
## 5.1.5 普遍有效性的双条件不保证语义等价

### 题目与思路

举例说明：在“$\models\varphi$ 当且仅当 $\models\psi$”的条件下，不一定有 $\models(\varphi\leftrightarrow\psi)$。

题目条件是在比较“是否普遍有效”这两个判断；结论要求两个公式在每个相同结构与赋值下真假一致。

### 反例

取

$$
\varphi=\forall x\forall y(x\approx y),\qquad\psi=\neg\varphi.
$$

在单元素结构中，$\varphi$ 真、$\psi$ 假；在二元素结构中，$\varphi$ 假、$\psi$ 真。

因此“$\models\varphi$”和“$\models\psi$”两个判断都为假，它们之间的元语言双条件成立，满足题目条件。但在单元素结构中 $\varphi\leftrightarrow\psi$ 为假，所以

$$
\not\models(\varphi\leftrightarrow\psi).
$$

**易错点：**题目条件不表示 $\varphi\models\psi$ 且 $\psi\models\varphi$。真正的互相语义蕴涵才等价于 $\models(\varphi\leftrightarrow\psi)$。两个公式各自不普遍有效的反例可以来自不同结构；检查一个语义蕴涵的反例时，则必须在同一个结构、同一个赋值下让前提真而结论假。

<a id="exercise-516"></a>
## 5.1.6 三个语句互不被其余两个语义蕴涵

### 题目与思路

证明下列任一句都不被其余两句共同语义蕴涵：

$$
\begin{aligned}
\sigma_1&=\forall x\forall y\forall z(Pxy\to(Pyz\to Pxz));\\
\sigma_2&=\forall x\forall y(Pxy\to(Pyx\to x\approx y));\\
\sigma_3&=(\forall x\exists yPxy)\to\exists y\forall xPxy.
\end{aligned}
$$

$\sigma_1$ 表示传递性，$\sigma_2$ 表示反对称性，$\sigma_3$ 表示“各自有对应对象，则有同一个共同对象”。每次构造一个结构，使目标句假、其余两句真。

### 三个反例

**（1）反驳 $\{\sigma_2,\sigma_3\}\models\sigma_1$。**取

$$
|\mathcal A_1|=\{0,1,2\},\qquad
P^{\mathcal A_1}=\{(0,1),(1,2)\}.
$$

- $\sigma_1$ 假：$0P1$、$1P2$，但没有 $0P2$。
- $\sigma_2$ 真：没有任何双向箭头，$Pxy\land Pyx$ 对所有 $x,y$ 都假，所以相应蕴涵为真。
- $\sigma_3$ 真：$2$ 没有出箭头，$\forall x\exists yPxy$ 假，故整个蕴涵真。

**（2）反驳 $\{\sigma_1,\sigma_3\}\models\sigma_2$。**取

$$
|\mathcal A_2|=\{0,1\},\qquad
P^{\mathcal A_2}=\{(0,0),(0,1),(1,0),(1,1)\}.
$$

- $\sigma_1$ 真：任意 $x,z$ 都满足 $Pxz$。
- $\sigma_2$ 假：$0P1$、$1P0$，却有 $0\ne1$。
- $\sigma_3$ 真：选择共同对象 $y=0$，有 $\forall xPx0$，后件真。

**（3）反驳 $\{\sigma_1,\sigma_2\}\models\sigma_3$。**取

$$
|\mathcal A_3|=\{0,1\},\qquad
P^{\mathcal A_3}=\{(0,0),(1,1)\}.
$$

- $\sigma_1$ 真：$P$ 解释为相等，具有传递性。
- $\sigma_2$ 真：$Pxy$ 已经要求 $x=y$。
- $\sigma_3$ 假：每个 $x$ 取 $y=x$，使前件真；但没有同一个 $y$ 同时等于 $0$ 和 $1$，后件假。

| 结构 | $\sigma_1$ | $\sigma_2$ | $\sigma_3$ |
| --- | --- | --- | --- |
| $\mathcal A_1$ | 假 | 真 | 真 |
| $\mathcal A_2$ | 真 | 假 | 真 |
| $\mathcal A_3$ | 真 | 真 | 假 |

每一行都是在同一个结构中比较三个句子的真假，故所需的三个不蕴涵均成立。

### 考试时如何想到这些结构

从目标为假的条件倒推，再检查另外两个句子：

- 破坏传递性：画 $0\to1\to2$，不画 $0\to2$。
- 破坏反对称性：在不同点之间画双向箭头；为保持传递性，再补两个自环。
- 破坏“各自有推出共同有”：让两个点各自只指向自己。

反对称性没有要求双向箭头存在，只禁止不同点之间出现双向箭头；一个蕴涵为真，也不要求它的前件为真。

<a id="exercise-517"></a>
## 5.1.7 对象参数与常数解释

### 题目与思路

设 $v_1$ 是 $\varphi(v_1)$ 唯一的自由变元，$d\in|\mathcal A|$。定义 $\mathcal A\models\varphi[d]$ 表示：对所有赋值 $s$，$(\mathcal A,s_d^{v_1})\models\varphi(v_1)$。证明

$$
\mathcal A\models(\forall v_2Qv_1v_2)[c^{\mathcal A}]
\iff
\mathcal A\models\forall v_2Qcv_2,
$$

其中 $Q$ 是二元谓词符号，$c$ 是常数符号。

左边通过赋值让 $v_1$ 指向对象 $c^{\mathcal A}$，右边直接用符号 $c$ 指向同一对象。方括号表示带对象参数的满足记号，不是把一个论域对象当作语言中的项来机械替换。

### 证明

由定义，左边等价于：对每个赋值 $s$ 和每个 $e\in|\mathcal A|$，

$$
\left(\mathcal A,(s_{c^{\mathcal A}}^{v_1})_e^{v_2}\right)
\models Qv_1v_2.
$$

这又等价于

$$
\text{对每个 }e\in|\mathcal A|,\quad
(c^{\mathcal A},e)\in Q^{\mathcal A}.
$$

右边的 $\forall v_2Qcv_2$ 是句子。根据常数解释、原子公式和全称量词的语义，它也恰好等价于上式，故两边等价。

<a id="exercise-518"></a>
## 5.1.8 全称公式下的分离规则

### 题目与思路

证明

$$
\{\forall x(\varphi\to\psi),\forall x\varphi\}\models\forall x\psi.
$$

对任意对象，都有“若 $\varphi$ 则 $\psi$”，且都有 $\varphi$，所以都有 $\psi$。

### 证明

任取 $\mathcal A,s$，假设它们满足两个前提。对任意 $d\in|\mathcal A|$，由全称量词的语义，

$$
(\mathcal A,s_d^x)\models\varphi\to\psi,
\qquad
(\mathcal A,s_d^x)\models\varphi.
$$

由蕴涵的语义，$(\mathcal A,s_d^x)\models\psi$。由 $d$ 的任意性，$(\mathcal A,s)\models\forall x\psi$，故题设的语义蕴涵成立。

两个前提必须用在同一个修改赋值 $s_d^x$ 下。

<a id="exercise-519"></a>
## 5.1.9 对非自由变元全称化

### 题目与思路

证明：若 $x$ 不在 $\varphi$ 中自由出现，则 $\varphi\models\forall x\varphi$。

改变 $x$ 的外部赋值不影响 $\varphi$ 的真假，因此可以让 $x$ 遍历论域。

### 证明

任取 $\mathcal A,s$，假设 $(\mathcal A,s)\models\varphi$。对任意 $d\in|\mathcal A|$，$s$ 与 $s_d^x$ 在 $\varphi$ 所有自由变元上的取值相同。由定理 5.1.5，

$$
(\mathcal A,s_d^x)\models\varphi.
$$

故 $(\mathcal A,s)\models\forall x\varphi$，所需语义蕴涵成立。

“不自由出现”允许约束出现。若去掉条件，结论不成立，例如自然数结构中取 $\varphi=(x\approx0)$、$s(x)=0$，则 $\varphi$ 真而 $\forall x\varphi$ 假。

<a id="exercise-5110"></a>
## 5.1.10 相等对象在函数和关系中的替换

### 题目与思路

证明公式

$$
x\approx y\to(Pzfx\to Pzfy)
$$

普遍有效，其中 $f$ 是一元函数符号，$P$ 是二元谓词符号。这里 $Pzfx$ 表示 $P(z,f(x))$。

若两个变元指向同一对象，函数作用后的结果相同，放入关系中得到的有序对也相同。

### 证明

任取 $\mathcal A,s$。若 $s(x)\ne s(y)$，则外层蕴涵前件假，公式真。若 $s(x)=s(y)$，则

$$
\bar s(fx)=f^{\mathcal A}(s(x))
=f^{\mathcal A}(s(y))=\bar s(fy).
$$

因此 $(s(z),\bar s(fx))$ 与 $(s(z),\bar s(fy))$ 是同一个有序对，它们是否属于 $P^{\mathcal A}$ 的情况一致。所以 $Pzfx$ 与 $Pzfy$ 真值相同，内部蕴涵真，整个公式真。由 $\mathcal A,s$ 的任意性，公式普遍有效。

**证明使用的语言：**这是元语言中的数学证明。使用的是实际函数对同一输入给出同一输出，以及相同有序对具有相同集合归属等背景数学事实。对象语言的 $\approx$ 由语义解释为对象真正相同；本题不调用待证的可靠性或完全性定理。

<a id="exercise-5111"></a>
## 5.1.11 普遍有效与全称量化

### 题目与思路

证明

$$
\models\varphi\iff\models\forall x\varphi.
$$

普遍有效已经要求所有赋值下都真，包含 $x$ 的所有可能取值，因此再加全称量词不增加要求。

### 证明

**正向。**假设 $\models\varphi$。任取 $\mathcal A,s$。对每个 $d\in|\mathcal A|$，$s_d^x$ 也是赋值，故 $(\mathcal A,s_d^x)\models\varphi$。于是 $(\mathcal A,s)\models\forall x\varphi$，故 $\models\forall x\varphi$。

**反向。**假设 $\models\forall x\varphi$。任取 $\mathcal A,s$，则 $(\mathcal A,s)\models\forall x\varphi$。特别令 $d=s(x)$，有 $(\mathcal A,s_{s(x)}^x)\models\varphi$。因为 $s_{s(x)}^x=s$，故 $(\mathcal A,s)\models\varphi$。由任意性得 $\models\varphi$。

**与 5.1.9 的区别：**本题不限制 $x$ 是否自由出现，因为起点是“所有结构、所有赋值下都真”。5.1.9 则从某个结构与赋值下 $\varphi$ 真出发，需要 $x$ 不自由出现。

<a id="exercise-5112"></a>
## 5.1.12 存在一个对象使全称蕴涵成立

### 题目与思路

证明

$$
\models\exists x(Px\to\forall xPx).
$$

先把内层约束变元改名，等价写为

$$
\exists x(Px\to\forall yPy).
$$

它表示“存在一个对象，使得若它有性质 $P$，则所有对象都有性质 $P$”。若所有人都会游泳，任选一人，后件真；若有人不会游泳，就选这个人，前件假。两种情况都使蕴涵真。

### 证明

任取 $\mathcal A,s$，分两种情况。

**（1）$P^{\mathcal A}=|\mathcal A|$。**所有对象都有性质 $P$，故 $\forall yPy$ 真。由论域非空，任选 $a\in|\mathcal A|$，都有

$$
(\mathcal A,s_a^x)\models Px\to\forall yPy.
$$

**（2）$P^{\mathcal A}\ne|\mathcal A|$。**由于 $P^{\mathcal A}\subseteq|\mathcal A|$，可取 $a\in|\mathcal A|\setminus P^{\mathcal A}$。此时在 $s_a^x$ 下，$Px$ 假，蕴涵同样真。

两种情况都找到了见证 $a$，故 $(\mathcal A,s)\models\exists x(Px\to\forall yPy)$。由任意性，原公式普遍有效。

**分类的依据：**按后件 $\forall yPy$ 的真假分类。后件真时直接成功；后件假时，“并非所有对象都有性质 $P$”恰好提供一个让前件为假的对象。

## 与第四章和第六章的联系

第四章用对象语言的公理和规则定义 $\Gamma\vdash\varphi$；第五章在元语言中通过结构和赋值定义 $\Gamma\models\varphi$。本节的语义证明直接使用满足定义和背景数学推理。

第六章将分别证明可靠性与完全性：

$$
\Gamma\vdash\varphi\Longrightarrow\Gamma\models\varphi,
\qquad
\Gamma\models\varphi\Longrightarrow\Gamma\vdash\varphi.
$$

5.1.8–5.1.11 验证了相关推理步骤或相等实例在语义上保持正确，是建立这座联系的具体工作。5.1.12 与第四章习题 4.2.4 中相应的形式定理也是同一公式在两个层次的对应。

整理日期：2026-11-03。
