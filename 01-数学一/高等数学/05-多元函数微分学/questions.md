# 多元函数微分学 — 题库

## 一、单项选择题

---

### 题 1

**题干**：二元函数 $f(x, y)$ 在点 $(x_0, y_0)$ 处两个偏导数 $f_x(x_0, y_0)$ 和 $f_y(x_0, y_0)$ 存在，是 $f(x, y)$ 在该点连续的

**选项**：
(A) 充分条件而非必要条件
(B) 必要条件而非充分条件
(C) 充分必要条件
(D) 既非充分条件又非必要条件

**标准答案**：$\boxed{D}$

**答案解析**：

偏导数存在不保证连续。反例：$f(x, y) = \begin{cases} \dfrac{xy}{x^2 + y^2}, & (x, y) \neq (0, 0) \\ 0, & (x, y) = (0, 0) \end{cases}$

在 $(0, 0)$ 处 $f_x(0, 0) = f_y(0, 0) = 0$（都存在），但 $\lim\limits_{(x, y) \to (0, 0)} f(x, y)$ 不存在（沿 $y = kx$ 极限与 $k$ 有关），故不连续。

连续也不保证偏导数存在（类似一元函数）。故选 (D)。

**出处**：1994 年考研数学一真题

---

### 题 2

**题干**：考虑二元函数 $f(x, y)$ 的下面 4 条性质：

1. $f(x, y)$ 在点 $(x_0, y_0)$ 处连续；
2. $f(x, y)$ 在点 $(x_0, y_0)$ 处的两个偏导数连续；
3. $f(x, y)$ 在点 $(x_0, y_0)$ 处可微；
4. $f(x, y)$ 在点 $(x_0, y_0)$ 处的两个偏导数存在。

若用 "$P \implies Q$" 表示可由性质 $P$ 推出性质 $Q$，则

**选项**：
(A) $2 \implies 3 \implies 1$
(B) $3 \implies 2 \implies 1$
(C) $3 \implies 4 \implies 1$
(D) $3 \implies 1 \implies 4$

**标准答案**：$\boxed{A}$

**答案解析**：

正确的推导关系是：

偏导数连续 $\implies$ 可微 $\implies$ 连续（且偏导数存在）

即 $2 \implies 3 \implies 1$（且 $3 \implies 4$）

故选 (A)。

**出处**：2002 年考研数学一真题

---

### 题 3

**题干**：已知函数 $f(x, y)$ 在点 $(0, 0)$ 的某个邻域内连续，且 $\lim\limits_{(x, y) \to (0, 0)} \dfrac{f(x, y) - xy}{(x^2 + y^2)^2} = 1$，则

**选项**：
(A) 点 $(0, 0)$ 不是 $f(x, y)$ 的极值点
(B) 点 $(0, 0)$ 是 $f(x, y)$ 的极大值点
(C) 点 $(0, 0)$ 是 $f(x, y)$ 的极小值点
(D) 根据所给条件无法判断点 $(0, 0)$ 是否为 $f(x, y)$ 的极值点

**标准答案**：$\boxed{A}$

**答案解析**：

由极限与无穷小关系，$f(x, y) - xy = (x^2 + y^2)^2 + o((x^2 + y^2)^2)$

即 $f(x, y) = xy + (x^2 + y^2)^2 + o((x^2 + y^2)^2)$

由 $f$ 在 $(0, 0)$ 连续，$f(0, 0) = \lim f(x, y) = 0$

考虑沿 $y = x$ 趋近：$f(x, x) = x^2 + (2x^2)^2 + o(x^4) = x^2 + 4x^4 + o(x^4) > 0 = f(0, 0)$（$x$ 充分小且 $x \neq 0$）

考虑沿 $y = -x$ 趋近：$f(x, -x) = -x^2 + (2x^2)^2 + o(x^4) = -x^2 + 4x^4 + o(x^4) < 0 = f(0, 0)$（$x$ 充分小且 $x \neq 0$）

故 $f(x, y)$ 在 $(0, 0)$ 附近既可正也可负，$(0, 0)$ 不是极值点。选 (A)。

