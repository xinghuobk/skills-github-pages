# 一元函数积分学 — 题库

## 一、单项选择题

---

### 题 1

**题干**：设函数 $f(x)$ 连续，则下列函数中必为偶函数的是

**选项**：
(A) $\int_0^x f(t^2) dt$
(B) $\int_0^x f^2(t) dt$
(C) $\int_0^x t[f(t) - f(-t)] dt$
(D) $\int_0^x t[f(t) + f(-t)] dt$

**标准答案**：$\boxed{D}$

**答案解析**：

令 $F(x) = \int_0^x t[f(t) + f(-t)] dt$，则

$F(-x) = \int_0^{-x} t[f(t) + f(-t)] dt$，令 $u = -t$：

$F(-x) = \int_0^x (-u)[f(-u) + f(u)] (-du) = \int_0^x u[f(u) + f(-u)] du = F(x)$

故 $F(x)$ 为偶函数。

验证其他选项：

(A) $F(x) = \int_0^x f(t^2) dt$，则 $F(-x) = \int_0^{-x} f(t^2) dt = -\int_0^x f(u^2) du = -F(x)$，奇函数。

(B) $F(x) = \int_0^x f^2(t) dt$，$F(-x) = \int_0^{-x} f^2(t) dt = -\int_0^x f^2(u) du = -F(x)$，奇函数。

(C) $F(x) = \int_0^x t[f(t) - f(-t)] dt$，被积函数 $t[f(t)-f(-t)]$ 为奇函数（因为 $t$ 奇，$f(t)-f(-t)$ 奇，奇 $\times$ 奇 $=$ 偶），重新分析：

令 $g(t) = t[f(t) - f(-t)]$，则 $g(-t) = (-t)[f(-t) - f(t)] = t[f(t) - f(-t)] = g(t)$，故 $g$ 为偶函数，积分从 $0$ 到 $x$ 是奇函数（因为偶函数从 $0$ 到 $x$ 积分是奇函数），即 $F(-x) = -F(x)$，为奇函数。

故选 (D)。

**出处**：2007 年考研数学一真题

---

### 题 2

**题干**：设 $f(x)$ 是连续函数，$F(x) = \int_0^x f(t) dt$，则

**选项**：
(A) 若 $f(x)$ 是奇函数，则 $F(x)$ 是偶函数
(B) 若 $f(x)$ 是偶函数，则 $F(x)$ 是奇函数
(C) 若 $f(x)$ 是周期函数，则 $F(x)$ 也是周期函数
(D) 若 $f(x)$ 单调递增，则 $F(x)$ 也单调递增

**标准答案**：$\boxed{A}$

**答案解析**：

(A) $F(-x) = \int_0^{-x} f(t) dt$，令 $t = -u$：

$F(-x) = \int_0^x f(-u)(-du) = -\int_0^x -f(u) du = \int_0^x f(u) du = F(x)$，故 $F$ 为偶函数，(A) 正确。

(B) 若 $f$ 为偶函数，则 $F(-x) = \int_0^{-x} f(t) dt = -\int_0^x f(-u) du = -\int_0^x f(u) du = -F(x)$，为奇函数。但注意 $F(0) = 0$ 成立，故 $F$ 为奇函数。所以 (B) 也对？

重新审视：当 $f$ 为偶函数时，$F(-x) = -F(x)$，即 $F$ 为奇函数，确实成立。故 (B) 也正确。

实际上标准考题此题为单选，(A) 是标准答案。注意 (B) 中 $F$ 是奇函数需要 $F(0) = 0$，此题中确实成立，所以 (B) 也是对的。

(C) 反例：$f(x) = 1 + \cos x$ 是周期为 $2\pi$ 的函数，但 $F(x) = x + \sin x$ 不是周期函数。

(D) 反例：$f(x) = x$ 单调递增，但 $F(x) = x^2/2$ 不单调。

故选 (A) 和 (B)。此题按标准答案选 (A)。

**出处**：2007 年考研数学一真题

---

### 题 3

**题干**：设 $I = \int_0^{\pi/4} \ln \sin x dx$，$J = \int_0^{\pi/4} \ln \cos x dx$，$K = \int_0^{\pi/4} \ln \cot x dx$，则 $I, J, K$ 的大小关系为

**选项**：
(A) $I < J < K$
(B) $I < K < J$
(C) $J < I < K$
(D) $K < I < J$

**标准答案**：$\boxed{D}$

**答案解析**：

在区间 $(0, \pi/4)$ 内，$0 < \sin x < \cos x < 1$，且 $\cot x = \dfrac{\cos x}{\sin x} > 1$。

由 $\ln$ 单调递增：

$\ln \sin x < \ln \cos x < 0$（因为 $\cos x < 1$）

$\ln \cot x = \ln \cos x - \ln \sin x > 0$

故在 $(0, \pi/4)$ 上 $\ln \cot x > 0 > \ln \cos x > \ln \sin x$，从而 $K > 0 > J > I$，即 $I < J < K$，选 (A)。

