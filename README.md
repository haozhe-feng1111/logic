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

## 阅读约定

- 使用 GitHub 支持的 Markdown 和 LaTeX 数学公式。
- §2.2 保留教材的完整括号写法：否定写作 $(\neg\alpha)$，二元复合写作 $(\alpha\star\beta)$。
- **公式长度**是符号出现的总次数；**构造序列长度**是序列的项数。
- §2.2 的题目与定义已对照教材印刷页 26–30 核对；习题正文在第 29–30 页。证明按复习需要展开，不作为教材原文引用。

整理日期：2026-10-13。最近更新：2026-11-03（补齐 §4.4 两道习题及六条量词规则的证明）。