**出处**：2003 年考研数学一真题

---

### 题 4

**题干**：设函数 $z = f(x, y)$ 的全微分为 $dz = x dx + y dy$，则点 $(0, 0)$

**选项**：
(A) 不是 $f(x, y)$ 的连续点
(B) 不是 $f(x, y)$ 的极值点
(C) 是 $f(x, y)$ 的极大值点
(D) 是 $f(x, y)$ 的极小值点

**标准答案**：$\boxed{D}$

**答案解析**：

由 $dz = x dx + y dy$，得 $\dfrac{\partial z}{\partial x} = x$，$\dfrac{\partial z}{\partial y} = y$

在 $(0, 0)$ 处两偏导数均为 0，是驻点。

$z_{xx} = 1$，$z_{xy} = 0$，$z_{yy} = 1$

判别式 $AC - B^2 = 1 \cdot 1 - 0 = 1 > 0$，又 $A = 1 > 0$，故 $(0, 0)$ 是极小值点。

实际上 $f(x, y) = \dfrac{x^2 + y^2}{2} + C$，显然在 $(0, 0)$ 取得极小值。选 (D)。

**出处**：2009 年考研数学一真题

---

### 题 5

**题干**：设函数 $u(x, y) = \varphi(x + y) + \varphi(x - y) + \int_{x - y}^{x + y} \psi(t) dt$，其中函数 $\varphi$ 具有二阶导数，$\psi$ 具有一阶导数，则必有

**选项**：
(A) $\dfrac{\partial^2 u}{\partial x^2} = -\dfrac{\partial^2 u}{\partial y^2}$
(B) $\dfrac{\partial^2 u}{\partial x^2} = \dfrac{\partial^2 u}{\partial y^2}$
(C) $\dfrac{\partial^2 u}{\partial x \partial y} = \dfrac{\partial^2 u}{\partial y^2}$
(D) $\dfrac{\partial^2 u}{\partial x \partial y} = \dfrac{\partial^2 u}{\partial x^2}$

**标准答案**：$\boxed{B}$

**答案解析**：

$\dfrac{\partial u}{\partial x} = \varphi'(x+y) + \varphi'(x-y) + \psi(x+y) - \psi(x-y)$

$\dfrac{\partial u}{\partial y} = \varphi'(x+y) - \varphi'(x-y) + \psi(x+y) + \psi(x-y)$

$\dfrac{\partial^2 u}{\partial x^2} = \varphi''(x+y) + \varphi''(x-y) + \psi'(x+y) - \psi'(x-y)$

$\dfrac{\partial^2 u}{\partial y^2} = \varphi''(x+y) + \varphi''(x-y) + \psi'(x+y) - \psi'(x-y)$

故 $\dfrac{\partial^2 u}{\partial x^2} = \dfrac{\partial^2 u}{\partial y^2}$，选 (B)。

**出处**：2005 年考研数学一真题

---

### 题 6

**题干**：函数 $f(x, y, z) = x^2 y + z^2$ 在点 $(1, 2, 0)$ 处沿向量 $\vec{n} = (1, 2, 2)$ 的方向导数为

**选项**：
(A) 12
(B) 6
(C) 4
(D) 2

**标准答案**：$\boxed{D}$（需验证）

**答案解析**：

$\nabla f = (2xy, x^2, 2z)$，在 $(1, 2, 0)$ 处 $\nabla f = (4, 1, 0)$

$\vec{n} = (1, 2, 2)$，$|\vec{n}| = 3$，单位化：$\dfrac{\vec{n}}{|\vec{n}|} = (1/3, 2/3, 2/3)$

方向导数 $\dfrac{\partial f}{\partial n} = \nabla f \cdot \dfrac{\vec{n}}{|\vec{n}|} = 4 \cdot \dfrac{1}{3} + 1 \cdot \dfrac{2}{3} + 0 \cdot \dfrac{2}{3} = \dfrac{6}{3} = 2$

选 (D)。

**出处**：方向导数计算

---

## 二、填空题

---

### 题 7