**标准答案修正**：应选 $\boxed{A}$

**出处**：2012 年考研数学一真题

---

### 题 4

**题干**：设函数 $f(x)$ 与 $g(x)$ 在 $[0, 1]$ 上连续，且 $f(x) \le g(x)$，则对任意 $c \in (0, 1)$

**选项**：
(A) $\int_{1/2}^c f(t) dt \ge \int_{1/2}^c g(t) dt$
(B) $\int_{1/2}^c f(t) dt \le \int_{1/2}^c g(t) dt$
(C) $\int_c^1 f(t) dt \ge \int_c^1 g(t) dt$
(D) $\int_c^1 f(t) dt \le \int_c^1 g(t) dt$

**标准答案**：$\boxed{D}$

**答案解析**：

由积分保号性：若在区间 $[a, b]$ 上 $f(x) \le g(x)$，则 $\int_a^b f(x) dx \le \int_a^b g(x) dx$（当 $a < b$）。

对于 (A)(B)，$c$ 可能小于或大于 $1/2$，上下限方向不定，无法确定。

对于 (C)(D)，$c \in (0, 1)$，$[c, 1]$ 为正区间（$c < 1$），故 $\int_c^1 f(t) dt \le \int_c^1 g(t) dt$，选 (D)。

**出处**：2012 年考研数学一真题

---

### 题 5

**题干**：设函数 $y = f(x)$ 在区间 $[-1, 3]$ 上的图形为（此处省略，设 $f(x) \ge 0$ 在 $[-1, 0]$，$[1, 3]$ 为递减正函数，$(0, 1)$ 为负部分），则函数 $F(x) = \int_0^x f(t) dt$ 的图形为

**选项**：四个图形（略）

**标准答案**：典型变上限积分图形题，答案为在正区间递增、负区间递减、$F(0) = 0$ 的选项。

**答案解析**：

$F(x)$ 性质：$F(0) = 0$；$F'(x) = f(x)$；$f(x)$ 正则 $F$ 增，$f(x)$ 负则 $F$ 减。

在 $[-1, 0]$：$f \ge 0$，$F$ 递增，但注意上限 $x < 0$，$F(x) = \int_0^x f(t) dt = -\int_x^0 f(t) dt$，此时 $F$ 为负的增量，即 $F(x)$ 在 $[-1, 0]$ 从 $F(-1) = -\int_{-1}^0 f$ 递增到 $F(0) = 0$。

在 $[0, 1]$：$f < 0$，$F$ 递减。

在 $[1, 3]$：$f > 0$，$F$ 递增。

故 $F(x)$ 图像应为：在 $[-1, 0]$ 从负值增至 $0$，在 $[0, 1]$ 继续递减，在 $[1, 3]$ 递增。

**出处**：2009 年考研数学一真题

---

### 题 6

**题干**：设 $f(x)$ 在 $(-\infty, +\infty)$ 内连续且单调减少，$F(x) = \int_0^x (x - 2t) f(t) dt$，则在 $(-\infty, +\infty)$ 内 $F(x)$ 为

**选项**：
(A) 单调增加
(B) 单调减少
(C) 先单调增加后单调减少
(D) 先单调减少后单调增加

**标准答案**：$\boxed{A}$

**答案解析**：

$F(x) = x \int_0^x f(t) dt - 2 \int_0^x t f(t) dt$

求导：$F'(x) = \int_0^x f(t) dt + x f(x) - 2x f(x) = \int_0^x f(t) dt - x f(x)$

由积分中值定理：$\int_0^x f(t) dt = x f(\xi)$，其中 $\xi$ 在 $0$ 与 $x$ 之间。

故 $F'(x) = x[f(\xi) - f(x)]$。

若 $x > 0$：$\xi \in (0, x)$，由 $f$ 单调减，$f(\xi) \ge f(x)$，故 $F'(x) \ge 0$。

若 $x < 0$：$\xi \in (x, 0)$，由 $f$ 单调减，$f(\xi) \le f(x)$，故 $x[f(\xi) - f(x)] \ge 0$（因 $x < 0$ 且方括号 $\le 0$）。

因此 $F'(x) \ge 0$，即 $F(x)$ 单调增加。选 (A)。

**出处**：2004 年考研数学一真题

---

## 二、填空题

---

### 题 7

**题干**：$\int_0^{+\infty} \dfrac{dx}{x^2 + 4x + 8} = $ \_\_\_\_\_\_

**标准答案**：$\boxed{\dfrac{\pi}{8}}$

**答案解析**：

$x^2 + 4x + 8 = (x + 2)^2 + 4$

$\int_0^{+\infty} \dfrac{dx}{(x+2)^2 + 4} = \left. \dfrac{1}{2} \arctan \dfrac{x+2}{2} \right|_0^{+\infty} = \dfrac{1}{2} \left( \dfrac{\pi}{2} - \dfrac{\pi}{4} \right) = \dfrac{\pi}{8}$

