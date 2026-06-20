# 特征值与特征向量 — 题库

## 一、单项选择题

---

### 题 1

**题干**：设 $A = \begin{pmatrix} 1 & 1 & 1 \\ 1 & 1 & 1 \\ 1 & 1 & 1 \end{pmatrix}$，则 $A$ 的三个特征值为

**选项**：
(A) 1, 1, 1
(B) 3, 0, 0
(C) 3, 1, 0
(D) 3, -1, -1

**标准答案**：$\boxed{B}$

**答案解析**：

$|A - \lambda I| = \begin{vmatrix} 1-\lambda & 1 & 1 \\ 1 & 1-\lambda & 1 \\ 1 & 1 & 1-\lambda \end{vmatrix} = (3-\lambda) \begin{vmatrix} 1 & 1 & 1 \\ 1 & 1-\lambda & 1 \\ 1 & 1 & 1-\lambda \end{vmatrix}$（第一行提取 $(3-\lambda)$

各行减去第一行后展开：$= (3-\lambda) \lambda^2$

故特征值为 $3, 0, 0$

**出处**：矩阵特征值基础

---

### 题 2

**题干**：设 $\lambda_1, \lambda_2$ 是矩阵 $A$ 的两个不同的特征值，对应的特征向量分别为 $\alpha_1, \alpha_2$，则 $\alpha_1, A(\alpha_1 + \alpha_2)$ 线性无关的充分必要条件是

**选项**：
(A) $\lambda_1 \neq 0$
(B) $\lambda_2 \neq 0$
(C) $\lambda_1 = 0$
(D) $\lambda_2 = 0$

**标准答案**：$\boxed{B}$

**答案解析**：

设 $k_1 \alpha_1 + k_2 A(\alpha_1 + \alpha_2) = 0$

即 $k_1 \alpha_1 + k_2 \lambda_1 \alpha_1 + k_2 \lambda_2 \alpha_2 = 0$

即 $(k_1 + k_2 \lambda_1) \alpha_1 + k_2 \lambda_2 \alpha_2 = 0$

由 $\alpha_1, \alpha_2$ 线性无关（不同特征值）

$k_1 + k_2 \lambda_1 = 0, k_2 \lambda_2 = 0$

要只有零解当且仅当 $\lambda_2 \neq 0$（此时由第二式 $k_2 = 0$，进而 $k_1 = 0$）

若 $\lambda_2 = 0$，则取 $k_1 = -\lambda_1, k_2 = 1$ 为非零解

故选 (B)。

**出处**：2005 年考研数学一真题

---

### 题 3

**题干**：设 $A$ 是 $n$ 阶方阵，且 $A^2 = A$，则 $A$ 的特征值为

**选项**：
(A) 只能是 0
(B) 只能是 1
(C) 0 或 1
(D) 0, 1 或其他

**标准答案**：$\boxed{C}$

**答案解析**：

设 $\lambda$ 为 $A$ 的特征值，$\alpha$ 为对应特征向量

由 $A^2 = A$，左乘 $A$：$A^2 \alpha = A \alpha$，即 $\lambda^2 \alpha = \lambda \alpha$

$(\lambda^2 - \lambda) \alpha = 0$，由 $\alpha \neq 0$，$\lambda(\lambda - 1) = 0$

故 $\lambda = 0$ 或 $\lambda = 1$

选 (C)。

**出处**：幂等矩阵特征值

---

### 题 4

**题干**：设 $A, B$ 为 $n$ 阶方阵，则下列命题正确的是

**选项**：
(A) 若 $A, B$ 有相同的特征值，则 $A$ 与 $B$ 相似
(B) 若 $A, B$ 相似，则 $A, B$ 有相同的特征值和特征向量
(C) 若 $A, B$ 相似，则 $|A| = |B|$
(D) 若 $A, B$ 等价，则 $A, B$ 相似

**标准答案**：$\boxed{C}$

**答案解析**：

相似矩阵有相同的特征多项式，故有相同的特征值和行列式

(A) 反例：$A = \begin{pmatrix} 0 & 0 \\ 0 & 0 \end{pmatrix}, B = \begin{pmatrix} 0 & 1 \\ 0 & 0 \end{pmatrix}$，特征值都是 0，但不相似（$A$ 可对角化，$B$ 不可对角化）

(B) 相似矩阵有相同的特征值但特征向量不一定相同

(D) 等价只要求秩相同，不保证相似

故选 (C)。

**出处**：相似矩阵性质

---

### 题 5

**题干**：设 $A$ 为 $n$ 阶实对称矩阵，$P$ 为 $n$ 阶可逆矩阵，$\alpha$ 是 $A$ 的属于特征值 $\lambda$ 的特征向量，则 $(P^{-1} A P)^T$ 属于特征值 $\lambda$ 的特征向量是

**选项**：
(A) $P^{-1} \alpha$
(B) $P^T \alpha$
(C) $P \alpha$
(D) $(P^{-1})^T \alpha$