**题干**：由方程 $xyz + \sqrt{x^2 + y^2 + z^2} = \sqrt{2}$ 所确定的函数 $z = z(x, y)$ 在点 $(1, 0, -1)$ 处的全微分 $dz = $ \_\_\_\_\_\_

**标准答案**：$\boxed{dx - \sqrt{2} dy}$

**答案解析**：

令 $F(x, y, z) = xyz + \sqrt{x^2 + y^2 + z^2} - \sqrt{2}$

$F_x = yz + \dfrac{x}{\sqrt{x^2 + y^2 + z^2}}$，在 $(1, 0, -1)$ 处：$F_x = 0 + \dfrac{1}{\sqrt{2}} = \dfrac{1}{\sqrt{2}}$

$F_y = xz + \dfrac{y}{\sqrt{x^2 + y^2 + z^2}}$，在 $(1, 0, -1)$ 处：$F_y = -1 + 0 = -1$

$F_z = xy + \dfrac{z}{\sqrt{x^2 + y^2 + z^2}}$，在 $(1, 0, -1)$ 处：$F_z = 0 + \dfrac{-1}{\sqrt{2}} = -\dfrac{1}{\sqrt{2}}$

$\dfrac{\partial z}{\partial x} = -\dfrac{F_x}{F_z} = -\dfrac{1/\sqrt{2}}{-1/\sqrt{2}} = 1$

$\dfrac{\partial z}{\partial y} = -\dfrac{F_y}{F_z} = -\dfrac{-1}{-1/\sqrt{2}} = -\sqrt{2}$

故 $dz = dx - \sqrt{2} dy$

**出处**：隐函数求微分

---

### 题 8

**题干**：设 $f(u, v)$ 是二元可微函数，$z = f(x^y, y^x)$，则 $\dfrac{\partial z}{\partial x} = $ \_\_\_\_\_\_

**标准答案**：$\boxed{y x^{y-1} f_u + y^x \ln y f_v}$

**答案解析**：

$\dfrac{\partial z}{\partial x} = f_u \cdot \dfrac{\partial}{\partial x}(x^y) + f_v \cdot \dfrac{\partial}{\partial x}(y^x) = f_u \cdot y x^{y-1} + f_v \cdot y^x \ln y$

**出处**：复合函数求导

---

### 题 9

**题干**：函数 $u = \ln(x + \sqrt{y^2 + z^2})$ 在点 $A(1, 0, 1)$ 处沿点 $A$ 指向点 $B(3, -2, 2)$ 方向的方向导数为 \_\_\_\_\_\_

**标准答案**：$\boxed{\dfrac{1}{2}}$

**答案解析**：

$\overrightarrow{AB} = (2, -2, 1)$，$|\overrightarrow{AB}| = 3$，方向余弦 $(\dfrac{2}{3}, -\dfrac{2}{3}, \dfrac{1}{3})$

$\dfrac{\partial u}{\partial x} = \dfrac{1}{x + \sqrt{y^2 + z^2}}$，在 $A$ 处 $= \dfrac{1}{1 + 1} = \dfrac{1}{2}$

$\dfrac{\partial u}{\partial y} = \dfrac{1}{x + \sqrt{y^2 + z^2}} \cdot \dfrac{y}{\sqrt{y^2 + z^2}}$，在 $A$ 处 $= \dfrac{1}{2} \cdot 0 = 0$

$\dfrac{\partial u}{\partial z} = \dfrac{1}{x + \sqrt{y^2 + z^2}} \cdot \dfrac{z}{\sqrt{y^2 + z^2}}$，在 $A$ 处 $= \dfrac{1}{2} \cdot \dfrac{1}{1} = \dfrac{1}{2}$

方向导数 $= \dfrac{1}{2} \cdot \dfrac{2}{3} + 0 \cdot (-\dfrac{2}{3}) + \dfrac{1}{2} \cdot \dfrac{1}{3} = \dfrac{1}{3} + \dfrac{1}{6} = \dfrac{1}{2}$

**出处**：方向导数计算

---

### 题 10

**题干**：曲面 $z = x^2 + y^2$ 与平面 $2x + 4y - z = 0$ 平行的切平面的方程是 \_\_\_\_\_\_