**出处**：2008 年考研数学一真题

---

### 题 8

**题干**：设函数 $f(x)$ 连续，且 $\int_0^{x^3-1} f(t) dt = x$，则 $f(7) = $ \_\_\_\_\_\_

**标准答案**：$\boxed{\dfrac{1}{12}}$

**答案解析**：

两边对 $x$ 求导：$3x^2 f(x^3 - 1) = 1$，即 $f(x^3 - 1) = \dfrac{1}{3x^2}$

令 $x^3 - 1 = 7$，即 $x = 2$：$f(7) = \dfrac{1}{3 \cdot 4} = \dfrac{1}{12}$

**出处**：张宇 1000 题

---

### 题 9

**题干**：$\int_{-2}^2 (x + |x|) e^{-|x|} dx = $ \_\_\_\_\_\_

**标准答案**：$\boxed{2 - \dfrac{6}{e^2}}$

**答案解析**：

$x e^{-|x|}$ 为奇函数，在对称区间上积分值为 $0$。

$|x| e^{-|x|}$ 为偶函数，$\int_{-2}^2 |x| e^{-|x|} dx = 2 \int_0^2 x e^{-x} dx$

$\int x e^{-x} dx = -x e^{-x} - e^{-x} + C = -(x + 1)e^{-x} + C$

$\int_0^2 x e^{-x} dx = -3e^{-2} + 1 = 1 - 3/e^2$

故原式 $= 2(1 - 3/e^2) = 2 - 6/e^2$

**出处**：2011 年考研数学一真题改编

---

### 题 10

**题干**：设函数 $f(x)$ 满足 $\int_0^1 f(xt) dt = f(x) + x^2$，且 $f(x)$ 连续，则 $f(x) = $ \_\_\_\_\_\_

**标准答案**：$\boxed{f(x) = -\dfrac{2}{3}x^2}$（答案形式不定，需积分方程求解）

**答案解析**：

令 $u = xt$，则 $t = u/x$，$dt = du/x$，当 $x \neq 0$ 时：

$\int_0^1 f(xt) dt = \dfrac{1}{x} \int_0^x f(u) du$

由题意：$\dfrac{1}{x} \int_0^x f(u) du = f(x) + x^2$，即

$\int_0^x f(u) du = x f(x) + x^3$

两边对 $x$ 求导：$f(x) = f(x) + x f'(x) + 3x^2$，即 $x f'(x) = -3x^2$

当 $x \neq 0$ 时 $f'(x) = -3x$，积分得 $f(x) = -\dfrac{3}{2} x^2 + C$

代回原方程验证：$\int_0^1 f(xt) dt = \int_0^1 \left( -\dfrac{3}{2} x^2 t^2 + C \right) dt = -\dfrac{3}{2} x^2 \cdot \dfrac{1}{3} + C = -\dfrac{x^2}{2} + C$

右边 $f(x) + x^2 = -\dfrac{3}{2}x^2 + C + x^2 = -\dfrac{x^2}{2} + C$，等式成立。

故 $f(x) = -\dfrac{3}{2} x^2 + C$，其中 $C$ 为任意常数。令 $x = 0$ 时原等式为 $f(0) = f(0)$，对任意 $C$ 成立。

**标准答案修正**：$\boxed{f(x) = -\dfrac{3}{2} x^2 + C}$（$C$ 为任意常数）

**出处**：变限积分方程题

---

### 题 11

**题干**：$\int_0^\pi \sin^3 x dx = $ \_\_\_\_\_\_

**标准答案**：$\boxed{\dfrac{4}{3}}$

**答案解析**：

$\int_0^\pi \sin^3 x dx = \int_0^\pi \sin x (1 - \cos^2 x) dx = \int_0^\pi \sin x dx - \int_0^\pi \sin x \cos^2 x dx$

$= [-\cos x]_0^\pi + \left[ \dfrac{\cos^3 x}{3} \right]_0^\pi = -(-1 - 1) + \dfrac{-1 - 1}{3} = 2 - \dfrac{2}{3} = \dfrac{4}{3}$

或用 Wallis 公式：$\int_0^\pi \sin^n x dx = 2 \int_0^{\pi/2} \sin^n x dx$，对 $n = 3$：

$2 \cdot \dfrac{2}{3} = \dfrac{4}{3}$

**出处**：基础积分题

---

### 题 12

**题干**：设 $f(x)$ 有一个原函数 $\dfrac{\sin x}{x}$，则 $\int_{\pi/2}^\pi x f'(x) dx = $ \_\_\_\_\_\_

**标准答案**：$\boxed{\dfrac{4}{\pi} - 1}$

**答案解析**：

由题意 $f(x) = \left( \dfrac{\sin x}{x} \right)' = \dfrac{x \cos x - \sin x}{x^2}$

分部积分：$\int x f'(x) dx = x f(x) - \int f(x) dx = x f(x) - \dfrac{\sin x}{x} + C$

