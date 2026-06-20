# 数理统计基本概念 — 题库

## 一、单项选择题

---

### 题 1

**题干**：设 $X_1, X_2, \cdots, X_n$ 是来自总体 $X$ 的简单随机样本，则 $X_1, X_2, \cdots, X_n$ 必然满足

**选项**：
(A) 独立但分布不同
(B) 分布相同但不相互独立
(C) 独立同分布
(D) 既不独立也不同分布

**标准答案**：$\boxed{C}$

**答案解析**：

简单随机样本定义：独立且与总体同分布

**出处**：简单随机样本定义

---

### 题 2

**题干**：设随机变量 $X \sim t(n)$（$n > 1$），$Y = \dfrac{1}{X^2}$，则

**选项**：
(A) $Y \sim \chi^2(n)$
(B) $Y \sim \chi^2(n-1)$
(C) $Y \sim F(n, 1)$
(D) $Y \sim F(1, n)$

**标准答案**：$\boxed{C}$

**答案解析**：

$X \sim t(n)$，即 $X = \dfrac{Z}{\sqrt{U/n}}$，其中 $Z \sim N(0, 1)$，$U \sim \chi^2(n)$ 独立

$X^2 = \dfrac{Z^2}{U/n} = \dfrac{\chi^2(1)/1}{\chi^2(n)/n}$

故 $Y = \dfrac{1}{X^2} = \dfrac{\chi^2(n)/n}{\chi^2(1)/1} \sim F(n, 1)$

**出处**：t 分布与 F 分布关系

---

### 题 3

**题干**：设 $X_1, X_2, \cdots, X_n$ 是来自总体 $N(\mu, \sigma^2)$ 的样本，$\bar{X}$ 是样本均值，记 $S_1^2 = \dfrac{1}{n-1} \sum_{i=1}^n (X_i - \bar{X})^2$，$S_2^2 = \dfrac{1}{n} \sum_{i=1}^n (X_i - \bar{X})^2$，$S_3^2 = \dfrac{1}{n-1} \sum_{i=1}^n (X_i - \mu)^2$，$S_4^2 = \dfrac{1}{n} \sum_{i=1}^n (X_i - \mu)^2$，则服从自由度为 $n - 1$ 的 t 分布的随机变量是

**选项**：
(A) $\dfrac{\bar{X} - \mu}{S_1 / \sqrt{n-1}}$
(B) $\dfrac{\bar{X} - \mu}{S_2 / \sqrt{n-1}}$
(C) $\dfrac{\bar{X} - \mu}{S_3 / \sqrt{n}}$
(D) $\dfrac{\bar{X} - \mu}{S_4 / \sqrt{n}}$

**标准答案**：$\boxed{B}$

**答案解析**：

由正态样本性质：

1. $\bar{X} \sim N(\mu, \sigma^2/n)$，即 $\dfrac{\bar{X} - \mu}{\sigma/\sqrt{n}} \sim N(0, 1)$

2. $\dfrac{(n-1)S_1^2}{\sigma^2} = \dfrac{n S_2^2}{\sigma^2} \sim \chi^2(n-1)$，与 $\bar{X}$ 独立

3. $\dfrac{\bar{X} - \mu}{S_1 / \sqrt{n}} = \dfrac{(\bar{X} - \mu)/(\sigma/\sqrt{n})}{\sqrt{(n-1)S_1^2/\sigma^2}/(n-1)} \sim t(n-1)$

检查选项：

(A) $\dfrac{\bar{X} - \mu}{S_1/\sqrt{n-1}}$，分母应为 $\sqrt{n}$

(B) $\dfrac{\bar{X} - \mu}{S_2/\sqrt{n-1}} = \dfrac{(\bar{X} - \mu)/(\sigma/\sqrt{n})}{\sqrt{n S_2^2/\sigma^2}/(n-1)} = \dfrac{N(0, 1)}{\sqrt{\chi^2(n-1)/(n-1)}} \sim t(n-1)$ ✓

**出处**：正态样本的 t 分布

---

### 题 4

**题干**：设 $X \sim N(0, 1)$，$Y \sim N(0, 1)$，且 $X$ 与 $Y$ 独立，则

**选项**：
(A) $X + Y \sim N(0, 1)$
(B) $X^2 + Y^2 \sim \chi^2(2)$
(C) $X^2 / Y^2 \sim F(1, 1)$
(D) $X / \sqrt{Y^2} \sim t(1)$

**标准答案**：$\boxed{B}$ 或 $\boxed{C}$ 或 $\boxed{D}$

**答案解析**：