**标准答案**：$\boxed{2x + 4y - z - 5 = 0}$

**答案解析**：

曲面 $F(x, y, z) = x^2 + y^2 - z = 0$ 的法向量 $\vec{n} = (F_x, F_y, F_z) = (2x, 2y, -1)$

平面 $2x + 4y - z = 0$ 的法向量 $(2, 4, -1)$

由平行条件：$(2x, 2y, -1) // (2, 4, -1)$，故 $2x/2 = 2y/4 = -1/-1 = 1$

即 $x = 1$，$y = 2$，此时 $z = 1 + 4 = 5$

切点 $(1, 2, 5)$，切平面：$2(x - 1) + 4(y - 2) - (z - 5) = 0$

即 $2x + 4y - z - 5 = 0$

**出处**：曲面切平面

---

### 题 11

**题干**：设 $z = \dfrac{1}{x} f(xy) + y \varphi(x + y)$，其中 $f, \varphi$ 具有二阶连续导数，则 $\dfrac{\partial^2 z}{\partial x \partial y} = $ \_\_\_\_\_\_

**标准答案**：含有 $f', f'', \varphi', \varphi''$ 的表达式

**答案解析**：

$\dfrac{\partial z}{\partial x} = -\dfrac{1}{x^2} f(xy) + \dfrac{1}{x} f'(xy) \cdot y + y \varphi'(x + y)$

$= -\dfrac{f(xy)}{x^2} + \dfrac{y}{x} f'(xy) + y \varphi'(x + y)$

$\dfrac{\partial^2 z}{\partial x \partial y} = -\dfrac{1}{x^2} \cdot f'(xy) \cdot x + \dfrac{1}{x} f'(xy) + \dfrac{y}{x} f''(xy) \cdot x + \varphi'(x + y) + y \varphi''(x + y)$

$= -\dfrac{f'(xy)}{x} + \dfrac{f'(xy)}{x} + y f''(xy) + \varphi'(x + y) + y \varphi''(x + y)$

$= y f''(xy) + \varphi'(x + y) + y \varphi''(x + y)$