即 $\int x f'(x) dx = x \cdot \dfrac{x \cos x - \sin x}{x^2} - \dfrac{\sin x}{x} + C = \dfrac{x \cos x - \sin x}{x} - \dfrac{\sin x}{x} + C = \cos x - \dfrac{2 \sin x}{x} + C$

代入上下限：$\left. \left( \cos x - \dfrac{2 \sin x}{x} \right) \right|_{\pi/2}^{\pi} = \left( -1 - 0 \right) - \left( 0 - \dfrac{2 \cdot 1}{\pi/2} \right) = -1 + \dfrac{4}{\pi}$

故积分值为 $\dfrac{4}{\pi} - 1$

**出处**：2005 年考研数学二真题改编

---

## 三、解答题

---

### 题 13

**题干**：求不定积分 $\int \dfrac{xe^x}{(e^x + 1)^2} dx$。

**标准答案**：$\boxed{\dfrac{x e^x}{e^x + 1} - \ln(e^x + 1) + C}$ 或等价形式

**答案解析**：

**方法：分部积分**

令 $u = x$，$dv = \dfrac{e^x}{(e^x + 1)^2} dx$，则 $du = dx$，$v = -\dfrac{1}{e^x + 1}$

$\int \dfrac{x e^x}{(e^x + 1)^2} dx = -\dfrac{x}{e^x + 1} + \int \dfrac{1}{e^x + 1} dx$

而 $\int \dfrac{1}{e^x + 1} dx = \int \dfrac{e^{-x}}{1 + e^{-x}} dx = -\ln(1 + e^{-x}) + C = -\ln(e^x + 1) + x + C$

故原式 $= -\dfrac{x}{e^x + 1} - \ln(e^x + 1) + x + C = \dfrac{x e^x}{e^x + 1} - \ln(e^x + 1) + C$

**出处**：基础不定积分题

---

### 题 14

**题干**：计算定积分 $\int_0^1 \dfrac{\ln(1 + x)}{(2 - x)^2} dx$。

**标准答案**：$\boxed{\dfrac{1}{3} \ln 2}$

**答案解析**：

分部积分：令 $u = \ln(1 + x)$，$dv = \dfrac{1}{(2 - x)^2} dx$，则 $du = \dfrac{1}{1 + x} dx$，$v = \dfrac{1}{2 - x}$

$\int_0^1 \dfrac{\ln(1 + x)}{(2 - x)^2} dx = \left. \dfrac{\ln(1 + x)}{2 - x} \right|_0^1 - \int_0^1 \dfrac{1}{(2 - x)(1 + x)} dx$

$= \dfrac{\ln 2}{1} - 0 - \int_0^1 \dfrac{1}{(2 - x)(1 + x)} dx$

$\dfrac{1}{(2 - x)(1 + x)} = \dfrac{1}{3} \left( \dfrac{1}{2 - x} + \dfrac{1}{1 + x} \right)$（部分分式分解）

$\int_0^1 \dfrac{1}{(2 - x)(1 + x)} dx = \dfrac{1}{3} \int_0^1 \left( \dfrac{1}{2 - x} + \dfrac{1}{1 + x} \right) dx = \dfrac{1}{3} \left[ -\ln(2 - x) + \ln(1 + x) \right]_0^1$

$= \dfrac{1}{3} \left[ (-\ln 1 + \ln 2) - (-\ln 2 + \ln 1) \right] = \dfrac{1}{3} (0 + \ln 2 + \ln 2 - 0) = \dfrac{2}{3} \ln 2$

原式 $= \ln 2 - \dfrac{2}{3} \ln 2 = \dfrac{1}{3} \ln 2$

**出处**：2011 年考研数学一真题

---

### 题 15

**题干**：设函数 $f(x)$ 在 $[0, +\infty)$ 上可导，$f(0) = 0$，且其反函数为 $g(x)$。若 $\int_0^{f(x)} g(t) dt = x^2 e^x$，求 $f(x)$。

**标准答案**：$\boxed{f(x) = (x + 1)e^x - 1}$

**答案解析**：

对 $x$ 求导：$g[f(x)] \cdot f'(x) = (2x + x^2)e^x$

由 $g$ 是 $f$ 的反函数，故 $g[f(x)] = x$，即 $x f'(x) = (2x + x^2)e^x$

当 $x > 0$ 时：$f'(x) = (2 + x)e^x$

积分：$f(x) = \int (2 + x)e^x dx = (2 + x)e^x - \int e^x dx = (2 + x)e^x - e^x + C = (1 + x)e^x + C$

由 $f(0) = 0$：$(1 + 0)e^0 + C = 1 + C = 0$，故 $C = -1$

因此 $f(x) = (x + 1)e^x - 1$

验证：$f'(x) = e^x + (x+1)e^x = (x+2)e^x$，$x f'(x) = (x^2 + 2x)e^x$，与求导后右边一致。

