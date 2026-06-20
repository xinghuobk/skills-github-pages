# 随机变量的数字特征 — 题库

## 一、单项选择题

---

### 题 1

**题干**：设随机变量 $X$ 服从参数为 $\lambda$ 的泊松分布，则随机变量 $Y = 2X$ 的方差 $D(Y) = $

**选项**：
(A) $\lambda$
(B) $2\lambda$
(C) $4\lambda$
(D) $2\lambda^2$

**标准答案**：$\boxed{C}$

**答案解析**：

$X \sim P(\lambda)$，则 $D(X) = \lambda$

$D(Y) = D(2X) = 4D(X) = 4\lambda$

**出处**：泊松分布方差

---

### 题 2

**题干**：设随机变量 $X$ 和 $Y$ 独立同分布，记 $U = X - Y$，$V = X + Y$，则随机变量 $U$ 和 $V$ 必然

**选项**：
(A) 不独立
(B) 独立
(C) 不相关
(D) 相关

**标准答案**：$\boxed{C}$

**答案解析**：

$\text{Cov}(U, V) = \text{Cov}(X-Y, X+Y) = D(X) - D(Y)$（对一般 $X, Y$）

由 $X, Y$ 同分布，$D(X) = D(Y)$，故 $\text{Cov}(U, V) = 0$

即 $U, V$ 不相关

独立性不一定成立（除非是正态）

**出处**：随机变量函数的协方差

---

### 题 3

**题干**：设随机变量 $X_1, X_2, \cdots, X_n$（$n > 1$）独立同分布，且其方差为 $\sigma^2 > 0$。令 $Y = \dfrac{1}{n} \sum_{i=1}^n X_i$，则

**选项**：
(A) $\text{Cov}(X_1, Y) = \dfrac{\sigma^2}{n}$
(B) $\text{Cov}(X_1, Y) = \sigma^2$
(C) $D(X_1 + Y) = \dfrac{n+2}{n} \sigma^2$
(D) $D(X_1 - Y) = \dfrac{n+1}{n} \sigma^2$

**标准答案**：$\boxed{A}$

**答案解析**：

$\text{Cov}(X_1, Y) = \text{Cov}\left(X_1, \dfrac{1}{n} \sum_{i=1}^n X_i\right) = \dfrac{1}{n} \sum_{i=1}^n \text{Cov}(X_1, X_i) = \dfrac{1}{n} D(X_1) = \dfrac{\sigma^2}{n}$（由独立性，$i \neq 1$ 时协方差为 0）

(B) 错

(C) $D(X_1 + Y) = D(X_1) + D(Y) + 2\text{Cov}(X_1, Y) = \sigma^2 + \sigma^2/n + 2\sigma^2/n = \sigma^2(1 + 3/n)$，不对

(D) $D(X_1 - Y) = D(X_1) + D(Y) - 2\text{Cov}(X_1, Y) = \sigma^2 + \sigma^2/n - 2\sigma^2/n = \sigma^2(1 - 1/n)$，不对

**出处**：样本均值协方差

---

### 题 4

**题干**：设 $X$ 是一个随机变量，$E(X) = \mu$，$D(X) = \sigma^2$（$\mu, \sigma > 0$ 为常数），则对任意常数 $C$，必有

**选项**：
(A) $E(X - C)^2 = E(X^2) - C^2$
(B) $E(X - C)^2 = E(X - \mu)^2$
(C) $E(X - C)^2 < E(X - \mu)^2$
(D) $E(X - C)^2 \ge E(X - \mu)^2$

**标准答案**：$\boxed{D}$

**答案解析**：

$E(X - C)^2 = E[(X - \mu) + (\mu - C)]^2 = E(X - \mu)^2 + 2(\mu - C)E(X - \mu) + (\mu - C)^2$

$= D(X) + 0 + (\mu - C)^2 = \sigma^2 + (\mu - C)^2 \ge \sigma^2 = E(X - \mu)^2$

等号当 $C = \mu$ 时成立

**出处**：均方误差最小性

---

### 题 5

**题干**：设随机变量 $X_1, X_2, \cdots, X_n$（$n \ge 2$）独立同分布，且方差 $\sigma^2 > 0$。令随机变量 $Y = \dfrac{1}{n} \sum_{i=1}^n X_i$，则

**选项**：
(A) $D(X_1 + Y) = \dfrac{(n+3)\sigma^2}{n}$
(B) $D(X_1 + Y) = \dfrac{(n+1)\sigma^2}{n}$
(C) $\text{Cov}(X_1, Y) = \sigma^2$
(D) $\text{Cov}(X_1, Y) = \dfrac{\sigma^2}{n}$

**标准答案**：$\boxed{D}$

**答案解析**：

同题 3，$\text{Cov}(X_1, Y) = \sigma^2/n$

$D(X_1 + Y) = D(X_1) + D(Y) + 2\text{Cov}(X_1, Y) = \sigma^2 + \sigma^2/n + 2\sigma^2/n = \sigma^2(1 + 3/n)$

(A)(B) 都不对

**出处**：数字特征综合

---

### 题 6

**题干**：设随机变量 $X$ 和 $Y$ 的方差存在且不等于 0，则 $D(X + Y) = D(X) + D(Y)$ 是 $X$ 和 $Y$

**选项**：
(A) 不相关的充分必要条件
(B) 独立的充分条件，但不是必要条件
(C) 不相关的充分条件，但不是必要条件
(D) 独立的充分必要条件

**标准答案**：$\boxed{A}$

**答案解析**：

$D(X + Y) = D(X) + D(Y) + 2\text{Cov}(X, Y)$

故 $D(X+Y) = D(X) + D(Y) \iff \text{Cov}(X, Y) = 0 \iff X, Y$ 不相关