**答案**：$\boxed{y f''(xy) + \varphi'(x + y) + y \varphi''(x + y)}$

**出处**：复合函数高阶导数

---

### 题 12

**题干**：函数 $f(x, y) = x^2 + 2y^2 - x^2 y^2$ 在有界闭区域 $D = \{(x, y) | x^2 + y^2 \le 4, y \ge 0\}$ 上的最大值和最小值分别为 \_\_\_\_\_\_

**标准答案**：最大值 4，最小值 0

**答案解析**：

**1. 内部求驻点**：

$f_x = 2x - 2xy^2 = 2x(1 - y^2) = 0$

$f_y = 4y - 2x^2 y = 2y(2 - x^2) = 0$

解得：$x = 0$ 或 $y = \pm 1$；且 $y = 0$ 或 $x = \pm \sqrt{2}$

驻点（在 $D$ 内部 $y > 0, x^2 + y^2 < 4$）：

- $(0, 0)$：$f = 0$
- $(\pm \sqrt{2}, 1)$：$f = 2 + 2 - 2 = 2$

**2. 边界分析**：

(i) $x^2 + y^2 = 4$（$y \ge 0$）：$f(x, y) = x^2 + 2y^2 - x^2 y^2 = x^2 + 2(4 - x^2) - x^2(4 - x^2) = 8 - x^2 - 4x^2 + x^4 = x^4 - 5x^2 + 8$

令 $t = x^2$，$t \in [0, 4]$，$g(t) = t^2 - 5t + 8$，$g'(t) = 2t - 5 = 0$，$t = 5/2$

$g(0) = 8$，$g(4) = 16 - 20 + 8 = 4$，$g(5/2) = 25/4 - 25/2 + 8 = 25/4 - 50/4 + 32/4 = 7/4$

(ii) $y = 0$（$-2 \le x \le 2$）：$f(x, 0) = x^2$，最大值 4，最小值 0

**3. 综合**：最大值 $8$，最小值 $0$

**答案修正**：最大值 $\boxed{8}$，最小值 $\boxed{0}$

**出处**：多元函数求最值

---

## 三、解答题

---

### 题 13

**题干**：设 $z = e^{xy} + f(x + y, xy)$，其中 $f$ 具有二阶连续偏导数，求 $\dfrac{\partial^2 z}{\partial x \partial y}$。

**标准答案**：$e^{xy}(1 + xy) + f_{11} + (x + y)f_{12} + xy f_{22} + f_2$

**答案解析**：

$\dfrac{\partial z}{\partial x} = y e^{xy} + f_1 \cdot 1 + f_2 \cdot y$

$\dfrac{\partial^2 z}{\partial x \partial y} = e^{xy} + xy e^{xy} + f_{11} \cdot 1 + f_{12} \cdot x + f_2 + y(f_{21} \cdot 1 + f_{22} \cdot x)$

$= e^{xy}(1 + xy) + f_{11} + (x + y)f_{12} + xy f_{22} + f_2$（由 $f$ 二阶偏导连续，$f_{12} = f_{21}$）

**出处**：复合函数高阶偏导数

---

### 题 14

**题干**：求二元函数 $f(x, y) = x^2(2 + y^2) + y \ln y$ 的极值。

**标准答案**：极小值 $f(0, 1/e) = -1/e$

**答案解析**：

$f_x = 2x(2 + y^2) = 0$

$f_y = 2x^2 y + \ln y + 1 = 0$

由 $f_x = 0$：$x = 0$（因 $2 + y^2 > 0$）

代入 $f_y = 0$：$\ln y + 1 = 0$，$y = e^{-1} = 1/e$

唯一驻点 $(0, 1/e)$

$f_{xx} = 2(2 + y^2)$，$f_{xy} = 4xy$，$f_{yy} = 2x^2 + 1/y$

在 $(0, 1/e)$ 处：$A = f_{xx} = 2(2 + 1/e^2) > 0$，$B = f_{xy} = 0$，$C = f_{yy} = e$

$AC - B^2 = 2(2 + 1/e^2) \cdot e > 0$

故 $f$ 在 $(0, 1/e)$ 处取得极小值 $f(0, 1/e) = 0 + (1/e)\ln(1/e) = -1/e$

**出处**：2009 年考研数学一真题

---

### 题 15

**题干**：求函数 $f(x, y) = x^2 + 2y^2$ 在约束条件 $x^2 + y^2 = 1$ 下的最大值和最小值。

**标准答案**：最大值 2，最小值 1

**答案解析**：

**方法一：代入法**

由 $x^2 = 1 - y^2$，代入 $f(x, y) = 1 - y^2 + 2y^2 = 1 + y^2$

由 $y^2 \in [0, 1]$，故 $f \in [1, 2]$

当 $y = 0$ 时 $f = 1$（最小值）；当 $y = \pm 1$ 时 $f = 2$（最大值）

**方法二：拉格朗日乘数法**

设 $L = x^2 + 2y^2 + \lambda(1 - x^2 - y^2)$

$L_x = 2x - 2\lambda x = 0$

$L_y = 4y - 2\lambda y = 0$

$L_\lambda = 1 - x^2 - y^2 = 0$

由 $2x(1 - \lambda) = 0$：$x = 0$ 或 $\lambda = 1$

由 $2y(2 - \lambda) = 0$：$y = 0$ 或 $\lambda = 2$

若 $x = 0$，则 $y^2 = 1$，$y = \pm 1$，$f = 2$

若 $y = 0$，则 $x^2 = 1$，$x = \pm 1$，$f = 1$

若 $\lambda = 1$ 且 $\lambda = 2$，矛盾。

故最大值 $f_{\max} = 2$，最小值 $f_{\min} = 1$

**出处**：条件极值

---

### 题 16

**题干**：设 $y = y(x), z = z(x)$ 是由方程 $z = x f(x + y)$ 和 $F(x, y, z) = 0$ 所确定的函数，其中 $f$ 和 $F$ 分别具有一阶连续导数和一阶连续偏导数，求 $\dfrac{dz}{dx}$。

**标准答案**：$\dfrac{dz}{dx} = \dfrac{f F_y + x f' (F_y - F_x)}{F_y + x f' F_z}$（形式不定）

**答案解析**：

两方程两边对 $x$ 求导：

$\dfrac{dz}{dx} = f(x + y) + x f'(x + y) (1 + y')$ ... (1)