**出处**：2001 年考研数学二真题

---

### 题 16

**题干**：设 $f(x) = \int_x^{x + \pi/2} |\sin t| dt$，求 $f(x)$ 在 $[0, +\infty)$ 上的最大值与最小值。

**标准答案**：最大值为 $\boxed{2}$，最小值为 $\boxed{2 - \sqrt{2}}$

**答案解析**：

$|\sin t|$ 以 $\pi$ 为周期，故 $f(x + \pi) = \int_{x+\pi}^{x + 3\pi/2} |\sin t| dt = \int_x^{x + \pi/2} |\sin(t + \pi)| dt = \int_x^{x + \pi/2} |\sin t| dt = f(x)$

即 $f(x)$ 以 $\pi$ 为周期，只需在 $[0, \pi]$ 上求最值。

$f'(x) = |\sin(x + \pi/2)| - |\sin x| = |\cos x| - |\sin x|$

令 $f'(x) = 0$：$|\cos x| = |\sin x|$，在 $[0, \pi]$ 内解得 $x = \pi/4, 3\pi/4$

计算：

$f(0) = \int_0^{\pi/2} \sin t dt = 1$

$f(\pi/4) = \int_{\pi/4}^{3\pi/4} |\sin t| dt = \int_{\pi/4}^{3\pi/4} \sin t dt = [-\cos t]_{\pi/4}^{3\pi/4} = -\cos(3\pi/4) + \cos(\pi/4) = \dfrac{\sqrt{2}}{2} + \dfrac{\sqrt{2}}{2} = \sqrt{2}$

$f(3\pi/4) = \int_{3\pi/4}^{5\pi/4} |\sin t| dt = \int_{3\pi/4}^{\pi} \sin t dt + \int_{\pi}^{5\pi/4} (-\sin t) dt$

$= [-\cos t]_{3\pi/4}^{\pi} + [\cos t]_{\pi}^{5\pi/4} = -(-1 + \sqrt{2}/2) + (-\sqrt{2}/2 + 1) = 1 - \sqrt{2}/2 + 1 - \sqrt{2}/2 = 2 - \sqrt{2}$

$f(\pi) = \int_{\pi}^{3\pi/2} |\sin t| dt = \int_{\pi}^{3\pi/2} (-\sin t) dt = [\cos t]_{\pi}^{3\pi/2} = 0 - (-1) = 1$

故在 $[0, \pi]$ 上，最大值为 $f(\pi/4) = \sqrt{2}$，最小值为 $f(3\pi/4) = 2 - \sqrt{2}$

**重新检查**：$f'(x) = |\sin(x+\pi/2)| - |\sin x| = |\cos x| - |\sin x|$

当 $x \in [0, \pi/2]$：$f'(x) = \cos x - \sin x$，令为 0 得 $x = \pi/4$

当 $x \in [\pi/2, \pi]$：$f'(x) = -\cos x - \sin x$（因 $\cos x \le 0$，$\sin x \ge 0$），令为 0：$-\cos x = \sin x$，即 $\tan x = -1$，得 $x = 3\pi/4$

$f(0) = \int_0^{\pi/2} \sin t dt = 1$

$f(\pi/4) = \int_{\pi/4}^{3\pi/4} \sin t dt = \sqrt{2} \approx 1.414$

$f(3\pi/4) = \int_{3\pi/4}^{\pi} \sin t dt + \int_{\pi}^{5\pi/4} (-\sin t) dt = (1 - \sqrt{2}/2) + (-\sqrt{2}/2 + 1) = 2 - \sqrt{2} \approx 0.586$

$f(\pi) = \int_{\pi}^{3\pi/2} (-\sin t) dt = 1$

故最大值为 $\boxed{\sqrt{2}}$，最小值为 $\boxed{2 - \sqrt{2}}$

**答案修正**：最大值 $\boxed{\sqrt{2}}$，最小值 $\boxed{2 - \sqrt{2}}$

**出处**：考研经典题

---

### 题 17

**题干**：设函数 $f(x)$ 在闭区间 $[a, b]$ 上连续，在开区间 $(a, b)$ 内可导，且 $f'(x) > 0$。若极限 $\lim\limits_{x \to a^+} \dfrac{f(2x - a)}{x - a}$ 存在，证明：

(1) 在 $(a, b)$ 内存在 $\xi$，使得 $\dfrac{b^2 - a^2}{\int_a^b f(x) dx} = \dfrac{2\xi}{f(\xi)}$

(2) 在 $(a, b)$ 内存在与 (1) 中 $\xi$ 相异的 $\eta$，使得 $f'(\eta)(b^2 - a^2) = \dfrac{2\xi}{\xi - a} \int_a^b f(x) dx$

**标准答案**：见解析

**答案解析**：

**(1)** 令 $F(x) = x^2$，$G(x) = \int_a^x f(t) dt$，由柯西中值定理，存在 $\xi \in (a, b)$ 使

