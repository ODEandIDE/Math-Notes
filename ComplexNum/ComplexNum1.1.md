# 复变函数与积分变换

[TOC]

## 第1章 复数与复平面

### 1.1 复数定义

$$
z = x + iy,\quad x\in\mathbb{R},\; y\in\mathbb{R},\; i^2 = -1
$$
*(Complex number)*

实部与虚部：

$$
\operatorname{Re}z = x,\qquad \operatorname{Im}z = y
$$
*(Real part, Imaginary part)*

$$
z = \operatorname{Re}z + i\operatorname{Im}z
$$

### 1.2 复数域

设 $z_1 = x_1+iy_1$，$z_2 = x_2+iy_2$，则

$$
z_1 \pm z_2 \in \mathbb{C},\quad z_1\cdot z_2 \in \mathbb{C},\quad \frac{z_1}{z_2}\in\mathbb{C}\;(z_2\neq0)
$$

### 1.3 模与共轭

$$
|z| = \sqrt{x^2+y^2},\qquad \overline{z} = x - iy
$$
*(Modulus, Complex conjugate)*

$$
|z|^2 = z \cdot \overline{z}
$$

复数相等：

$$
z_1 = z_2 \iff x_1=x_2,\; y_1=y_2
$$

### 1.4 不等式

$$
|x|\le|z|,\quad |y|\le|z|
$$

三角不等式（Triangle inequality）：

$$
\bigl||z_1|-|z_2|\bigr| \le |z_1+z_2| \le |z_1|+|z_2|
$$

### 1.5 实部虚部与共轭的关系

$$
\operatorname{Re}z = \frac{z+\overline{z}}{2},\qquad \operatorname{Im}z = \frac{z-\overline{z}}{2i}
$$

### 2. 复平面与辐角

复数 $z=x+iy$ 对应复平面上点 $(x,y)$。

极坐标表示（Polar form）：

$$
x = \rho\cos\theta,\quad y = \rho\sin\theta,\quad \rho = |z| = \sqrt{x^2+y^2}
$$

辐角 $\theta = \arg z$（Argument），有无穷多个值（相差 $2\pi$ 整数倍）。

主辐角（Principal argument）记为 $\operatorname{Arg}z$，通常取 $-\pi < \operatorname{Arg}z \le \pi$。

## 第2章 欧拉公式与复数运算

### 2.1 欧拉公式（Euler's formula）

$$
e^{i\theta} = \cos\theta + i\sin\theta
$$

由此，复数可表示为指数形式（Exponential form）：

$$
z = x+iy = \rho e^{i\theta}
$$

### 2.2 四则运算

加减法：

$$
z_1 \pm z_2 = (x_1\pm x_2) + i(y_1\pm y_2)
$$

乘法：

$$
z_1 z_2 = (x_1x_2 - y_1y_2) + i(x_1y_2 + x_2y_1) = \rho_1\rho_2 e^{i(\theta_1+\theta_2)}
$$

除法（$z_2\neq0$）：

$$
\frac{z_1}{z_2} = \frac{x_1x_2 + y_1y_2}{x_2^2+y_2^2} + i\frac{x_2y_1 - x_1y_2}{x_2^2+y_2^2} = \frac{\rho_1}{\rho_2} e^{i(\theta_1-\theta_2)}
$$

### 2.3 乘方与开方

棣莫弗公式（De Moivre's formula）：

$$
(e^{i\theta})^n = e^{in\theta} = \cos n\theta + i\sin n\theta
$$

乘方（Power）：

$$
z^n = \rho^n e^{in\theta} = \rho^n(\cos n\theta + i\sin n\theta)
$$

开方（Root）：解 $w^n = z$（$z\neq0$）。设 $z = \rho e^{i\theta}$，$w = r e^{i\varphi}$，则

$$
r^n = \rho,\quad n\varphi = \theta + 2k\pi,\; k\in\mathbb{Z}
$$

于是

$$
r = \rho^{1/n},\quad \varphi = \frac{\theta+2k\pi}{n},\quad k=0,1,\dots,n-1
$$

共有 $n$ 个不同的 $n$ 次根。

### 2.4 共轭性质

$$
\overline{\overline{z}} = z,\quad \overline{z_1\pm z_2} = \overline{z_1}\pm\overline{z_2},\quad \overline{z_1z_2} = \overline{z_1}\cdot\overline{z_2}
$$

$$
\overline{\left(\frac{z_1}{z_2}\right)} = \frac{\overline{z_1}}{\overline{z_2}},\quad \overline{\rho e^{i\theta}} = \rho e^{-i\theta}
$$

$$
|z|^2 = z\overline{z}
$$

## 第3章 复平面的拓扑与曲线

### 3.1 邻域（Neighbourhood）

- **$\rho$-邻域**：$N_\rho(z_0) = \{z \in \mathbb{C} : |z-z_0| < \rho\}$

- **去心 $\rho$-邻域**（Deleted neighbourhood）：$N_\rho^\circ(z_0) = \{0 < |z-z_0| < \rho\}$

### 3.2 内点、开集、边界点

设 $E \subseteq \mathbb{C}$，$z_0 \in \mathbb{C}$。

- **内点（Interior point）**：若 $\exists \rho>0$ 使得 $N_\rho(z_0) \subseteq E$，则称 $z_0$ 为 $E$ 的内点。

- **开集（Open set）**：若 $E$ 中每一点都是 $E$ 的内点，则称 $E$ 为开集。

- **边界点（Boundary point）**：若对任意 $\rho>0$，$N_\rho(z_0)$ 既包含 $E$ 的点也包含 $E^c$ 的点，则称 $z_0$ 为 $E$ 的边界点。$E$ 的全体边界点称为边界 $\partial E$。

### 3.3 连通性与区域

- **连通集（Connected set）**：若 $E$ 不能表示为两个非空不相交开集的并，则称 $E$ 是连通的。等价地，$E$ 中任意两点可用一条连续曲线连接。

- **区域（Region / Domain）**：连通的开集称为区域。

- **闭区域（Closed region）**：区域与其边界的并集称为闭区域。

### 3.4 曲线（Curves）

设 $z(t) = x(t) + iy(t)$，$t \in [a,b]$。

- **连续曲线（Continuous curve）**：$x(t), y(t)$ 连续。

- **简单曲线（Simple curve / Jordan curve）**：无自交点的连续曲线，即若 $t_1 \neq t_2$，则 $z(t_1) \neq z(t_2)$（端点除外）。

- **光滑曲线（Smooth curve）**：$x'(t), y'(t)$ 连续且不同时为零。

- **分段光滑曲线（Piecewise smooth curve）**：有限条光滑曲线首尾相接而成。

### 3.5 单连通与多连通区域

- **单连通区域（Simply connected domain）**：区域 $D$ 内任意一条简单闭曲线所围成的内部仍完全包含在 $D$ 中（即无“洞”）。

- **多连通区域（Multiply connected domain）**：不是单连通的区域（有洞）。

### 3.6 黎曼球与无穷远点（Riemann sphere and point at infinity）

通过球极投影，复平面与球面（去掉北极）一一对应。北极对应**无穷远点** $\infty$，扩充复平面 $\mathbb{C}\cup\{\infty\}$ 与球面同胚（双射且双向连续）。

## 第4章 复变函数

### 4.1 定义

设 $D \subseteq \mathbb{C}$ 为非空集合。若存在法则 $f$ 使得对每个 $z \in D$，有唯一的 $w \in \mathbb{C}$ 与之对应，则称 $f$ 为定义在 $D$ 上的**复变函数**（Complex function），记作

$$
w = f(z),\quad z \in D
$$

令 $z = x+iy$，$w = u+iv$，则

$$
f(z) = u(x,y) + i v(x,y)
$$

其中 $u(x,y) = \operatorname{Re}f(z)$，$v(x,y) = \operatorname{Im}f(z)$ 是二元实值函数。

### 4.2 单值函数与多值函数

- **单值函数（Single-valued function）**：每个 $z \in D$ 对应唯一的 $w$，如 $w = z^2$。

- **多值函数（Multi-valued function）**：一个 $z$ 可能对应多个 $w$，如 $w = \sqrt{z}$，$w = \ln z$。多值函数通常通过分支切割和黎曼面处理。

## 第5章 复变函数的极限

### 5.1 $\varepsilon$-$\delta$ 定义

设 $f(z)$ 在 $z_0$ 的某去心邻域内有定义。若存在复数 $w_0$ 使得

$$
\forall \varepsilon > 0,\; \exists \delta > 0,\; 0 < |z-z_0| < \delta \;\Longrightarrow\; |f(z)-w_0| < \varepsilon
$$

则称当 $z \to z_0$ 时 $f(z)$ 的极限为 $w_0$，记作 $\displaystyle\lim_{z\to z_0} f(z) = w_0$。
*(Limit of a complex function)*

### 5.2 极限与实部虚部的关系

设 $f(z)=u(x,y)+iv(x,y)$，$z_0=x_0+iy_0$，$A=a+ib$，则

$$
\lim_{z\to z_0} f(z) = A \quad\iff\quad 
\lim_{(x,y)\to(x_0,y_0)} u(x,y)=a \;\text{且}\; \lim_{(x,y)\to(x_0,y_0)} v(x,y)=b
$$

### 5.3 四则运算法则

若 $\lim_{z\to z_0} f(z)=A$，$\lim_{z\to z_0} g(z)=B$，则

- $\lim (f\pm g) = A \pm B$

- $\lim (f\cdot g) = A\cdot B$

- $\lim (f/g) = A/B$（$B \neq 0$）

## 第6章 复变函数的连续性

### 6.1 定义

若 $\displaystyle\lim_{z\to z_0} f(z) = f(z_0)$，则称 $f$ 在 $z_0$ 处连续（Continuous at $z_0$）。

若 $f$ 在区域 $D$ 内每一点都连续，则称 $f$ 在 $D$ 内连续。

### 6.2 连续性判别

$f(z)=u(x,y)+iv(x,y)$ 在 $z_0=x_0+iy_0$ 处连续当且仅当 $u(x,y)$ 与 $v(x,y)$ 都在 $(x_0,y_0)$ 处连续。

### 6.3 有界闭集上连续函数的性质

设 $E$ 为有界闭集（如有界闭区域或闭曲线），$f(z)$ 在 $E$ 上连续，则

- **有界性（Boundedness）**：存在 $M>0$ 使得 $|f(z)|\le M$ 对所有 $z\in E$ 成立。

- **最值定理（Extreme value theorem）**：$|f(z)|$ 在 $E$ 上达到最大值与最小值。

- **一致连续性（Uniform continuity）**：对任意 $\varepsilon>0$，存在 $\delta>0$，使得当 $z_1,z_2\in E$ 且 $|z_1-z_2|<\delta$ 时，$|f(z_1)-f(z_2)|<\varepsilon$

## 第7章 导数与微分

### 7.1 导数的定义

**一元实函数导数**：

$$
f'(x) = \lim_{\Delta x \to 0} \frac{f(x+\Delta x) - f(x)}{\Delta x}
$$
*(Derivative of real function)*

**复变函数导数**：

设 $f(z)$ 在包含 $z_0$ 的某区域 $D$ 内有定义。若极限

$$
\lim_{\Delta z \to 0} \frac{f(z_0+\Delta z) - f(z_0)}{\Delta z}
$$
*(Complex derivative)*

存在（与 $\Delta z \to 0$ 的方式无关），则称 $f$ 在 $z_0$ 处可导，导数为

$$
f'(z_0) = \lim_{\Delta z \to 0} \frac{f(z_0+\Delta z) - f(z_0)}{\Delta z}
$$

### 7.2 微分

复变函数的微分定义为 $dw = f'(z) dz$，可导 $\iff$ 微分存在。

求导法则与实函数完全相同（线性、乘积、商、链式、反函数）。

---

## 第8章 解析函数

**解析**：$f(z)$ 在 $z_0$ 处可导，且存在 $\rho>0$ 使得在 $N_\rho(z_0)$ 内处处可导，则称 $f$ 在 $z_0$ 解析。若在区域 $D$ 内每点解析，则称 $f$ 在 $D$ 内解析。
*(Analytic / Holomorphic function)*

**奇点**：$z_0$ 处不解析，但任意邻域内存在解析点。
*(Singularity)*

---

## 第9章 柯西-黎曼方程（完整证明）

### 9.1 定理陈述

设 $f(z) = u(x,y) + i v(x,y)$ 定义在区域 $D$ 内，$z_0 = x_0+iy_0 \in D$。则 $f$ 在 $z_0$ 处可导的**充要条件**是：

1. $u(x,y)$ 与 $v(x,y)$ 在 $(x_0,y_0)$ 处**可微**（即全微分存在）；
2. 在 $(x_0,y_0)$ 处满足柯西-黎曼方程：

$$
\frac{\partial u}{\partial x} = \frac{\partial v}{\partial y}, \qquad \frac{\partial u}{\partial y} = -\frac{\partial v}{\partial x}. \tag{9.1}
$$
*(Cauchy-Riemann equations)*

此时导数可表示为

$$
f'(z_0) = \frac{\partial u}{\partial x} + i \frac{\partial v}{\partial x} = \frac{\partial v}{\partial y} - i \frac{\partial u}{\partial y}. \tag{9.2}
$$

### 9.2 必要性证明（可导 $\Rightarrow$ C-R 方程且可微）

假设 $f'(z_0)$ 存在，记 $A = f'(z_0) = a + i b$（$a,b \in \mathbb{R}$）。由导数定义：

$$
\lim_{\Delta z \to 0} \frac{f(z_0+\Delta z) - f(z_0)}{\Delta z} = A.
$$

记 $\Delta z = \Delta x + i \Delta y$，$\Delta f = f(z_0+\Delta z) - f(z_0) = \Delta u + i \Delta v$，则

$$
\frac{\Delta u + i \Delta v}{\Delta x + i \Delta y} = A + \varepsilon(\Delta z),
$$

其中 $\varepsilon(\Delta z) \to 0$ 当 $\Delta z \to 0$。于是

$$
\Delta u + i \Delta v = (a+ib)(\Delta x + i \Delta y) + \varepsilon(\Delta z)(\Delta x + i \Delta y).
$$

记 $\varepsilon(\Delta z) = \varepsilon_1 + i \varepsilon_2$，则 $\varepsilon_1, \varepsilon_2 \to 0$ 且

$$
\Delta u + i \Delta v = a\Delta x - b\Delta y + i(b\Delta x + a\Delta y) + (\varepsilon_1+i\varepsilon_2)(\Delta x + i \Delta y).
$$

展开最后一项：$(\varepsilon_1 \Delta x - \varepsilon_2 \Delta y) + i(\varepsilon_1 \Delta y + \varepsilon_2 \Delta x)$。合并实部虚部：

$$
\Delta u = a\Delta x - b\Delta y + \varepsilon_1 \Delta x - \varepsilon_2 \Delta y,
$$
$$
\Delta v = b\Delta x + a\Delta y + \varepsilon_1 \Delta y + \varepsilon_2 \Delta x.
$$

由于 $\varepsilon_1, \varepsilon_2 \to 0$，右边 $\varepsilon_1 \Delta x - \varepsilon_2 \Delta y = o(|\Delta z|)$（因为 $|\varepsilon_1 \Delta x| \le |\varepsilon_1| |\Delta z|$，同理 $\varepsilon_2 \Delta y$）。同理第二式中的余项也是 $o(|\Delta z|)$。因此

$$
\Delta u = a\Delta x - b\Delta y + o(|\Delta z|),\quad
\Delta v = b\Delta x + a\Delta y + o(|\Delta z|).
$$

这表明 $u$ 和 $v$ 在 $(x_0,y_0)$ 处可微（全微分存在），且

$$
\frac{\partial u}{\partial x} = a,\quad \frac{\partial u}{\partial y} = -b,\quad
\frac{\partial v}{\partial x} = b,\quad \frac{\partial v}{\partial y} = a.
$$

直接比较得

$$
\frac{\partial u}{\partial x} = \frac{\partial v}{\partial y},\qquad \frac{\partial u}{\partial y} = -\frac{\partial v}{\partial x}.
$$

必要性证毕。