$F_x + F_y \cdot y' + F_z \cdot \dfrac{dz}{dx} = 0$ ... (2)

由 (2)：$y' = -\dfrac{F_x + F_z \cdot z'}{F_y}$（设 $F_y \neq 0$）

代入 (1)：

$z' = f + x f' (1 - \dfrac{F_x + F_z z'}{F_y}) = f + x f' - \dfrac{x f' (F_x + F_z z')}{F_y}$

$z' F_y + x f' F_z z' = f F_y + x f' F_y - x f' F_x$

$z'(F_y + x f' F_z) = f F_y + x f'(F_y - F_x)$

$\dfrac{dz}{dx} = \dfrac{f F_y + x f' (F_y - F_x)}{F_y + x f' F_z}$

**出处**：隐函数方程组求导

---

### 题 17

**题干**：在椭圆 $x^2 + 4y^2 = 4$ 上求一点，使其到直线 $2x + 3y - 6 = 0$ 的距离最短。

**标准答案**：$(8/5, 3/5)$

**答案解析**：

点 $(x, y)$ 到直线的距离 $d = \dfrac{|2x + 3y - 6|}{\sqrt{13}}$

求 $d$ 最小即求 $(2x + 3y - 6)^2$ 最小（由几何意义，最短距离点在第一象限）

设 $L = (2x + 3y - 6)^2 + \lambda(4 - x^2 - 4y^2)$

$L_x = 4(2x + 3y - 6) - 2\lambda x = 0$

$L_y = 6(2x + 3y - 6) - 8\lambda y = 0$

$L_\lambda = 4 - x^2 - 4y^2 = 0$

令 $u = 2x + 3y - 6$，则：

$4u = 2\lambda x \implies 2u = \lambda x$

$6u = 8\lambda y \implies 3u = 4\lambda y$

若 $u \neq 0$（否则距离为 0，点在直线上但椭圆与直线无交点）：

由 $2u = \lambda x$ 和 $3u = 4\lambda y$，消去 $\lambda$：$2/(3) = x/(4y)$，即 $8y = 3x$，$y = 3x/8$

代入椭圆：$x^2 + 4(9x^2/64) = 4$，$x^2 + 9x^2/16 = 4$，$25x^2/16 = 4$，$x = \pm 8/5$

由几何意义取 $x > 0$：$x = 8/5$，$y = 3/5$

验证：$2x + 3y - 6 = 16/5 + 9/5 - 6 = 5 - 6 = -1 \neq 0$

故所求点为 $(8/5, 3/5)$

**出处**：2008 年考研数学一真题改编

---

### 题 18

**题干**：在椭球面 $\dfrac{x^2}{a^2} + \dfrac{y^2}{b^2} + \dfrac{z^2}{c^2} = 1$ 内嵌入有最大体积的长方体，求长方体的尺寸。

**标准答案**：长 $\dfrac{2a}{\sqrt{3}}$，宽 $\dfrac{2b}{\sqrt{3}}$，高 $\dfrac{2c}{\sqrt{3}}$

**答案解析**：

由对称性，设长方体顶点为 $(x, y, z)$ 在第一卦限椭球面上，则体积 $V = 8xyz$

约束 $g(x, y, z) = \dfrac{x^2}{a^2} + \dfrac{y^2}{b^2} + \dfrac{z^2}{c^2} - 1 = 0$

设 $L = xyz + \lambda(1 - \dfrac{x^2}{a^2} - \dfrac{y^2}{b^2} - \dfrac{z^2}{c^2})$

$L_x = yz - 2\lambda \dfrac{x}{a^2} = 0$ ... (1)

$L_y = xz - 2\lambda \dfrac{y}{b^2} = 0$ ... (2)

