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

## 阅读约定

- 使用 GitHub 支持的 Markdown 和 LaTeX 数学公式。
- §2.2 保留教材的完整括号写法：否定写作 $(\neg\alpha)$，二元复合写作 $(\alpha\star\beta)$。
- **公式长度**是符号出现的总次数；**构造序列长度**是序列的项数。
- §2.2 的题目与定义已对照教材印刷页 26–30 核对；习题正文在第 29–30 页。证明按复习需要展开，不作为教材原文引用。

整理日期：2026-10-13。最近更新：2026-11-02（新增 §3.1 全部五道习题及 §3.2 全部两道习题）。