### 9.3 充分性证明（C-R 方程 + 可微 $\Rightarrow$ 可导）

假设 $u,v$ 在 $(x_0,y_0)$ 处可微，且满足 C-R 方程。由可微性：

$$
\Delta u = \frac{\partial u}{\partial x} \Delta x + \frac{\partial u}{\partial y} \Delta y + o_1(|\Delta z|),
$$
$$
\Delta v = \frac{\partial v}{\partial x} \Delta x + \frac{\partial v}{\partial y} \Delta y + o_2(|\Delta z|),
$$

其中 $o_1, o_2$ 是比 $|\Delta z|$ 高阶的无穷小。利用 C-R 方程：设 $\frac{\partial u}{\partial x} = \frac{\partial v}{\partial y} = p$，$\frac{\partial u}{\partial y} = -\frac{\partial v}{\partial x} = q$，则 $\frac{\partial v}{\partial x} = -q$，$\frac{\partial v}{\partial y} = p$。代入：

$$
\Delta u = p \Delta x + q \Delta y + o_1,
$$
$$
\Delta v = (-q) \Delta x + p \Delta y + o_2.
$$

构造 $\Delta f = \Delta u + i \Delta v$：

$$
\Delta f = (p \Delta x + q \Delta y) + i(-q \Delta x + p \Delta y) + (o_1 + i o_2).
$$

计算 $(p - i q)(\Delta x + i \Delta y) = p\Delta x + i p \Delta y - i q \Delta x - i^2 q \Delta y = (p\Delta x + q \Delta y) + i(p \Delta y - q \Delta x)$。

这与上式括号内完全一致，因为 $i(p \Delta y - q \Delta x) = i p \Delta y - i q \Delta x = i(-q \Delta x + p \Delta y)$。所以

$$
\Delta f = (p - i q) \Delta z + o(|\Delta z|).
$$

于是

$$
\frac{\Delta f}{\Delta z} = p - i q + \frac{o(|\Delta z|)}{\Delta z}.
$$

当 $\Delta z \to 0$，余项趋于 0，故极限存在且为 $p - i q$。因此 $f'(z_0) = p - i q$。由 C-R 方程，$p = \frac{\partial u}{\partial x}$，$q = \frac{\partial u}{\partial y}$，且 $p - i q = \frac{\partial u}{\partial x} - i \frac{\partial u}{\partial y}$。又因为 $\frac{\partial v}{\partial x} = -q$，$\frac{\partial v}{\partial y} = p$，也可写为 $f'(z_0) = \frac{\partial v}{\partial y} - i \frac{\partial u}{\partial y}$。统一形式：

$$
f'(z_0) = \frac{\partial u}{\partial x} + i \frac{\partial v}{\partial x} = \frac{\partial v}{\partial y} - i \frac{\partial u}{\partial y}. \tag{9.3}
$$

充分性证毕。

### 9.4 补充说明

如果 $u,v$ 的四个偏导数在 $(x_0,y_0)$ 处存在且连续，则 $u,v$ 必然可微，此时 C-R 条件即为充要条件。该推论常用于判断解析性。

---

## 第10章 调和函数

### 10.1 定义与推导

设 $f(z)=u+iv$ 解析，则 $u,v$ 满足 C-R 方程。假设 $u,v$ 具有二阶连续偏导，则对 C-R 方程分别求导：

$$
\frac{\partial^2 u}{\partial x^2} = \frac{\partial}{\partial x} \left( \frac{\partial v}{\partial y} \right) = \frac{\partial^2 v}{\partial x \partial y},
$$

$$
\frac{\partial^2 u}{\partial y^2} = \frac{\partial}{\partial y} \left( -\frac{\partial v}{\partial x} \right) = -\frac{\partial^2 v}{\partial y \partial x}.
$$

由于二阶混合偏导可交换（$C^2$ 保证），$\frac{\partial^2 v}{\partial x \partial y} = \frac{\partial^2 v}{\partial y \partial x}$，相加得

