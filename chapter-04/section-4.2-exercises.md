# §4.2 推理和元定理：习题笔记

[返回习题目录](../README.md) · [本节概念与证明工具](section-4.2-notes.md)

**范围：**习题 4.2.1–4.2.5，共五道大题。题目依据本次提供的教材截图整理；公理形式沿用教材第 43、73 页。证明和直观解释为复习展开。

| 题号 | 核心问题 | 主要工具 |
| --- | --- | --- |
| [4.2.1](#exercise-421) | 不使用元定理证明全称蕴涵存在 | 公理实例、分离规则 |
| [4.2.2](#exercise-422) | 概括后推演长度的上界 | 对推演各行归纳、计数 |
| [4.2.3](#exercise-423) | 无前提定理与额外前提的区别 | 概括定理、第三组公理、反例 |
| [4.2.4](#exercise-424) | 存在性命题与量词推理 | 反证法、全称实例化、概括定理 |
| [4.2.5](#exercise-425) | 量词与联词的关系 | 重言规则、量词单调性、演绎定理 |

仅 4.2.1 明确禁止使用元定理；其余各题可以使用已经证明的工具。以下 $\exists x\alpha$ 始终按 $\neg\forall x\neg\alpha$ 理解。

<a id="exercise-421"></a>
## 4.2.1 不使用元定理的推演序列

### 题目

给出从空集到 $\forall x\varphi\to\exists x\varphi$ 的推演。须给出推演序列，不使用任何元定理。

### 记号缩写

以下只作书写缩写，不引入前提或额外推理规则：

$$
A:=\forall x\varphi,\qquad B:=\forall x\neg\varphi,\qquad U:=\neg B,\qquad W:=\neg\neg B.
$$

存在量词按教材定义展开，所以目标就是 $A\to U$。

公理使用本书的三个模板：

$$
\begin{aligned}
\mathrm{A1}:\;&\alpha\to(\beta\to\alpha),\\
\mathrm{A2}:\;&(\alpha\to(\beta\to\delta))\to((\alpha\to\beta)\to(\alpha\to\delta)),\\
\mathrm{A3}:\;&(\neg\beta\to\neg\alpha)\to((\neg\beta\to\alpha)\to\beta).
\end{aligned}
$$

MP 表示分离规则。下面不直接引用重言规则、演绎定理、反证法或双重否定消去。

### 完整推演

| 行 | 公式 | 依据 |
| --- | --- | --- |
| 1 | $U\to ((U\to U)\to U)$ | A1 |
| 2 | $U\to (U\to U)$ | A1 |
| 3 | $(U\to ((U\to U)\to U))\to ((U\to (U\to U))\to (U\to U))$ | A2 |
| 4 | $(U\to (U\to U))\to (U\to U)$ | MP(1,3) |
| 5 | $U\to U$ | MP(2,4) |
| 6 | $(U\to W)\to ((U\to U)\to B)$ | A3 |
| 7 | $W\to (U\to W)$ | A1 |
| 8 | $((U\to W)\to ((U\to U)\to B))\to (W\to ((U\to W)\to ((U\to U)\to B)))$ | A1 |
| 9 | $W\to ((U\to W)\to ((U\to U)\to B))$ | MP(6,8) |
| 10 | $(W\to ((U\to W)\to ((U\to U)\to B)))\to ((W\to (U\to W))\to (W\to ((U\to U)\to B)))$ | A2 |
| 11 | $(W\to (U\to W))\to (W\to ((U\to U)\to B))$ | MP(9,10) |
| 12 | $W\to ((U\to U)\to B)$ | MP(7,11) |
| 13 | $(U\to U)\to (W\to (U\to U))$ | A1 |
| 14 | $W\to (U\to U)$ | MP(5,13) |
| 15 | $(W\to ((U\to U)\to B))\to ((W\to (U\to U))\to (W\to B))$ | A2 |
| 16 | $(W\to (U\to U))\to (W\to B)$ | MP(12,15) |
| 17 | $W\to B$ | MP(14,16) |
| 18 | $B\to \neg \varphi$ | 第二组 |
| 19 | $(B\to \neg \varphi)\to (W\to (B\to \neg \varphi))$ | A1 |
| 20 | $W\to (B\to \neg \varphi)$ | MP(18,19) |
| 21 | $(W\to (B\to \neg \varphi))\to ((W\to B)\to (W\to \neg \varphi))$ | A2 |
| 22 | $(W\to B)\to (W\to \neg \varphi)$ | MP(20,21) |
| 23 | $W\to \neg \varphi$ | MP(17,22) |
| 24 | $(W\to \neg \varphi)\to ((W\to \varphi)\to U)$ | A3 |
| 25 | $(W\to \varphi)\to U$ | MP(23,24) |
| 26 | $A\to \varphi$ | 第二组 |
| 27 | $\varphi\to (W\to \varphi)$ | A1 |
| 28 | $(\varphi\to (W\to \varphi))\to (A\to (\varphi\to (W\to \varphi)))$ | A1 |
| 29 | $A\to (\varphi\to (W\to \varphi))$ | MP(27,28) |
| 30 | $(A\to (\varphi\to (W\to \varphi)))\to ((A\to \varphi)\to (A\to (W\to \varphi)))$ | A2 |
| 31 | $(A\to \varphi)\to (A\to (W\to \varphi))$ | MP(29,30) |
| 32 | $A\to (W\to \varphi)$ | MP(26,31) |
| 33 | $((W\to \varphi)\to U)\to (A\to ((W\to \varphi)\to U))$ | A1 |
| 34 | $A\to ((W\to \varphi)\to U)$ | MP(25,33) |
| 35 | $(A\to ((W\to \varphi)\to U))\to ((A\to (W\to \varphi))\to (A\to U))$ | A2 |
| 36 | $(A\to (W\to \varphi))\to (A\to U)$ | MP(34,35) |
| 37 | $A\to U$ | MP(32,36) |

第 18 行是第二组公理取内部公式 $\neg\varphi$、换入项 $x$；第 26 行取内部公式 $\varphi$、换入项 $x$。两次都是用变元替换自己，按无冲突替换定义符合条件。它们是公理实例，不是额外前提。

最后一行 $A\to U$ 展开为 $\forall x\varphi\to\neg\forall x\neg\varphi$，即所求 $\forall x\varphi\to\exists x\varphi$。全部 37 行仅使用公理实例和分离规则。

### 验证与阅读提示

已用公式语法树逐行核验 (A1)–(A3) 的实例形状及所有 MP 行的引用匹配，最后核验目标为 $A\to U$；两条第二组公理实例另按替换定义检查。

前 17 行展开双重否定消去在 $B$ 上的实例；第 18–25 行得到 $(W\to\varphi)\to U$；第 26–37 行连接全称实例化并得到最终蕴涵。这些说明仅解释已经逐行列出的序列，不作为额外证明步骤，也不直接援引任何元定理。此推演不主张最短。

<a id="exercise-422"></a>
## 4.2.2 概括后的推演长度

### 题目与思路

已知从 $\Gamma$ 到 $\varphi$ 有长度为 $n$ 的推演，且 $x$ 不在 $\Gamma$ 中自由出现。估计从 $\Gamma$ 到 $\forall x\varphi$ 的推演长度，尽量使上界增长缓慢。

长度指公式序列的项数，不是所有公式的总符号数。直接重做概括定理的证明，并统计每一行需要多少新行。

### 证明

设原推演为 $\varphi_1,\ldots,\varphi_n=\varphi$。按顺序构造各个 $\forall x\varphi_i$ 的证明。

**公理行：1 行。** 若 $\varphi_i$ 是逻辑公理，$\forall x\varphi_i$ 仍是逻辑公理，直接写出。

**前提行：3 行。** 若 $\varphi_i\in\Gamma$，因 $x$ 不在其中自由出现，可以写：

$$
\varphi_i,\qquad
\varphi_i\to\forall x\varphi_i,\qquad
\forall x\varphi_i.
$$

依次是前提、第四组公理、分离规则。

**分离行：再添 3 行。** 若 $\varphi_i$ 由前面的 $\alpha$ 与 $\alpha\to\varphi_i$ 得到，构造的新推演中已经有 $\forall x\alpha$ 和 $\forall x(\alpha\to\varphi_i)$，只需再添：

$$
\begin{gathered}
\forall x(\alpha\to\varphi_i)\to(\forall x\alpha\to\forall x\varphi_i),\\
\forall x\alpha\to\forall x\varphi_i,\\
\forall x\varphi_i.
\end{gathered}
$$

依次是第三组公理、两次分离规则。

每个原证明行最多贡献 3 行。因此构造出的推演长度 $L$ 满足

$$
\boxed{L\le 3n.}
$$

若原推演有 $a$ 个公理行、$b$ 个前提行、$c$ 个分离行，则上述构造的长度为 $a+3b+3c\le3n$，其中 $a+b+c=n$。可取线性上界 $f(n)=3n$；这里不主张常数 3 最优，也没有证明所有可能构造的最优下界。

**易错点：**这是把原推演改造成新推演，不是先保留原来的全部 $n$ 行再添上述步骤，所以不用另外加 $n$。

<a id="exercise-423"></a>
## 4.2.3 定理与前提的区别

### （1）若 $\vdash\varphi\to\psi$，则 $\vdash\forall x\varphi\to\forall x\psi$

空前提集自动满足概括条件，因此

$$
\vdash\forall x(\varphi\to\psi).
$$

第三组公理是

$$
\forall x(\varphi\to\psi)\to(\forall x\varphi\to\forall x\psi).
$$

用一次分离规则，得到

$$
\boxed{\vdash\forall x\varphi\to\forall x\psi.}
$$

### （2）$\varphi\to\psi\vdash\forall x\varphi\to\forall x\psi$ 不一定成立

取 $\varphi=Px$、$\psi=Qx$。考虑论域 $\{a,b\}$，其中

| 对象 | $P$ | $Q$ |
| --- | --- | --- |
| $a$ | 真 | 真 |
| $b$ | 真 | 假 |

令自由变元 $x$ 的赋值为 $a$。此时前提 $Px\to Qx$ 真，而结论 $\forall xPx\to\forall xQx$ 假。

为什么这足以排除形式推演？本书的逻辑公理在该结构的任意赋值下都真，分离规则保持真；因而对推演逐行归纳，从这个真前提出发不能得到上述假结论。这是在本反例中使用公理及规则的保真性，并不是把语义直观当作正向形式证明。

因此

$$
\boxed{Px\to Qx\nvdash\forall xPx\to\forall xQx.}
$$

**关键区别：**（1）的蕴涵式无额外前提即可证明；（2）的蕴涵式只是额外假设，可能只对当前赋值成立。前提中有自由的 $x$，不能直接对它概括。但仅仅发现概括条件不满足，还不足以证明不可推导；上面的反例才完成了否定结论。

<a id="exercise-424"></a>
## 4.2.4 两个量词推理

### （1）$\vdash\exists x(Px\to\forall xPx)$

**直观理解。**若所有对象都满足 $P$，任选一个对象，蕴涵式的后件为真；若有人不满足 $P$，选这个对象，前件为假，蕴涵式仍真。这里采用一阶逻辑的非空论域约定。

“存在一个对象”允许根据整体情况选择对象。实质蕴涵只排除“前件真、后件假”；它不表示这个对象能决定其他对象，也不表示改变这个对象的性质就能改变全体对象。

**形式证明。**记 $A:=\forall xPx$。存在量词展开后，目标为

$$
\vdash\neg\forall x\neg(Px\to A).
$$

令 $H:=\forall x\neg(Px\to A)$。由全称实例化和重言规则，

$$
H\vdash\neg(Px\to A),\qquad
H\vdash Px,\qquad H\vdash\neg A.
$$

前提 $H$ 中没有自由的 $x$，因此可概括 $Px$，得到

$$
H\vdash\forall xPx,
$$

即 $H\vdash A$。所以 $\{H\}$ 不一致。由反证法，$\vdash\neg H$，展开即为所求。

### （2）$\{Qy,\forall y(Qy\to\forall zPz)\}\vdash\forall xPx$

记 $\Gamma:=\{Qy,\forall y(Qy\to\forall zPz)\}$。

| 步骤 | 结论 | 依据 |
| --- | --- | --- |
| 1 | $\Gamma\vdash Qy$ | 前提 |
| 2 | $\Gamma\vdash Qy\to\forall zPz$ | 第二个前提全称实例化，用 $y$ 替换自身 |
| 3 | $\Gamma\vdash\forall zPz$ | 1、2 分离 |
| 4 | $\Gamma\vdash Px$ | 全称实例化，用 $x$ 替换 $z$ |
| 5 | $\Gamma\vdash\forall xPx$ | 概括定理 |

按题中 $x,y,z$ 为不同变元的通常记号约定，$x$ 不在 $\Gamma$ 中自由出现。前提 $Qy$ 中虽有自由的 $y$，但概括的是 $x$，不受影响。证明没有直接把 $\forall zPz$ 改写成 $\forall xPx$，而是通过实例化和概括完成转换。

<a id="exercise-425"></a>
## 4.2.5 量词与联词的关系

### 题目

证明下列公式都是内定理，即在每个公式前加上 $\vdash$：

$$
\begin{aligned}
\text{（1）}\quad &(\exists x\varphi\lor\exists x\psi)\leftrightarrow\exists x(\varphi\lor\psi);\\
\text{（2）}\quad &(\forall x\varphi\lor\forall x\psi)\to\forall x(\varphi\lor\psi);\\
\text{（3）}\quad &\exists x(\varphi\land\psi)\to(\exists x\varphi\land\exists x\psi);\\
\text{（4）}\quad &\forall x(\varphi\land\psi)\leftrightarrow(\forall x\varphi\land\forall x\psi);\\
\text{（5）}\quad &\exists x(Py\land Qx)\leftrightarrow(Py\land\exists xQx),\quad x\ne y.
\end{aligned}
$$

### 共同工具：量词保持可证明的蕴涵

若 $\Gamma\vdash\alpha\to\beta$，并且 $x$ 不在 $\Gamma$ 中自由出现，则

$$
\Gamma\vdash\forall x\alpha\to\forall x\beta,
\qquad
\Gamma\vdash\exists x\alpha\to\exists x\beta.
$$

第一条：概括得到 $\forall x(\alpha\to\beta)$，再用第三组公理分离。第二条：先由重言规则得到 $\neg\beta\to\neg\alpha$，用第一条得到 $\forall x\neg\beta\to\forall x\neg\alpha$，再逆否并展开存在量词。

特别地，$\Gamma=\varnothing$ 时无须额外检查自由出现条件。若 $\vdash\alpha\leftrightarrow\beta$，对两个方向分别使用此工具，即可在两边同时加上同一种量词。

### （4）的证明：先处理全称与合取

先证明（4），供（1）使用。

由重言式 $(\varphi\land\psi)\to\varphi$ 和 $(\varphi\land\psi)\to\psi$，使用共同工具，得到

$$
\vdash\forall x(\varphi\land\psi)\to\forall x\varphi,
\qquad
\vdash\forall x(\varphi\land\psi)\to\forall x\psi.
$$

用重言规则合并，即得正方向。

反方向令 $H:=\forall x\varphi\land\forall x\psi$。拆出合取项并分别实例化，得

$$
H\vdash\varphi,\qquad H\vdash\psi,
\quad\text{从而}\quad H\vdash\varphi\land\psi.
$$

因为 $x$ 不在 $H$ 中自由出现，可以概括为 $H\vdash\forall x(\varphi\land\psi)$。再用演绎定理，即得反方向。两方向合并得到（4）。

### （1）的证明：对偶转换

下面每一行等价都是可证明的；量词内的等价替换由共同工具保证：

$$
\begin{aligned}
\exists x(\varphi\lor\psi)
&\leftrightarrow\neg\forall x\neg(\varphi\lor\psi)\\
&\leftrightarrow\neg\forall x(\neg\varphi\land\neg\psi)\\
&\leftrightarrow\neg(\forall x\neg\varphi\land\forall x\neg\psi)\\
&\leftrightarrow(\neg\forall x\neg\varphi\lor\neg\forall x\neg\psi)\\
&\leftrightarrow(\exists x\varphi\lor\exists x\psi).
\end{aligned}
$$

依次使用存在量词定义、德摩根律、（4）、德摩根律和存在量词定义。由重言规则连接这些等价，得到（1）。

### （2）的证明：分别推出共同结论

由重言式 $\varphi\to(\varphi\lor\psi)$ 和 $\psi\to(\varphi\lor\psi)$，用共同工具得

$$
\vdash\forall x\varphi\to\forall x(\varphi\lor\psi),\qquad
\vdash\forall x\psi\to\forall x(\varphi\lor\psi).
$$

再用重言式 $(A\to C)\to((B\to C)\to((A\lor B)\to C))$，即得（2）。

### （3）的证明：分别取出两个存在结论

由重言式 $(\varphi\land\psi)\to\varphi$ 和 $(\varphi\land\psi)\to\psi$，用共同工具得

$$
\vdash\exists x(\varphi\land\psi)\to\exists x\varphi,\qquad
\vdash\exists x(\varphi\land\psi)\to\exists x\psi.
$$

用重言规则合并两个后件，即得（3）。

### （5）的证明：移出与 $x$ 无关的条件

记 $C:=Py$，$E:=\exists x(C\land Qx)$。因 $x\ne y$，$x$ 不在 $C$ 中自由出现。

**正方向。**由第四组公理和全称实例化，

$$
\vdash\neg C\to\forall x\neg C,
\qquad
\vdash\forall x\neg C\to\neg C.
$$

故 $\vdash\forall x\neg C\leftrightarrow\neg C$。两边否定，结合存在量词定义及双重否定消去，得到

$$
\vdash\exists xC\leftrightarrow C.
$$

由（3），$\vdash E\to(\exists xC\land\exists xQx)$。结合上式，得 $\vdash E\to(C\land\exists xQx)$。

**反方向。**以前提集 $\{C\}$ 为基础，由重言规则有

$$
C\vdash Qx\to(C\land Qx).
$$

因 $x$ 不在前提 $C$ 中自由出现，可以使用共同工具的存在量词形式，得到

$$
C\vdash\exists xQx\to\exists x(C\land Qx).
$$

由演绎定理，$\vdash C\to(\exists xQx\to E)$；再由重言规则，$\vdash(C\land\exists xQx)\to E$。两方向合并得到（5）。

### 复习时抓住的区别

| 搭配 | 已证明的关系 | 直观理由 |
| --- | --- | --- |
| $\exists$ 与 $\lor$ | 两方向等价 | 存在满足任一条件的对象，等价于至少一个条件有满足者 |
| $\forall$ 与 $\land$ | 两方向等价 | 每个对象同时满足两条件，等价于两个条件分别对全体成立 |
| $\forall$ 与 $\lor$ | 本题（2）的方向成立 | 全体统一满足某一条件，可以保证逐个对象至少满足一条件 |
| $\exists$ 与 $\land$ | 本题（3）的方向成立 | 同一个满足者可分别充当两个存在命题的满足者 |
| 量词外移 | 要检查自由出现条件 | （5）的 $Py$ 不含自由的 $x$，不随被量化对象改变 |

（2）的逆方向一般不成立：可让两个对象分别只满足 $P$、只满足 $Q$。（3）的逆方向也一般不成立：$P$ 和 $Q$ 各有满足者，但可以没有共同满足者。这些说明用于理解方向，不替代上面的形式证明。

整理日期：2026-11-03。