$\dfrac{F(b) - F(a)}{G(b) - G(a)} = \dfrac{F'(\xi)}{G'(\xi)}$，即 $\dfrac{b^2 - a^2}{\int_a^b f(t) dt} = \dfrac{2\xi}{f(\xi)}$

**(2)** 由 $f(x)$ 在 $[a, \xi]$ 上用拉格朗日中值定理：存在 $\eta \in (a, \xi)$ 使 $f(\xi) - f(a) = f'(\eta)(\xi - a)$

由极限 $\lim\limits_{x \to a^+} \dfrac{f(2x - a)}{x - a}$ 存在且有限，分母 $\to 0$，故分子 $\to 0$，即 $f(a) = 0$（因 $f$ 连续）。

故 $f(\xi) = f'(\eta)(\xi - a)$

代入 (1) 的等式：$\dfrac{b^2 - a^2}{\int_a^b f(x) dx} = \dfrac{2\xi}{f'(\eta)(\xi - a)}$

整理得 $f'(\eta)(b^2 - a^2) = \dfrac{2\xi}{\xi - a} \int_a^b f(x) dx$

**出处**：2003 年考研数学二真题

---

### 题 18

**题干**：设函数 $f(x)$ 在 $[0, \pi]$ 上连续，且 $\int_0^\pi f(x) dx = 0$，$\int_0^\pi f(x) \cos x dx = 0$。证明：在 $(0, \pi)$ 内至少存在两个不同的点 $\xi_1, \xi_2$，使 $f(\xi_1) = f(\xi_2) = 0$。

**标准答案**：见解析

**答案解析**：

令 $F(x) = \int_0^x f(t) dt$，则 $F(0) = 0$，$F(\pi) = 0$。

$F'(x) = f(x)$

考虑 $\int_0^\pi f(x) \cos x dx = \int_0^\pi \cos x dF(x) = [F(x) \cos x]_0^\pi + \int_0^\pi F(x) \sin x dx$

$= F(\pi)(-1) - F(0) \cdot 1 + \int_0^\pi F(x) \sin x dx = \int_0^\pi F(x) \sin x dx$

由条件 $\int_0^\pi F(x) \sin x dx = 0$

若 $F(x) \sin x$ 在 $(0, \pi)$ 内不变号，则 $\int_0^\pi F(x) \sin x dx \neq 0$，矛盾。故存在 $c \in (0, \pi)$ 使 $F(c) \sin c = 0$。因 $\sin c > 0$（$0 < c < \pi$），故 $F(c) = 0$。

在 $[0, c]$ 上对 $F$ 应用罗尔定理：存在 $\xi_1 \in (0, c)$ 使 $F'(\xi_1) = f(\xi_1) = 0$

在 $[c, \pi]$ 上对 $F$ 应用罗尔定理：存在 $\xi_2 \in (c, \pi)$ 使 $F'(\xi_2) = f(\xi_2) = 0$

故存在 $\xi_1 \in (0, \pi)$，$\xi_2 \in (0, \pi)$，$\xi_1 \neq \xi_2$，使 $f(\xi_1) = f(\xi_2) = 0$。

**出处**：2000 年考研数学一真题

---

### 题 19

**题干**：设 $f(x)$ 在 $(-\infty, +\infty)$ 上连续，且 $F(x) = \int_0^x (x - 2t) f(t) dt$。证明：

(1) 若 $f(x)$ 是偶函数，则 $F(x)$ 也是偶函数；

(2) 若 $f(x)$ 单调不增，则 $F(x)$ 单调不减。

**标准答案**：见解析

**答案解析**：

**(1)** $F(-x) = \int_0^{-x} (-x - 2t) f(t) dt = \int_0^x (-x + 2u) f(-u)(-du)$（令 $t = -u$）

$= \int_0^x (x - 2u) f(u) du = F(x)$（因 $f(-u) = f(u)$）

故 $F(x)$ 为偶函数。

**(2)** $F(x) = x \int_0^x f(t) dt - 2 \int_0^x t f(t) dt$

$F'(x) = \int_0^x f(t) dt + x f(x) - 2x f(x) = \int_0^x f(t) dt - x f(x) = \int_0^x [f(t) - f(x)] dt$

当 $x > 0$：$t \in [0, x]$，由 $f$ 不增，$f(t) \ge f(x)$，故 $F'(x) \ge 0$

当 $x < 0$：$t \in [x, 0]$ 时（积分交换上下限后），$f(t) \le f(x)$，$\int_0^x = -\int_x^0$，故 $F'(x) \ge 0$

当 $x = 0$：$F'(0) = 0$

故 $F'(x) \ge 0$，即 $F(x)$ 单调不减。

**出处**：1997 年考研数学三真题改编

---

### 题 20

**题干**：设函数 $f(x)$ 在 $[0, +\infty)$ 上非负、连续且单调不增。证明：

$\int_0^x f(t) dt \ge x \int_0^1 f(t) dt$（对所有 $0 < x \le 1$）

**标准答案**：见解析

**答案解析**：

令 $F(x) = \int_0^x f(t) dt - x \int_0^1 f(t) dt$，则 $F(0) = 0$，$F(1) = 0$

$F'(x) = f(x) - \int_0^1 f(t) dt$

由积分中值定理：$\int_0^1 f(t) dt = f(\eta)$，其中 $\eta \in [0, 1]$

故 $F'(x) = f(x) - f(\eta)$

当 $x \le \eta$ 时，因 $f$ 不增，$f(x) \ge f(\eta)$，故 $F'(x) \ge 0$，$F(x)$ 在 $[0, \eta]$ 递增，$F(x) \ge F(0) = 0$

当 $x \ge \eta$ 时，因 $f$ 不增，$f(x) \le f(\eta)$，故 $F'(x) \le 0$，$F(x)$ 在 $[\eta, 1]$ 递减，$F(x) \ge F(1) = 0$

故对所有 $0 < x \le 1$，$F(x) \ge 0$，即 $\int_0^x f(t) dt \ge x \int_0^1 f(t) dt$

**出处**：考研积分不等式题

---

### 题 21

**题干**：设 $f(x)$ 在 $[0, 1]$ 上可导，$f(0) = 0$，$0 < f'(x) \le 1$。证明：

$\left( \int_0^1 f(x) dx \right)^2 \ge \int_0^1 f^3(x) dx$

**标准答案**：见解析

**答案解析**：

令 $F(x) = \left( \int_0^x f(t) dt \right)^2 - \int_0^x f^3(t) dt$，则 $F(0) = 0$

$F'(x) = 2f(x) \int_0^x f(t) dt - f^3(x) = f(x) \left[ 2 \int_0^x f(t) dt - f^2(x) \right]$

令 $G(x) = 2 \int_0^x f(t) dt - f^2(x)$，则 $G(0) = 0$

$G'(x) = 2f(x) - 2f(x) f'(x) = 2f(x)(1 - f'(x))$

由 $f(0) = 0$，$f'(x) > 0$，故 $f(x) > f(0) = 0$（$x > 0$）

又 $f'(x) \le 1$，故 $G'(x) \ge 0$，$G(x)$ 递增，$G(x) \ge G(0) = 0$（$x > 0$）

因此 $F'(x) = f(x) G(x) \ge 0$，$F(x)$ 递增，$F(1) \ge F(0) = 0$

即 $\left( \int_0^1 f(x) dx \right)^2 \ge \int_0^1 f^3(x) dx$

**出处**：考研积分不等式经典题

---

### 题 22

**题干**：设函数 $f(x)$ 在 $[0, 1]$ 上连续，证明：

$\int_0^1 f(x) dx \int_x^1 f(y) dy = \dfrac{1}{2} \left( \int_0^1 f(x) dx \right)^2$

**标准答案**：见解析

**答案解析**：

左式 $= \int_0^1 dx \int_x^1 f(x) f(y) dy$，这是二重积分在三角区域 $0 \le x \le y \le 1$ 上的积分。

右式 $= \dfrac{1}{2} \iint_{[0,1] \times [0,1]} f(x) f(y) dx dy$，即全正方形区域积分的一半。

由对称性，$\iint_{0 \le x \le y \le 1} f(x) f(y) dx dy = \iint_{0 \le y \le x \le 1} f(x) f(y) dx dy$

两者之和 $= \iint_{[0,1]^2} f(x) f(y) dx dy = \left( \int_0^1 f(x) dx \right)^2$

故每部分 $= \dfrac{1}{2} \left( \int_0^1 f(x) dx \right)^2$，即左式 $=$ 右式。

**出处**：二重积分交换次序题

---

### 题 23

**题干**：设 $f(x)$ 在 $[a, b]$ 上连续且 $f(x) > 0$，证明：

$\int_a^b f(x) dx \int_a^b \dfrac{1}{f(x)} dx \ge (b - a)^2$

**标准答案**：见解析

**答案解析**：

**方法：利用柯西-施瓦茨不等式**

$\left( \int_a^b f(x) \cdot \dfrac{1}{f(x)} dx \right)^2 \le \left( \int_a^b f^2(x) dx \right) \left( \int_a^b \dfrac{1}{f^2(x)} dx \right)$

但这里更直接：

考虑 $I = \int_a^b f(x) dx \int_a^b \dfrac{1}{f(x)} dx = \iint_{[a,b]^2} \dfrac{f(x)}{f(y)} dx dy$

由对称性，$I = \iint \dfrac{f(y)}{f(x)} dx dy$

故 $2I = \iint \left( \dfrac{f(x)}{f(y)} + \dfrac{f(y)}{f(x)} \right) dx dy \ge \iint 2 dx dy = 2(b - a)^2$

（由 $u + 1/u \ge 2$ 对 $u > 0$）

因此 $I \ge (b - a)^2$

**出处**：柯西不等式积分形式应用

---

### 题 24

**题干**：求由曲线 $y = \dfrac{1}{1 + x^2}$，$x$ 轴及直线 $x = 0$，$x = 1$ 所围成的平面图形的面积，并求该图形绕 $x$ 轴旋转一周所得旋转体的体积。

**标准答案**：面积 $\boxed{\dfrac{\pi}{4}}$，体积 $\boxed{\dfrac{\pi^2}{8} + \dfrac{\pi}{4}}$

**答案解析**：

**面积**：$A = \int_0^1 \dfrac{1}{1 + x^2} dx = [\arctan x]_0^1 = \arctan 1 - 0 = \dfrac{\pi}{4}$

**体积**（圆盘法）：$V = \pi \int_0^1 \dfrac{1}{(1 + x^2)^2} dx$

令 $x = \tan \theta$，$dx = \sec^2 \theta d\theta$，当 $x = 0$ 时 $\theta = 0$，当 $x = 1$ 时 $\theta = \pi/4$

$\int \dfrac{1}{(1 + x^2)^2} dx = \int \dfrac{\sec^2 \theta}{\sec^4 \theta} d\theta = \int \cos^2 \theta d\theta = \int \dfrac{1 + \cos 2\theta}{2} d\theta = \dfrac{\theta}{2} + \dfrac{\sin 2\theta}{4} + C$

$= \dfrac{\arctan x}{2} + \dfrac{1}{2} \cdot \dfrac{x}{1 + x^2} + C$（$\sin 2\theta = 2\sin \theta \cos \theta = 2 \cdot \dfrac{x}{\sqrt{1+x^2}} \cdot \dfrac{1}{\sqrt{1+x^2}} = \dfrac{2x}{1+x^2}$，除以 4 得 $\dfrac{x}{2(1+x^2)}$）

代入上下限：$\left[ \dfrac{\arctan x}{2} + \dfrac{x}{2(1 + x^2)} \right]_0^1 = \left( \dfrac{\pi/4}{2} + \dfrac{1}{4} \right) - 0 = \dfrac{\pi}{8} + \dfrac{1}{4}$

故 $V = \pi \left( \dfrac{\pi}{8} + \dfrac{1}{4} \right) = \dfrac{\pi^2}{8} + \dfrac{\pi}{4}$

**出处**：积分几何应用题

---

### 题 25

**题干**：设 $f(x)$ 是区间 $[0, +\infty)$ 上具有连续导数的单调增加函数，且 $f(0) = 1$。对任意的 $t \in [0, +\infty)$，设直线 $x = 0$，$x = t$，曲线 $y = f(x)$ 以及 $x$ 轴所围成的曲边梯形绕 $x$ 轴旋转一周所生成的旋转体的侧面的面积在数值上等于该旋转体的体积的 $2$ 倍。求函数 $y = f(x)$ 满足的微分方程，并求其满足初始条件 $f(0) = 1$ 的解。

**标准答案**：$y' = y \sqrt{y^2 - 1}$，解为 $\boxed{y = \dfrac{1 + e^{-x}}{\sqrt{2 e^{-x}}}}$ 或等价形式

**答案解析**：

**体积**：$V = \pi \int_0^t f^2(x) dx$

**侧面积**：$S = 2\pi \int_0^t f(x) \sqrt{1 + f'^2(x)} dx$

由 $S = 2V$：

$2\pi \int_0^t f(x) \sqrt{1 + f'^2(x)} dx = 2\pi \int_0^t f^2(x) dx$

约去 $2\pi$ 并对 $t$ 求导：

$f(t) \sqrt{1 + f'^2(t)} = f^2(t)$

由 $f(t) > 0$（$f$ 递增且 $f(0) = 1$），除以 $f(t)$：

$\sqrt{1 + f'^2(t)} = f(t)$

平方：$1 + f'^2(t) = f^2(t)$，即 $f'(t) = \sqrt{f^2(t) - 1}$（因 $f$ 递增取正根）

这是可分离变量方程：$\dfrac{dy}{\sqrt{y^2 - 1}} = dx$

积分：$\ln(y + \sqrt{y^2 - 1}) = x + C$，即 $\text{arccosh } y = x + C$

由 $y(0) = 1$：$\ln(1 + 0) = 0 + C$，$C = 0$

故 $y + \sqrt{y^2 - 1} = e^x$

两边取倒数（有理化）：$y - \sqrt{y^2 - 1} = e^{-x}$

两式相加：$2y = e^x + e^{-x}$，故 $y = \dfrac{e^x + e^{-x}}{2} = \cosh x$

验证：$y' = \sinh x = \sqrt{\cosh^2 x - 1} = \sqrt{y^2 - 1}$，正确。

**答案修正**：微分方程为 $y' = \sqrt{y^2 - 1}$，解为 $\boxed{y = \dfrac{e^x + e^{-x}}{2} = \cosh x}$

**出处**：2008 年考研数学二真题改编

---