**标准答案**：$\boxed{D}$

**答案解析**：

设 $B = (P^{-1} A P)^T = P^T A^T (P^{-1})^T = P^T A (P^{-1})^T$（$A$ 对称）

由 $A \alpha = \lambda \alpha$

$B (P^T \alpha) = P^T A (P^{-1})^T P^T \alpha = P^T A \alpha = P^T (\lambda \alpha) = \lambda (P^T \alpha)$

所以 $P^T \alpha$ 是 $B$ 的特征向量？不对

令 $B = (P^{-1}AP)^T = P^T A^T (P^{-1})^T = P^T A (P^T)^{-1}$

若取 $\beta = (P^{-1})^T \alpha = (P^T)^{-1} \alpha$

则 $B \beta = P^T A (P^T)^{-1} (P^T)^{-1} \alpha$？不对重新

设 $\beta = (P^{-1})^T \alpha$

$B \beta = (P^{-1}AP)^T (P^{-1})^T \alpha = P^T A^T (P^{-1})^T (P^{-1})^T \alpha$？

正确做法：设 $Q = (P^{-1})^T$，则 $B = Q^{-1} A Q$

$B Q^{-1} \alpha = Q^{-1} A \alpha = Q^{-1} \lambda \alpha = \lambda Q^{-1} \alpha$

所以 $B$ 的属于 $\lambda$ 的特征向量是 $Q^{-1} \alpha = P^T \alpha$

选 (B)。

**出处**：相似矩阵特征向量

---

### 题 6

**题干**：设矩阵 $A = \begin{pmatrix} 1 & 1 & 1 \\ 1 & 1 & 1 \\ 1 & 1 & 1 \end{pmatrix}$，$B = \begin{pmatrix} 1 & 0 & 0 \\ 0 & 0 & 0 \\ 0 & 0 & 0 \end{pmatrix}$，则 $A$ 与 $B$

**选项**：
(A) 合同且相似
(B) 合同但不相似
(C) 不合同但相似
(D) 既不合同也不相似

**标准答案**：$\boxed{A}$

**答案解析**：

$A$ 特征值 3, 0, 0；$B$ 特征值 1, 0, 0

$A$ 与 $B$ 都是实对称矩阵，都可对角化

$A$ 合同于 $\text{diag}(3, 0, 0)$，$B$ 本身是 $\text{diag}(1, 0, 0)$

合同的条件是正负惯性指数相同

$A$ 正惯性指数 1，负惯性指数 0$

$B$ 正惯性指数 1，负惯性指数 0

故合同

但 $A$ 与 $B$ 不相似（特征值不同）

**答案修正**：(B) 合同但不相似

**标准答案**：$\boxed{B}$

**出处**：合同与相似关系

---

## 二、填空题

---

### 题 7

**题干**：设 3 阶方阵 $A$ 的特征值为 $1, 2, 3$，则 $|A^* + I|A|I = $ \_\_\_\_\_\_

**标准答案**：$\boxed{2016}$（或其他等价形式

**答案解析**：

$|A| = 1 \cdot 2 \cdot 3 = 6$

$A^* = |A| A^{-1} = 6 A^{-1}$

$A^*$ 的特征值为 $6/1, 6/2, 6/3，即 $6, 3, 2$

$A^* + I$ 的特征值为 $7, 4, 3$

$|A^* + I| = 7 \cdot 4 \cdot 3 = 84$

题目中 $||A|I|$ 部分不清楚，若求 $|A^* + I = 84$

按题目应为特定值为 $\boxed{84}$

**出处**：伴随矩阵特征值

---

### 题 8

**题干**：设 $A$ 为 2 阶矩阵，$\alpha_1, \alpha_2$ 为线性无关的 2 维列向量，$A \alpha_1 = 0$，$A \alpha_2 = 2 \alpha_1 + \alpha_2$，则 $A$ 的非零特征值为 \_\_\_\_\_\_

**标准答案**：$\boxed{1}$

**答案解析**：

$A(\alpha_1, \alpha_2) = (A \alpha_1, A \alpha_2) = (0, 2 \alpha_1 + \alpha_2) = (\alpha_1, \alpha_2) \begin{pmatrix} 0 & 2 \\ 0 & 1 \end{pmatrix}$

设 $P = (\alpha_1, \alpha_2)$，则 $P^{-1} A P = \begin{pmatrix} 0 & 2 \\ 0 & 1 \end{pmatrix}$

$A$ 与 $\begin{pmatrix} 0 & 2 \\ 0 & 1 \end{pmatrix}$ 相似，有相同特征值 0 和 1

故非零特征值为 1

**出处**：通过相似求特征值

---

### 题 9

**题干**：设 $A$ 为 $n$ 阶方阵，$|A| \neq 0$，$\lambda$ 为 $A$ 的特征值，则 $(A^*)^2 + I$ 必有特征值 \_\_\_\_\_\_