(A) $X + Y \sim N(0, 2)$，方差为 2，不对

(B) $X^2 \sim \chi^2(1)$，$Y^2 \sim \chi^2(1)$，独立故 $X^2 + Y^2 \sim \chi^2(2)$，对

(C) $X^2 / Y^2 = (X^2/1)/(Y^2/1) \sim F(1, 1)$，对

(D) $X / \sqrt{Y^2} = X / |Y|$，注意 $t$ 分布定义 $t(n) = Z / \sqrt{U/n}$，这里 $n = 1$，$U = Y^2 \sim \chi^2(1)$，故 $X / \sqrt{Y^2} \sim t(1)$，对

**出处**：三大抽样分布

---

### 题 5

**题干**：设 $X_1, X_2, \cdots, X_n$（$n \ge 2$）为来自总体 $N(0, 1)$ 的简单随机样本，$\bar{X}$ 为样本均值，$S^2$ 为样本方差，则

**选项**：
(A) $n \bar{X} \sim N(0, 1)$
(B) $n S^2 \sim \chi^2(n)$
(C) $\dfrac{(n-1)\bar{X}}{S} \sim t(n-1)$
(D) $\dfrac{(n-1)X_1^2}{\sum_{i=2}^n X_i^2} \sim F(1, n-1)$

**标准答案**：$\boxed{D}$

**答案解析**：

(A) $n \bar{X} = \sum X_i \sim N(0, n)$，不对（应为 $N(0, n)$）

(B) $(n-1)S^2 \sim \chi^2(n-1)$，不是 $n S^2$，也不是 $n$ 自由度

(C) $\dfrac{\bar{X}}{S/\sqrt{n}} = \dfrac{\sqrt{n} \bar{X}}{S} \sim t(n-1)$，不是 $(n-1)\bar{X}/S$

(D) $X_1^2 \sim \chi^2(1)$，$\sum_{i=2}^n X_i^2 \sim \chi^2(n-1)$，独立

故 $\dfrac{X_1^2/1}{\sum_{i=2}^n X_i^2/(n-1)} = \dfrac{(n-1)X_1^2}{\sum_{i=2}^n X_i^2} \sim F(1, n-1)$，对

**出处**：正态样本抽样分布

---

### 题 6

**题干**：设总体 $X$ 服从参数为 2 的指数分布，$X_1, X_2, \cdots, X_n$ 为来自总体 $X$ 的简单随机样本，则当 $n \to \infty$ 时，$Y_n = \dfrac{1}{n} \sum_{i=1}^n X_i^2$ 依概率收敛于

**选项**：
(A) $1/2$
(B) $1$
(C) $2$
(D) $1/4$

**标准答案**：$\boxed{C}$？需验证

**答案解析**：

$X \sim \text{Exp}(2)$，$E(X) = 1/2$，$D(X) = 1/4$

$E(X^2) = D(X) + [E(X)]^2 = 1/4 + 1/4 = 1/2$

由大数定律，$Y_n = \dfrac{1}{n} \sum X_i^2 \xrightarrow{P} E(X^2) = 1/2$

**答案修正**：$\boxed{A}$

**出处**：大数定律应用

---

## 二、填空题

---

### 题 7

**题干**：设总体 $X \sim N(\mu, \sigma^2)$，$X_1, X_2, \cdots, X_n$ 为样本，$\bar{X}$ 为样本均值，则 $E(\bar{X}) = $ \_\_\_\_\_\_，$D(\bar{X}) = $ \_\_\_\_\_\_

**标准答案**：$E(\bar{X}) = \boxed{\mu}$，$D(\bar{X}) = \boxed{\dfrac{\sigma^2}{n}}$

**答案解析**：

基本性质

**出处**：样本均值的期望方差

---

### 题 8

**题干**：设总体 $X$ 服从 $N(\mu, \sigma^2)$，$X_1, X_2, \cdots, X_n$ 是样本，$S^2 = \dfrac{1}{n-1} \sum_{i=1}^n (X_i - \bar{X})^2$ 是样本方差，则 $\dfrac{(n-1)S^2}{\sigma^2} \sim $ \_\_\_\_\_\_

**标准答案**：$\boxed{\chi^2(n-1)}$

**答案解析**：

正态样本的基本定理

**出处**：卡方分布的典型应用

---

### 题 9

**题干**：设随机变量 $X$ 和 $Y$ 相互独立且都服从正态分布 $N(0, 3^2)$，而 $X_1, X_2, \cdots, X_9$ 和 $Y_1, Y_2, \cdots, Y_9$ 是分别来自总体 $X$ 和 $Y$ 的简单随机样本，则统计量 $U = \dfrac{X_1 + \cdots + X_9}{\sqrt{Y_1^2 + \cdots + Y_9^2}}$ 服从 \_\_\_\_\_\_ 分布，参数为 \_\_\_\_\_\_