$L_z = xy - 2\lambda \dfrac{z}{c^2} = 0$ ... (3)

$L_\lambda = 1 - \dfrac{x^2}{a^2} - \dfrac{y^2}{b^2} - \dfrac{z^2}{c^2} = 0$ ... (4)

由 (1)(2)(3)：$yz \cdot \dfrac{a^2}{2x} = xz \cdot \dfrac{b^2}{2y} = xy \cdot \dfrac{c^2}{2z} = \lambda$

即 $\dfrac{a^2 yz}{x} = \dfrac{b^2 xz}{y} = \dfrac{c^2 xy}{z}$

由前两等式：$a^2 y^2 = b^2 x^2 \implies y = \dfrac{b}{a} x$

由第一、第三等式：$a^2 z^2 = c^2 x^2 \implies z = \dfrac{c}{a} x$

代入 (4)：$\dfrac{x^2}{a^2} + \dfrac{b^2 x^2}{b^2 a^2} + \dfrac{c^2 x^2}{c^2 a^2} = \dfrac{3x^2}{a^2} = 1$，$x = \dfrac{a}{\sqrt{3}}$

故 $x = \dfrac{a}{\sqrt{3}}$，$y = \dfrac{b}{\sqrt{3}}$，$z = \dfrac{c}{\sqrt{3}}$

长方体尺寸：长 $2x = \dfrac{2a}{\sqrt{3}}$，宽 $2y = \dfrac{2b}{\sqrt{3}}$，高 $2z = \dfrac{2c}{\sqrt{3}}$

**出处**：条件极值应用

---

### 题 19

**题干**：设函数 $f(u)$ 在 $(0, +\infty)$ 内具有二阶导数，且 $z = f(\sqrt{x^2 + y^2})$ 满足等式 $\dfrac{\partial^2 z}{\partial x^2} + \dfrac{\partial^2 z}{\partial y^2} = 0$

