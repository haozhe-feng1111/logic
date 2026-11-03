# §4.3 其他元定理：习题笔记

[返回习题目录](../README.md) · [§4.2 的证明工具](section-4.2-notes.md)

**范围：**习题 4.3.1–4.3.4，共四道大题。题目依据本次提供的教材截图整理；证明、解释和易错点为复习展开。

| 题号 | 内容 | 主要方法 |
| --- | --- | --- |
| [4.3.1](#exercise-431) | 替换后换回的反例与循环替换引理 | 变元捕获、项与公式的结构归纳 |
| [4.3.2](#exercise-432) | 两层全称公式中的变元改名 | 新变元、全称实例化、概括定理 |
| [4.3.3](#exercise-433) | 相等的传递性（Eq3） | 第六组公理、演绎定理、概括定理 |
| [4.3.4](#exercise-434) | 等价替换定理 | 对替换位置外层结构归纳 |

本节继续使用 §4.1–§4.2 的证明工具，重点研究替换、改名与相等操作的合法性。

## 阅读前的三个区分

**自由出现与约束出现要按位置判断。**在 $P(x)\land\forall xQ(x)$ 中，前一个 $x$ 自由，后一个 $x$ 被约束。同一个变元符号可以有不同类型的出现。

**语法替换与无冲突替换不同。**记号 $\varphi_y^x$ 表示把 $\varphi$ 中自由出现的 $x$ 换成 $y$，不修改被约束的 $x$。教材的语法定义允许算出捕获后的结果；无冲突性是能否用于替换公理的额外条件。例如

$$
(\forall yPx)_y^x=\forall yPy
$$

可以计算，但换入的 $y$ 被捕获，因此这个替换不满足无冲突条件。此处不先改约束变元的名字。

**公式相同与公式等价不同。**$Px$ 和 $Py$ 是不同的公式；即使二者的变元都自由，也不能直接写成同一公式。在同一个赋值下，它们甚至可以真假不同。4.3.1 中的等号要求恢复完全相同的公式；4.3.4 则要求替换前后可证明地等价。

<a id="exercise-431"></a>
## 4.3.1 循环替换引理

### （1）两种不能恢复原公式的例子

题目要求给出两个 $(\varphi_y^x)_x^y\ne\varphi$ 的例子：一个使 $x$ 从无到有，另一个使 $x$ 从有到无。以下取 $x\ne y$。

**例一：原来没有 $x$，换一圈后有 $x$。**取 $\varphi:=Py$。则

$$
\varphi_y^x=Py,\qquad (\varphi_y^x)_x^y=Px\ne Py.
$$

第一次没有自由的 $x$ 可换；第二次却把原本就有的自由 $y$ 换成了 $x$。问题是第二次替换无法区分“原有的 $y$”与“第一次换入的 $y$”。

**例二：原来有 $x$，换一圈后没有 $x$。**取 $\varphi:=\forall yPx$。则

$$
\varphi_y^x=\forall yPy,\qquad
(\varphi_y^x)_x^y=\forall yPy\ne\forall yPx.
$$

第一次换入的 $y$ 被量词捕获；第二次只处理自由的 $y$，所以无法把它换回来。

### （2）循环替换引理

**题目。**若 $y$ 完全不在公式 $\varphi$ 中出现，则 $x$ 可以在 $\varphi_y^x$ 中无冲突地替换 $y$，并且

$$
\boxed{(\varphi_y^x)_x^y=\varphi.}
$$

**思想。**“完全不出现”同时排除两种障碍：没有原有自由 $y$ 被误换，也没有 $\forall y$ 捕获第一次换入的 $y$。结果中的自由 $y$ 都来自原来自由的 $x$；这些位置原来没有受到 $\forall x$ 约束，所以换回也不会捕获。

**证明。**若 $x=y$，因该变元完全不出现，结论立即成立。以下设 $x\ne y$，对公式结构归纳，同时证明无冲突性与还原等式。

**原子公式。**先对项 $t$ 归纳证明：若 $y$ 不在 $t$ 中出现，则 $(t_y^x)_x^y=t$。

- $t=x$ 时，两次替换为 $x\mapsto y\mapsto x$。
- $t$ 是其他变元或常数时，两次替换均不改变它；其中“其他变元”不可能是 $y$。
- $t=f(t_1,\ldots,t_n)$ 时，对每个子项使用归纳假设。

因此，若原子公式为 $R(t_1,\ldots,t_n)$ 或 $t_1\approx t_2$，逐项替换后恢复原公式。原子公式没有量词，第二次替换不会发生捕获。

**否定公式。**若 $\varphi=\neg\alpha$，由归纳假设，

$$
(\varphi_y^x)_x^y
=\neg\bigl((\alpha_y^x)_x^y\bigr)
=\neg\alpha=\varphi.
$$

否定不增加量词，无冲突性也由归纳假设继承。

**蕴涵公式。**若 $\varphi=\alpha\to\beta$，分别对两边使用归纳假设，得到

$$
(\varphi_y^x)_x^y
=(\alpha_y^x)_x^y\to(\beta_y^x)_x^y
=\alpha\to\beta=\varphi.
$$

无冲突性同样分别继承。

**全称公式。**若 $\varphi=\forall z\alpha$，由 $y$ 完全不出现可知 $z\ne y$。

- 若 $z=x$，第一次替换不进入 $\forall x$ 的辖域，故 $\varphi_y^x=\varphi$。原公式又没有 $y$，所以第二次也不改变它，且无冲突性自动满足。
- 若 $z\ne x$，则 $z$ 与 $x,y$ 都不同。由归纳假设，

$$
(\varphi_y^x)_x^y
=\forall z\bigl((\alpha_y^x)_x^y\bigr)
=\forall z\alpha=\varphi.
$$

第二次替换在内部无冲突；外层量词绑定的是 $z\ne x$，也不会捕获换入的 $x$。

归纳完成。其他联词及存在量词按教材的缩写定义展开处理。

**易错点。**条件是 $y$ 完全不出现，比“$y$ 不自由出现”强。上面的第二个反例中，$y$ 只约束出现，换回仍然失败。

<a id="exercise-432"></a>
## 4.3.2 两层全称公式中的变元改名

### 题目与思路

证明

$$
\forall x\forall yPxy\vdash\forall y\forall xPyx.
$$

不仅外层量词的名字交换了，谓词中对应的变元也交换了。使用新变元 $z$ 周转，保证两个位置在操作中保持独立。

### 证明

记 $\Gamma:=\{\forall x\forall yPxy\}$，取与 $x,y$ 不同的新变元 $z$。

| 行 | 在 $\Gamma$ 下得到的公式 | 依据 |
| --- | --- | --- |
| 1 | $\forall x\forall yPxy$ | 前提 |
| 2 | $\forall yPzy$ | 全称实例化，外层 $x$ 换成 $z$ |
| 3 | $Pzx$ | 全称实例化，$y$ 换成 $x$ |
| 4 | $\forall zPzx$ | 对 $z$ 概括 |
| 5 | $Pyx$ | 全称实例化，$z$ 换成 $y$ |
| 6 | $\forall xPyx$ | 对 $x$ 概括 |
| 7 | $\forall y\forall xPyx$ | 对 $y$ 概括 |

每次“全称实例化”都是第二组公理加一次分离规则。例如第 2 行使用

$$
\forall x\forall yPxy\to\forall yPzy,
$$

第 3 行使用 $\forall yPzy\to Pzx$。三次替换均满足无冲突条件。唯一前提没有自由变元，所以三次概括也都合法。

### 易错点

不能直接把外层 $x$ 实例化成 $y$：内部公式是 $\forall yPxy$，换入的 $y$ 会被捕获，得到 $\forall yPyy$，所以这不是合法的第二组公理实例。

中间得到的 $Pzx$ 等公式是结论，不是额外添加的前提。概括时检查的前提集始终是 $\Gamma$。

本题直接使用前面建立的工具；与 §4.3 的联系在于控制变元改名和捕获，而不是必须另引一个新定理。

<a id="exercise-433"></a>
## 4.3.3 相等的传递性（Eq3）

### 题目

$$
\vdash\forall x\forall y\forall z
\bigl(x\approx y\to(y\approx z\to x\approx z)\bigr).
$$

蕴涵向右结合，因此只需在两个假设 $x\approx y$、$y\approx z$ 下证明 $x\approx z$，再撤去假设并概括。

### 怎样选择第六组公理

第六组公理的形式是

$$
u\approx v\to(\alpha\to\alpha'),
$$

其中 $\alpha$ 是原子公式，$\alpha'$ 由把其中某些位置的 $u$ 换成 $v$ 得到。模板中的变元不限定必须叫 $x,y$。

本题选择如下：

| 公理中的角色 | 本题选择 |
| --- | --- |
| 替换依据 $u\approx v$ | $y\approx z$ |
| 原子公式 $\alpha$ | $x\approx y$ |
| 替换后的 $\alpha'$ | $x\approx z$ |

因此得到公理实例

$$
\boxed{y\approx z\to(x\approx y\to x\approx z).}
$$

这是用 $y\approx z$ 作为依据，修改原公式 $x\approx y$；没有把题目中的第一个假设改成别的假设。公理实例的前件顺序也不要求与最终目标一致。

### 证明

令 $\Gamma:=\{x\approx y,y\approx z\}$。

| 行 | 在 $\Gamma$ 下得到的公式 | 依据 |
| --- | --- | --- |
| 1 | $y\approx z$ | 前提 |
| 2 | $y\approx z\to(x\approx y\to x\approx z)$ | 第六组公理 |
| 3 | $x\approx y\to x\approx z$ | 1、2 分离 |
| 4 | $x\approx y$ | 前提 |
| 5 | $x\approx z$ | 4、3 分离 |

先撤去 $y\approx z$，得到

$$
x\approx y\vdash y\approx z\to x\approx z.
$$

再撤去 $x\approx y$，得到

$$
\vdash x\approx y\to(y\approx z\to x\approx z).
$$

现在前提集为空，可以依次对 $z$、$y$、$x$ 概括，得到所求。

**易错点。**两个假设尚未撤去时，其中有自由变元，不能直接按空前提情形任意概括。先用演绎定理撤去假设，再加上量词。

<a id="exercise-434"></a>
## 4.3.4 等价替换定理

### 题目与思想

假设 $\varphi'$ 由把 $\varphi$ 中某个子公式 $\psi$ 的指定出现替换成 $\psi'$ 得到。若 $\vdash\psi\leftrightarrow\psi'$，证明

$$
\boxed{\vdash\varphi\leftrightarrow\varphi'.}
$$

这里替换的是整个子公式，不是自由变元。例如，由 $\vdash\neg\neg Px\leftrightarrow Px$，可以推出

$$
\vdash\forall x(\neg\neg Px\to Qx)
\leftrightarrow\forall x(Px\to Qx).
$$

证明只需从指定的替换位置开始，逐层证明外面的公式仍然等价。

### 证明

对从整个公式到指定替换位置的结构层数归纳。

**起点：整个公式就是要替换的部分。**此时 $\varphi=\psi$、$\varphi'=\psi'$，结论正是已知的 $\vdash\psi\leftrightarrow\psi'$。这里 $\psi$ 不必是原子公式。

**否定层。**若 $\varphi=\neg\alpha$、$\varphi'=\neg\alpha'$，由归纳假设 $\vdash\alpha\leftrightarrow\alpha'$，再使用重言式

$$
(\alpha\leftrightarrow\alpha')\to(\neg\alpha\leftrightarrow\neg\alpha'),
$$

得到 $\vdash\varphi\leftrightarrow\varphi'$。

**蕴涵层。**若替换发生在前件，$\varphi=\alpha\to\beta$、$\varphi'=\alpha'\to\beta$。由归纳假设和重言式

$$
(\alpha\leftrightarrow\alpha')\to
\bigl((\alpha\to\beta)\leftrightarrow(\alpha'\to\beta)\bigr),
$$

得到所求。若替换发生在后件，同理使用

$$
(\beta\leftrightarrow\beta')\to
\bigl((\alpha\to\beta)\leftrightarrow(\alpha\to\beta')\bigr).
$$

**全称量词层。**若 $\varphi=\forall x\alpha$、$\varphi'=\forall x\alpha'$，归纳假设给出

$$
\vdash\alpha\to\alpha',\qquad\vdash\alpha'\to\alpha.
$$

分别使用习题 4.2.3（1），即概括定理配合第三组公理，得到

$$
\vdash\forall x\alpha\to\forall x\alpha',\qquad
\vdash\forall x\alpha'\to\forall x\alpha.
$$

由重言规则合并，得 $\vdash\forall x\alpha\leftrightarrow\forall x\alpha'$。

以上情况覆盖从替换位置向外的所有基本构造，故归纳完成。如果要替换多个指定出现，可逐次使用本结论，再由等价的传递性连接。

### 为什么没有其他结构情况

本书以原子公式、否定、蕴涵、全称量词为基本构造。原子公式形如 $R(t_1,\ldots,t_n)$ 或 $t_1\approx t_2$；它不仅没有量词，也没有逻辑联词。项内部可以有函数符号。

其他符号通过缩写引入，例如

$$
\alpha\lor\beta:=\neg\alpha\to\beta,\qquad
\alpha\land\beta:=\neg(\alpha\to\neg\beta),\qquad
\exists x\alpha:=\neg\forall x\neg\alpha.
$$

因此无需给 $\land,\lor,\exists$ 另设基本归纳情况。本题的归纳起点则是“到达指定替换位置”，不要求该处公式为原子公式。

**关键条件。**假设是无前提可证的 $\psi\leftrightarrow\psi'$，所以量词层的概括条件自动满足。不能把某个含自由变元的等价式仅作为额外前提，却不检查条件就照样向量词内部替换。

整理日期：2026-11-03。
