# 向量 — 题库

## 一、单项选择题

---

### 题 1

**题干**：设 $\alpha_1, \alpha_2, \alpha_3$ 是 3 维列向量，记矩阵 $A = (\alpha_1, \alpha_2, \alpha_3)$，$B = (\alpha_1 + \alpha_2 + \alpha_3, \alpha_1 + 2\alpha_2 + 4\alpha_3, \alpha_1 + 3\alpha_2 + 9\alpha_3)$。若 $|A| = 1$，则 $|B| = $

**选项**：
(A) 1
(B) 2
(C) 3
(D) 4

**标准答案**：$\boxed{B}$

**答案解析**：

$B = A \begin{pmatrix} 1 & 1 & 1 \\ 1 & 2 & 3 \\ 1 & 4 & 9 \end{pmatrix}$

$|B| = |A| \cdot \begin{vmatrix} 1 & 1 & 1 \\ 1 & 2 & 3 \\ 1 & 4 & 9 \end{vmatrix} = 1 \cdot (2 \cdot 9 - 3 \cdot 4) - (1 \cdot 9 - 3) + (1 \cdot 4 - 2)$

$= (18 - 12) - (9 - 3) + (4 - 2) = 6 - 6 + 2 = 2$

（或识别为范德蒙德行列式：$(2-1)(3-1)(3-2) = 1 \cdot 2 \cdot 1 = 2$）

**出处**：2005 年考研数学一真题

---

### 题 2

**题干**：设向量组 $\alpha_1, \alpha_2, \alpha_3$ 线性无关，则下列向量组中线性无关的是

**选项**：
(A) $\alpha_1 + \alpha_2, \alpha_2 + \alpha_3, \alpha_3 - \alpha_1$
(B) $\alpha_1 + \alpha_2, \alpha_2 + \alpha_3, \alpha_1 + 2\alpha_2 + \alpha_3$
(C) $\alpha_1 + 2\alpha_2, 2\alpha_2 + 3\alpha_3, 3\alpha_3 + \alpha_1$
(D) $\alpha_1 + \alpha_2 + \alpha_3, 2\alpha_1 - 3\alpha_2 + 2\alpha_3, 3\alpha_1 + 5\alpha_2 - 5\alpha_3$

**标准答案**：$\boxed{C}$

**答案解析**：

各选项向量组均是 $\alpha_1, \alpha_2, \alpha_3$ 的线性组合，只需判断系数矩阵是否可逆。

(A) $\begin{pmatrix} 1 & 0 & -1 \\ 1 & 1 & 0 \\ 0 & 1 & 1 \end{pmatrix}$？$(\alpha_1+\alpha_2, \alpha_2+\alpha_3, \alpha_3-\alpha_1) = (\alpha_1, \alpha_2, \alpha_3) \begin{pmatrix} 1 & 0 & -1 \\ 1 & 1 & 0 \\ 0 & 1 & 1 \end{pmatrix}$

行列式 $= 1(1-0) - 0 + (-1)(1-0) = 1 - 1 = 0$，相关

(B) $(\alpha_1+\alpha_2, \alpha_2+\alpha_3, \alpha_1+2\alpha_2+\alpha_3)$，注意第三向量 $=$ 第一 $+$ 第二，故相关

(C) $(\alpha_1+2\alpha_2, 2\alpha_2+3\alpha_3, 3\alpha_3+\alpha_1) = (\alpha_1, \alpha_2, \alpha_3) \begin{pmatrix} 1 & 0 & 1 \\ 2 & 2 & 0 \\ 0 & 3 & 3 \end{pmatrix}$

行列式 $= 1(6-0) + 1(6-0) = 6 + 6 = 12 \neq 0$，无关

(D) 系数矩阵行列式 $= 0$（由题意），相关

故选 (C)。

**出处**：1997 年考研数学一真题

---

### 题 3

**题干**：设 $A$ 为 $m \times n$ 矩阵，$B$ 为 $n \times m$ 矩阵，则

**选项**：
(A) 当 $m > n$ 时，必有行列式 $|AB| \neq 0$
(B) 当 $m > n$ 时，必有行列式 $|AB| = 0$
(C) 当 $n > m$ 时，必有行列式 $|AB| \neq 0$
(D) 当 $n > m$ 时，必有行列式 $|AB| = 0$