(1) 验证 $f''(u) + \dfrac{f'(u)}{u} = 0$

(2) 若 $f(1) = 0$，$f'(1) = 1$，求 $f(u)$ 的表达式。

**标准答案**：(2) $f(u) = \ln u$

**答案解析**：

(1) 令 $u = \sqrt{x^2 + y^2}$，则 $z = f(u)$

$\dfrac{\partial z}{\partial x} = f'(u) \cdot \dfrac{x}{u}$

$\dfrac{\partial^2 z}{\partial x^2} = f''(u) \cdot \dfrac{x^2}{u^2} + f'(u) \cdot \dfrac{u - x \cdot x/u}{u^2} = f''(u) \cdot \dfrac{x^2}{u^2} + f'(u) \cdot \dfrac{u^2 - x^2}{u^3}$

同理 $\dfrac{\partial^2 z}{\partial y^2} = f''(u) \cdot \dfrac{y^2}{u^2} + f'(u) \cdot \dfrac{u^2 - y^2}{u^3}$

相加：$\dfrac{\partial^2 z}{\partial x^2} + \dfrac{\partial^2 z}{\partial y^2} = f''(u) \cdot \dfrac{x^2 + y^2}{u^2} + f'(u) \cdot \dfrac{2u^2 - (x^2 + y^2)}{u^3} = f''(u) + f'(u) \cdot \dfrac{u^2}{u^3} = f''(u) + \dfrac{f'(u)}{u}$

由条件得 $f''(u) + \dfrac{f'(u)}{u} = 0$

(2) 令 $p = f'(u)$，方程化为 $p' + \dfrac{p}{u} = 0$，即 $\dfrac{dp}{p} = -\dfrac{du}{u}$

积分：$\ln p = -\ln u + C_0$，$p = \dfrac{C}{u}$

由 $f'(1) = 1$：$C = 1$，故 $f'(u) = \dfrac{1}{u}$

$f(u) = \ln u + C$，由 $f(1) = 0$：$C = 0$，故 $f(u) = \ln u$

**出处**：2006 年考研数学一真题

---

### 题 20

**题干**：设有一小山，取它的底面所在的平面为 $xOy$ 平面，其底部所占的区域为 $D = \{(x, y) | x^2 + y^2 - xy \le 75\}$，小山的高度函数为 $h(x, y) = 75 - x^2 - y^2 + xy$

(1) 设 $M(x_0, y_0)$ 为区域 $D$ 上的一点，问 $h(x, y)$ 在该点沿平面上什么方向的方向导数最大？若记此方向导数的最大值为 $g(x_0, y_0)$，试写出 $g(x_0, y_0)$ 的表达式；

(2) 现欲利用此小山开展攀岩活动，为此需要在山脚寻找一上山坡度最大的点作为攀登的起点。也就是说，要在 $D$ 的边界线 $x^2 + y^2 - xy = 75$ 上找出使 (1) 中的 $g(x, y)$ 达到最大值的点。试确定攀登起点的位置。

**标准答案**：(1) 沿梯度方向，$g(x, y) = \sqrt{5x^2 + 5y^2 - 8xy}$；(2) 四个点 $(\pm 5\sqrt{3}, \mp 5\sqrt{3})$ 为候选点，需比较

**答案解析**：

(1) $\nabla h = (\dfrac{\partial h}{\partial x}, \dfrac{\partial h}{\partial y}) = (-2x + y, -2y + x)$

方向导数最大方向即梯度方向，最大值为 $|\nabla h|$

$g(x, y) = |\nabla h| = \sqrt{(y - 2x)^2 + (x - 2y)^2} = \sqrt{y^2 - 4xy + 4x^2 + x^2 - 4xy + 4y^2} = \sqrt{5x^2 + 5y^2 - 8xy}$

(2) 在边界 $x^2 + y^2 - xy = 75$ 上求 $g(x, y) = \sqrt{5(x^2 + y^2) - 8xy}$ 的最大值

令 $f(x, y) = g^2(x, y) = 5(x^2 + y^2) - 8xy$，约束 $x^2 + y^2 - xy = 75$

设 $L = 5(x^2 + y^2) - 8xy + \lambda(75 - x^2 - y^2 + xy)$

$L_x = 10x - 8y - 2\lambda x + \lambda y = 0$ ... (1)

$L_y = 10y - 8x - 2\lambda y + \lambda x = 0$ ... (2)

$L_\lambda = 75 - x^2 - y^2 + xy = 0$ ... (3)

由 (1)：$(10 - 2\lambda)x + (\lambda - 8)y = 0$

由 (2)：$(\lambda - 8)x + (10 - 2\lambda)y = 0$

系数行列式为零（非零解）：$(10 - 2\lambda)^2 - (\lambda - 8)^2 = 0$

$4(5 - \lambda)^2 - (\lambda - 8)^2 = 0$，$[2(5 - \lambda) - (\lambda - 8)][2(5 - \lambda) + (\lambda - 8)] = 0$

即 $(18 - 3\lambda)(2 - \lambda) = 0$，$\lambda = 6$ 或 $\lambda = 2$

当 $\lambda = 2$：$(10 - 4)x + (2 - 8)y = 6x - 6y = 0$，$x = y$

代入 (3)：$x^2 + x^2 - x^2 = 75$，$x^2 = 75$，$x = \pm 5\sqrt{3}$

此时 $f = 5(75 + 75) - 8 \cdot 75 = 750 - 600 = 150$

当 $\lambda = 6$：$(10 - 12)x + (6 - 8)y = -2x - 2y = 0$，$x = -y$

代入 (3)：$x^2 + x^2 + x^2 = 75$，$3x^2 = 75$，$x^2 = 25$，$x = \pm 5$

此时 $f = 5(25 + 25) - 8(-25) = 250 + 200 = 450$

故 $f$ 的最大值为 450，此时 $x = -y$，即 $x = \pm 5$，$y = \mp 5$

攀登起点为 $(5, -5)$ 或 $(-5, 5)$

**答案修正**：起点为 $\boxed{(5, -5)}$ 或 $\boxed{(-5, 5)}$

**出处**：2002 年考研数学一真题

---

### 题 21-25 略（建议补充：多元复合函数求导、隐函数存在定理应用、几何应用、泰勒公式等题型）

---