**标准答案**：$\boxed{\left(\dfrac{|A|}{\lambda}\right)^2 + 1}$

**答案解析**：

$A^* = |A| A^{-1}$，故 $A^*$ 特征值为 $|A|/\lambda$

$(A^*)^2$ 特征值为 $(|A|/\lambda)^2$

$(A^*)^2 + I$ 特征值为 $(|A|/\lambda)^2 + 1$

**出处**：伴随矩阵特征值

---

### 题 10

**题干**：设 $\begin{pmatrix} 0 & -2 & -2 \\ 2 & 2 & -2 \\ -2 & -2 & 2 \end{pmatrix}$ 的非零特征值是 \_\_\_\_\_\_

**标准答案**：$\boxed{4}$

**答案解析**：

$|A - \lambda I| = \begin{vmatrix} -\lambda & -2 & -2 \\ 2 & 2-\lambda & -2 \\ -2 & -2 & 2-\lambda \end{vmatrix} = \begin{vmatrix} -\lambda & -2 & -2 \\ 2 & 2-\lambda & -2 \\ 0 & -\lambda & -\lambda \end{vmatrix}$（第三行 $+$ 第一行

$= -\lambda \begin{vmatrix} 2-\lambda & -2 \\ -\lambda & -\lambda \end{vmatrix} + 2 \begin{vmatrix} 2 & -2 \\ 0 & -\lambda \end{vmatrix} - 2 \begin{vmatrix} 2 & 2-\lambda \\ 0 & -\lambda \end{vmatrix}$

$= -\lambda[-\lambda(2-\lambda) - 2\lambda] + 2(-2\lambda) - 2(-2\lambda)$

$= -\lambda[-2\lambda + \lambda^2 - 2\lambda] - 4\lambda + 4\lambda = -\lambda(\lambda^2 - 4\lambda) = -\lambda^2(\lambda - 4)$

特征值 $\lambda = 0, 0, 4$

非零特征值为 4

**出处**：矩阵特征值计算

---

### 题 11

**题干**：设 $A$ 为 3 阶矩阵，$\alpha_1, \alpha_2, \alpha_3$ 是 3 维线性无关列向量，且 $A \alpha_1 = 0$，$A \alpha_2 = \alpha_1 + 2 \alpha_2$，$A \alpha_3 = \alpha_2 + 2 \alpha_3$，则 $A$ 的三个特征值为 \_\_\_\_\_\_

**标准答案**：$\boxed{0, 2, 2}$

**答案解析**：

$A(\alpha_1, \alpha_2, \alpha_3) = (A\alpha_1, A\alpha_2, A\alpha_3) = (0, \alpha_1 + 2\alpha_2, \alpha_2 + 2\alpha_3)$

$= (\alpha_1, \alpha_2, \alpha_3) \begin{pmatrix} 0 & 1 & 0 \\ 0 & 2 & 1 \\ 0 & 0 & 2 \end{pmatrix}$

设 $P = (\alpha_1, \alpha_2, \alpha_3)$，则 $P^{-1} A P = \begin{pmatrix} 0 & 1 & 0 \\ 0 & 2 & 1 \\ 0 & 0 & 2 \end{pmatrix}$

特征值为 $0, 2, 2$

**出处**：2004 年考研数学三真题

---

### 题 12

**题干**：设 $A$ 为 2 阶矩阵，$P = (\alpha, A \alpha)$，其中 $\alpha$ 是非零向量，且不是 $A$ 的特征向量，若 $A^2 \alpha + A \alpha - 6 \alpha = 0$，则 $A$ 的特征值为 \_\_\_\_\_\_

**标准答案**：$\boxed{2}$ 和 $\boxed{-3}$

**答案解析**：

由 $A^2 \alpha + A \alpha - 6 \alpha = 0$，即 $(A^2 + A - 6I) \alpha = 0$

$(A + 3I)(A - 2I) \alpha = 0$

若 $(A - 2I) \alpha = 0$ 或 $(A + 3I) \alpha = 0$

因 $\alpha$ 不是 $A$ 的特征向量，即 $A \alpha \neq \lambda \alpha$

但由 $A^2 \alpha = 6 \alpha - A \alpha$

$A(\alpha, A \alpha) = (A \alpha, A^2 \alpha) = (A \alpha, 6 \alpha - A \alpha) = (\alpha, A \alpha) \begin{pmatrix} 0 & 6 \\ 1 & -1 \end{pmatrix}$

$P^{-1} A P = \begin{pmatrix} 0 & 6 \\ 1 & -1 \end{pmatrix}$

特征方程 $|\lambda I - B| = \begin{vmatrix} \lambda & -6 \\ -1 & \lambda+1 \end{vmatrix} = \lambda(\lambda+1) - 6 = \lambda^2 + \lambda - 6 = 0$

$\lambda = 2$ 或 $\lambda = -3$

**出处**：抽象矩阵特征值

---

## 三、解答题（略）

---