**标准答案**：$\boxed{B}$

**答案解析**：

$AB$ 为 $m$ 阶方阵

当 $m > n$ 时，$r(AB) \le \min(r(A), r(B)) \le n < m$

故 $AB$ 非满秩，$|AB| = 0$，选 (B)

**出处**：1999 年考研数学一真题

---

### 题 4

**题干**：设向量组 I：$\alpha_1, \alpha_2, \cdots, \alpha_r$ 可由向量组 II：$\beta_1, \beta_2, \cdots, \beta_s$ 线性表示，则

**选项**：
(A) 当 $r < s$ 时，向量组 II 必线性相关
(B) 当 $r > s$ 时，向量组 II 必线性相关
(C) 当 $r < s$ 时，向量组 I 必线性相关
(D) 当 $r > s$ 时，向量组 I 必线性相关

**标准答案**：$\boxed{D}$

**答案解析**：

由定理：若向量组 I 可由 II 表示，且 $r > s$，则 I 必线性相关

故选 (D)。

**出处**：2003 年考研数学一真题

---

### 题 5

**题干**：设 $n$ 维列向量组 $\alpha_1, \cdots, \alpha_m$（$m < n$）线性无关，则 $n$ 维列向量组 $\beta_1, \cdots, \beta_m$ 线性无关的充分必要条件是

**选项**：
(A) 向量组 $\alpha_1, \cdots, \alpha_m$ 可由 $\beta_1, \cdots, \beta_m$ 线性表示
(B) 向量组 $\beta_1, \cdots, \beta_m$ 可由 $\alpha_1, \cdots, \alpha_m$ 线性表示
(C) 向量组 $\alpha_1, \cdots, \alpha_m$ 与 $\beta_1, \cdots, \beta_m$ 等价
(D) 矩阵 $A = (\alpha_1, \cdots, \alpha_m)$ 与矩阵 $B = (\beta_1, \cdots, \beta_m)$ 等价

**标准答案**：$\boxed{D}$

**答案解析**：

(A) 充分不必要：若 $\alpha_1, \cdots, \alpha_m$ 可由 $\beta_1, \cdots, \beta_m$ 表示，则 $m = r(\alpha_1, \cdots, \alpha_m) \le r(\beta_1, \cdots, \beta_m) \le m$，故 $r(B) = m$，无关；反之不然

(B) 不充分：$\beta$ 可由 $\alpha$ 表示不能推出 $\beta$ 无关（例如 $\beta_i = 0$）

(C) 等价即互相可表示，由 (A) 是充分条件，但不必要

(D) 矩阵 $A$ 与 $B$ 等价当且仅当 $r(A) = r(B)$，而 $r(A) = m$（因 $\alpha$ 无关），故 $r(B) = m$，即 $\beta$ 无关，反之亦然

故选 (D)。

**出处**：2000 年考研数学一真题

---

### 题 6

**题干**：设 $\alpha_1, \alpha_2, \alpha_3$ 线性无关，$\beta_1 = \alpha_1 + \alpha_2$，$\beta_2 = \alpha_2 + \alpha_3$，$\beta_3 = \alpha_3 + \alpha_1$，则 $\beta_1, \beta_2, \beta_3$ 是

**选项**：
(A) 线性相关
(B) 线性无关
(C) 可能相关可能无关
(D) 不确定

**标准答案**：$\boxed{B}$

**答案解析**：

$(\beta_1, \beta_2, \beta_3) = (\alpha_1, \alpha_2, \alpha_3) \begin{pmatrix} 1 & 0 & 1 \\ 1 & 1 & 0 \\ 0 & 1 & 1 \end{pmatrix}$

系数矩阵行列式 $= 1(1-0) + 1(1-0) = 2 \neq 0$，故 $\beta_1, \beta_2, \beta_3$ 线性无关

选 (B)。

**出处**：向量组线性相关性

---

## 二、填空题

---

### 题 7

**题干**：设向量组 $\alpha_1 = (1, 2, -1, 1)^T$，$\alpha_2 = (2, 0, t, 0)^T$，$\alpha_3 = (0, -4, 5, -2)^T$ 线性相关，则 $t = $ \_\_\_\_\_\_

**标准答案**：$\boxed{3}$

**答案解析**：