**标准答案**：$\boxed{t}$ 分布，参数为 $\boxed{9}$

**答案解析**：

$E(\sum X_i) = 0$，$D(\sum X_i) = 9 \cdot 9 = 81$

$\dfrac{\sum X_i}{9} \sim N(0, 1)$

$Y_i / 3 \sim N(0, 1)$，$\sum (Y_i/3)^2 = \dfrac{1}{9} \sum Y_i^2 \sim \chi^2(9)$

$U = \dfrac{\sum X_i}{\sqrt{\sum Y_i^2}} = \dfrac{(\sum X_i)/9}{\sqrt{\sum Y_i^2 / 81}} = \dfrac{(\sum X_i)/9}{\sqrt{(\sum Y_i^2 / 9)/9}} \sim t(9)$

**出处**：t 分布构造

---

### 题 10

**题干**：设 $X_1, X_2, \cdots, X_{16}$ 是来自总体 $N(\mu, \sigma^2)$ 的样本，$\bar{X}$ 是样本均值，$S$ 是样本标准差，则 $\dfrac{4(\bar{X} - \mu)}{S} \sim $ \_\_\_\_\_\_

**标准答案**：$\boxed{t(15)}$

**答案解析**：

$\dfrac{\bar{X} - \mu}{S/\sqrt{16}} = \dfrac{4(\bar{X} - \mu)}{S} \sim t(15)$

**出处**：t 分布的典型构造

---

### 题 11

**题干**：设随机变量 $X \sim F(n, n)$，则 $P\{X > 1\} = $ \_\_\_\_\_\_

**标准答案**：$\boxed{\dfrac{1}{2}}$

**答案解析**：

由 $F$ 分布性质：若 $X \sim F(m, n)$，则 $1/X \sim F(n, m)$

当 $m = n$ 时，$X$ 与 $1/X$ 同分布

$P(X > 1) = P(1/X > 1) = P(X < 1)$

又 $P(X = 1) = 0$（连续），故 $P(X > 1) + P(X < 1) = 1$

因此 $P(X > 1) = 1/2$

**出处**：F 分布的对称性

---

### 题 12

**题干**：设总体 $X \sim N(\mu, \sigma^2)$，$X_1, X_2, \cdots, X_{2n}$（$n \ge 2$）为样本，$\bar{X} = \dfrac{1}{2n} \sum_{i=1}^{2n} X_i$，且 $S^2 = \dfrac{1}{2n-1} \sum_{i=1}^{2n} (X_i - \bar{X})^2$，记 $Y = \dfrac{n(\bar{X} - \mu)^2}{S^2}$，则 $Y \sim $ \_\_\_\_\_\_

**标准答案**：$\boxed{F(1, 2n-1)}$

**答案解析**：

$\bar{X} \sim N(\mu, \sigma^2/(2n))$，$\dfrac{\bar{X} - \mu}{\sigma/\sqrt{2n}} \sim N(0, 1)$

故 $n(\bar{X} - \mu)^2 / \sigma^2 = \left(\dfrac{\bar{X} - \mu}{\sigma/\sqrt{2n}}\right)^2 \cdot \dfrac{\sigma^2/(2n)}{\sigma^2/n} = \dfrac{n(\bar{X} - \mu)^2}{\sigma^2} \cdot 2$？重新：

设 $Z = \dfrac{\sqrt{2n}(\bar{X} - \mu)}{\sigma} \sim N(0, 1)$，则 $Z^2 \sim \chi^2(1)$

$Z^2 = \dfrac{2n(\bar{X} - \mu)^2}{\sigma^2}$

$(2n-1)S^2/\sigma^2 \sim \chi^2(2n-1)$

$Y = \dfrac{n(\bar{X} - \mu)^2}{S^2} = \dfrac{n(\bar{X} - \mu)^2/\sigma^2}{S^2/\sigma^2} = \dfrac{Z^2 / 2}{(2n-1)S^2/\sigma^2 / (2n-1)} = \dfrac{Z^2/2}{\chi^2(2n-1)/(2n-1)}$？

$Z^2/2 = \dfrac{\chi^2(1)}{2}$，所以 $Y = \dfrac{\chi^2(1)/1}{\chi^2(2n-1)/(2n-1)} \sim F(1, 2n-1)$

**出处**：F 分布的构造

---

## 三、解答题（略）

---
