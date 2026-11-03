# 数理逻辑习题与复习笔记

依据郝兆宽、杨睿之、杨跃《数理逻辑：证明及其限度（第二版）》整理，供期末复习使用。每题包含完整题目、规范证明或定义，以及关键思路和易错点。

## 习题目录

### 第二章：命题逻辑

[§2.2 命题逻辑的语言：习题 2.2.1–2.2.9](chapter-02/section-2.2-exercises.md)

| 题号 | 内容 | 主要方法 |
| --- | --- | --- |
| [2.2.1](chapter-02/section-2.2-exercises.md#exercise-221) | 闭包的两种构造等价 | 双向包含、自然数归纳、共同层级 |
| [2.2.2](chapter-02/section-2.2-exercises.md#exercise-222) | 好公式的两种定义 | 最小封闭集、有限构造序列 |
| [2.2.3](chapter-02/section-2.2-exercises.md#exercise-223) | 合式公式的归纳原理 | 对构造序列的项数归纳 |
| [2.2.4](chapter-02/section-2.2-exercises.md#exercise-224) | 可能的公式长度 | 排除短长度、构造与递推 |
| [2.2.5](chapter-02/section-2.2-exercises.md#exercise-225) | 由联词次数计算长度 | 结构归纳、符号计数 |
| [2.2.6](chapter-02/section-2.2-exercises.md#exercise-226) | 命题符号与二元联词的次数 | 结构归纳 |
| [2.2.7](chapter-02/section-2.2-exercises.md#exercise-227) | 构造序列长度的上界 | 拼接构造序列 |
| [2.2.8](chapter-02/section-2.2-exercises.md#exercise-228) | 删除包含无关命题符号的项 | 检查保留项的依赖 |
| [2.2.9](chapter-02/section-2.2-exercises.md#exercise-229) | 子公式与最短构造序列 | 连续子串、传递性、删除冗余项 |

### 第三章：一阶逻辑的语言

[§3.1 一阶逻辑的语言：习题 3.1.1–3.1.5](chapter-03/section-3.1-exercises.md)

| 题号 | 内容 | 主要方法 |
| --- | --- | --- |
| [3.1.1](chapter-03/section-3.1-exercises.md#exercise-311) | “存在着的鬼”与存在断言 | 形式化、重言式、反例结构 |
| [3.1.2](chapter-03/section-3.1-exercises.md#exercise-312) | 数、好玩与量词的范围 | 受限量词、多层否定、自然语言歧义 |
| [3.1.3](chapter-03/section-3.1-exercises.md#exercise-313) | 将公式翻译成日常中文 | 蕴涵右结合、量词与蕴涵的否定 |
| [3.1.4](chapter-03/section-3.1-exercises.md#exercise-314) | 奇数与平方和 | 存在量词、整数表达、明确平方项数 |
| [3.1.5](chapter-03/section-3.1-exercises.md#exercise-315) | 极限的否定与线性无关 | 量词翻转、德摩根律、否定蕴涵 |

[§3.2 自由出现和约束出现：习题 3.2.1–3.2.2](chapter-03/section-3.2-exercises.md)

| 题号 | 内容 | 主要方法 |
| --- | --- | --- |
| [3.2.1](chapter-03/section-3.2-exercises.md#exercise-321) | 三个公式中的自由出现与约束出现 | 量词辖域、逐次出现分析、自由变元集合 |
| [3.2.2](chapter-03/section-3.2-exercises.md#exercise-322) | 六次自由变元替换 | 按教材递归定义替换、识别变元捕获 |

§3.2 同时整理了公式记号 $\varphi$ 的含义、替换的用途，以及语法替换与合法实例化的区别。

### 第四章：形式证明

[§4.2 推理和元定理：概念与证明工具](chapter-04/section-4.2-notes.md) · [全部五道课后习题](chapter-04/section-4.2-exercises.md)

| 题号 | 内容 | 主要方法 |
| --- | --- | --- |
| [4.2.1](chapter-04/section-4.2-exercises.md#exercise-421) | 从空集推演全称蕴涵存在，不使用元定理 | 37 行公理实例与分离规则 |
| [4.2.2](chapter-04/section-4.2-exercises.md#exercise-422) | 概括后推演长度的线性上界 | 对推演各行归纳、每行最多 3 行 |
| [4.2.3](chapter-04/section-4.2-exercises.md#exercise-423) | 无前提定理与额外前提的区别 | 概括定理、第三组公理、反例 |
| [4.2.4](chapter-04/section-4.2-exercises.md#exercise-424) | 两个量词推理及实质蕴涵的理解 | 反证法、全称实例化、概括定理 |
| [4.2.5](chapter-04/section-4.2-exercises.md#exercise-425) | 量词与联词的五个内定理 | 量词单调性、德摩根律、演绎定理 |

§4.2 笔记同时整理了元定理的含义、重言规则、演绎定理、反证法，以及“前提中有全称量词”与“前提中有自由变元”的区别。

[§4.3 其他元定理：习题 4.3.1–4.3.4](chapter-04/section-4.3-exercises.md)

| 题号 | 内容 | 主要方法 |
| --- | --- | --- |
| [4.3.1](chapter-04/section-4.3-exercises.md#exercise-431) | 循环替换的反例与引理 | 变元捕获、项与公式的结构归纳 |
| [4.3.2](chapter-04/section-4.3-exercises.md#exercise-432) | 两层全称公式中的变元改名 | 新变元、实例化与概括 |
| [4.3.3](chapter-04/section-4.3-exercises.md#exercise-433) | 相等的传递性（Eq3） | 相等替换公理、演绎定理 |
| [4.3.4](chapter-04/section-4.3-exercises.md#exercise-434) | 等价替换定理 | 对替换位置外层结构归纳 |

§4.3 习题笔记同时说明了语法替换与无冲突替换、公式相同与等价，以及原子公式与复合公式的区别。

[§4.4 前束范式：规则证明与习题 4.4.1–4.4.2](chapter-04/section-4.4-exercises.md)

| 题号 | 内容 | 主要方法 |
| --- | --- | --- |
| [4.4.1](chapter-04/section-4.4-exercises.md#exercise-441) | 证明后件存在量词与前件全称量词的提取规则 | 量词与析取、逆否等价 |
| [4.4.2](chapter-04/section-4.4-exercises.md#exercise-442) | 两个公式的前束化 | 约束变元改名、展开双条件、逐步提取量词 |

§4.4 笔记同时整理了六条量词操作规则的证明、前束范式定理的归纳思路，以及前件量词翻转和保留自由变元的易错点。

[§4.5 自然推演：规则与习题 4.5.1–4.5.2](chapter-04/section-4.5-exercises.md)

| 题号 | 内容 | 主要方法 |
| --- | --- | --- |
| [4.5.1](chapter-04/section-4.5-exercises.md#exercise-451) | 弱化定理的弱形式 | 对证明树高度归纳、特征变元改名 |
| [4.5.2](chapter-04/section-4.5-exercises.md#exercise-452) | 全称公式的实例化与替换条件 | 公理′、存在规则、弱化、切割 |

§4.5 笔记同时整理了公式集的析取式理解、转写与证明树的阅读方法，并区分无捕获实例与 §3.2 的机械替换，保留教材记号约定尚需核对的边界。

### 第五章：结构与真

[§5.1 一阶语言的结构：习题 5.1.1–5.1.12 与复习笔记](chapter-05/section-5.1-exercises.md)

| 题号 | 内容 | 主要方法 |
| --- | --- | --- |
| [5.1.1](chapter-05/section-5.1-exercises.md#exercise-511) | 或、且、存在量词的语义 | 展开缩写 |
| [5.1.2](chapter-05/section-5.1-exercises.md#exercise-512) | 全称蕴涵存在 | 非空论域提供见证 |
| [5.1.3](chapter-05/section-5.1-exercises.md#exercise-513) | 固定结构中的真假与普遍有效 | 单元素、二元素结构 |
| [5.1.4](chapter-05/section-5.1-exercises.md#exercise-514) | 语义版演绎定理 | 两方向证明、蕴涵真值 |
| [5.1.5](chapter-05/section-5.1-exercises.md#exercise-515) | 普遍有效性的双条件与语义等价 | 两个都不普遍有效的公式 |
| [5.1.6](chapter-05/section-5.1-exercises.md#exercise-516) | 三个语句互不被其余两个蕴涵 | 三个有限反例结构 |
| [5.1.7](chapter-05/section-5.1-exercises.md#exercise-517) | 对象参数与常数解释 | 展开新记号与满足定义 |
| [5.1.8](chapter-05/section-5.1-exercises.md#exercise-518) | 全称公式下的分离规则 | 同一修改赋值下使用前提 |
| [5.1.9](chapter-05/section-5.1-exercises.md#exercise-519) | 对非自由变元全称化 | 自由变元赋值一致性 |
| [5.1.10](chapter-05/section-5.1-exercises.md#exercise-5110) | 相等对象在函数和关系中的替换 | 项的解释、相同有序对 |
| [5.1.11](chapter-05/section-5.1-exercises.md#exercise-5111) | 普遍有效与全称量化 | 所有赋值与修改赋值 |
| [5.1.12](chapter-05/section-5.1-exercises.md#exercise-5112) | 存在一个对象使全称蕴涵成立 | 后件真假分类 |

§5.1 笔记同时整理了结构与赋值、自由和约束出现、语义蕴涵不保证前提可满足、元语言证明，以及与可靠性和完全性定理的联系。

## 阅读约定

- 使用 GitHub 支持的 Markdown 和 LaTeX 数学公式。
- §2.2 保留教材的完整括号写法：否定写作 $(\neg\alpha)$，二元复合写作 $(\alpha\star\beta)$。
- **公式长度**是符号出现的总次数；**构造序列长度**是序列的项数。
- §2.2 的题目与定义已对照教材印刷页 26–30 核对；习题正文在第 29–30 页。证明按复习需要展开，不作为教材原文引用。

整理日期：2026-10-13。最近更新：2026-11-03（新增 §5.1 全部十二道习题、概念说明与反例构造方法）。