$$
\frac{\partial^2 u}{\partial x^2} + \frac{\partial^2 u}{\partial y^2} = 0.
$$
*(Laplace's equation for u)*

同理对 $v$ 也满足 Laplace 方程。满足 $\Delta \phi = 0$ 的函数称为**调和函数**（*Harmonic function*）。此时 $v$ 称为 $u$ 的**共轭调和函数**（*Conjugate harmonic function*）。

### 10.2 已知 $u$ 求 $v$（通过 C-R 方程积分）

例：$u = x^2 - y^2$，则 $\frac{\partial u}{\partial x}=2x$，$\frac{\partial u}{\partial y}=-2y$。由 C-R 方程：$\frac{\partial v}{\partial y} = \frac{\partial u}{\partial x}=2x$，$\frac{\partial v}{\partial x} = -\frac{\partial u}{\partial y}=2y$。对第一式积分 $v = 2xy + \varphi(x)$，代入第二式得 $2y + \varphi'(x) = 2y$，故 $\varphi'(x)=0$，$\varphi(x)=C$。所以 $v = 2xy + C$，解析函数 $f(z)= (x^2-y^2) + i(2xy+C) = z^2 + iC$。

---

## 第11章 初等解析函数

### 11.1 指数函数 $e^z$

定义：$e^z = e^x(\cos y + i \sin y)$。
*(Exponential function)*

验证 C-R 方程：$u=e^x \cos y$，$v=e^x \sin y$。则 $u_x = e^x \cos y$，$u_y = -e^x \sin y$；$v_x = e^x \sin y$，$v_y = e^x \cos y$。显然 $u_x = v_y$，$u_y = -v_x$，且偏导连续，故 $e^z$ 在全平面解析，且

$$
(e^z)' = u_x + i v_x = e^x \cos y + i e^x \sin y = e^z.
$$

### 11.2 三角函数

定义：
$$
\sin z = \frac{e^{iz}-e^{-iz}}{2i},\qquad \cos z = \frac{e^{iz}+e^{-iz}}{2}.
$$
*(Sine and cosine of complex variable)*

直接求导：

$$
(\sin z)' = \frac{i e^{iz} - (-i)e^{-iz}}{2i} = \frac{i(e^{iz}+e^{-iz})}{2i} = \frac{e^{iz}+e^{-iz}}{2} = \cos z.
$$

同理 $(\cos z)' = -\sin z$。

所有三角恒等式可由指数形式推导，例如：

$$
\sin^2 z + \cos^2 z = \left(\frac{e^{iz}-e^{-iz}}{2i}\right)^2 + \left(\frac{e^{iz}+e^{-iz}}{2}\right)^2 = \frac{-(e^{2iz}-2+e^{-2iz}) + (e^{2iz}+2+e^{-2iz})}{4} = 1.
$$
*(Pythagorean identity)*

### 11.3 双曲函数

定义：
$$
\sinh z = \frac{e^z - e^{-z}}{2},\qquad \cosh z = \frac{e^z + e^{-z}}{2}.
$$
*(Hyperbolic sine and cosine)*

求导：

$$
(\sinh z)' = \frac{e^z + e^{-z}}{2} = \cosh z,\quad (\cosh z)' = \sinh z.
$$

关系 $\sin(iz) = i \sinh z$ 直接由定义验证：

$$
\sin(iz) = \frac{e^{i(iz)}-e^{-i(iz)}}{2i} = \frac{e^{-z}-e^{z}}{2i} = i \frac{e^{z}-e^{-z}}{2} = i \sinh z.
$$

### 11.4 对数函数

定义 $w = \operatorname{Ln} z$ 为 $e^w = z$ 的解。
*(Complex logarithm)*

设 $z = \rho e^{i\theta}$，则

$$
w = \ln \rho + i(\theta + 2k\pi),\quad k\in\mathbb{Z}.
$$

主值 $\ln z = \ln|z| + i \operatorname{Arg} z$，其中 $-\pi < \operatorname{Arg} z \le \pi$。

求导：由反函数求导法则，$ (\ln z)' = \frac{1}{z} $（除负实轴和原点外）。推导：令 $w = \ln z$，则 $e^w = z$，两边对 $z$ 求导得 $e^w \frac{dw}{dz} = 1$，所以 $\frac{dw}{dz} = e^{-w} = 1/z$。

### 11.5 一般幂函数

定义：
$$
z^\alpha = e^{\alpha \ln z},\quad \alpha \in \mathbb{C}.
$$
*(General power function)*

- 当 $\alpha = n$（整数）时，$z^n$ 单值。
- 当 $\alpha = p/q$（既约有理数）时，$z^{p/q}$ 有 $q$ 个分支，多值。
- 当 $\alpha$ 为无理数或虚数时，无穷多值。

导数（在主值分支上，且 $z \neq 0$）：

$$
(z^\alpha)' = \alpha z^{\alpha-1}.
$$

---

## 第12章 复变函数积分

### 12.1 原函数与不定积分

**定义（原函数）**：设 $F(z)$ 在区域 $D$ 内可导，且对任意 $z\in D$ 有 $F'(z) = f(z)$，则称 $F(z)$ 为 $f(z)$ 在 $D$ 内的一个**原函数**（*Primitive / Antiderivative*）。

**定义（不定积分）**：$f(z)$ 的所有原函数构成的集合称为不定积分：

$$
\int f(z)\,dz = F(z) + C,\quad C\in\mathbb{C}.
$$
*(Indefinite integral)*

**基本初等函数的不定积分**（形式上与实函数一致，但注意定义域与多值性）：

1. $\displaystyle\int e^z\,dz = e^z + C$  （指数函数，全平面解析）
2. $\displaystyle\int z^n\,dz = \frac{z^{n+1}}{n+1} + C,\quad n\in\mathbb{C},\,n\neq -1$  
   （幂函数，在去掉原点的单连通区域内成立）
3. $\displaystyle\int \frac{1}{z}\,dz = \operatorname{Ln} z + C = \ln|z| + i\arg z + 2k\pi i + C$  
   （*Logarithmic integral*，多值函数，主值分支记为 $\ln z$）
4. $\displaystyle\int \cos z\,dz = \sin z + C$
5. $\displaystyle\int \sin z\,dz = -\cos z + C$
6. $\displaystyle\int \sec^2 z\,dz = \tan z + C$
7. $\displaystyle\int \csc^2 z\,dz = -\cot z + C$
8. $\displaystyle\int \sinh z\,dz = \cosh z + C$
9. $\displaystyle\int \cosh z\,dz = \sinh z + C$

注：在复变中，$\int z^n dz$ 当 $n$ 不是整数时一般涉及多值函数，需指定单值分支。特别地，$\int \frac{1}{z} dz$ 的结果 $\operatorname{Ln} z$ 是多值的，其主值 $\ln z$ 在除去负实轴和原点的区域上解析，且 $(\ln z)' = 1/z$。

---

### 12.2 复积分的定义（定积分）

设 $C$ 是一条以 $z_0$ 为起点、$z$ 为终点的简单光滑曲线，$f(z)$ 在 $C$ 上有界。将 $C$ 依次分点为 $z_0, z_1, z_2, \dots, z_{n-1}, z_n = z$ 分成 $n$ 个小弧段，在每一弧段 $[z_{k-1}, z_k]$ 上任取一点 $\xi_k$，作和式

$$
S_n = \sum_{k=1}^{n} f(\xi_k)(z_k - z_{k-1}).
$$

记 $\lambda = \max\limits_{1\le k\le n} |z_k - z_{k-1}|$（弧段的最大长度）。若当 $n\to\infty$ 且 $\lambda\to 0$ 时，$S_n$ 的极限存在且与分法及 $\xi_k$ 的取法无关，则称该极限为 $f(z)$ 沿曲线 $C$（从 $z_0$ 到 $z$）的**积分**，记为

$$
\int_C f(z)\,dz = \lim_{\lambda\to 0}\sum_{k=1}^{n} f(\xi_k)(z_k - z_{k-1}).
$$
*(Complex line integral)*

规定：若 $C$ 是闭曲线，则积分记为 $\oint_C f(z)\,dz$，通常取逆时针方向为正方向。

---

### 12.3 复积分的计算方法

#### 12.3.1 化为第二类曲线积分

设 $f(z)=u(x,y)+iv(x,y)$，$dz = dx + i\,dy$，则

$$
\int_C f(z)\,dz = \int_C (u+iv)(dx+i\,dy)
= \int_C (u\,dx - v\,dy) + i\int_C (v\,dx + u\,dy).
$$
*(Conversion to real line integrals)*

#### 12.3.2 参数化方法

若曲线 $C$ 的参数方程为 $z = z(t) = x(t) + iy(t)$，$t\in[\alpha,\beta]$，且 $z'(t)$ 连续且不为零（光滑），则

$$
\int_C f(z)\,dz = \int_\alpha^\beta f(z(t))\,z'(t)\,dt.
$$
*(Parametrization formula)*

这是因为 $dz = z'(t)dt$，且 $f(z(t))$ 是复合函数。

---

### 12.4 复积分的性质

设 $C$ 为可求长曲线，$f,g$ 可积，则：

1. **线性性**：$\displaystyle\int_C [af(z) + bg(z)]\,dz = a\int_C f(z)\,dz + b\int_C g(z)\,dz$，$a,b\in\mathbb{C}$。
2. **路径可加性**：若 $C = C_1 + C_2 + \cdots + C_n$（首尾相接），则
   $\displaystyle\int_C f(z)\,dz = \int_{C_1} f(z)\,dz + \cdots + \int_{C_n} f(z)\,dz$。
3. **反向性**：$\displaystyle\int_{C^-} f(z)\,dz = -\int_C f(z)\,dz$，其中 $C^-$ 是 $C$ 的反向曲线。
4. **模不等式**（*Estimation lemma*）：
   $$
   \left|\int_C f(z)\,dz\right| \le \int_C |f(z)|\,|dz| = \int_C |f(z)|\,ds,
   $$
   其中 $ds$ 是弧长微元。特别地，若 $|f(z)|\le M$ 在 $C$ 上，$L$ 为 $C$ 的弧长，则
   $$
   \left|\int_C f(z)\,dz\right| \le M L.
   $$

---

### 12.5 柯西积分定理（Cauchy's Integral Theorem）

**定理**：设 $C$ 是一条简单正向（逆时针）闭曲线，$D$ 是以 $C$ 为边界的有限闭区域。若 $f(z)$ 在 $D$ 上解析，且 $f'(z)$ 在 $D$ 上连续（注：该条件可去掉，见 Goursat 引理），则

$$
\oint_C f(z)\,dz = 0. \tag{12.1}
$$
*(Cauchy's Integral Theorem)*

**证明（利用格林公式，需要 $f'$ 连续）**：

设 $f(z)=u+iv$，则

$$
\oint_C f(z)\,dz = \oint_C (u\,dx - v\,dy) + i\oint_C (v\,dx + u\,dy).
$$

对两个实积分分别应用格林公式（*Green's theorem*）：

$$
\oint_C P\,dx + Q\,dy = \iint_D \left( \frac{\partial Q}{\partial x} - \frac{\partial P}{\partial y} \right) dx\,dy.
$$

对于第一项 $\oint_C (u\,dx - v\,dy)$，视 $P=u$，$Q=-v$，则

$$
\frac{\partial Q}{\partial x} - \frac{\partial P}{\partial y} = \frac{\partial(-v)}{\partial x} - \frac{\partial u}{\partial y} = -\frac{\partial v}{\partial x} - \frac{\partial u}{\partial y}.
$$

对于第二项 $\oint_C (v\,dx + u\,dy)$，视 $P=v$，$Q=u$，则

$$
\frac{\partial Q}{\partial x} - \frac{\partial P}{\partial y} = \frac{\partial u}{\partial x} - \frac{\partial v}{\partial y}.
$$

于是

$$
\oint_C f(z)\,dz = \iint_D \left( -\frac{\partial v}{\partial x} - \frac{\partial u}{\partial y} \right) dx\,dy \;+\; i \iint_D \left( \frac{\partial u}{\partial x} - \frac{\partial v}{\partial y} \right) dx\,dy.
$$

由 $f$ 解析，满足柯西-黎曼方程 $\frac{\partial u}{\partial x} = \frac{\partial v}{\partial y}$，$\frac{\partial u}{\partial y} = -\frac{\partial v}{\partial x}$，代入得两个被积函数均为零，故积分值为零。$\square$

> 注：Goursat 证明了连续性条件可以去掉，即只要 $f$ 在 $D$ 内解析（可导），定理即成立。

---

### 12.6 柯西定理的重要推论

#### 12.6.1 原函数的存在性

若 $f(z)$ 在单连通区域 $D$ 内解析，则对任意 $z_0\in D$，函数

$$
F(z) = \int_{z_0}^z f(\zeta)\,d\zeta
$$
（积分路径取 $D$ 内任意从 $z_0$ 到 $z$ 的曲线）与路径无关，且 $F'(z)=f(z)$，即 $F(z)$ 是 $f(z)$ 的一个原函数。

**证明**：由柯西定理，对 $D$ 内任意两条从 $z_0$ 到 $z$ 的路径 $C_1, C_2$，有 $\int_{C_1} f\,dz - \int_{C_2} f\,dz = \oint_{C_1-C_2} f\,dz = 0$，故积分与路径无关。再直接计算导数：

$$
\frac{F(z+\Delta z)-F(z)}{\Delta z} = \frac{1}{\Delta z}\int_z^{z+\Delta z} f(\zeta)\,d\zeta \to f(z) \quad (\Delta z\to 0).
$$
详细极限过程略。$\square$

#### 12.6.2 牛顿-莱布尼茨公式（Newton-Leibniz formula）

若 $f(z)$ 在单连通区域 $D$ 内解析，$\Phi(z)$ 是 $f(z)$ 的任一原函数，则

$$
\int_{z_0}^{z_1} f(z)\,dz = \Phi(z_1) - \Phi(z_0). \tag{12.2}
$$

#### 12.6.3 积分路径无关性

在单连通解析区域内，积分 $\int_C f(z)\,dz$ 的值只依赖于起点和终点，与路径无关。等价地，沿任何闭曲线的积分为零。

---

### 12.7 典型例题

#### 例1 计算 $I = \oint_C \frac{dz}{(z-z_0)^n}$，其中 $C$ 是以 $z_0$ 为圆心、$r>0$ 为半径的正向圆周，$n\in\mathbb{Z}$

**解**：参数化 $C: z = z_0 + r e^{i\theta}$，$\theta:0\to 2\pi$，则 $dz = i r e^{i\theta}d\theta$。

$$
I = \int_0^{2\pi} \frac{i r e^{i\theta} d\theta}{(r e^{i\theta})^n}
   = \frac{i}{r^{n-1}} \int_0^{2\pi} e^{i(1-n)\theta} d\theta.
$$

- 当 $n=1$ 时，$e^{i(1-n)\theta}=e^{0}=1$，积分值为 $2\pi$，故 $I = \frac{i}{r^{0}}\cdot 2\pi = 2\pi i$。
- 当 $n\neq 1$ 时，$\int_0^{2\pi} e^{i(1-n)\theta} d\theta = \left.\frac{e^{i(1-n)\theta}}{i(1-n)}\right|_0^{2\pi} = 0$（因为 $e^{i(1-n)2\pi}=1$），故 $I = 0$。

因此

$$
\oint_{|z-z_0|=r} \frac{dz}{(z-z_0)^n} = 
\begin{cases}
2\pi i, & n=1,\\
0, & n\neq 1.
\end{cases}
$$

#### 例2 计算 $I = \oint_C \frac{dz}{(z-z_0)^n}$，其中 $C$ 是任意一条包含点 $z_0$ 在其内部的正向简单闭曲线

**解**（挖洞法）：由于被积函数在 $z_0$ 处不解析（奇点），我们以 $z_0$ 为圆心作一个小圆 $C_1$ 半径 $r$ 充分小，使 $C_1$ 完全位于 $C$ 的内部。在 $C$ 与 $C_1$ 之间的环形区域上，被积函数解析。由柯西定理，沿 $C$ 与 $C_1$ 的积分满足

$$
\oint_C \frac{dz}{(z-z_0)^n} = \oint_{C_1} \frac{dz}{(z-z_0)^n},
$$

其中 $C_1$ 取逆时针方向。由例1结论，右边当 $n=1$ 时为 $2\pi i$，当 $n\neq1$ 时为 $0$。故结果相同。

#### 例3 计算 $I = \oint_C \frac{2z-1}{z(z-1)}\,dz$，其中 $C$ 为椭圆 $\frac{x^2}{2}+y^2=1$（正向）

**解**：被积函数在 $z=0$ 和 $z=1$ 处有奇点，两者均在椭圆内部（因椭圆含原点及点 $(1,0)$）。先将函数分解为部分分式：

$$
\frac{2z-1}{z(z-1)} = \frac{1}{z} + \frac{1}{z-1}.
$$

验证：$ \frac{1}{z} + \frac{1}{z-1} = \frac{(z-1)+z}{z(z-1)} = \frac{2z-1}{z(z-1)}$。

由柯西定理的挖洞法，分别以 $0$ 和 $1$ 为心作小圆 $C_0, C_1$ 完全在 $C$ 内部且互不相交，则

$$
I = \oint_{C_0} \frac{1}{z}\,dz + \oint_{C_1} \frac{1}{z-1}\,dz.
$$

由例1（$n=1$），$\oint_{C_0} \frac{1}{z}\,dz = 2\pi i$；对第二个积分，令 $w = z-1$，则 $C_1$ 变为以 $0$ 为心的小圆，$\oint_{C_1} \frac{1}{z-1}\,dz = \oint_{|w|=r} \frac{1}{w}\,dw = 2\pi i$。

因此

$$
I = 2\pi i + 2\pi i = 4\pi i.
$$

---

## 第13章 柯西积分公式及其推论

### 13.1 Morera 定理（柯西积分逆定理）

**定理**（*Morera's theorem*）：设 $f(z)$ 在单连通区域 $D$ 内连续，且对 $D$ 内任意简单闭曲线 $C$ 有
$$
\oint_C f(z)\,dz = 0,
$$

则 $f(z)$ 在 $D$ 内解析。

**证明**：固定 $z_0\in D$，对于任意 $z\in D$，定义

$$
F(z) = \int_{z_0}^z f(\zeta)\,d\zeta,
$$

其中积分路径取 $D$ 内任意一条从 $z_0$ 到 $z$ 的曲线。由于沿任何闭曲线积分为零，该积分与路径无关，因此 $F(z)$ 是单值函数。下证 $F'(z)=f(z)$。

取 $\Delta z$ 充分小，使 $z+\Delta z\in D$。由积分与路径无关，有

$$
F(z+\Delta z)-F(z) = \int_z^{z+\Delta z} f(\zeta)\,d\zeta.
$$

将积分路径取为直线段，则

$$
\frac{F(z+\Delta z)-F(z)}{\Delta z} - f(z) = \frac{1}{\Delta z}\int_z^{z+\Delta z} [f(\zeta)-f(z)]\,d\zeta.
$$

由 $f$ 的连续性，对任意 $\varepsilon>0$，存在 $\delta>0$ 使得当 $|\zeta-z|<\delta$ 时 $|f(\zeta)-f(z)|<\varepsilon$。当 $|\Delta z|<\delta$ 时，直线段长度 $=|\Delta z|$，因此

$$
\left|\frac{F(z+\Delta z)-F(z)}{\Delta z} - f(z)\right| \le \frac{1}{|\Delta z|}\cdot \varepsilon\cdot |\Delta z| = \varepsilon.
$$

故极限为 $0$，即 $F'(z)=f(z)$。于是 $F$ 在 $D$ 内可导，从而 $F$ 解析。又 $f = F'$，解析函数的导数仍解析（见后文），因此 $f$ 在 $D$ 内解析。$\square$

---

### 13.2 柯西积分公式（Cauchy's Integral Formula）

**定理**：设 $C$ 是一条简单正向（逆时针）闭曲线，$D$ 是以 $C$ 为边界的有限区域。若 $f(z)$ 在 $\overline{D}=D\cup C$ 上解析，则对 $D$ 内任意一点 $z_0$，有

$$
f(z_0) = \frac{1}{2\pi i} \oint_C \frac{f(z)}{z-z_0}\,dz. \tag{13.1}
$$
*(Cauchy's integral formula)*

**证明**（利用挖洞法）：

由于 $f(z)/(z-z_0)$ 在 $z_0$ 处不解析，我们以 $z_0$ 为圆心作小圆周 $C_\rho: |z-z_0|=\rho$，取逆时针方向，使 $C_\rho$ 完全位于 $C$ 内部。在 $C$ 与 $C_\rho$ 之间的环形区域上，被积函数解析，由柯西定理有

$$
\oint_C \frac{f(z)}{z-z_0}\,dz = \oint_{C_\rho} \frac{f(z)}{z-z_0}\,dz.
$$

在 $C_\rho$ 上，设 $z = z_0 + \rho e^{i\theta}$，$\theta$ 从 $0$ 到 $2\pi$，则 $dz = i\rho e^{i\theta}d\theta$，$z-z_0 = \rho e^{i\theta}$，于是

$$
\oint_{C_\rho} \frac{f(z)}{z-z_0}\,dz = \int_0^{2\pi} \frac{f(z_0+\rho e^{i\theta})}{\rho e^{i\theta}} \cdot i\rho e^{i\theta} d\theta = i\int_0^{2\pi} f(z_0+\rho e^{i\theta})\,d\theta.
$$

因此

$$
\oint_C \frac{f(z)}{z-z_0}\,dz = i\int_0^{2\pi} f(z_0+\rho e^{i\theta})\,d\theta.
$$

令 $\rho\to 0$，由 $f$ 的连续性，$f(z_0+\rho e^{i\theta}) \to f(z_0)$ 一致（对 $\theta$），所以右边极限为 $i\cdot 2\pi f(z_0)$。左边与 $\rho$ 无关，故

$$
\oint_C \frac{f(z)}{z-z_0}\,dz = 2\pi i f(z_0).
$$

两边除以 $2\pi i$ 即得公式。$\square$

**第二种证法**（直接利用极限）：

考虑

$$
\oint_C \frac{f(z)}{z-z_0}\,dz - 2\pi i f(z_0) = \oint_C \frac{f(z)-f(z_0)}{z-z_0}\,dz,
$$

因为 $\oint_C \frac{f(z_0)}{z-z_0}\,dz = 2\pi i f(z_0)$（由 $\oint \frac{dz}{z-z_0}=2\pi i$）。对于小圆 $C_\rho$，有

$$
\oint_C \frac{f(z)-f(z_0)}{z-z_0}\,dz = \oint_{C_\rho} \frac{f(z)-f(z_0)}{z-z_0}\,dz.
$$

在 $C_\rho$ 上，$|z-z_0|=\rho$，且 $|f(z)-f(z_0)|<\varepsilon$ 当 $\rho$ 充分小时，于是

$$
\left|\oint_{C_\rho} \frac{f(z)-f(z_0)}{z-z_0}\,dz\right| \le \oint_{C_\rho} \frac{|f(z)-f(z_0)|}{|z-z_0|}\,|dz| \le \frac{\varepsilon}{\rho}\cdot 2\pi\rho = 2\pi\varepsilon.
$$

令 $\varepsilon\to 0$ 得该积分为零，故原积分等于 $2\pi i f(z_0)$。$\square$

**柯西积分中值定理**（平均值性质）：由上述证明过程中的 $i\int_0^{2\pi} f(z_0+\rho e^{i\theta})d\theta = 2\pi i f(z_0)$ 可得

$$
\frac{1}{2\pi}\int_0^{2\pi} f(z_0+\rho e^{i\theta})\,d\theta = f(z_0),
$$

即解析函数在圆心处的值等于它在圆周上的平均值。

---

### 13.3 高阶导数公式（Cauchy's Integral Formula for Derivatives）

**定理**：设 $f(z)$ 在简单正向闭曲线 $C$ 及其所围区域 $D$ 上解析，$z_0\in D$，则 $f$ 在 $z_0$ 处具有任意阶导数，且

$$
f^{(n)}(z_0) = \frac{n!}{2\pi i} \oint_C \frac{f(z)}{(z-z_0)^{n+1}}\,dz,\qquad n=0,1,2,\dots \tag{13.2}
$$
*(Cauchy's differentiation formula)*

**证明**（数学归纳法，详细步骤）：

- **基础步骤** $n=1$：

由柯西积分公式，$f(z_0)=\frac{1}{2\pi i}\oint_C \frac{f(z)}{z-z_0}dz$。对 $z_0$ 求导（考虑差商极限）：

$$
f'(z_0) = \lim_{h\to 0}\frac{f(z_0+h)-f(z_0)}{h}
= \lim_{h\to 0}\frac{1}{2\pi i}\oint_C f(z)\left[\frac{1}{h}\left(\frac{1}{z-z_0-h} - \frac{1}{z-z_0}\right)\right]dz.
$$

计算括号内：

$$
\frac{1}{h}\left(\frac{1}{z-z_0-h} - \frac{1}{z-z_0}\right) = \frac{1}{h}\cdot\frac{h}{(z-z_0-h)(z-z_0)} = \frac{1}{(z-z_0-h)(z-z_0)}.
$$

因此

$$
f'(z_0) = \lim_{h\to 0}\frac{1}{2\pi i}\oint_C \frac{f(z)}{(z-z_0-h)(z-z_0)}\,dz.
$$

当 $h\to 0$ 时，被积函数在 $C$ 上一致收敛到 $\frac{f(z)}{(z-z_0)^2}$（因为 $|z-z_0|\ge d>0$），故极限与积分可交换，得

$$
f'(z_0) = \frac{1}{2\pi i}\oint_C \frac{f(z)}{(z-z_0)^2}\,dz.
$$

即 $n=1$ 时公式成立。

- **归纳步骤**：假设对 $n=k$ 公式成立：

$$
f^{(k)}(z_0) = \frac{k!}{2\pi i}\oint_C \frac{f(z)}{(z-z_0)^{k+1}}\,dz.
$$

对 $z_0$ 求导，类似地有

$$
f^{(k+1)}(z_0) = \lim_{h\to 0}\frac{f^{(k)}(z_0+h)-f^{(k)}(z_0)}{h}
= \lim_{h\to 0}\frac{k!}{2\pi i}\oint_C f(z)\cdot\frac{1}{h}\left(\frac{1}{(z-z_0-h)^{k+1}}-\frac{1}{(z-z_0)^{k+1}}\right)dz.
$$

利用代数恒等式：
$$
\frac{1}{h}\left(\frac{1}{A^{k+1}} - \frac{1}{B^{k+1}}\right) = -\frac{1}{A^{k+1}B^{k+1}}\cdot\frac{A^{k+1}-B^{k+1}}{h}
$$
其中 $A = z-z_0-h$, $B = z-z_0$。更直接地用导数思想：由
$$
\frac{d}{dz_0}\left(\frac{1}{(z-z_0)^{k+1}}\right) = \frac{k+1}{(z-z_0)^{k+2}},
$$
当 $h\to 0$ 时，差商趋向该导数。严格地，利用一致收敛性，可交换极限与积分，得到
$$
f^{(k+1)}(z_0) = \frac{k!}{2\pi i} \oint_C f(z) \frac{(k+1)}{(z-z_0)^{k+2}} dz = \frac{(k+1)!}{2\pi i} \oint_C \frac{f(z)}{(z-z_0)^{k+2}} dz.
$$

故对 $n=k+1$ 也成立。由归纳法，公式对所有非负整数 $n$ 成立。$\square$

**重要推论**：解析函数具有任意阶导数，且每一阶导数仍然解析。

---

### 13.4 柯西不等式与刘维尔定理

**柯西不等式**（*Cauchy's estimate*）：设 $f(z)$ 在 $|z-z_0|<R$ 内解析，且 $|f(z)|\le M$（$M$ 为常数），则

$$
|f^{(n)}(z_0)| \le \frac{n!\, M}{R^n},\qquad n=0,1,2,\dots \tag{13.3}
$$

**证明**：取 $C$ 为圆周 $|z-z_0|=\rho$（$0<\rho<R$），由高阶导数公式和模不等式：

$$
|f^{(n)}(z_0)| = \left|\frac{n!}{2\pi i}\oint_C \frac{f(z)}{(z-z_0)^{n+1}}dz\right|
\le \frac{n!}{2\pi} \oint_C \frac{|f(z)|}{|z-z_0|^{n+1}}|dz|
\le \frac{n!}{2\pi}\cdot \frac{M}{\rho^{n+1}}\cdot 2\pi\rho = \frac{n!\,M}{\rho^n}.
$$

令 $\rho\to R^-$ 即得 $\le n!M/R^n$。$\square$

**刘维尔定理**（*Liouville's theorem*）：若 $f(z)$ 在整个复平面 $\mathbb{C}$ 上解析且有界，则 $f(z)$ 必为常数。

**证明**：设 $|f(z)|\le M$ 对一切 $z\in\mathbb{C}$ 成立。对任意 $z_0\in\mathbb{C}$，在柯西不等式中取 $R$ 任意大，有

$$
|f'(z_0)| \le \frac{1!\,M}{R} \to 0 \quad (R\to\infty).
$$

故 $f'(z_0)=0$ 对所有 $z_0$ 成立，因此 $f$ 为常数。$\square$

**整函数**（*Entire function*）：在 $\mathbb{C}$ 上处处解析的函数。刘维尔定理表明：有界整函数必为常数。

**亚纯函数**（*Meromorphic function*）：在区域 $D$ 内除极点外处处解析的函数。亚纯函数可以表示为两个整函数的商。

---

### 13.5 典型例题

#### 例1 计算积分 $I = \frac{1}{2\pi i} \oint_{|z|=R} \frac{dz}{(z-a)^n (z-b)}$，其中 $a,b$ 不在圆周 $|z|=R$ 上，$n$ 为正整数

**解**：分三种情况。

**(1) $a$ 和 $b$ 均在圆外**：此时被积函数在 $|z|\le R$ 内解析，由柯西定理，$I=0$。

**(2) $a$ 在圆外，$b$ 在圆内**：记 $f(z)=\frac{1}{(z-a)^n}$，则 $f(z)$ 在圆内解析。由柯西积分公式

$$
I = \frac{1}{2\pi i} \oint_{|z|=R} \frac{f(z)}{z-b}\,dz = f(b) = \frac{1}{(b-a)^n}.
$$

**(3) $a$ 在圆内，$b$ 在圆外**：类似地，令 $g(z)=\frac{1}{z-b}$，则 $g(z)$ 在圆内解析。由高阶导数公式（$n\ge 1$）：

$$
I = \frac{1}{2\pi i} \oint_{|z|=R} \frac{g(z)}{(z-a)^n}\,dz = \frac{g^{(n-1)}(a)}{(n-1)!}.
$$

计算 $g(z)=\frac{1}{z-b}$，则 $g^{(n-1)}(z)=(-1)^{n-1}\frac{(n-1)!}{(z-b)^n}$，因此

$$
g^{(n-1)}(a)=(-1)^{n-1}\frac{(n-1)!}{(a-b)^n}.
$$

于是

$$
I = \frac{1}{(n-1)!}\cdot (-1)^{n-1}\frac{(n-1)!}{(a-b)^n} = \frac{(-1)^{n-1}}{(a-b)^n}.
$$

注意 $(a-b)^n = (-1)^n (b-a)^n$，所以 $\frac{(-1)^{n-1}}{(a-b)^n} = \frac{(-1)^{n-1}}{(-1)^n (b-a)^n} = -\frac{1}{(b-a)^n}$。故

$$
I = -\frac{1}{(b-a)^n}.
$$

**(4) $a$ 和 $b$ 均在圆内**：取两个小圆 $C_a$ 和 $C_b$ 分别包围 $a$ 和 $b$，由柯西定理的挖洞法：

$$
I = \frac{1}{2\pi i}\oint_{C_a} \frac{dz}{(z-a)^n (z-b)} + \frac{1}{2\pi i}\oint_{C_b} \frac{dz}{(z-a)^n (z-b)}.
$$

第一个积分：在 $C_a$ 上，$z-b$ 解析且非零，利用高阶导数公式（$n\ge 1$）得

$$
\frac{1}{2\pi i}\oint_{C_a} \frac{1/(z-b)}{(z-a)^n}\,dz = \frac{1}{(n-1)!}\left.\frac{d^{n-1}}{dz^{n-1}}\left(\frac{1}{z-b}\right)\right|_{z=a} = \frac{(-1)^{n-1}}{(a-b)^n}.
$$

第二个积分：在 $C_b$ 上，$1/(z-a)^n$ 解析，由普通柯西公式（$n=1$时即为函数值，但这里 $n$ 任意）注意被积函数为 $\frac{1}{(z-a)^n (z-b)}$，对于 $C_b$ 我们视 $F(z)=\frac{1}{(z-a)^n}$，则

$$
\frac{1}{2\pi i}\oint_{C_b} \frac{F(z)}{z-b}\,dz = F(b) = \frac{1}{(b-a)^n}.
$$

因此

$$
I = \frac{(-1)^{n-1}}{(a-b)^n} + \frac{1}{(b-a)^n}.
$$

由于 $(-1)^{n-1}/(a-b)^n = (-1)^{n-1} / [(-1)^n (b-a)^n] = -1/(b-a)^n$，故两项相加为零。所以 $I=0$。

综上，结果归纳为：

- $a,b$ 均在圆外：$I=0$；
- $a$ 外 $b$ 内：$I=\frac{1}{(b-a)^n}$；
- $a$ 内 $b$ 外：$I=-\frac{1}{(b-a)^n}$；
- $a,b$ 均在圆内：$I=0$。

---

## 第14章 级数

### 14.1 实数项级数回顾

**定义**：给定数列 $\{a_n\}\subset\mathbb{R}$，形式和 $\sum_{n=1}^{\infty} a_n = a_1 + a_2 + \cdots$ 称为**级数**（*series*）。部分和 $S_n = \sum_{k=1}^{n} a_k$。若 $\lim_{n\to\infty} S_n = S$ 存在且有限，则级数收敛于 $S$；否则发散。

**Cauchy 收敛准则**（*Cauchy criterion*）：级数 $\sum a_n$ 收敛 $\iff$ $\forall\varepsilon>0,\exists N,\forall n>N,\forall p\ge1$，有 $|a_{n+1}+a_{n+2}+\cdots+a_{n+p}|<\varepsilon$。

**绝对收敛与条件收敛**：

- **绝对收敛**（*absolutely convergent*）：$\sum |a_n|$ 收敛。
- **条件收敛**（*conditionally convergent*）：$\sum a_n$ 收敛但 $\sum |a_n|$ 发散。

**莱布尼茨判别法**（*Leibniz test*）：若交错级数 $\sum_{n=1}^{\infty}(-1)^{n+1}u_n$ 满足：

1. $u_n \to 0$（单调递减），
2. $u_n \ge u_{n+1} > 0$，
则级数收敛。

---

### 14.2 复级数

**定义**：设 $z_n = x_n + i y_n \in \mathbb{C}$，则级数 $\sum_{n=1}^{\infty} z_n$ 收敛 $\iff$ 实部级数 $\sum x_n$ 与虚部级数 $\sum y_n$ 均收敛。此时

$$
\sum_{n=1}^{\infty} z_n = \sum_{n=1}^{\infty} x_n + i \sum_{n=1}^{\infty} y_n.
$$
*(Convergence of complex series)*

部分和 $S_n = \sum_{k=1}^{n} z_k = X_n + iY_n$，则 $\lim S_n = a+ib \iff \lim X_n = a,\ \lim Y_n = b$。

**Cauchy 收敛准则**（复形式）：

$$
\sum_{n=1}^{\infty} z_n \text{ 收敛 } \iff \forall\varepsilon>0,\exists N,\forall n>N,\forall p\ge1,\ \left|\sum_{k=n+1}^{n+p} z_k\right| < \varepsilon.
$$

**绝对收敛**：若 $\sum_{n=1}^{\infty} |z_n|$ 收敛，则 $\sum z_n$ 收敛（绝对收敛 $\Rightarrow$ 收敛）。反之不成立。

---

### 14.3 幂级数

**定义**：形如 $\sum_{n=0}^{\infty} C_n (z - z_0)^n$ 的级数称为以 $z_0$ 为中心的**幂级数**（*power series*）。

#### 收敛半径（Radius of convergence）

**定理**（Cauchy-Hadamard）：收敛半径 $R$ 由下式给出

$$
\frac{1}{R} = \limsup_{n\to\infty} \sqrt[n]{|C_n|},\qquad R = \frac{1}{\limsup_{n\to\infty} \sqrt[n]{|C_n|}}.
$$

若 $\limsup \sqrt[n]{|C_n|} = 0$，则 $R = +\infty$；若等于 $+\infty$，则 $R = 0$。

**达朗贝尔（比值）法**（*D'Alembert's ratio test*）：若 $\lim_{n\to\infty} \left|\frac{C_{n+1}}{C_n}\right| = l$ 存在（或为 $\infty$），则

$$
R = \frac{1}{l}\quad (\text{规定 } 1/0 = +\infty,\ 1/+\infty = 0).
$$

**柯西（根值）法**（*Cauchy's root test*）：若 $\lim_{n\to\infty} \sqrt[n]{|C_n|} = l$，则 $R = 1/l$。

**推导**：由比值判别法，$\sum C_n (z-z_0)^n$ 收敛当 $\lim_{n\to\infty} \left|\frac{C_{n+1}(z-z_0)^{n+1}}{C_n(z-z_0)^n}\right| = |z-z_0| \lim_{n\to\infty}\left|\frac{C_{n+1}}{C_n}\right| < 1$，故 $|z-z_0| < 1/l$。

**收敛圆**（*circle of convergence*）：$|z-z_0| < R$ 内幂级数绝对收敛且内闭一致收敛，边界上可能收敛或发散。

---

### 14.4 函数项级数与一致收敛

设 $\{u_n(z)\}$ 是区域 $D$ 上的函数列，$S(z) = \sum_{n=1}^{\infty} u_n(z)$。

- **逐点收敛**：对每个 $z\in D$，$\lim_{n\to\infty} S_n(z) = S(z)$。
- **一致收敛**（*uniform convergence*）：$\forall\varepsilon>0,\exists N,\forall n>N,\forall z\in D$，有 $|S(z) - S_n(z)| < \varepsilon$。

**Cauchy 准则**（一致收敛）：$\forall\varepsilon>0,\exists N,\forall n>N,\forall p\ge1,\forall z\in D$，$|\sum_{k=n+1}^{n+p} u_k(z)| < \varepsilon$。

**Weierstrass M-判别法**：若存在正项级数 $\sum M_n$ 收敛，且 $|u_n(z)| \le M_n$ 对一切 $z\in D$ 成立，则 $\sum u_n(z)$ 在 $D$ 上绝对且一致收敛。

**性质**：一致收敛级数可以逐项积分和逐项求导（在解析函数条件下）：

- 若 $u_n(z)$ 连续且级数一致收敛，则和函数连续，且 $\int_C \sum u_n(z) dz = \sum \int_C u_n(z) dz$。
- 若 $u_n(z)$ 解析且级数内闭一致收敛，则和函数解析，且 $\bigl(\sum u_n(z)\bigr)' = \sum u_n'(z)$。

---

### 14.5 泰勒定理（Taylor's theorem for analytic functions）

**定理**：设 $f(z)$ 在区域 $D$ 内解析，$z_0\in D$，$R$ 为 $z_0$ 到 $D$ 的边界（或到最近的奇点）的距离，则当 $|z-z_0| < R$ 时，$f(z)$ 可展开为幂级数

$$
f(z) = \sum_{n=0}^{\infty} C_n (z - z_0)^n,
$$
其中
$$
C_n = \frac{f^{(n)}(z_0)}{n!} = \frac{1}{2\pi i} \oint_C \frac{f(\zeta)}{(\zeta - z_0)^{n+1}} d\zeta,
$$
$C$ 是 $D$ 内包围 $z_0$ 的任一正向简单闭曲线。

**证明**（利用柯西积分公式）：对任意满足 $|z-z_0|<\rho<R$ 的点 $z$，取 $C$ 为圆周 $|\zeta - z_0| = \rho$，则

$$
f(z) = \frac{1}{2\pi i} \oint_C \frac{f(\zeta)}{\zeta - z} d\zeta.
$$

将 $\frac{1}{\zeta - z}$ 展开为几何级数：

$$
\frac{1}{\zeta - z} = \frac{1}{(\zeta - z_0) - (z - z_0)} = \frac{1}{\zeta - z_0} \cdot \frac{1}{1 - \frac{z - z_0}{\zeta - z_0}} = \sum_{n=0}^{\infty} \frac{(z - z_0)^n}{(\zeta - z_0)^{n+1}},
$$

该级数在 $|\zeta - z_0| = \rho$ 上一致收敛（因为 $|z - z_0| < \rho$）。代入积分：

$$
f(z) = \sum_{n=0}^{\infty} \left( \frac{1}{2\pi i} \oint_C \frac{f(\zeta)}{(\zeta - z_0)^{n+1}} d\zeta \right) (z - z_0)^n.
$$

由柯西导数公式，括号内的积分等于 $f^{(n)}(z_0)/n!$。$\square$

**推论**：$f(z)$ 在 $D$ 内解析 $\iff$ $f(z)$ 在 $D$ 内每点可展开为收敛幂级数（即解析与可展等价）。

---

### 14.6 常见泰勒展开（在 $z_0=0$）

1. **指数函数**：
   $$
   e^z = \sum_{n=0}^{\infty} \frac{z^n}{n!},\quad R = +\infty.
   $$
   *(Exponential series)*

2. **正弦与余弦**：
   $$
   \sin z = \sum_{n=0}^{\infty} \frac{(-1)^n z^{2n+1}}{(2n+1)!},\quad
   \cos z = \sum_{n=0}^{\infty} \frac{(-1)^n z^{2n}}{(2n)!},\quad R = +\infty.
   $$

3. **对数主支**（$|\ln(1+z)|$ 取主值）：
   $$
   \ln(1+z) = \sum_{n=1}^{\infty} (-1)^{n-1} \frac{z^n}{n},\quad |z|<1.
   $$
   多值完整形式：$\operatorname{Ln}(1+z) = \ln|1+z| + i\arg(1+z) + 2k\pi i = 2k\pi i + \sum_{n=1}^{\infty} (-1)^{n-1} \frac{z^n}{n}$。

4. **二项式级数**（*Binomial series*）：
   $$
   (1+z)^\alpha = \sum_{n=0}^{\infty} \binom{\alpha}{n} z^n,\quad \binom{\alpha}{n}=\frac{\alpha(\alpha-1)\cdots(\alpha-n+1)}{n!},\ |z|<1.
   $$
   特别地，$\frac{1}{1-z} = \sum_{n=0}^{\infty} z^n,\ |z|<1$。

---

### 14.7 唯一性定理与最大模原理

#### 唯一性定理（*Uniqueness theorem*）

若 $f(z)$ 在区域 $D$ 内解析，且存在点列 $\{z_k\}\subset D$ 聚于 $z_0\in D$，满足 $f(z_k)=0$，则 $f(z)\equiv 0$ 于 $D$。

推论：若两个解析函数在 $D$ 的一个聚点集上相等，则它们恒等。因此泰勒展开系数由 $f$ 唯一确定。

#### 最大模原理（*Maximum modulus principle*）

**定理**：设 $f(z)$ 在区域 $D$ 内解析，且非常数，则 $|f(z)|$ 在 $D$ 内**不能达到最大值**。即若存在 $z_0\in D$ 使得 $|f(z_0)| \ge |f(z)|$ 对所有 $z\in D$ 成立，则 $f(z)\equiv \text{常数}$。

**证明**（利用平均值性质）：对任意 $z_0\in D$，取小圆 $C_\rho: |z-z_0|=\rho$ 完全在 $D$ 内。由柯西积分公式，

$$
f(z_0) = \frac{1}{2\pi i} \oint_{C_\rho} \frac{f(z)}{z-z_0} dz = \frac{1}{2\pi} \int_0^{2\pi} f(z_0+\rho e^{i\theta}) d\theta.
$$

两边取模：

$$
|f(z_0)| \le \frac{1}{2\pi} \int_0^{2\pi} |f(z_0+\rho e^{i\theta})| d\theta \le \max_{\theta} |f(z_0+\rho e^{i\theta})|.
$$

若 $|f(z_0)|$ 是 $D$ 内的最大值，则等号必须成立，从而被积函数的模为常数，且由连续性推出 $|f(z)|$ 为常数，再由 C-R 方程推出 $f$ 为常数。$\square$

**推论**：解析函数在闭区域上的最大值必在边界达到（非常数时）。

---

### 14.8 例题

#### 例1 将 $f(z)=\frac{1}{(1-z)^2}$ 在 $z=i$ 处展开为幂级数，并求收敛半径

**解**：$f(z)$ 有唯一奇点 $z=1$，故收敛半径 $R=|1-i|=\sqrt{2}$。

先展开 $\frac{1}{1-z}$：

$$
\frac{1}{1-z} = \frac{1}{1-i - (z-i)} = \frac{1}{1-i} \cdot \frac{1}{1 - \frac{z-i}{1-i}}
= \frac{1}{1-i} \sum_{n=0}^{\infty} \left( \frac{z-i}{1-i} \right)^n,\quad \left| \frac{z-i}{1-i} \right| < 1,
$$

即 $|z-i| < |1-i| = \sqrt{2}$。

然后逐项求导：

$$
\frac{1}{(1-z)^2} = \frac{d}{dz}\left( \frac{1}{1-z} \right) = \frac{1}{1-i} \sum_{n=0}^{\infty} \frac{n (z-i)^{n-1}}{(1-i)^n} = \sum_{n=0}^{\infty} \frac{(n+1)(z-i)^n}{(1-i)^{n+2}},\quad |z-i|<\sqrt{2}.
$$

#### 例2 求级数 $\sum_{n=1}^{\infty} \frac{z^n}{n(n+1)}$ 的收敛半径

**解**：$C_n = \frac{1}{n(n+1)}$，使用比值法：

$$
\lim_{n\to\infty} \left| \frac{C_{n+1}}{C_n} \right| = \lim_{n\to\infty} \frac{n(n+1)}{(n+1)(n+2)} = \lim_{n\to\infty} \frac{n}{n+2} = 1,
$$

故 $R=1$。也可用根值法：$\sqrt[n]{|C_n|} = (n(n+1))^{-1/n} \to 1$。

#### 例3 讨论 $\sum_{n=1}^{\infty} \frac{z^n}{1-z^n}$ 的收敛性

**解**：当 $|z|>1$ 时，$|z^n| \to \infty$，$\frac{z^n}{1-z^n} \to -1 \neq 0$，通项不趋于零，级数发散。

当 $|z|<1$ 时，$|z^n| \le |z|^n$，且 $\left| \frac{z^n}{1-z^n} \right| \le \frac{|z|^n}{1-|z|^n} \le \frac{|z|^n}{1-|z|}$（对足够大 $n$），由 Weierstrass M-判别法，级数在闭圆 $|z|\le r<1$ 上一致收敛，故在 $|z|<1$ 内绝对收敛且内闭一致收敛。但在开圆内不一致收敛，因为边界附近收敛速度不一致。

#### 例4 证明若 $f(z)$ 是整函数，且 $M(r)=\max_{|z|=r}|f(z)|$，则 $M(r)$ 单调递增

**证**：由最大模原理，对 $0<r_1<r_2$，闭圆 $|z|\le r_1$ 包含在圆 $|z|<r_2$ 内，且 $f$ 解析。若 $f$ 非常数，则 $|f(z)|$ 在 $|z|\le r_1$ 上的最大值必在边界 $|z|=r_1$ 上达到，且该值小于在 $|z|=r_2$ 上的最大值（否则内部会达到更大值）。故 $M(r_1)\le M(r_2)$。若 $f$ 为常数，则等号成立。因此 $M(r)$ 单调不减。

---

## 第15章 洛朗级数与孤立奇点

### 15.1 洛朗级数的引入

考虑函数 $f(z)=\frac{1}{1-z}$，它在 $z=1$ 处有一个奇点。在 $z=0$ 的邻域内，可以展开为泰勒级数：

$$
\frac{1}{1-z} = \sum_{n=0}^{\infty} z^n,\qquad |z|<1.
$$

该级数在 $|z|>1$ 时发散。但在 $|z|>1$ 的区域，$|\frac{1}{z}|<1$，我们可以进行另一种展开：

$$
\frac{1}{1-z} = -\frac{1}{z}\cdot\frac{1}{1-\frac{1}{z}} = -\frac{1}{z}\sum_{n=0}^{\infty}\left(\frac{1}{z}\right)^n = -\sum_{n=1}^{\infty}\frac{1}{z^n},\qquad |z|>1.
$$

这启发我们：在一个圆环域 $R_1<|z-z_0|<R_2$ 内解析的函数，可以展开为既包含正幂次也包含负幂次的级数，即**洛朗级数**（*Laurent series*）。

---

### 15.2 洛朗定理

**定理**（*Laurent's theorem*）：设函数 $f(z)$ 在圆环域 $D: R_1 < |z-z_0| < R_2$（$0\le R_1<R_2\le+\infty$）内解析，则 $f(z)$ 在 $D$ 内可唯一地展开为双边幂级数：

$$
f(z) = \sum_{n=-\infty}^{+\infty} a_n (z-z_0)^n,
$$

其中系数为

$$
a_n = \frac{1}{2\pi i} \oint_C \frac{f(\zeta)}{(\zeta-z_0)^{n+1}}\,d\zeta,\qquad n=0,\pm1,\pm2,\dots,
$$

$C$ 是 $D$ 内绕 $z_0$ 的任意一条正向简单闭曲线（例如圆周 $|z-z_0|=\rho$，$R_1<\rho<R_2$）。

**唯一性**：如果存在另一种双边幂级数表示 $f(z)=\sum b_n (z-z_0)^n$，则沿 $C$ 逐项积分并由 $\oint_C (z-z_0)^{m} dz = 2\pi i \delta_{m,-1}$ 可得 $b_n = a_n$。故展开唯一。

**证明**：取 $C_1$ 和 $C_2$ 分别为圆环内半径为 $\rho_1$ 和 $\rho_2$ 的圆周（$R_1<\rho_1<\rho_2<R_2$），均取正向（逆时针）。由柯西积分公式，对 $D$ 内任意一点 $z$，有

$$
f(z) = \frac{1}{2\pi i}\oint_{C_2}\frac{f(\zeta)}{\zeta-z}\,d\zeta - \frac{1}{2\pi i}\oint_{C_1}\frac{f(\zeta)}{\zeta-z}\,d\zeta.
$$

对于 $C_2$ 上的积分，由于 $|z-z_0|<|\zeta-z_0|$，可展开

$$
\frac{1}{\zeta-z} = \frac{1}{(\zeta-z_0)-(z-z_0)} = \frac{1}{\zeta-z_0}\sum_{n=0}^{\infty}\left(\frac{z-z_0}{\zeta-z_0}\right)^n,
$$

该级数在 $C_2$ 上一致收敛。代入得

$$
\frac{1}{2\pi i}\oint_{C_2}\frac{f(\zeta)}{\zeta-z}\,d\zeta = \sum_{n=0}^{\infty}\left(\frac{1}{2\pi i}\oint_{C_2}\frac{f(\zeta)}{(\zeta-z_0)^{n+1}}\,d\zeta\right)(z-z_0)^n.
$$

对于 $C_1$ 上的积分，由于 $|\zeta-z_0|<|z-z_0|$，可展开

$$
\frac{1}{\zeta-z} = -\frac{1}{z-z_0}\cdot\frac{1}{1-\frac{\zeta-z_0}{z-z_0}} = -\sum_{n=1}^{\infty}\frac{(\zeta-z_0)^{n-1}}{(z-z_0)^n}.
$$

于是

$$
-\frac{1}{2\pi i}\oint_{C_1}\frac{f(\zeta)}{\zeta-z}\,d\zeta = \sum_{n=1}^{\infty}\left(\frac{1}{2\pi i}\oint_{C_1}\frac{f(\zeta)}{(\zeta-z_0)^{-n+1}}\,d\zeta\right)(z-z_0)^{-n}.
$$

令 $a_{-n} = \frac{1}{2\pi i}\oint_{C_1}\frac{f(\zeta)}{(\zeta-z_0)^{-n+1}}\,d\zeta$，结合两个级数即得双边幂级数。由柯西定理，积分路径 $C_1$ 和 $C_2$ 可替换为任意一条在 $D$ 内绕 $z_0$ 的闭曲线 $C$，且系数公式统一为 $a_n = \frac{1}{2\pi i}\oint_C \frac{f(\zeta)}{(\zeta-z_0)^{n+1}}d\zeta$（$n$ 可为负整数）。唯一性由级数系数的积分表达式保证。$\square$

**注**：洛朗级数中，非负幂次部分 $\sum_{n=0}^{\infty}a_n(z-z_0)^n$ 称为**解析部分**（*analytic part*），负幂次部分 $\sum_{n=-\infty}^{-1}a_n(z-z_0)^n$ 称为**主要部分**（*principal part*）。若函数在 $|z-z_0|<R_2$ 内解析（即 $R_1=0$），则洛朗级数退化为泰勒级数。

---

### 15.3 洛朗展开的方法

1. **直接展开**：利用系数公式 $a_n = \frac{1}{2\pi i}\oint_C \frac{f(z)}{(z-z_0)^{n+1}}dz$ 计算积分。通常较繁琐，不常用。
2. **间接展开**：利用已知泰勒级数，通过代数运算、求导、积分、变量替换等，将函数分解为若干个简单函数在相应收敛环内的级数之和。

**步骤**：

- 确定函数的奇点，以展开点 $z_0$ 为中心，将复平面划分为不同的圆环域（$|z-z_0|<r_1$，$r_1<|z-z_0|<r_2$，…，$|z-z_0|>r_k$）。
- 在每个圆环域内，将函数分解为部分分式或利用已知展开式，得到洛朗级数。

---

### 15.4 例题：展开 $f(z)=\frac{1}{(z-1)(z-2)}$ 在 $z=0$ 的洛朗级数

**解**：$f(z)$ 有奇点 $z=1$ 和 $z=2$。以 $z_0=0$ 为中心，将复平面分为三个解析环：

1. $0\le|z|<1$，
2. $1<|z|<2$，
3. $2<|z|<+\infty$。

首先将 $f(z)$ 分解为部分分式：

$$
f(z)=\frac{1}{z-1}-\frac{1}{z-2}= -\frac{1}{1-z}+\frac{1}{2}\cdot\frac{1}{1-\frac{z}{2}}.
$$

**环1** $|z|<1$：此时 $\left|\frac{z}{2}\right|<1$，可展开为泰勒级数：

$$
\frac{1}{1-z}=\sum_{n=0}^{\infty}z^n,\qquad \frac{1}{1-\frac{z}{2}}=\sum_{n=0}^{\infty}\left(\frac{z}{2}\right)^n.
$$

因此

$$
f(z)= -\sum_{n=0}^{\infty}z^n + \frac{1}{2}\sum_{n=0}^{\infty}\frac{z^n}{2^n} = \sum_{n=0}^{\infty}\left(-1+\frac{1}{2^{n+1}}\right)z^n = \sum_{n=0}^{\infty}\left( \frac{1}{2^{n+1}}-1\right)z^n.
$$

**环2** $1<|z|<2$：此时 $|z|>1$，$\left|\frac{z}{2}\right|<1$。改写第一项：

$$
\frac{1}{1-z}= -\frac{1}{z}\cdot\frac{1}{1-\frac{1}{z}} = -\frac{1}{z}\sum_{n=0}^{\infty}\frac{1}{z^n}= -\sum_{n=0}^{\infty}\frac{1}{z^{n+1}}= -\sum_{n=1}^{\infty}\frac{1}{z^{n}}.
$$

第二项不变：$\frac{1}{2}\sum_{n=0}^{\infty}\frac{z^n}{2^n}$。于是

$$
f(z)= -\sum_{n=1}^{\infty}\frac{1}{z^{n}} + \frac{1}{2}\sum_{n=0}^{\infty}\frac{z^n}{2^n}.
$$

**环3** $|z|>2$：此时 $|z|>1$ 且 $|z|>2$，两项都需展为 $z$ 的负幂次：

$$
\frac{1}{1-z}= -\sum_{n=1}^{\infty}\frac{1}{z^{n}},\qquad \frac{1}{z-2}= \frac{1}{z}\cdot\frac{1}{1-\frac{2}{z}} = \frac{1}{z}\sum_{n=0}^{\infty}\left(\frac{2}{z}\right)^n = \sum_{n=1}^{\infty}\frac{2^{n-1}}{z^{n}}.
$$

因此

$$
f(z)= -\frac{1}{1-z}-\frac{1}{z-2}?? \text{注意符号：} f(z)=\frac{1}{z-1}-\frac{1}{z-2}= -\frac{1}{1-z}-\frac{1}{z-2}.
$$

实际上直接部分分式：$f(z)=\frac{1}{z-1}-\frac{1}{z-2}$，在 $|z|>2$ 时，两个分式都展开为 $1/z$ 的幂级数：

$$
\frac{1}{z-1}=\frac{1}{z}\cdot\frac{1}{1-\frac{1}{z}}=\sum_{n=1}^{\infty}\frac{1}{z^{n}},\qquad 
\frac{1}{z-2}=\frac{1}{z}\cdot\frac{1}{1-\frac{2}{z}}=\sum_{n=1}^{\infty}\frac{2^{n-1}}{z^{n}}.
$$

故

$$
f(z)=\sum_{n=1}^{\infty}\frac{1}{z^{n}}-\sum_{n=1}^{\infty}\frac{2^{n-1}}{z^{n}}=\sum_{n=1}^{\infty}\frac{1-2^{n-1}}{z^{n}}.
$$

---

### 15.5 孤立奇点的定义与分类

**奇点**：函数不解析的点。

**孤立奇点**（*isolated singularity*）：若 $z_0$ 是奇点，且存在 $\delta>0$ 使得 $f(z)$ 在去心邻域 $0<|z-z_0|<\delta$ 内处处解析，则称 $z_0$ 为 $f(z)$ 的孤立奇点。

例：

- $z=0$ 是 $\frac{1}{z}$ 的孤立奇点。
- $z=0$ 是 $\sin\frac{1}{z}$ 的奇点，但不是孤立的（因为 $\frac{1}{n\pi}$ 也是奇点，且以 $0$ 为聚点）。

不孤立奇点不在本课程讨论范围内。

**孤立奇点的分类**：设 $z_0$ 为孤立奇点，$f(z)$ 在 $0<|z-z_0|<R$ 内的洛朗级数为

$$
f(z)=\sum_{n=-\infty}^{+\infty} a_n (z-z_0)^n.
$$

根据负幂次项的多少，分为三类：

#### 15.5.1 可去奇点（*removable singularity*）

若洛朗级数中不含 $(z-z_0)$ 的负幂次项（即 $a_n=0$ 对所有 $n<0$），则称 $z_0$ 为可去奇点。此时

$$
f(z)=\sum_{n=0}^{\infty} a_n (z-z_0)^n,\quad 0<|z-z_0|<R.
$$

极限 $\lim_{z\to z_0}f(z)=a_0$ 存在且有限。若补充定义 $f(z_0)=a_0$，则 $f$ 在 $z_0$ 解析。

**判定定理**：

1. $z_0$ 是可去奇点 $\iff$ $\lim_{z\to z_0}f(z)$ 存在且有限。
2. $z_0$ 是可去奇点 $\iff$ $f(z)$ 在 $z_0$ 的某个去心邻域内有界。

**例**：$f(z)=\frac{\sin z}{z}$，在 $z=0$ 的洛朗展开为

$$
\frac{\sin z}{z}=\frac{1}{z}\left(z-\frac{z^3}{3!}+\frac{z^5}{5!}-\cdots\right)=1-\frac{z^2}{3!}+\frac{z^4}{5!}-\cdots,
$$

不含负幂次，故 $z=0$ 是可去奇点。且 $\lim_{z\to0}\frac{\sin z}{z}=1$。

#### 15.5.2 极点（*pole*）

若洛朗级数中只有有限个负幂次项，且最高负幂次为 $m\ge1$（即 $a_{-m}\neq0$，但对 $n<-m$ 有 $a_n=0$），则称 $z_0$ 为 $f(z)$ 的 **$m$ 阶极点**（*pole of order m*）。此时

$$
f(z)=\frac{g(z)}{(z-z_0)^m},
$$

其中 $g(z)=\sum_{n=0}^{\infty}a_{-m+n}(z-z_0)^n$ 在 $z_0$ 解析且 $g(z_0)=a_{-m}\neq0$。

**判定**：

- $\lim_{z\to z_0}f(z)=\infty$（充要条件）。
- $z_0$ 是 $f(z)$ 的 $m$ 阶极点 $\iff$ $g(z)=\frac{1}{f(z)}$ 在 $z_0$ 有 $m$ 阶零点。

**例**：$f(z)=\frac{e^z}{(z-1)^2}$，在 $z=1$ 处，

$$
e^z=e\cdot e^{z-1}=e\left[1+(z-1)+\frac{(z-1)^2}{2!}+\cdots\right],
$$

所以

$$
f(z)=\frac{e}{(z-1)^2}+\frac{e}{z-1}+\frac{e}{2}+\cdots,
$$

负幂次最高为 $-2$，故 $z=1$ 是二阶极点。

#### 15.5.3 本性奇点（*essential singularity*）

若洛朗级数中含有无穷多个负幂次项，则称 $z_0$ 为本性奇点。

**判定**：$\lim_{z\to z_0}f(z)$ 不存在且不为 $\infty$（即既非有限也非无穷）。

**例**：$f(z)=e^{1/z}$，在 $z=0$ 的洛朗展开为

$$
e^{1/z}=\sum_{n=0}^{\infty}\frac{1}{n!\,z^n},\qquad 0<|z|<+\infty,
$$

含有无穷多负幂次，故 $z=0$ 为本性奇点。极限不存在：沿正实轴 $z=x\to0^+$ 时 $e^{1/x}\to+\infty$；沿负实轴 $z=x\to0^-$ 时 $e^{1/x}\to0$。

**分类极限特征**：

- 可去奇点：$\lim_{z\to z_0}f(z)$ 存在且有限。
- 极点：$\lim_{z\to z_0}f(z)=\infty$。
- 本性奇点：$\lim_{z\to z_0}f(z)$ 不存在且不为 $\infty$。

---

### 15.6 零点与极点的关系

**定义**：设 $f(z)$ 在 $z_0$ 解析，且 $f(z_0)=0$，则称 $z_0$ 为 $f(z)$ 的零点。若存在正整数 $m$ 使得

$$
f(z)=(z-z_0)^m\varphi(z),\quad \varphi(z_0)\neq0,
$$

且 $\varphi(z)$ 在 $z_0$ 解析，则称 $z_0$ 为 $f(z)$ 的 **$m$ 阶零点**（*zero of order m*）。

**判定**（导数条件）：$z_0$ 是 $f(z)$ 的 $m$ 阶零点 $\iff$ 

$$
f(z_0)=f'(z_0)=\cdots=f^{(m-1)}(z_0)=0,\quad f^{(m)}(z_0)\neq0.
$$

**极点与零点的关系**：若 $z_0$ 是 $f(z)$ 的 $m$ 阶极点，则 $\frac{1}{f(z)}$ 在 $z_0$ 处有 $m$ 阶零点（可去奇点后）。更一般地，若 $f(z)=\frac{f_1(z)}{f_2(z)}$，其中 $f_1,f_2$ 解析，$z_0$ 是 $f_1$ 的 $m$ 阶零点，$f_2$ 的 $n$ 阶零点，则：

- 若 $m\ge n$，$z_0$ 是 $f(z)$ 的可去奇点（实际上若 $m>n$，可补定义为零点）；
- 若 $m<n$，$z_0$ 是 $f(z)$ 的 $(n-m)$ 阶极点。

**例**：求 $f(z)=\frac{1}{\sin z}$ 的奇点类型。

$\sin z$ 的零点为 $z=k\pi$（$k\in\mathbb{Z}$），且 $(\sin z)'|_{z=k\pi}=\cos(k\pi)=(-1)^k\neq0$，故每个 $z=k\pi$ 是 $\sin z$ 的一阶零点。因此 $\frac{1}{\sin z}$ 在这些点处有一阶极点。

---

### 15.7 无穷远点作为孤立奇点

设 $f(z)$ 在无穷远点的去心邻域 $R<|z|<\infty$ 内解析，则称 $\infty$ 为 $f(z)$ 的孤立奇点。作变换 $w=1/z$，则 $g(w)=f(1/w)$ 在 $0<|w|<1/R$ 内解析。$f(z)$ 在 $z=\infty$ 的性态由 $g(w)$ 在 $w=0$ 的性态决定。


**分类**：

- 可去奇点：$\lim_{z\to\infty}f(z)$ 存在且有限 $\iff$ $g(w)$ 在 $w=0$ 可去。
- 极点：$\lim_{z\to\infty}f(z)=\infty$ $\iff$ $g(w)$ 在 $w=0$ 有极点。
- 本性奇点：$\lim_{z\to\infty}f(z)$ 不存在且不为 $\infty$ $\iff$ $g(w)$ 在 $w=0$ 为本性奇点。

**例**：$f(z)=\frac{z^2}{1+z^2}$，当 $z\to\infty$ 时 $f(z)\to1$，故 $\infty$ 是可去奇点。事实上 $g(w)=\frac{1/w^2}{1+1/w^2}=\frac{1}{1+w^2}$，在 $w=0$ 解析。



---

## 第16章 留数理论

### 16.1 留数的定义

设 $z_0$ 为 $f(z)$ 的一个孤立奇点，$f(z)$ 在 $0<|z-z_0|<R$ 内的洛朗展开式为

$$
f(z)=\sum_{n=-\infty}^{+\infty} a_n (z-z_0)^n,
$$

其中 $a_{-1}$ 是 $(z-z_0)^{-1}$ 项的系数。沿去心邻域内绕 $z_0$ 的正向简单闭曲线 $C$ 逐项积分，由柯西积分公式

$$
\oint_C (z-z_0)^n dz = 
\begin{cases}
2\pi i, & n=-1,\\
0, & n\neq -1,
\end{cases}
$$

得

$$
\oint_C f(z) dz = 2\pi i \, a_{-1}.
$$

称 $a_{-1}$ 为 $f(z)$ 在孤立奇点 $z_0$ 处的**留数**（*residue*），记作

$$
\operatorname{Res}[f(z), z_0] = a_{-1} = \frac{1}{2\pi i} \oint_C f(z) dz. \tag{16.1}
$$

---

### 16.2 留数定理

**定理**（*Residue theorem*）：设函数 $f(z)$ 在区域 $D$ 内除有限个孤立奇点 $z_1, z_2, \dots, z_n$ 外处处解析，$C$ 是 $D$ 内包围所有奇点的一条正向简单闭曲线，则

$$
\oint_C f(z) dz = 2\pi i \sum_{k=1}^{n} \operatorname{Res}[f(z), z_k]. \tag{16.2}
$$

**证明**：以每个奇点 $z_k$ 为圆心作充分小的圆周 $C_k$（正向，彼此不相交且均位于 $C$ 内部），使得 $C_k$ 内只含奇点 $z_k$。在 $C$ 与各 $C_k$ 之间的多连通区域上，$f(z)$ 解析，由柯西定理（复合闭路定理）有

$$
\oint_C f(z) dz = \sum_{k=1}^{n} \oint_{C_k} f(z) dz.
$$

而由留数定义，$\oint_{C_k} f(z) dz = 2\pi i \operatorname{Res}[f(z), z_k]$。代入即得结论。$\square$

---

### 16.3 不同奇点类型的留数计算

#### 16.3.1 可去奇点

若 $z_0$ 是可去奇点，则洛朗级数中无负幂次项，故 $a_{-1}=0$，因此

$$
\operatorname{Res}[f(z), z_0] = 0.
$$

#### 16.3.2 本性奇点

本性奇点没有统一的简单公式，通常需要直接展开洛朗级数求出 $a_{-1}$，或通过围道积分计算。

#### 16.3.3 极点

**(1) 一阶极点（简单极点）**

若 $z_0$ 是 $f(z)$ 的一阶极点，则在 $z_0$ 附近

$$
f(z) = \frac{\varphi(z)}{z-z_0},
$$

其中 $\varphi(z)$ 在 $z_0$ 解析且 $\varphi(z_0)\neq 0$。于是

$$
\operatorname{Res}[f(z), z_0] = \lim_{z\to z_0} (z-z_0) f(z) = \varphi(z_0).
$$

**(2) $m$ 阶极点（$m\ge 1$）**

若 $z_0$ 是 $f(z)$ 的 $m$ 阶极点，则

$$
f(z) = \frac{\varphi(z)}{(z-z_0)^m},
$$

其中 $\varphi(z)$ 在 $z_0$ 解析且 $\varphi(z_0)\neq 0$。将 $\varphi(z)$ 在 $z_0$ 泰勒展开：

$$
\varphi(z)=\sum_{k=0}^{\infty} \frac{\varphi^{(k)}(z_0)}{k!}(z-z_0)^k.
$$

于是

$$
f(z)=\sum_{k=0}^{\infty} \frac{\varphi^{(k)}(z_0)}{k!}(z-z_0)^{k-m}.
$$

$(z-z_0)^{-1}$ 项出现在 $k=m-1$ 时，其系数为

$$
\frac{\varphi^{(m-1)}(z_0)}{(m-1)!}.
$$

因此

$$
\operatorname{Res}[f(z), z_0] = \frac{\varphi^{(m-1)}(z_0)}{(m-1)!}.
$$

又因为 $\varphi(z)=(z-z_0)^m f(z)$，所以

$$
\operatorname{Res}[f(z), z_0] = \frac{1}{(m-1)!} \lim_{z\to z_0} \frac{d^{m-1}}{dz^{m-1}} \left[ (z-z_0)^m f(z) \right]. \tag{16.3}
$$
*(Residue at a pole of order m)*

**(3) 有理分式的一阶极点公式**

设 $f(z)=\dfrac{P(z)}{Q(z)}$，其中 $P(z), Q(z)$ 在 $z_0$ 解析，$Q(z_0)=0$，$Q'(z_0)\neq 0$，$P(z_0)\neq 0$，则 $z_0$ 是 $f(z)$ 的一阶极点，且

$$
\operatorname{Res}[f(z), z_0] = \frac{P(z_0)}{Q'(z_0)}.
$$

**证明**：

$$
\operatorname{Res}[f(z), z_0] = \lim_{z\to z_0} (z-z_0) \frac{P(z)}{Q(z)} = \lim_{z\to z_0} \frac{P(z)}{\frac{Q(z)-Q(z_0)}{z-z_0}} = \frac{P(z_0)}{Q'(z_0)}.
$$

$\square$

---

### 16.4 留数定理应用示例

**例1**：计算 $I = \oint_{|z|=2} \dfrac{3e^z}{z^2-1} dz$。

**解**：被积函数 $f(z)=\dfrac{3e^z}{(z-1)(z+1)}$ 在 $|z|=2$ 内有两个一阶极点 $z=1$ 和 $z=-1$。

由一阶极点公式：

$$
\operatorname{Res}[f(z),1] = \lim_{z\to 1}(z-1)\frac{3e^z}{(z-1)(z+1)} = \frac{3e}{2}.
$$

$$
\operatorname{Res}[f(z),-1] = \lim_{z\to -1}(z+1)\frac{3e^z}{(z-1)(z+1)} = \frac{3e^{-1}}{-2} = -\frac{3}{2e}.
$$

由留数定理：

$$
I = 2\pi i \left( \frac{3e}{2} - \frac{3}{2e} \right) = 3\pi i \left( e - \frac{1}{e} \right) = 3\pi i \cdot \frac{e^2-1}{e}.
$$



---

### 16.5 无穷远点的留数

#### 16.5.1 定义

设 $f(z)$ 在圆环域 $R<|z|<\infty$ 内解析，$C$ 是该圆环域内绕原点的任意一条正向简单闭曲线。则 $f(z)$ 在无穷远点 $\infty$ 处的留数定义为

$$
\operatorname{Res}[f(z), \infty] = \frac{1}{2\pi i} \oint_{C^-} f(z) dz,
$$

其中 $C^-$ 表示**顺时针**方向（即 $C$ 的反向）。若取 $C$ 为半径 $>R$ 的圆周，顺时针方向相当于绕无穷远点一周的“正向”。

设 $f(z)$ 在 $R<|z|<\infty$ 内的洛朗展开为 $f(z)=\sum_{n=-\infty}^{+\infty} C_n z^n$，则

$$
\oint_{C^-} f(z) dz = -\oint_{C} f(z) dz = -2\pi i C_{-1},
$$

其中 $C$ 为正向圆周。因此

$$
\operatorname{Res}[f(z), \infty] = -C_{-1}.
$$

即无穷远点的留数等于洛朗展开中 $z^{-1}$ 项系数的**相反数**。

**注意**：即使 $\infty$ 是 $f(z)$ 的可去奇点（即洛朗展开无正幂次），$C_{-1}$ 不一定为零，故留数未必为零。

#### 16.5.2 变换公式

作变换 $w=1/z$，则 $z=1/w$，$dz = -dw/w^2$。设 $g(w)=f(1/w)$，则

$$
\operatorname{Res}[f(z), \infty] = \frac{1}{2\pi i} \oint_{C^-} f(z) dz = -\frac{1}{2\pi i} \oint_{C^+} f(z) dz.
$$

其中 $C^+$ 为正向（逆时针）大圆。在 $w$ 平面上，$C$ 映射为一个小圆 $\gamma$ 绕原点顺时针（因为 $z$ 逆时针时 $w$ 顺时针）。但通常我们取逆时针，需调整符号。标准结果：

$$
\operatorname{Res}[f(z), \infty] = - \operatorname{Res}\left[ \frac{1}{w^2} f\left(\frac{1}{w}\right), 0 \right]. \tag{16.4}
$$

**推导**：令 $z=1/w$，则 $dz = -dw/w^2$，且 $C^-$（$z$ 平面顺时针大圆）对应 $w$ 平面逆时针小圆（方向相反两次抵消）。具体：

$$
\operatorname{Res}[f(z), \infty] = \frac{1}{2\pi i} \oint_{C^-} f(z) dz = \frac{1}{2\pi i} \oint_{\gamma} f\left(\frac{1}{w}\right) \left(-\frac{dw}{w^2}\right) = -\frac{1}{2\pi i} \oint_{\gamma} \frac{1}{w^2} f\left(\frac{1}{w}\right) dw.
$$

而 $\oint_{\gamma} \frac{1}{w^2} f(1/w) dw = 2\pi i \operatorname{Res}\left[ \frac{1}{w^2} f(1/w), 0 \right]$，所以

$$
\operatorname{Res}[f(z), \infty] = -\operatorname{Res}\left[ \frac{1}{w^2} f\left(\frac{1}{w}\right), 0 \right].
$$

注意：使用该公式时，必须确保 $0$ 是 $g(w)=\frac{1}{w^2}f(1/w)$ 的孤立奇点（通常成立），然后计算 $g$ 在 $0$ 处的留数并取负号。

---

### 16.6 扩充复平面上所有留数之和为零

**定理**：若 $f(z)$ 在扩充复平面 $\overline{\mathbb{C}}=\mathbb{C}\cup\{\infty\}$ 上只有有限个孤立奇点（包括无穷远点），则所有奇点的留数之和为零：

$$
\sum_{k=1}^{n} \operatorname{Res}[f(z), z_k] + \operatorname{Res}[f(z), \infty] = 0.
$$

**证明**：取一个大圆周 $C$ 正向（逆时针）包围所有有限奇点，由留数定理

$$
\oint_C f(z) dz = 2\pi i \sum_{k=1}^{n} \operatorname{Res}[f(z), z_k].
$$

另一方面，按无穷远点留数定义，$ \operatorname{Res}[f(z), \infty] = \frac{1}{2\pi i} \oint_{C^-} f(z) dz = -\frac{1}{2\pi i} \oint_C f(z) dz $。因此

$$
\oint_C f(z) dz = -2\pi i \operatorname{Res}[f(z), \infty].
$$

比较两式得

$$
2\pi i \sum_{k=1}^{n} \operatorname{Res}[f(z), z_k] = -2\pi i \operatorname{Res}[f(z), \infty],
$$

即 $\sum \operatorname{Res}[f(z), z_k] + \operatorname{Res}[f(z), \infty] = 0$。$\square$

该定理常用于简化计算：当有限奇点处留数和难求时，可转而计算无穷远点的留数。

---

### 16.7 利用无穷远点留数计算积分（正难则反）

**例2**：计算 $I = \oint_{|z|=4} \frac{z^{15}}{(z^4+2)^3 (z^2+1)^2} dz$。

**解**：被积函数 $f(z)$ 在 $|z|=4$ 内部有多个极点：$z=\pm i$（二阶）及 $z^4+2=0$ 的四个根 $\sqrt[4]{2}\, e^{i(\pi+2k\pi)/4}$（三阶），直接计算留数非常繁琐。考虑利用全平面留数和为零。

$f(z)$ 在 $|z|>4$ 内无有限奇点（所有极点都在圆内），故无穷远点 $\infty$ 是唯一的外部奇点。由留数和定理：

$$
\sum_{\text{有限奇点}} \operatorname{Res}[f(z), z_k] = - \operatorname{Res}[f(z), \infty].
$$

从而

$$
I = 2\pi i \sum \operatorname{Res}[f(z), z_k] = -2\pi i \operatorname{Res}[f(z), \infty].
$$

计算 $\operatorname{Res}[f(z), \infty]$ 用变换公式。令 $w=1/z$，则 $z=1/w$，$dz=-dw/w^2$，且

$$
f(z) = \frac{(1/w)^{15}}{\left((1/w)^4+2\right)^3 \left((1/w)^2+1\right)^2}
= \frac{w^{-15}}{\left(w^{-4}+2\right)^3 \left(w^{-2}+1\right)^2}.
$$

化简分母：

$$
(w^{-4}+2)^3 = \left(\frac{1+2w^4}{w^4}\right)^3 = \frac{(1+2w^4)^3}{w^{12}},
$$
$$
(w^{-2}+1)^2 = \left(\frac{1+w^2}{w^2}\right)^2 = \frac{(1+w^2)^2}{w^{4}}.
$$

因此

$$
f(z) = w^{-15} \cdot \frac{w^{12}}{(1+2w^4)^3} \cdot \frac{w^{4}}{(1+w^2)^2} = \frac{w^{1}}{(1+2w^4)^3 (1+w^2)^2}.
$$

于是

$$
\frac{1}{w^2} f\left(\frac{1}{w}\right) = \frac{1}{w^2} \cdot \frac{w}{(1+2w^4)^3 (1+w^2)^2} = \frac{1}{w (1+2w^4)^3 (1+w^2)^2}.
$$

由变换公式，

$$
\operatorname{Res}[f(z), \infty] = - \operatorname{Res}\left[ \frac{1}{w^2} f(1/w), 0 \right] = - \operatorname{Res}\left[ \frac{1}{w (1+2w^4)^3 (1+w^2)^2}, 0 \right].
$$

在 $w=0$ 附近，被积函数 $\frac{1}{w} \cdot \frac{1}{(1+2w^4)^3 (1+w^2)^2}$ 的洛朗展开中，$\frac{1}{w}$ 项的系数即为 $1$（因为后部分在 $w=0$ 处值为 $1$）。所以

$$
\operatorname{Res}\left[ \frac{1}{w (1+2w^4)^3 (1+w^2)^2}, 0 \right] = 1.
$$

因此 $\operatorname{Res}[f(z), \infty] = -1$，从而

$$
I = -2\pi i \cdot (-1) = 2\pi i.
$$

---

## 第17章 留数在实积分计算中的应用

### 概述

留数定理是计算某些实积分的有力工具。其核心思想是：将实积分视为复平面上某个围道积分的一部分，通过巧妙地构造围道并计算围道内奇点的留数，从而得到原实积分的值。

本章将系统介绍以下几类实积分的计算方法：

- 有理三角函数的全周期积分
- 有理函数的无穷反常积分
- 含指数因子 $e^{iax}$ 的无穷积分（Fourier型积分）
- 积分路径上含有奇点的主值积分
- 涉及多值函数的积分（含幂函数或对数函数）

同时，我们将详细证明大圆弧引理、小圆弧引理以及Jordan引理，这些是围道积分估计的核心工具。

---

### 17.1 围道积分估计引理

#### 17.1.1 大圆弧引理

**引理**（*Large Arc Lemma*）：设 $f(z)$ 在圆弧 $C_R: z = z_0 + R e^{i\theta}, \theta \in [\alpha, \beta]$ 上连续，且
$$
\lim_{R \to \infty} (z - z_0) f(z) = A
$$
（$A$ 为有限常数），则
$$
\lim_{R \to \infty} \int_{C_R} f(z) \, dz = i A (\beta - \alpha).
$$

**证明**：由极限定义，对任意 $\varepsilon > 0$，存在 $M > 0$，当 $|z - z_0| > M$ 时，有 $|(z - z_0)f(z) - A| < \varepsilon$。取 $R > M$，则
$$
\begin{aligned}
\left| \int_{C_R} f(z) dz - \int_{\alpha}^{\beta} iA \, d\theta \right|
&= \left| \int_{\alpha}^{\beta} [f(z_0+Re^{i\theta}) iRe^{i\theta} - iA] \, d\theta \right| \\
&= \left| \int_{\alpha}^{\beta} i\left[(z - z_0)f(z) - A\right] d\theta \right| \\
&\le \int_{\alpha}^{\beta} |(z - z_0)f(z) - A| \, d\theta \\
&< \varepsilon (\beta - \alpha).
\end{aligned}
$$
由于 $\varepsilon$ 任意，故极限成立。$\square$

**推论**：若 $\lim_{R \to \infty} \max_{z \in C_R} |z f(z)| = 0$，则 $\int_{C_R} f(z) dz \to 0$。特别地，当 $f(z) = \frac{P(z)}{Q(z)}$ 为有理函数且 $\deg Q \ge \deg P + 2$ 时，$\int_{C_R} f(z) dz \to 0$。

---

#### 17.1.2 小圆弧引理

**引理**（*Small Arc Lemma*）：设 $f(z)$ 在圆弧 $C_\delta: z = z_0 + \delta e^{i\theta}, \theta \in [\alpha, \beta]$ 上连续，且
$$
\lim_{z \to z_0} (z - z_0) f(z) = A,
$$
则
$$
\lim_{\delta \to 0} \int_{C_\delta} f(z) \, dz = i A (\beta - \alpha).
$$

**证明**：与上述证明完全类似，利用极限定义，对任意 $\varepsilon > 0$，存在 $\eta > 0$，当 $0<|z-z_0|<\eta$ 时 $|(z-z_0)f(z)-A|<\varepsilon$。取 $\delta < \eta$，则
$$
\left| \int_{C_\delta} f(z) dz - iA(\beta-\alpha) \right|
= \left| \int_{\alpha}^{\beta} i[(z-z_0)f(z)-A] d\theta \right|
\le \varepsilon (\beta-\alpha).
$$
因此极限成立。$\square$

该引理用于计算围道绕过孤立奇点时小圆弧的贡献。注意：若 $A=0$，则小圆弧积分为零；若 $A \neq 0$，则贡献为 $iA$ 乘圆心角。**方向**：若圆弧是顺时针方向，则应取负号，即 $\int_{C_\delta^+} f(z) dz = -iA(\beta-\alpha)$。

---

#### 17.1.3 Jordan引理

**引理**（*Jordan's Lemma*）：设 $f(z)$ 在上半平面 $\operatorname{Im}(z) \ge 0$ 和实轴上连续，且当 $|z| \to \infty$ 时 $f(z) \to 0$。则对任意正数 $a > 0$，沿上半圆周 $C_R: z = R e^{i\theta}, \theta \in [0, \pi]$ 的积分满足
$$
\lim_{R \to \infty} \int_{C_R} f(z) e^{i a z} \, dz = 0.
$$

**证明**：在 $C_R$ 上，$z = Re^{i\theta}$，$dz = iRe^{i\theta}d\theta$，$e^{iaz} = e^{iaR(\cos\theta + i\sin\theta)} = e^{-aR\sin\theta} e^{iaR\cos\theta}$。于是
$$
\begin{aligned}
\left| \int_{C_R} f(z) e^{iaz} dz \right|
&\le \int_0^{\pi} |f(Re^{i\theta})| e^{-aR\sin\theta} R \, d\theta \\
&\le \left( \max_{0\le\theta\le\pi} |f(Re^{i\theta})| \right) \cdot R \int_0^{\pi} e^{-aR\sin\theta} d\theta.
\end{aligned}
$$
由于 $\sin\theta$ 在 $[0,\pi]$ 上非负且对称，有 $\int_0^{\pi} e^{-aR\sin\theta} d\theta = 2\int_0^{\pi/2} e^{-aR\sin\theta} d\theta$。利用不等式 $\sin\theta \ge \frac{2}{\pi}\theta$（当 $0\le\theta\le\pi/2$），得
$$
\int_0^{\pi/2} e^{-aR\sin\theta} d\theta \le \int_0^{\pi/2} e^{-aR \cdot \frac{2}{\pi}\theta} d\theta = \frac{\pi}{2aR} (1 - e^{-aR}) \le \frac{\pi}{2aR}.
$$
因此
$$
R \int_0^{\pi} e^{-aR\sin\theta} d\theta \le R \cdot 2 \cdot \frac{\pi}{2aR} = \frac{\pi}{a}.
$$
令 $M_R = \max_{0\le\theta\le\pi} |f(Re^{i\theta})|$，则 $\left| \int_{C_R} f(z) e^{iaz} dz \right| \le M_R \cdot \frac{\pi}{a}$。由条件 $M_R \to 0$（当 $R\to\infty$），故积分趋于零。$\square$

**注**：当 $a<0$ 时，应取下半平面构造围道。Jordan引理是计算傅里叶型积分 $\int_{-\infty}^{\infty} f(x)e^{iax}dx$ 的关键。

---

### 17.2 有理三角函数的全周期积分

#### 问题形式

$$
I = \int_{0}^{2\pi} R(\cos\theta, \sin\theta) \, d\theta,
$$
其中 $R(u,v)$ 是 $u,v$ 的有理函数，且在积分区间上分母不为零。

#### 变换方法

令 $z = e^{i\theta}$，则
$$
\cos\theta = \frac{z+z^{-1}}{2}, \quad \sin\theta = \frac{z-z^{-1}}{2i}, \quad d\theta = \frac{dz}{i z}.
$$
当 $\theta$ 从 $0$ 到 $2\pi$ 时，$z$ 沿单位圆 $|z|=1$ 逆时针绕行一周。代入得
$$
I = \oint_{|z|=1} R\left( \frac{z+z^{-1}}{2}, \frac{z-z^{-1}}{2i} \right) \frac{dz}{i z} = \oint_{|z|=1} F(z) \, dz.
$$
其中 $F(z)$ 是 $z$ 的有理函数。由留数定理，
$$
I = 2\pi i \sum_{|z_k|<1} \operatorname{Res}[F(z), z_k].
$$

#### 例题

计算 $I = \int_0^{2\pi} \frac{1}{a + \cos\theta} d\theta$，其中 $a>1$。

**解**：令 $z = e^{i\theta}$，$\cos\theta = \frac{z+z^{-1}}{2}$，则
$$
I = \oint_{|z|=1} \frac{1}{a + \frac{z+z^{-1}}{2}} \cdot \frac{dz}{iz}
= \frac{2}{i} \oint_{|z|=1} \frac{dz}{z^2 + 2az + 1}.
$$
分母 $z^2+2az+1=0$ 的根为 $z = -a \pm \sqrt{a^2-1}$。由于 $a>1$，$| -a - \sqrt{a^2-1} | > 1$ 在圆外，$| -a + \sqrt{a^2-1} | < 1$ 在圆内。圆内只有单极点 $z_1 = -a + \sqrt{a^2-1}$。其留数为
$$
\operatorname{Res}\left[ \frac{1}{z^2+2az+1}, z_1 \right] = \frac{1}{2z_1+2a} = \frac{1}{2\sqrt{a^2-1}}.
$$
因此
$$
I = \frac{2}{i} \cdot 2\pi i \cdot \frac{1}{2\sqrt{a^2-1}} = \frac{2\pi}{\sqrt{a^2-1}}.
$$

---

### 17.3 有理函数的无穷反常积分

#### 问题形式

$$
I = \int_{-\infty}^{\infty} \frac{P(x)}{Q(x)} \, dx,
$$
其中 $P(x), Q(x)$ 是实系数多项式，$\deg Q \ge \deg P + 2$，且 $Q(x) \neq 0$ 在实轴上。

#### 处理方法

构造上半平面的半圆形围道：实轴线段 $[-R,R]$ 加上大圆弧 $C_R: z = Re^{i\theta}, \theta \in [0,\pi]$。取 $R$ 充分大使得所有上半平面的极点都位于围道内。则
$$
\oint_{\text{contour}} f(z) dz = \int_{-R}^{R} f(x) dx + \int_{C_R} f(z) dz = 2\pi i \sum_{\operatorname{Im}(z_k)>0} \operatorname{Res}[f(z), z_k].
$$
由大圆弧引理（$\deg Q \ge \deg P + 2$ 保证 $|zf(z)| \to 0$），$\int_{C_R} f(z) dz \to 0$。令 $R \to \infty$ 得
$$
I = 2\pi i \sum_{\operatorname{Im}(z_k)>0} \operatorname{Res}[f(z), z_k].
$$

#### 例题

计算 $I = \int_{-\infty}^{\infty} \frac{dx}{(x^2+1)(x^2+4)}$。

**解**：$f(z) = \frac{1}{(z^2+1)(z^2+4)} = \frac{1}{(z-i)(z+i)(z-2i)(z+2i)}$。上半平面内的极点为 $z=i$（一阶）和 $z=2i$（一阶）。
$$
\operatorname{Res}[f,i] = \lim_{z\to i} (z-i)f(z) = \frac{1}{(i+i)(i^2+4)} = \frac{1}{2i \cdot 3} = \frac{1}{6i},
$$
$$
\operatorname{Res}[f,2i] = \lim_{z\to 2i} (z-2i)f(z) = \frac{1}{((2i)^2+1)(2i+2i)} = \frac{1}{(-4+1) \cdot 4i} = \frac{1}{-12i}.
$$
因此
$$
I = 2\pi i \left( \frac{1}{6i} - \frac{1}{12i} \right) = 2\pi i \cdot \frac{1}{12i} = \frac{\pi}{6}.
$$

---

### 17.4 含 $e^{iax}$ 的无穷积分（Fourier型）

#### 问题形式

$$
I = \int_{-\infty}^{\infty} f(x) e^{i a x} dx, \quad a > 0,
$$
其中 $f(z)$ 在实轴上解析，且当 $|z|\to\infty$ 时 $f(z)\to 0$ 足够快（例如有理函数且分母次数比分子至少高一次）。

#### 处理方法


采用上半平面的半圆形围道。由Jordan引理，大圆弧积分 $\int_{C_R} f(z) e^{iaz} dz \to 0$。于是
$$
\int_{-\infty}^{\infty} f(x) e^{iax} dx = 2\pi i \sum_{\operatorname{Im}(z_k)>0} \operatorname{Res}[f(z) e^{iaz}, z_k].
$$
通过分离实部和虚部，可计算 $\int_{-\infty}^{\infty} f(x) \cos(ax) dx$ 和 $\int_{-\infty}^{\infty} f(x) \sin(ax) dx$。

#### 例题


计算 $I = \int_{-\infty}^{\infty} \frac{\cos x}{x^2+1} dx$。

**解**：考虑 $J = \int_{-\infty}^{\infty} \frac{e^{ix}}{x^2+1} dx$。上半平面内极点为 $z=i$（一阶）。留数：
$$
\operatorname{Res}\left[ \frac{e^{iz}}{z^2+1}, i \right] = \lim_{z\to i} (z-i) \frac{e^{iz}}{(z-i)(z+i)} = \frac{e^{-1}}{2i}.
$$
因此 $J = 2\pi i \cdot \frac{e^{-1}}{2i} = \frac{\pi}{e}$。取实部得
$$
\int_{-\infty}^{\infty} \frac{\cos x}{x^2+1} dx = \operatorname{Re}(J) = \frac{\pi}{e}.
$$

---

### 17.5 积分路径上含有奇点的主值积分


#### 问题形式

当被积函数在实轴上有孤立奇点时，通常考虑柯西主值（Cauchy principal value）：
$$
P.V. \int_{-\infty}^{\infty} f(x) dx = \lim_{\epsilon \to 0^+} \left( \int_{-\infty}^{x_0-\epsilon} + \int_{x_0+\epsilon}^{\infty} \right) f(x) dx,
$$
其中 $x_0$ 是实轴上的奇点。

#### 处理方法

构造上半平面围道，但在实轴奇点处用小半圆弧绕过（通常取上半平面小半圆）。应用小圆弧引理计算该小弧的贡献，然后取极限。

#### 例题

计算 $I = P.V. \int_{-\infty}^{\infty} \frac{\sin x}{x} dx$。

**解**：考虑 $J = P.V. \int_{-\infty}^{\infty} \frac{e^{ix}}{x} dx$。围道：$[-R, -\epsilon] \cup C_\epsilon^+ \cup [\epsilon, R] \cup C_R^+$，其中 $C_\epsilon^+$ 是上半平面小半圆 $z = \epsilon e^{i\theta}, \theta: \pi \to 0$（顺时针方向），$C_R^+$ 是上半平面大半圆。在 $C_\epsilon^+$ 上，$\frac{e^{iz}}{z}$ 满足 $(z-0)\cdot \frac{e^{iz}}{z} = e^{iz} \to 1$ 当 $z\to 0$。由小圆弧引理（顺时针方向为负）：
$$
\int_{C_\epsilon^+} \frac{e^{iz}}{z} dz = - i \cdot 1 \cdot (\pi - 0) = -i\pi.
$$
大圆弧积分由Jordan引理为0。围道内无奇点，故总积分为0：
$$
\lim_{\epsilon\to0,R\to\infty} \left( \int_{-R}^{-\epsilon} \frac{e^{ix}}{x} dx + \int_{\epsilon}^{R} \frac{e^{ix}}{x} dx \right) - i\pi = 0.
$$
因此 $J = i\pi$。取虚部得 $P.V. \int_{-\infty}^{\infty} \frac{\sin x}{x} dx = \operatorname{Im}(i\pi) = \pi$。

---

### 17.6 涉及多值函数的积分

#### 问题形式

形如 $\int_0^{\infty} x^{\alpha-1} R(x) dx$ 或 $\int_0^{\infty} (\ln x) R(x) dx$，其中 $\alpha$ 非整数，$R(x)$ 为有理函数。

#### 处理方法

采用“锁孔”围道（keyhole contour），它由两个同心圆（半径 $R$ 和 $\epsilon$）以及沿正实轴上下两侧的线段构成。由于被积函数存在支点（通常取 $z=0$），需指定辐角范围，例如取 $0 \le \arg z < 2\pi$，此时正实轴上下两侧的辐角分别为 $0$ 和 $2\pi$，从而函数值相差一个因子 $e^{2\pi i \alpha}$。通过计算围道积分并取极限，可得到所需积分。

#### 例题

计算 $I = \int_0^{\infty} \frac{dx}{x^{\frac12}(1+x)}$。

**解**：设 $f(z) = \frac{1}{z^{1/2}(1+z)}$，取 $z^{1/2}$ 的主支：$z^{1/2} = |z|^{1/2} e^{i\arg z/2}$，$\arg z \in (0,2\pi)$。在正实轴上方，$\arg z = 0$，$z^{1/2} = \sqrt{x}$；在正实轴下方，$\arg z = 2\pi$，$z^{1/2} = \sqrt{x} e^{i\pi} = -\sqrt{x}$。围道为锁孔形：大圆 $C_R$（半径 $R$），小圆 $C_\epsilon$（半径 $\epsilon$），以及沿正实轴的上边缘 $L^+$（$z=x$，$x:\epsilon\to R$）和下边缘 $L^-$（$z=x$，$x:R\to \epsilon$）。由留数定理，
$$
\int_{C_R} + \int_{C_\epsilon} + \int_{L^+} + \int_{L^-} = 2\pi i \operatorname{Res}[f(z), -1].
$$
在 $L^+$ 上，$f(x) = \frac{1}{\sqrt{x}(1+x)}$。在 $L^-$ 上，$f(x) = \frac{1}{(-\sqrt{x})(1+x)} = -\frac{1}{\sqrt{x}(1+x)}$。因此
$$
\int_{L^+} + \int_{L^-} = \int_{\epsilon}^{R} \frac{dx}{\sqrt{x}(1+x)} + \int_{R}^{\epsilon} \left(-\frac{dx}{\sqrt{x}(1+x)}\right) = 2 \int_{\epsilon}^{R} \frac{dx}{\sqrt{x}(1+x)}.
$$
当 $R\to\infty$，$\int_{C_R} \to 0$（因为 $|zf(z)| \sim R^{-1/2} \to 0$）；当 $\epsilon\to 0$，$\int_{C_\epsilon} \to 0$（因为 $|zf(z)| \sim \epsilon^{1/2} \to 0$）。留数：
$$
\operatorname{Res}[f, -1] = \lim_{z\to -1} (z+1) \frac{1}{z^{1/2}(z+1)} = \frac{1}{(-1)^{1/2}}.
$$
取 $-1 = e^{i\pi}$，则 $(-1)^{1/2} = e^{i\pi/2} = i$，故留数为 $\frac{1}{i} = -i$。于是
$$
2 \int_0^{\infty} \frac{dx}{\sqrt{x}(1+x)} = 2\pi i \cdot (-i) = 2\pi.
$$
因此 $I = \pi$。

---

### 17.7 含参积分与特殊技巧

#### 17.7.1 引入参数求导法（Feynman技巧）

有时直接积分困难，可考虑在积分中引入一个参数，对参数求导，将问题转化为微分方程或更简单的积分。

例：$I(a) = \int_0^{\infty} \frac{\cos(ax)}{x^2+1} dx$，已知 $I(0) = \pi/2$。对 $a$ 求导得 $I'(a) = -\int_0^{\infty} \frac{x\sin(ax)}{x^2+1} dx$，再通过分部积分或复分析求解微分方程。最终得 $I(a) = \frac{\pi}{2} e^{-a}$。

#### 17.7.2 利用对称性与积分变换

对于形如 $\int_0^{\infty} \frac{\ln x}{x^2+1} dx$ 的积分，可构造 $f(z) = \frac{(\ln z)^2}{z^2+1}$ 的锁孔围道，利用上下边缘对数函数的差值，最终得到值为 $0$（因为被积函数是奇函数经变换）。

---

### 17.8 总结

| 积分类型         | 典型形式                                          | 常用围道       | 关键引理      | 留数公式                                                     |
| ---------------- | ------------------------------------------------- | -------------- | ------------- | ------------------------------------------------------------ |
| 三角有理式       | $\int_0^{2\pi} R(\cos\theta,\sin\theta)d\theta$   | 单位圆 $|z|=1$ | 直接代换      | $2\pi i\sum_{|z_k|<1}\operatorname{Res}F(z)$                 |
| 有理函数无穷积分 | $\int_{-\infty}^{\infty}\frac{P(x)}{Q(x)}dx$      | 上半半圆       | 大圆弧引理    | $2\pi i\sum_{\operatorname{Im}z_k>0}\operatorname{Res}f(z)$  |
| Fourier型        | $\int_{-\infty}^{\infty}f(x)e^{iax}dx$            | 上半半圆       | Jordan引理    | $2\pi i\sum_{\operatorname{Im}z_k>0}\operatorname{Res}[f(z)e^{iaz}]$ |
| 实轴奇点主值     | $P.V.\int_{-\infty}^{\infty}\frac{g(x)}{x-x_0}dx$ | 半圆带小圆弧   | 小圆弧引理    | 主值 = $2\pi i\sum \operatorname{Res} \pm \pi i \operatorname{Res}_{x_0}$ |
| 多值函数积分     | $\int_0^{\infty}x^{\alpha-1}R(x)dx$               | 锁孔围道       | 大/小圆弧引理 | 留数贡献乘以 $(1-e^{2\pi i\alpha})$                          |

掌握这些基本方法和引理的证明，能够处理复变函数中绝大多数利用留数计算实积分的典型问题。

---

## 第18章 幅角原理与儒歇定理（补充）

这两个定理是留数定理的重要推论，用于计算解析函数在区域内的零点个数。

### 18.1 对数留数与幅角原理

设 $f(z)$ 在简单闭曲线 $C$ 上解析且无零点，在 $C$ 内部除有限个极点外解析。考虑积分
$$
\frac{1}{2\pi i} \oint_C \frac{f'(z)}{f(z)} dz,
$$
称为 $f(z)$ 关于 $C$ 的对数留数。它等于 $f(z)$ 在 $C$ 内部的零点个数（按重数计）减去极点个数（按阶数计）。即
$$
\frac{1}{2\pi i} \oint_C \frac{f'(z)}{f(z)} dz = N - P,
$$
其中 $N$ 为零点个数，$P$ 为极点个数。

若 $f(z)$ 在 $C$ 内解析且无极点，则 $P=0$，该积分等于零点个数。
同时，注意到 $\frac{f'(z)}{f(z)} = \frac{d}{dz} \operatorname{Ln} f(z)$，积分表示 $\operatorname{Ln} f(z)$ 绕 $C$ 一周的改变量除以 $2\pi i$，即 $\frac{1}{2\pi i} \Delta_C \operatorname{Ln} f(z)$。而 $\operatorname{Ln} f(z) = \ln|f(z)| + i \arg f(z)$，其实部回到原值，虚部变化量为 $i \Delta_C \arg f(z)$。因此
$$
\frac{1}{2\pi i} \oint_C \frac{f'(z)}{f(z)} dz = \frac{\Delta_C \arg f(z)}{2\pi}.
$$
此即**幅角原理**（*Argument principle*）：当 $z$ 沿 $C$ 正向绕行一周时，$f(z)$ 的辐角的增量除以 $2\pi$ 等于 $f(z)$ 在 $C$ 内的零点个数与极点个数之差。

特别地，若 $f$ 解析且无极点，则零点个数 $N = \frac{1}{2\pi} \Delta_C \arg f(z)$。

### 18.2 儒歇定理（Rouché's Theorem）

**定理**：设 $C$ 为简单闭曲线，$f(z)$ 和 $g(z)$ 在 $C$ 及其内部解析，且在 $C$ 上满足 $|f(z)| > |g(z)|$，则 $f(z)$ 和 $f(z)+g(z)$ 在 $C$ 内部有相同个数的零点（按重数计）。

**证明思路**：令 $F(z) = f(z) + g(z) = f(z)\left(1 + \frac{g(z)}{f(z)}\right)$。由条件在 $C$ 上 $|g/f| < 1$，故 $1 + g/f$ 的辐角变化为 $0$，从而 $F$ 的辐角变化等于 $f$​ 的辐角变化，由幅角原理即得零点个数相等。

**证明**

**Step 1. 边界无零点**
由条件，在 $C$ 上 $|f(z)| > |g(z)| \ge 0$，故 $f(z) \neq 0$。又

$$
|f(z)+g(z)| \ge |f(z)| - |g(z)| > 0,
$$

因而 $f(z)+g(z)$ 在 $C$ 上亦无零点。所以两个函数在围道 $C$ 上均不为零。

**Step 2. 构造含参函数族**
对每一个实数 $t \in [0,1]$，定义

$$
F_t(z) = f(z) + t\,g(z).
$$

显然 $F_t(z)$ 在 $C$ 及其内部解析。在 $C$ 上，由于 $t \le 1$，有

$$
|F_t(z)| \ge |f(z)| - t|g(z)| \ge |f(z)| - |g(z)| > 0.
$$

因此对一切 $t \in [0,1]$，$F_t(z)$ 在 $C$ 上没有零点。

**Step 3. 零点个数的连续性**
记 $N(t)$ 为 $F_t(z)$ 在 $C$ 内部的零点个数（计重数）。由**幅角原理**（或对数留数公式），因为 $F_t$ 在 $C$ 内解析、在 $C$ 上不为零，我们有

$$
N(t) = \frac{1}{2\pi i} \oint_C \frac{F_t'(z)}{F_t(z)}\,dz. \tag{1}
$$

理由简述：被积函数 $\dfrac{F_t'}{F_t}$ 在 $C$ 内部的奇点恰为 $F_t$ 的零点；若 $z_0$ 是 $F_t$ 的 $m$ 阶零点，则它是一阶极点且留数为 $m$，留数定理给出总留数之和 $=$ $N(t)$。

**Step 4. 同伦不变性**
注意到对于固定的 $z \in C$，函数 $t \mapsto \dfrac{F_t'(z)}{F_t(z)}$ 在 $[0,1]$ 上连续；又因为积分路径 $C$ 是紧集，整个被积函数关于 $t$ 一致连续，故 $N(t)$ 是 $[0,1]$ 上的**连续函数**。
但 $N(t)$ 只取非负整数值（零点个数必为整数），连续且在整数集上取值的函数必然是**常数**。因此

$$
N(t) \equiv \text{const}, \qquad \forall t \in [0,1].
$$

**Step 5. 比较 $t=0$ 与 $t=1$**
当 $t=0$ 时，$F_0(z) = f(z)$；当 $t=1$ 时，$F_1(z) = f(z)+g(z)$。由常值性得到

$$
N(0) = N(1).
$$

而 $N(0)$ 就是 $f(z)$ 在 $C$ 内部的零点个数，$N(1)$ 就是 $f(z)+g(z)$ 在 $C$ 内部的零点个数。这就完成了儒歇定理的证明。 $\square$

---

**注记**

- 上述证明本质上利用了 “解析函数零点个数的同伦不变性”，完全避免了复杂的对数多值性讨论。
- 若 $f$ 与 $g$ 在 $C$ 内仅仅是亚纯（允许有极点），则条件 $|f|>|g|$ 仍能导出 $f$ 与 $f+g$ 在 $C$ 内的零点个数与极点个数的**差值**相同，证明完全相同，只需将 $N(t)$ 解释为 “零点数 $-$ 极点数” 即可。
- 儒歇定理是复分析中最重要的计数工具之一，常用于判断多项式根的位置（例如证明代数学基本定理）以及研究算子谱的分布。


---

## 第19章 典型围道补充与习题

### 19.1 矩形围道

用于计算形如 $\int_{-\infty}^{\infty} e^{-x^2} dx$ 或含双曲函数的积分。

例：证明 $\int_{-\infty}^{\infty} e^{-x^2} dx = \sqrt{\pi}$ （复变方法：取矩形围道，利用 $f(z)=e^{-z^2}$ 的积分与路径无关及当纵向边趋于无穷时积分为零）。

### 19.2 扇形围道

用于计算 $\int_0^{\infty} x^{\alpha-1} R(x) dx$ 或傅里叶型积分在某些角度上的变体。

### 19.3 习题精选

1. 计算 $\int_0^{2\pi} \frac{d\theta}{5+4\sin\theta}$。
2. 计算 $P.V. \int_{-\infty}^{\infty} \frac{x \cos x}{x^2 - 1} dx$。
3. 求 $\sum_{n=1}^{\infty} \frac{1}{n^2}$ 利用留数定理（考虑 $\pi \cot \pi z / z^2$）。
4. 证明：若 $f(z)$ 在单位圆内解析且 $|f(z)|\le 1$，$f(0)=0$，则 $|f(z)|\le |z|$ 且 $|f'(0)|\le 1$（Schwarz引理，可用最大模原理证明）。

---