这是充要条件

**出处**：方差可加性与不相关

---

## 二、填空题

---

### 题 7

**题干**：设随机变量 $X$ 服从参数为 $\lambda$ 的泊松分布，则 $E(X^2) = $ \_\_\_\_\_\_

**标准答案**：$\boxed{\lambda + \lambda^2}$

**答案解析**：

$E(X) = \lambda$，$D(X) = \lambda$

由 $D(X) = E(X^2) - [E(X)]^2$，$E(X^2) = D(X) + [E(X)]^2 = \lambda + \lambda^2$

**出处**：泊松分布二阶矩

---

### 题 8

**题干**：设随机变量 $X$ 服从二项分布 $B(n, p)$，则 $E(X) = $ \_\_\_\_\_\_，$D(X) = $ \_\_\_\_\_\_

**标准答案**：$E(X) = \boxed{np}$，$D(X) = \boxed{np(1-p)}$

**答案解析**：

标准结果，$X$ 可分解为 $n$ 个独立伯努利之和

**出处**：二项分布数字特征

---

### 题 9

**题干**：设随机变量 $X$ 和 $Y$ 的相关系数为 0.5，$E(X) = E(Y) = 0$，$E(X^2) = E(Y^2) = 2$，则 $E[(X + Y)^2] = $ \_\_\_\_\_\_

**标准答案**：$\boxed{6}$

**答案解析**：

$E[(X+Y)^2] = E(X^2) + E(Y^2) + 2E(XY) = 2 + 2 + 2E(XY) = 4 + 2E(XY)$

$\rho_{XY} = \dfrac{\text{Cov}(X, Y)}{\sqrt{D(X)}\sqrt{D(Y)}} = \dfrac{E(XY) - E(X)E(Y)}{\sqrt{2}\sqrt{2}} = \dfrac{E(XY)}{2} = 0.5$

故 $E(XY) = 1$

$E[(X+Y)^2] = 4 + 2 \cdot 1 = 6$

**出处**：相关系数应用

---

### 题 10

**题干**：设随机变量 $X$ 服从正态分布 $N(\mu, \sigma^2)$，则 $E|X - \mu| = $ \_\_\_\_\_\_

**标准答案**：$\boxed{\sigma \sqrt{\dfrac{2}{\pi}}}$

**答案解析**：

$Y = \dfrac{X - \mu}{\sigma} \sim N(0, 1)$

$E|Y| = \int_{-\infty}^{\infty} |y| \dfrac{1}{\sqrt{2\pi}} e^{-y^2/2} dy = \dfrac{2}{\sqrt{2\pi}} \int_0^{\infty} y e^{-y^2/2} dy = \dfrac{2}{\sqrt{2\pi}} = \sqrt{\dfrac{2}{\pi}}$

$E|X - \mu| = \sigma E|Y| = \sigma \sqrt{2/\pi}$

**出处**：正态分布绝对值期望

---

### 题 11

**题干**：设连续型随机变量 $X$ 的概率密度为 $f(x) = \begin{cases} 1 + x, & -1 \le x \le 0 \\ 1 - x, & 0 < x \le 1 \\ 0, & \text{其他} \end{cases}$，则方差 $D(X) = $ \_\_\_\_\_\_

**标准答案**：$\boxed{\dfrac{1}{6}}$

**答案解析**：

$E(X) = \int_{-1}^0 x(1+x) dx + \int_0^1 x(1-x) dx = \int_{-1}^0 (x + x^2) dx + \int_0^1 (x - x^2) dx$

$= \left[\dfrac{x^2}{2} + \dfrac{x^3}{3}\right]_{-1}^0 + \left[\dfrac{x^2}{2} - \dfrac{x^3}{3}\right]_0^1 = -\left(\dfrac{1}{2} - \dfrac{1}{3}\right) + \left(\dfrac{1}{2} - \dfrac{1}{3}\right) = 0$

$E(X^2) = \int_{-1}^0 x^2(1+x) dx + \int_0^1 x^2(1-x) dx = \int_{-1}^0 (x^2 + x^3) dx + \int_0^1 (x^2 - x^3) dx$

$= \left[\dfrac{x^3}{3} + \dfrac{x^4}{4}\right]_{-1}^0 + \left[\dfrac{x^3}{3} - \dfrac{x^4}{4}\right]_0^1 = -\left(-\dfrac{1}{3} + \dfrac{1}{4}\right) + \left(\dfrac{1}{3} - \dfrac{1}{4}\right) = \dfrac{1}{3} - \dfrac{1}{4} + \dfrac{1}{3} - \dfrac{1}{4} = \dfrac{2}{3} - \dfrac{1}{2} = \dfrac{1}{6}$

$D(X) = E(X^2) = 1/6$

**出处**：连续型随机变量方差

---

### 题 12

**题干**：设随机变量 $X$ 和 $Y$ 独立，且 $X \sim N(1, 2)$，$Y \sim N(0, 1)$，则 $Z = 2X - Y + 3$ 的概率密度为 \_\_\_\_\_\_

**标准答案**：$\boxed{\dfrac{1}{3\sqrt{2\pi}} e^{-\dfrac{(z - 5)^2}{18}}}$

**答案解析**：

$E(Z) = 2E(X) - E(Y) + 3 = 2 \cdot 1 - 0 + 3 = 5$

$D(Z) = 4D(X) + D(Y) = 4 \cdot 2 + 1 = 9$（因 $X, Y$ 独立）

故 $Z \sim N(5, 9)$

密度 $f_Z(z) = \dfrac{1}{3\sqrt{2\pi}} e^{-(z-5)^2/18}$

**出处**：正态随机变量线性函数

---

## 三、解答题（略）

---