$A = \begin{pmatrix} 1 & 2 & 0 \\ 2 & 0 & -4 \\ -1 & t & 5 \\ 1 & 0 & -2 \end{pmatrix}$，$r(A) < 3$

行变换：$r_2 = r_2 - 2r_1$，$r_3 = r_3 + r_1$，$r_4 = r_4 - r_1$

$A \to \begin{pmatrix} 1 & 2 & 0 \\ 0 & -4 & -4 \\ 0 & t+2 & 5 \\ 0 & -2 & -2 \end{pmatrix} \to \begin{pmatrix} 1 & 2 & 0 \\ 0 & 1 & 1 \\ 0 & t+2 & 5 \\ 0 & -2 & -2 \end{pmatrix} \to \begin{pmatrix} 1 & 2 & 0 \\ 0 & 1 & 1 \\ 0 & 0 & 3-t \\ 0 & 0 & 0 \end{pmatrix}$

$r(A) < 3$ 要求 $3 - t = 0$，即 $t = 3$

**出处**：向量组线性相关条件

---

### 题 8

**题干**：已知向量组 $\alpha_1 = (1, 2, 3, 4)$，$\alpha_2 = (2, 3, 4, 5)$，$\alpha_3 = (3, 4, 5, 6)$，$\alpha_4 = (4, 5, 6, 7)$，则该向量组的秩为 \_\_\_\_\_\_

**标准答案**：$\boxed{2}$

**答案解析**：

以行向量作矩阵 $A = \begin{pmatrix} 1 & 2 & 3 & 4 \\ 2 & 3 & 4 & 5 \\ 3 & 4 & 5 & 6 \\ 4 & 5 & 6 & 7 \end{pmatrix}$

$r_i = r_i - r_{i-1}$（$i = 4, 3, 2$）：$A \to \begin{pmatrix} 1 & 2 & 3 & 4 \\ 1 & 1 & 1 & 1 \\ 1 & 1 & 1 & 1 \\ 1 & 1 & 1 & 1 \end{pmatrix} \to \begin{pmatrix} 1 & 2 & 3 & 4 \\ 0 & -1 & -2 & -3 \\ 0 & 0 & 0 & 0 \\ 0 & 0 & 0 & 0 \end{pmatrix}$

$r(A) = 2$

**出处**：向量组的秩

---

### 题 9

**题干**：设 $A$ 为 $n$ 阶非奇异矩阵，$\alpha$ 为 $n$ 维列向量，$b$ 为常数。记分块矩阵

$P = \begin{pmatrix} I & 0 \\ -\alpha^T A^* & |A| \end{pmatrix}$，$Q = \begin{pmatrix} A & \alpha \\ \alpha^T & b \end{pmatrix}$

其中 $A^*$ 是 $A$ 的伴随矩阵，则 $PQ = $ \_\_\_\_\_\_

**标准答案**：$\boxed{\begin{pmatrix} A & \alpha \\ 0 & |A|(b - \alpha^T A^{-1} \alpha) \end{pmatrix}}$

**答案解析**：

$PQ = \begin{pmatrix} I & 0 \\ -\alpha^T A^* & |A| \end{pmatrix} \begin{pmatrix} A & \alpha \\ \alpha^T & b \end{pmatrix} = \begin{pmatrix} A & \alpha \\ -\alpha^T A^* A + |A| \alpha^T & -\alpha^T A^* \alpha + |A| b \end{pmatrix}$

由 $A^* A = |A| I$，故 $-\alpha^T A^* A + |A| \alpha^T = -|A| \alpha^T + |A| \alpha^T = 0$

又 $-\alpha^T A^* \alpha + |A| b = |A| b - |A| \alpha^T A^{-1} \alpha = |A|(b - \alpha^T A^{-1} \alpha)$（因 $A^* = |A|A^{-1}$）

故 $PQ = \begin{pmatrix} A & \alpha \\ 0 & |A|(b - \alpha^T A^{-1} \alpha) \end{pmatrix}$

**出处**：1997 年考研数学三真题

---

### 题 10

**题干**：从 $\mathbb{R}^2$ 的基 $\alpha_1 = (1, 0)^T$，$\alpha_2 = (1, -1)^T$ 到基 $\beta_1 = (1, 1)^T$，$\beta_2 = (1, 2)^T$ 的过渡矩阵为 \_\_\_\_\_\_

