# 大数定律与中心极限定理 — 题库

## 一、单项选择题

---

### 题 1

**题干**：设随机变量 $X_1, X_2, \cdots, X_n$ 独立同分布，其分布律为 $P\{X_i = -1\} = P\{X_i = 1\} = 1/2$（$i = 1, 2, \cdots$），则对 $n = 1, 2, \cdots$，下列选项正确的是

**选项**：
(A) $\lim_{n \to \infty} P\left\{\dfrac{\sum_{i=1}^n X_i}{n} < 0\right\} = 0$
(B) $\lim_{n \to \infty} P\left\{\dfrac{\sum_{i=1}^n X_i}{\sqrt{n}} \le x\right\} = \Phi(x)$
(C) $\lim_{n \to \infty} P\left\{\dfrac{\sum_{i=1}^n X_i}{n} \le x\right\} = \Phi(x)$
(D) 以上都不对

**标准答案**：$\boxed{B}$

**答案解析**：

$E(X_i) = -1 \cdot 1/2 + 1 \cdot 1/2 = 0$

$E(X_i^2) = 1 \cdot 1/2 + 1 \cdot 1/2 = 1$，$D(X_i) = 1$

由中心极限定理：$\dfrac{\sum_{i=1}^n X_i - n \cdot 0}{\sqrt{n} \cdot 1} = \dfrac{\sum X_i}{\sqrt{n}} \xrightarrow{d} N(0, 1)$

故 $P\left(\dfrac{\sum X_i}{\sqrt{n}} \le x\right) \to \Phi(x)$

(A) $P\left(\dfrac{\sum X_i}{n} < 0\right) = P\left(\dfrac{\sum X_i}{\sqrt{n}} < 0\right) \to \Phi(0) = 1/2 \neq 0$

(C) 应为 $\sqrt{n}$ 而非 $n$

选 (B)。

**出处**：中心极限定理

---

### 题 2

**题干**：设随机变量 $X_1, X_2, \cdots$ 相互独立，$S_n = X_1 + X_2 + \cdots + X_n$，根据林德伯格-列维中心极限定理，当 $n \to \infty$ 时，$S_n$ 近似服从正态分布，只要 $X_1, X_2, \cdots$

**选项**：
(A) 有相同的数学期望
(B) 有相同的方差
(C) 服从同一指数分布
(D) 服从同一离散型分布

**标准答案**：$\boxed{C}$

**答案解析**：

林德伯格-列维中心极限定理要求独立同分布且方差有限

(A)(B) 不充分，需同分布

(C) 同一指数分布，期望和方差都存在，满足条件

(D) 同一离散型分布可能方差不存在（如柯西），不一定满足

选 (C)。

**出处**：独立同分布中心极限定理条件

---

### 题 3

**题干**：设 $X_1, X_2, \cdots, X_n, \cdots$ 为独立同分布的随机变量列，且均服从参数为 $\lambda$（$\lambda > 1$）的指数分布，记 $\Phi(x)$ 为标准正态分布函数，则

**选项**：
(A) $\lim_{n \to \infty} P\left\{\dfrac{\sum_{i=1}^n X_i - n\lambda}{\lambda \sqrt{n}} \le x\right\} = \Phi(x)$
(B) $\lim_{n \to \infty} P\left\{\dfrac{\sum_{i=1}^n X_i - n\lambda}{\sqrt{n\lambda}} \le x\right\} = \Phi(x)$
(C) $\lim_{n \to \infty} P\left\{\dfrac{\lambda \sum_{i=1}^n X_i - n}{\sqrt{n}} \le x\right\} = \Phi(x)$
(D) $\lim_{n \to \infty} P\left\{\dfrac{\sum_{i=1}^n X_i - \lambda}{\sqrt{n \lambda^2}} \le x\right\} = \Phi(x)$

**标准答案**：$\boxed{C}$

**答案解析**：

$E(X_i) = 1/\lambda$，$D(X_i) = 1/\lambda^2$

$\sum_{i=1}^n X_i$ 的均值 $n/\lambda$，方差 $n/\lambda^2$

标准化：$\dfrac{\sum X_i - n/\lambda}{\sqrt{n}/\lambda} = \dfrac{\lambda \sum X_i - n}{\sqrt{n}}$

由中心极限定理，其极限分布为 $N(0, 1)$

即 (C) 成立

**出处**：中心极限定理应用

---

### 题 4

**题干**：设 $X_1, X_2, \cdots, X_n$ 独立同分布，$E(X_i) = \mu$，$D(X_i) = \sigma^2 > 0$，记 $\bar{X}_n = \dfrac{1}{n} \sum_{i=1}^n X_i$，则由切比雪夫不等式有 $P\{|\bar{X}_n - \mu| < 3\sigma\} \ge $

**选项**：
(A) $1 - \dfrac{1}{9n}$
(B) $1 - \dfrac{1}{9}$
(C) $1 - \dfrac{1}{3n}$
(D) $\dfrac{1}{9n}$

**标准答案**：$\boxed{A}$

**答案解析**：

$E(\bar{X}_n) = \mu$，$D(\bar{X}_n) = \sigma^2/n$

由切比雪夫：$P(|\bar{X}_n - \mu| \ge \varepsilon) \le \dfrac{D(\bar{X}_n)}{\varepsilon^2}$

取 $\varepsilon = 3\sigma$，$P(|\bar{X}_n - \mu| \ge 3\sigma) \le \dfrac{\sigma^2/n}{9\sigma^2} = \dfrac{1}{9n}$