**标准答案**：$\boxed{\begin{pmatrix} 2 & 3 \\ -1 & -2 \end{pmatrix}}$

**答案解析**：

设过渡矩阵 $P$ 满足 $(\beta_1, \beta_2) = (\alpha_1, \alpha_2) P$

即 $\begin{pmatrix} 1 & 1 \\ 1 & 2 \end{pmatrix} = \begin{pmatrix} 1 & 1 \\ 0 & -1 \end{pmatrix} P$

$P = \begin{pmatrix} 1 & 1 \\ 0 & -1 \end{pmatrix}^{-1} \begin{pmatrix} 1 & 1 \\ 1 & 2 \end{pmatrix} = \begin{pmatrix} 1 & 1 \\ 0 & -1 \end{pmatrix} \begin{pmatrix} 1 & 1 \\ 1 & 2 \end{pmatrix} = \begin{pmatrix} 2 & 3 \\ -1 & -2 \end{pmatrix}$

**出处**：向量空间的基变换

---

### 题 11

**题干**：设 $\alpha = (1, 0, -1)^T$，矩阵 $A = \alpha \alpha^T$，则 $|a I - A^n| = $ \_\_\_\_\_\_

**标准答案**：$\boxed{a^2(a - 2^n)}$

**答案解析**：

$A = \alpha \alpha^T = \begin{pmatrix} 1 \\ 0 \\ -1 \end{pmatrix} (1, 0, -1) = \begin{pmatrix} 1 & 0 & -1 \\ 0 & 0 & 0 \\ -1 & 0 & 1 \end{pmatrix}$

$A^2 = \alpha \alpha^T \alpha \alpha^T = (\alpha^T \alpha) A = 2A$

$A^n = 2^{n-1} A$

$|a I - A^n| = |a I - 2^{n-1} A|$

$A$ 的特征值：$\alpha^T \alpha = 2$，故 $A$ 的特征值为 $2, 0, 0$（秩为 1 的矩阵）

$a I - A^n$ 的特征值为 $a - 2^{n-1} \cdot 2 = a - 2^n$，$a$，$a$

故 $|a I - A^n| = a^2 (a - 2^n)$

**出处**：矩阵特征值与行列式

---

### 题 12

**题干**：设 $\alpha_1, \alpha_2, \alpha_3$ 为 3 维向量空间的一组基，则由基 $\alpha_1, \dfrac{1}{2}\alpha_2, \dfrac{1}{3}\alpha_3$ 到基 $\alpha_1 + \alpha_2, \alpha_2 + \alpha_3, \alpha_3 + \alpha_1$ 的过渡矩阵为 \_\_\_\_\_\_

**标准答案**：$\boxed{\begin{pmatrix} 1 & 0 & 1 \\ 2 & 2 & 0 \\ 0 & 3 & 3 \end{pmatrix}}$

**答案解析**：

设 $A = (\alpha_1, \alpha_2/2, \alpha_3/3)$，$B = (\alpha_1+\alpha_2, \alpha_2+\alpha_3, \alpha_3+\alpha_1)$

由 $A = (\alpha_1, \alpha_2, \alpha_3) \begin{pmatrix} 1 & 0 & 0 \\ 0 & 1/2 & 0 \\ 0 & 0 & 1/3 \end{pmatrix}$，$B = (\alpha_1, \alpha_2, \alpha_3) \begin{pmatrix} 1 & 0 & 1 \\ 1 & 1 & 0 \\ 0 & 1 & 1 \end{pmatrix}$

故 $B = A \begin{pmatrix} 1 & 0 & 0 \\ 0 & 2 & 0 \\ 0 & 0 & 3 \end{pmatrix} \begin{pmatrix} 1 & 0 & 1 \\ 1 & 1 & 0 \\ 0 & 1 & 1 \end{pmatrix} = A \begin{pmatrix} 1 & 0 & 1 \\ 2 & 2 & 0 \\ 0 & 3 & 3 \end{pmatrix}$

过渡矩阵为 $\begin{pmatrix} 1 & 0 & 1 \\ 2 & 2 & 0 \\ 0 & 3 & 3 \end{pmatrix}$

**出处**：基变换与过渡矩阵

---

## 三、解答题（略）

---