故 $P(|\bar{X}_n - \mu| < 3\sigma) \ge 1 - \dfrac{1}{9n}$

**出处**：切比雪夫不等式

---

### 题 5

**题干**：设 $X \sim B(n, p)$，由中心极限定理，近似地有 $X \sim $

**选项**：
(A) $N(np, np(1-p))$
(B) $N(np, np)$
(C) $N(p, p(1-p)/n)$
(D) $N(0, 1)$

**标准答案**：$\boxed{A}$

**答案解析**：

二项分布可分解为 $n$ 个独立伯努利之和

由中心极限定理，$X$ 近似服从 $N(np, np(1-p))$

**出处**：二项分布的正态近似

---

### 题 6

**题干**：设随机变量 $X_1, X_2, \cdots, X_n, \cdots$ 相互独立，则根据辛钦大数定律，当 $n \to \infty$ 时，$\dfrac{1}{n} \sum_{i=1}^n X_i$ 依概率收敛到其数学期望，只要 $X_1, X_2, \cdots$

**选项**：
(A) 服从同一连续型分布
(B) 服从同一离散型分布
(C) 服从同一泊松分布
(D) 方差存在

**标准答案**：$\boxed{C}$

**答案解析**：

辛钦大数定律要求独立同分布且期望存在

(A) 同一连续型分布未必期望有限（如柯西）

(B) 同一离散型分布也未必期望有限

(C) 泊松分布的期望有限（$\lambda$），满足条件

(D) 方差存在不充分，还需同分布和期望存在

**出处**：辛钦大数定律条件

---

## 二、填空题

---

### 题 7

**题干**：设随机变量 $X$ 的数学期望 $E(X) = \mu$，方差 $D(X) = \sigma^2$，则由切比雪夫不等式，$P\{|X - \mu| \ge 2\sigma\} \le $ \_\_\_\_\_\_

**标准答案**：$\boxed{\dfrac{1}{4}}$

**答案解析**：

切比雪夫：$P(|X - \mu| \ge \varepsilon) \le \dfrac{D(X)}{\varepsilon^2}$

取 $\varepsilon = 2\sigma$，$P(|X - \mu| \ge 2\sigma) \le \dfrac{\sigma^2}{4\sigma^2} = 1/4$

**出处**：切比雪夫不等式

---

### 题 8

**题干**：设 $X_1, X_2, \cdots, X_n$ 独立同服从 $B(1, p)$，则由中心极限定理，$\lim_{n \to \infty} P\left\{\dfrac{\sum_{i=1}^n X_i - np}{\sqrt{np(1-p)}} \le x\right\} = $ \_\_\_\_\_\_

**标准答案**：$\boxed{\Phi(x)}$

**答案解析**：

标准中心极限定理结果

**出处**：二项分布的正态近似

---

### 题 9

**题干**：设 $X_1, X_2, \cdots$ 独立同分布，$E(X_i) = \mu$，$D(X_i) = \sigma^2$，则对任意 $\varepsilon > 0$，$\lim_{n \to \infty} P\left\{\left|\dfrac{1}{n} \sum_{i=1}^n X_i - \mu\right| \ge \varepsilon\right\} = $ \_\_\_\_\_\_

**标准答案**：$\boxed{0}$

**答案解析**：

由大数定律（切比雪夫或辛钦），样本均值依概率收敛到 $\mu$

**出处**：大数定律

---

### 题 10

**题干**：设 $X \sim B(100, 0.2)$，由切比雪夫不等式估计 $P\{|X - 20| \ge 10\} \le $ \_\_\_\_\_\_

**标准答案**：$\boxed{0.16}$

**答案解析**：

$E(X) = np = 20$，$D(X) = np(1-p) = 100 \cdot 0.2 \cdot 0.8 = 16$

切比雪夫：$P(|X - 20| \ge 10) \le \dfrac{16}{100} = 0.16$

**出处**：切比雪夫不等式应用

---

### 题 11

**题干**：设 $X_1, X_2, \cdots, X_n$ 独立同分布，$E(X_i) = 0$，$D(X_i) = 1$，则由中心极限定理，$P\left\{\sum_{i=1}^n X_i \le 0\right\} \approx $ \_\_\_\_\_\_（当 $n$ 较大时）

**标准答案**：$\boxed{1/2}$

**答案解析**：

$\sum X_i$ 近似 $N(0, n)$

$P\left(\sum X_i \le 0\right) = P\left(\dfrac{\sum X_i}{\sqrt{n}} \le 0\right) \approx \Phi(0) = 1/2$

**出处**：中心极限定理近似

---

### 题 12

**题干**：设随机变量 $X_1, X_2, \cdots, X_{100}$ 独立同服从 $U(0, 1)$，则由中心极限定理，$P\left\{\sum_{i=1}^{100} X_i \le 50\right\} \approx $ \_\_\_\_\_\_（用标准正态分布函数表示）

**标准答案**：$\boxed{\Phi(0) = \dfrac{1}{2}}$（或等价形式）

**答案解析**：

$E(X_i) = 1/2$，$D(X_i) = 1/12$

$E(\sum X_i) = 50$，$D(\sum X_i) = 100/12 = 25/3$

$P\left(\sum X_i \le 50\right) = P\left(\dfrac{\sum X_i - 50}{\sqrt{25/3}} \le 0\right) \approx \Phi(0) = 1/2$

**出处**：均匀分布的中心极限近似

---

## 三、解答题（略）

---
