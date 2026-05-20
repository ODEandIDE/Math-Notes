
# 线性代数核心笔记

[TOC]

## 第一章 线性方程组与矩阵

### 1.1 线性方程组及其解法

#### 1.1.1 基本概念

**线性方程**：含有未知量 $x_1,x_2,\dots,x_n$ 的一次方程
$$
a_1x_1 + a_2x_2 + \cdots + a_nx_n = b,
$$
其中 $a_i$ 为系数，$b$ 为常数项。当 $b=0$ 时称为**齐次方程**；否则为**非齐次方程**。

**线性方程组**：由 $m$ 个方程构成的集合
$$
\begin{cases}
a_{11}x_1 + a_{12}x_2 + \cdots + a_{1n}x_n = b_1 \\
a_{21}x_1 + a_{22}x_2 + \cdots + a_{2n}x_n = b_2 \\
\quad \vdots \\
a_{m1}x_1 + a_{m2}x_2 + \cdots + a_{mn}x_n = b_m
\end{cases}
$$

方程组的**解**是一组数 $(s_1,s_2,\dots,s_n)$，代入后使每个方程成为恒等式。解集可能为空（无解）、含唯一解或无穷多解。

#### 1.1.2 矩阵记法

**系数矩阵**：
$$
A = \begin{pmatrix}
a_{11} & a_{12} & \dots & a_{1n} \\
a_{21} & a_{22} & \dots & a_{2n} \\
\vdots & \vdots & \ddots & \vdots \\
a_{m1} & a_{m2} & \dots & a_{mn}
\end{pmatrix}
$$

**增广矩阵**：
$$
\tilde A = [A \mid \mathbf{b}] = \left(\begin{array}{cccc|c}
a_{11} & a_{12} & \cdots & a_{1n} & b_1 \\
a_{21} & a_{22} & \cdots & a_{2n} & b_2 \\
\vdots & \vdots & \ddots & \vdots & \vdots \\
a_{m1} & a_{m2} & \cdots & a_{mn} & b_m
\end{array}\right)
$$

方程组的求解完全由增广矩阵确定。我们通过**初等行变换**化简矩阵来求解。

#### 1.1.3 初等行变换与行等价

**定义**：以下三种操作称为初等行变换：


1. （换行）交换两行；
2. （倍乘）某行乘以一个非零常数 $c$；
3. （倍加）某行的常数倍加到另一行。

若矩阵 $A$ 经过一系列初等行变换变成 $B$，则称 $A$ 与 $B$ **行等价**，记作 $A\sim B$。行等价关系是等价关系（自反、对称、传递）。

**重要性质**：初等行变换不改变方程组的解集。因此，我们可以将增广矩阵化为更简单的形式来求解。

#### 1.1.4 行阶梯形与简化行阶梯形

**行阶梯形 (Row Echelon Form, REF)**：

- 每一非零行的首个非零元素（称为**主元**）出现在上一行主元的右侧；
- 全零行位于矩阵底部；
- 通常要求主元为 1（但有时不强制，简化阶梯形才要求）。

**简化行阶梯形 (Reduced Row Echelon Form, RREF)**：

- 满足 REF 的所有条件；
- 每个主元都是 1；
- 每个主元所在列的其余元素均为 0。

**定理 1.1（简化行阶梯形的唯一性）**：每个矩阵行等价于唯一的简化行阶梯形矩阵。

**证明梗概**：通过归纳法，可证任何两个行等价的矩阵化为阶梯形后，主元位置必须相同；而简化阶梯形由主元列唯一确定，因此唯一。详见附录 A。

#### 1.1.5 求解算法：高斯消元法

**步骤**：

1. 写出增广矩阵 $\tilde A$。
2. 用初等行变换将 $\tilde A$ 化为行阶梯形（前向消元）。
3. 判断解的情况：
   - 若阶梯形中出现形如 $[0\ \dots\ 0 \mid c]$ 且 $c\neq 0$ 的行，则方程无解；
   - 否则有解，继续化简为简化行阶梯形（后向代入）。
4. 从简化行阶梯形中读出解：主元对应的变量为**基本变量**，其余变量为**自由变量**。自由变量可取任意值，解集用参数向量形式表示。

**例 1.1** 解方程组：
$$
\begin{cases}
x_1 - 2x_2 + x_3 = 0 \\
2x_2 - 8x_3 = 8 \\
-4x_1 + 5x_2 + 9x_3 = -9
\end{cases}
$$

**解**：增广矩阵
$$
\left(\begin{array}{ccc|c}
1 & -2 & 1 & 0 \\
0 & 2 & -8 & 8 \\
-4 & 5 & 9 & -9
\end{array}\right)
$$
将第一行的 4 倍加到第三行：
$$
\left(\begin{array}{ccc|c}
1 & -2 & 1 & 0 \\
0 & 2 & -8 & 8 \\
0 & -3 & 13 & -9
\end{array}\right)
$$
第二行乘以 $\frac12$：
$$
\left(\begin{array}{ccc|c}
1 & -2 & 1 & 0 \\
0 & 1 & -4 & 4 \\
0 & -3 & 13 & -9
\end{array}\right)
$$
将第二行的 3 倍加到第三行：
$$
\left(\begin{array}{ccc|c}
1 & -2 & 1 & 0 \\
0 & 1 & -4 & 4 \\
0 & 0 & 1 & 3
\end{array}\right)
$$
此时已是行阶梯形。继续简化：第三行乘以 1（已满足），将第三行的适当倍数加到前两行以消除上方元素。

- 第二行 + 4×第三行：$[0\ 1\ 0\ 16]$
- 第一行 - 1×第三行：$[1\ -2\ 0\ -3]$
- 第一行 + 2×第二行：$[1\ 0\ 0\ 29]$

得简化行阶梯形：
$$
\left(\begin{array}{ccc|c}
1 & 0 & 0 & 29 \\
0 & 1 & 0 & 16 \\
0 & 0 & 1 & 3
\end{array}\right)
$$
解为 $x_1=29,\ x_2=16,\ x_3=3$。

**例 1.2** 解方程组：
$$
\begin{cases}
x_1 + 2x_2 - x_3 = 4 \\
2x_1 - x_2 + 3x_3 = 1
\end{cases}
$$

**解**：增广矩阵
$$
\left(\begin{array}{ccc|c}
1 & 2 & -1 & 4 \\
2 & -1 & 3 & 1
\end{array}\right)
\xrightarrow{R_2-2R_1}
\left(\begin{array}{ccc|c}
1 & 2 & -1 & 4 \\
0 & -5 & 5 & -7
\end{array}\right)
\xrightarrow{R_2/( -5)}
\left(\begin{array}{ccc|c}
1 & 2 & -1 & 4 \\
0 & 1 & -1 & \frac{7}{5}
\end{array}\right)
\xrightarrow{R_1-2R_2}
\left(\begin{array}{ccc|c}
1 & 0 & 1 & \frac{6}{5} \\
0 & 1 & -1 & \frac{7}{5}
\end{array}\right)
$$
基本变量 $x_1,x_2$，自由变量 $x_3$。解为
$$
\begin{pmatrix}
x_1 \\ x_2 \\ x_3
\end{pmatrix}
=
\begin{pmatrix}
\frac{6}{5} \\[2pt] \frac{7}{5} \\[2pt] 0
\end{pmatrix}
+
t
\begin{pmatrix}
-1 \\ 1 \\ 1
\end{pmatrix},\quad t\in\mathbb{R}.
$$

**例 1.3（无解情形）** 解方程组：
$$
\begin{cases}
x_1 + 2x_2 = 3 \\
2x_1 + 4x_2 = 7
\end{cases}
$$
**解**：增广矩阵 $\begin{pmatrix}1&2&3\\2&4&7\end{pmatrix} \xrightarrow{R_2-2R_1} \begin{pmatrix}1&2&3\\0&0&1\end{pmatrix}$，第二行为 $0x_1+0x_2=1$，矛盾，无解。

### 1.2 向量方程与矩阵方程

#### 1.2.1 向量与线性组合

$n$ 维列向量 $\mathbf{v} = (v_1,v_2,\dots,v_n)^T \in \mathbb{R}^n$。向量的加法与数乘遵循分量运算。

**线性组合**：给定向量 $\mathbf{v}_1,\mathbf{v}_2,\dots,\mathbf{v}_p \in \mathbb{R}^n$ 和标量 $c_1,\dots,c_p$，称
$$
\mathbf{y} = c_1\mathbf{v}_1 + c_2\mathbf{v}_2 + \cdots + c_p\mathbf{v}_p
$$
为这些向量的一个线性组合。$c_i$ 为权。

#### 1.2.2 向量方程

向量方程 $x_1\mathbf{a}_1 + x_2\mathbf{a}_2 + \cdots + x_n\mathbf{a}_n = \mathbf{b}$ 等价于以 $\mathbf{a}_1,\dots,\mathbf{a}_n$ 为列向量的矩阵 $A$ 的线性方程组 $A\mathbf{x}=\mathbf{b}$。求解此方程即求 $\mathbf{b}$ 能否写成 $A$ 的列向量的线性组合，以及若能的话，系数是什么。

**例 1.4** 将 $\mathbf{b} = \begin{pmatrix}3\\5\end{pmatrix}$ 表示为 $\mathbf{a}_1=\begin{pmatrix}1\\2\end{pmatrix}, \mathbf{a}_2=\begin{pmatrix}2\\1\end{pmatrix}$ 的线性组合。

解：解 $x_1\begin{pmatrix}1\\2\end{pmatrix}+x_2\begin{pmatrix}2\\1\end{pmatrix} = \begin{pmatrix}3\\5\end{pmatrix}$，即
$$
\begin{pmatrix}
1 & 2 \\
2 & 1
\end{pmatrix}
\begin{pmatrix}x_1\\x_2\end{pmatrix}
= \begin{pmatrix}3\\5\end{pmatrix}.
$$
解得 $x_1=\frac{7}{3}, x_2=\frac{1}{3}$，故 $\mathbf{b} = \frac73\mathbf{a}_1 + \frac13\mathbf{a}_2$。

#### 1.2.3 齐次方程组的解集

齐次方程 $A\mathbf{x}=\mathbf{0}$ 必有平凡解 $\mathbf{x}=\mathbf{0}$。是否存在非平凡解取决于是否有自由变量。

**定理 1.2**：若 $A$ 是 $m\times n$ 矩阵且 $m<n$（方程数小于未知数），则 $A\mathbf{x}=\mathbf{0}$ 必有非平凡解。
**证明**：行化简后主元个数最多为 $m$，因此至少存在 $n-m>0$ 个自由变量，从而有非零解。

**齐次解的参数向量形式**：通解可写为 $\mathbf{x} = t_1\mathbf{v}_1 + \cdots + t_k\mathbf{v}_k$，其中 $k$ 是自由变量个数，向量 $\mathbf{v}_i$ 是解空间的一组基。

**例 1.5** 求 $A = \begin{pmatrix}1&3&-2&0\\0&1&1&1\end{pmatrix}$ 的零空间基。

解：将 $A$ 化为简化阶梯形（此处略步骤），得到
$$
\begin{pmatrix}
1 & 0 & -5 & -3 \\
0 & 1 & 1 & 1
\end{pmatrix}
$$
自由变量 $x_3,x_4$。令 $x_3=1,x_4=0$ 得 $\mathbf{v}_1 = (5,-1,1,0)^T$；$x_3=0,x_4=1$ 得 $\mathbf{v}_2 = (3,-1,0,1)^T$。解集为 $\operatorname{span}\{\mathbf{v}_1,\mathbf{v}_2\}$。

#### 1.2.4 非齐次方程组的解集

**定理 1.3**：若 $A\mathbf{x}=\mathbf{b}$ 有一特解 $\mathbf{p}$，则其通解为 $\mathbf{p} + \operatorname{Nul}A$（即特解加上齐次通解）。
**证明**：设 $\mathbf{x}$ 为任意解，则 $A(\mathbf{x}-\mathbf{p}) = A\mathbf{x}-A\mathbf{p} = \mathbf{b}-\mathbf{b} = \mathbf{0}$，故 $\mathbf{x}-\mathbf{p}\in\operatorname{Nul}A$；反之，若 $\mathbf{v}\in\operatorname{Nul}A$，则 $A(\mathbf{p}+\mathbf{v})=\mathbf{b}$。因此解集为 $\mathbf{p} + \operatorname{Nul}A$。

### 1.3 线性无关与线性变换

#### 1.3.1 线性无关与线性相关

**定义**：$\mathbb{R}^n$ 中的向量组 $\{\mathbf{v}_1,\dots,\mathbf{v}_p\}$ 称为**线性无关**，若向量方程
$$
c_1\mathbf{v}_1 + c_2\mathbf{v}_2 + \cdots + c_p\mathbf{v}_p = \mathbf{0}
$$
只有零解 $c_1 = c_2 = \cdots = c_p = 0$。否则称它们**线性相关**。

**几何解释**：两个向量线性相关意味着它们共线；三个向量线性相关意味着它们共面。

**定理 1.4**：向量组线性相关 $\iff$ 至少有一个向量可表示为其余向量的线性组合。

**线性无关的判别准则**：将向量作为矩阵的列，构造 $A = [\mathbf{v}_1 \ \mathbf{v}_2 \ \cdots \ \mathbf{v}_p]$，然后行化简。若主元个数 $= p$，则列向量线性无关；若主元个数 $< p$，则线性相关。

**例 1.6** 判断向量组 $\mathbf{v}_1=(1,2,3)^T,\ \mathbf{v}_2=(4,5,6)^T,\ \mathbf{v}_3=(7,8,9)^T$ 是否线性无关。

解：构造矩阵 $\begin{pmatrix}1&4&7\\2&5&8\\3&6&9\end{pmatrix}$，行化简：
$$
\xrightarrow{R_2-2R_1,\ R_3-3R_1}
\begin{pmatrix}
1 & 4 & 7 \\
0 & -3 & -6 \\
0 & -6 & -12
\end{pmatrix}
\xrightarrow{R_3-2R_2}
\begin{pmatrix}
1 & 4 & 7 \\
0 & -3 & -6 \\
0 & 0 & 0
\end{pmatrix}.
$$
主元个数为 2，小于向量个数 3，故线性相关。事实上，$\mathbf{v}_3 = 2\mathbf{v}_2 - \mathbf{v}_1$。

**定理 1.5**：若向量组包含零向量，则必然线性相关。若向量组中向量个数大于其维数（$p > n$），则必然线性相关。

#### 1.3.2 线性变换简介

**定义**：映射 $T:\mathbb{R}^n \to \mathbb{R}^m$ 称为**线性变换**，若对所有 $\mathbf{u},\mathbf{v}\in\mathbb{R}^n$ 和标量 $c$，满足：

1. $T(\mathbf{u}+\mathbf{v}) = T(\mathbf{u}) + T(\mathbf{v})$；
2. $T(c\mathbf{u}) = c\,T(\mathbf{u})$。

**矩阵变换**：对任意 $m\times n$ 矩阵 $A$，定义 $T(\mathbf{x}) = A\mathbf{x}$，则 $T$ 是线性变换。反之，任何一个线性变换 $T:\mathbb{R}^n\to\mathbb{R}^m$ 都存在唯一的矩阵 $A$（称为 $T$ 的**标准矩阵**），使得 $T(\mathbf{x}) = A\mathbf{x}$。且 $A$ 的第 $j$ 列为 $T(\mathbf{e}_j)$，其中 $\mathbf{e}_j$ 是 $\mathbb{R}^n$ 的标准基向量。

**例 1.7** 求旋转变换 $R_\theta: \mathbb{R}^2\to\mathbb{R}^2$ 将向量逆时针旋转 $\theta$ 角的矩阵。

解：$\mathbf{e}_1 = (1,0)^T$ 旋转后为 $(\cos\theta,\sin\theta)^T$；$\mathbf{e}_2 = (0,1)^T$ 旋转后为 $(-\sin\theta,\cos\theta)^T$。故标准矩阵为
$$
A = \begin{pmatrix}
\cos\theta & -\sin\theta \\
\sin\theta & \cos\theta
\end{pmatrix}.
$$

**例 1.8** 求将平面上的点关于 $x$ 轴反射的线性变换矩阵。

解：$T(\mathbf{e}_1)=\mathbf{e}_1=(1,0)^T$，$T(\mathbf{e}_2)=-\mathbf{e}_2=(0,-1)^T$，矩阵 $\begin{pmatrix}1&0\\0&-1\end{pmatrix}$。

### 1.4 矩阵运算与代数

#### 1.4.1 矩阵加法与数乘

同型矩阵相加：对应元素相加。数乘：每个元素乘以该常数。满足结合律、交换律、分配律。

#### 1.4.2 矩阵乘法

**定义**：若 $A$ 是 $m\times n$ 矩阵，$B$ 是 $n\times p$ 矩阵，则乘积 $C = AB$ 是 $m\times p$ 矩阵，其 $(i,j)$ 元素为
$$
c_{ij} = \sum_{k=1}^n a_{ik}b_{kj},
$$
即 $A$ 的第 $i$ 行与 $B$ 的第 $j$ 列的内积。

**注意**：矩阵乘法不满足交换律，即一般情况下 $AB \neq BA$。但结合律成立：$(AB)C = A(BC)$。分配律成立。

**转置乘积**：$(AB)^T = B^T A^T$。

**例 1.9** 计算 $AB$ 和 $BA$：
$$
A = \begin{pmatrix}2&1\\0&3\end{pmatrix},\quad B = \begin{pmatrix}1&-1\\2&4\end{pmatrix}.
$$
解：
$$
AB = \begin{pmatrix}2\cdot1+1\cdot2 & 2\cdot(-1)+1\cdot4 \\ 0\cdot1+3\cdot2 & 0\cdot(-1)+3\cdot4\end{pmatrix} = \begin{pmatrix}4&2\\6&12\end{pmatrix}.
$$
$$
BA = \begin{pmatrix}1\cdot2+(-1)\cdot0 & 1\cdot1+(-1)\cdot3 \\ 2\cdot2+4\cdot0 & 2\cdot1+4\cdot3\end{pmatrix} = \begin{pmatrix}2&-2\\4&14\end{pmatrix}.
$$

显然 $AB \neq BA$。

#### 1.4.3 矩阵的逆

**定义**：$n\times n$ 方阵 $A$ 称为**可逆**（非奇异），若存在 $n\times n$ 矩阵 $B$ 使得
$$
AB = BA = I_n.
$$
矩阵 $B$ 称为 $A$ 的**逆矩阵**，记作 $A^{-1}$。若不存在这样的 $B$，则 $A$ 是**不可逆**或**奇异**的。

**定理 1.6（逆矩阵的唯一性）**：若 $A$ 可逆，则其逆是唯一的。

**证明**：设 $B$ 和 $C$ 都是 $A$ 的逆，则 $B = BI = B(AC) = (BA)C = IC = C$。

**$2\times2$ 求逆公式**：
$$
A = \begin{pmatrix}a & b \\ c & d\end{pmatrix} \quad\Longrightarrow\quad
A^{-1} = \frac{1}{ad-bc}\begin{pmatrix}d & -b \\ -c & a\end{pmatrix},\quad \text{当 } ad-bc \neq 0.
$$
数 $ad-bc$ 称为 $A$ 的行列式（见 1.6 节）。

**一般求逆算法**：对矩阵 $[A \mid I_n]$ 进行初等行变换，直到左侧化为 $I_n$，此时右侧即为 $A^{-1}$。原理是行变换等价于左乘初等矩阵，将 $A$ 变为 $I$ 的过程相当于左乘 $A^{-1}$。

**例 1.10** 求 $A = \begin{pmatrix}1&2\\3&4\end{pmatrix}$ 的逆。

解：增广矩阵
$$
\left(\begin{array}{cc|cc}
1 & 2 & 1 & 0 \\
3 & 4 & 0 & 1
\end{array}\right)
\xrightarrow{R_2-3R_1}
\left(\begin{array}{cc|cc}
1 & 2 & 1 & 0 \\
0 & -2 & -3 & 1
\end{array}\right)
\xrightarrow{R_2/(-2)}
\left(\begin{array}{cc|cc}
1 & 2 & 1 & 0 \\
0 & 1 & \frac32 & -\frac12
\end{array}\right)
\xrightarrow{R_1-2R_2}
\left(\begin{array}{cc|cc}
1 & 0 & -2 & 1 \\
0 & 1 & \frac32 & -\frac12
\end{array}\right).
$$
故 $A^{-1} = \begin{pmatrix}-2&1\\ \frac32 & -\frac12\end{pmatrix}$。

**性质**：

- $(A^{-1})^{-1} = A$；
- $(AB)^{-1} = B^{-1} A^{-1}$（前提 $A,B$ 均可逆）；
- $(A^T)^{-1} = (A^{-1})^T$。

**可逆矩阵定理**（部分等价命题）：
设 $A$ 为 $n\times n$ 矩阵，下列命题等价：

1. $A$ 可逆；
2. $A$ 行等价于 $I_n$；
3. $A$ 有 $n$ 个主元位置；
4. $A\mathbf{x} = \mathbf{0}$ 仅有平凡解；
5. $A$ 的列线性无关；
6. 对任意 $\mathbf{b}\in\mathbb{R}^n$，$A\mathbf{x}=\mathbf{b}$ 有唯一解；
7. $\det A \neq 0$；
8. $\operatorname{rank}A = n$；
9. $A$ 的特征值全不为零；
等等。这些等价关系贯穿整个线性代数。

#### 1.4.4 分块矩阵

矩阵可以按行和列分为更小的子块。分块矩阵的加法和数乘按块进行；乘法类似，只要分块大小满足相容条件：左矩阵的列划分与右矩阵的行划分一致，则可用块乘公式，每个块的内积仍然是常规矩阵乘法。

**例 1.11（分块乘法）** 设 $A = \begin{pmatrix} B & 0 \\ 0 & C \end{pmatrix}$，$B$ 和 $C$ 可逆，求 $A^{-1}$。

解：由分块乘法验证 $\begin{pmatrix} B^{-1} & 0 \\ 0 & C^{-1} \end{pmatrix}$ 即为逆矩阵。

分块对角矩阵在简化计算中非常有用。

### 1.5 LU 分解

#### 1.5.1 为什么需要 LU 分解

对于一列方程组 $A\mathbf{x} = \mathbf{b}_1, \mathbf{b}_2, \dots$，若每次都对增广矩阵从头消元，计算量较大。LU 分解将 $A$ 分解为下三角矩阵 $L$ 和上三角矩阵 $U$ 的乘积，使得解方程变成解两个三角方程组，计算量显著降低。

#### 1.5.2 定义与算法

**定义**：对 $n\times n$ 矩阵 $A$，若存在下三角矩阵 $L$（主对角线全为 1）和上三角矩阵 $U$，使得 $A = LU$，则称为 $A$ 的 LU 分解。

**算法（Doolittle 方法）**：对 $A$ 进行行倍加变换（不换行），每次消元时记录乘子。将 $A$ 化为上三角矩阵 $U$，而乘子构成单位下三角矩阵 $L$。

具体地，对 $k=1$ 到 $n-1$，将第 $k$ 行的适当倍数加到下方各行，使第 $k$ 列主元以下元素变为 0。这些乘子 $l_{ik} = \frac{a_{ik}^{(k)}}{a_{kk}^{(k)}}$ 填入 $L$ 的对应位置。

**例 1.12** 求 $A = \begin{pmatrix} 2 & 1 & 1 \\ 4 & 3 & 4 \\ 8 & 7 & 9 \end{pmatrix}$ 的 LU 分解。

解：将 $A$ 化为阶梯形：


- 第 1 步：用 $R_2 - 2R_1,\ R_3 - 4R_1$，乘子 $l_{21}=2,\ l_{31}=4$。矩阵变为
  $$
  \begin{pmatrix}
  2 & 1 & 1 \\
  0 & 1 & 2 \\
  0 & 3 & 5
  \end{pmatrix}.
  $$
- 第 2 步：用 $R_3 - 3R_2$，乘子 $l_{32}=3$。矩阵变为
  $$
  U = \begin{pmatrix}
  2 & 1 & 1 \\
  0 & 1 & 2 \\
  0 & 0 & 3
  \end{pmatrix}.
  $$
  则


$$
L = \begin{pmatrix}
1 & 0 & 0 \\
2 & 1 & 0 \\
4 & 3 & 1
\end{pmatrix}.
$$
验证 $LU = \begin{pmatrix}1&0&0\\2&1&0\\4&3&1\end{pmatrix}\begin{pmatrix}2&1&1\\0&1&2\\0&0&3\end{pmatrix} = \begin{pmatrix}2&1&1\\4&3&4\\8&7&9\end{pmatrix} = A$。

若分解过程中需要行交换，则需引入置换矩阵 $P$，得到 $PA = LU$。

**解方程组**：对 $A\mathbf{x} = \mathbf{b}$，先解 $L\mathbf{y} = \mathbf{b}$（前向代入），再解 $U\mathbf{x} = \mathbf{y}$（后向代入）。

**例 1.13** 解 $A\mathbf{x} = (3,7,12)^T$，其中 $A$ 如上。

解：解 $L\mathbf{y} = \mathbf{b}$：
$$
\begin{pmatrix}1&0&0\\2&1&0\\4&3&1\end{pmatrix}
\begin{pmatrix}y_1\\y_2\\y_3\end{pmatrix} = \begin{pmatrix}3\\7\\12\end{pmatrix}
\implies y_1=3,\ y_2=7-2\cdot3=1,\ y_3=12-4\cdot3-3\cdot1 = -3.
$$
再解 $U\mathbf{x} = \mathbf{y}$：
$$
\begin{pmatrix}2&1&1\\0&1&2\\0&0&3\end{pmatrix}
\begin{pmatrix}x_1\\x_2\\x_3\end{pmatrix} = \begin{pmatrix}3\\1\\-3\end{pmatrix}
\implies x_3=-1,\ x_2=1-2(-1)=3,\ x_1=\frac{3-3-(-1)}{2}=\frac12.
$$
解为 $\mathbf{x} = (\frac12,3,-1)^T$。

### 1.6 行列式

#### 1.6.1 行列式的定义

**二阶行列式**：$\det\begin{pmatrix}a&b\\c&d\end{pmatrix} = \begin{vmatrix}a&b\\c&d\end{vmatrix} = ad-bc$。

**$n$ 阶行列式**的递归定义（按第一行展开）：
$$
\det A = \sum_{j=1}^n (-1)^{1+j} a_{1j} \det A_{1j},
$$
其中 $A_{1j}$ 是划去第 1 行和第 $j$ 列所得的 $(n-1)\times(n-1)$ 子式。展开结果与选择哪一行或哪一列无关。

**代数余子式**：$C_{ij} = (-1)^{i+j}\det A_{ij}$，则 $\det A = \sum_{j} a_{ij} C_{ij}$。

**例 1.14** 计算三阶行列式 $\begin{vmatrix}1&2&3\\4&5&6\\7&8&9\end{vmatrix}$。

解：按第一行展开：
$$
= 1\cdot \begin{vmatrix}5&6\\8&9\end{vmatrix} - 2\cdot \begin{vmatrix}4&6\\7&9\end{vmatrix} + 3\cdot \begin{vmatrix}4&5\\7&8\end{vmatrix}
= 1\cdot(-3) - 2\cdot(-6) + 3\cdot(-3) = -3+12-9 = 0.
$$

#### 1.6.2 行列式的性质

以下性质极大简化计算：

1. **转置不变**：$\det A^T = \det A$。
2. **换行变号**：交换两行，行列式反号。推论：有两行相同，行列式为 0。
3. **行倍乘**：某行乘以常数 $c$，行列式乘以 $c$。
4. **倍加不变**：将一行的倍数加到另一行，行列式不变。
5. **三角阵行列式**：等于主对角线元素之积。
6. **乘积行列式**：$\det(AB) = (\det A)(\det B)$。

**证明（乘积定理概要）**：当 $A$ 为初等矩阵时，可直接验证性质 6。对一般可逆矩阵 $A$，可分解为初等矩阵的乘积 $A = E_k \cdots E_1$，则
$$
\det(AB) = \det(E_k \cdots E_1 B) = (\det E_k)\cdots(\det E_1) \det B = (\det A) \det B.
$$
若 $A$ 不可逆，则 $\det A=0$，且 $AB$ 也不可逆（否则存在 $C$ 使 $ABC=I$，得 $A$ 可逆），故 $\det(AB)=0$，等式成立。

**例 1.15** 利用性质简化计算：
$$
\begin{vmatrix}
1 & 2 & 3 \\
4 & 5 & 6 \\
7 & 8 & 9
\end{vmatrix}
\xrightarrow{R_2-4R_1,\ R_3-7R_1}
\begin{vmatrix}
1 & 2 & 3 \\
0 & -3 & -6 \\
0 & -6 & -12
\end{vmatrix}
\xrightarrow{R_3-2R_2}
\begin{vmatrix}
1 & 2 & 3 \\
0 & -3 & -6 \\
0 & 0 & 0
\end{vmatrix} = 0.
$$

#### 1.6.3 克拉默法则

**定理 1.7（克拉默法则）**：若 $n\times n$ 矩阵 $A$ 可逆（$\det A \neq 0$），则方程组 $A\mathbf{x} = \mathbf{b}$ 有唯一解，其解为
$$
x_j = \frac{\det A_j(\mathbf{b})}{\det A},
$$
其中 $A_j(\mathbf{b})$ 是将 $A$ 的第 $j$ 列换成 $\mathbf{b}$ 所得的矩阵。

**证明思路**：将 $A$ 的第 $j$ 列用 $\mathbf{b}$ 替换，其行列式等于 $\det A$ 乘以 $x_j$。可用行列式的多重线性性质推导。

**例 1.16** 用克拉默法则解：
$$
\begin{cases}
2x + 3y = 8 \\
x + 2y = 5
\end{cases}
$$
解：$\det A = 2\cdot2 - 3\cdot1 = 1$，
$$
x = \frac{\begin{vmatrix}8&3\\5&2\end{vmatrix}}{1} = 16-15 = 1,\quad
y = \frac{\begin{vmatrix}2&8\\1&5\end{vmatrix}}{1} = 10-8 = 2.
$$

**求逆公式**：$A^{-1} = \frac{1}{\det A} \operatorname{adj}A$，其中 $\operatorname{adj}A$ 是 $C_{ij}$ 的转置（伴随矩阵）。此公式在理论推导中有用，但对高阶矩阵计算量巨大，不如行化简算法。

#### 1.6.4 几何意义

$\det A$ 的绝对值表示由 $A$ 的列向量张成的平行多面体的有向体积。特别地，$\det A = 0$ 意味着这些向量线性相关，张成的体积为零。

**例 1.17** 求由向量 $(1,2)^T$ 和 $(3,4)^T$ 张成的平行四边形面积。

解：面积 $= |\det\begin{pmatrix}1&3\\2&4\end{pmatrix}| = |4-6| = 2$。

---


## 第二章 向量空间与线性变换

### 2.1 向量空间与子空间

#### 2.1.1 向量空间的定义

在第一章中，我们主要在 $\mathbb{R}^n$ 中讨论向量及其运算。但线性代数的许多概念可以推广到更一般的集合上。

**定义（实向量空间）**：设 $V$ 是一个非空集合，在其上定义了两种运算：


- **加法**：对任意 $\mathbf{u},\mathbf{v}\in V$，有 $\mathbf{u}+\mathbf{v}\in V$；
- **数乘**：对任意实数 $c$ 和 $\mathbf{u}\in V$，有 $c\mathbf{u}\in V$。


若对任意 $\mathbf{u},\mathbf{v},\mathbf{w}\in V$ 和标量 $c,d$，满足以下八条公理，则称 $V$ 为（实）向量空间：

1. $\mathbf{u}+\mathbf{v} = \mathbf{v}+\mathbf{u}$（加法交换律）
2. $(\mathbf{u}+\mathbf{v})+\mathbf{w} = \mathbf{u}+(\mathbf{v}+\mathbf{w})$（加法结合律）
3. 存在零向量 $\mathbf{0}\in V$，使得 $\mathbf{u}+\mathbf{0}=\mathbf{u}$
4. 对任意 $\mathbf{u}$，存在负向量 $-\mathbf{u}\in V$，使得 $\mathbf{u}+(-\mathbf{u})=\mathbf{0}$
5. $c(\mathbf{u}+\mathbf{v}) = c\mathbf{u} + c\mathbf{v}$
6. $(c+d)\mathbf{u} = c\mathbf{u} + d\mathbf{u}$
7. $c(d\mathbf{u}) = (cd)\mathbf{u}$
8. $1\mathbf{u} = \mathbf{u}$


**常见的向量空间**：

- $\mathbb{R}^n$：$n$ 维列向量空间。
- $M_{m\times n}$：所有 $m\times n$ 实矩阵构成的集合，按矩阵加法和数乘构成向量空间。
- $\mathbb{P}_n$：次数不超过 $n$ 的多项式全体，按多项式加法和数乘构成向量空间。
- $C[a,b]$：闭区间 $[a,b]$ 上所有连续函数构成的空间，加法和数乘逐点定义。

#### 2.1.2 子空间

**定义（子空间）**：向量空间 $V$ 的非空子集 $H$ 称为 $V$ 的**子空间**，若 $H$ 对 $V$ 的加法和数乘封闭，即：

1. 若 $\mathbf{u},\mathbf{v}\in H$，则 $\mathbf{u}+\mathbf{v}\in H$；
2. 若 $c\in\mathbb{R}$，$\mathbf{u}\in H$，则 $c\mathbf{u}\in H$。

**判定**：$H$ 是子空间 $\iff$ $H$ 非空且对线性组合封闭（等价于零向量属于 $H$，注意从封闭性可推出 $0\mathbf{u}=\mathbf{0}\in H$）。

**重要的子空间例子**（由矩阵或线性变换产生）：

- **零空间**：对于 $m\times n$ 矩阵 $A$，
  $$
  \operatorname{Nul}A = \{\mathbf{x}\in\mathbb{R}^n \mid A\mathbf{x}=\mathbf{0}\}.
  $$
  它是 $\mathbb{R}^n$ 的子空间。因为 $A\mathbf{0}=\mathbf{0}$，且若 $A\mathbf{u}=\mathbf{0},A\mathbf{v}=\mathbf{0}$，则 $A(\mathbf{u}+\mathbf{v})=\mathbf{0}$，$A(c\mathbf{u})=\mathbf{0}$。

- **列空间**：对于 $m\times n$ 矩阵 $A$，其列向量张成的 $\mathbb{R}^m$ 的子集：
  $$
  \operatorname{Col}A = \operatorname{span}\{\mathbf{a}_1,\dots,\mathbf{a}_n\} \subseteq \mathbb{R}^m.
  $$
  它也是 $\mathbb{R}^m$ 的子空间（由生成集的定义保证封闭性）。注意，$\operatorname{Col}A$ 等于所有形如 $A\mathbf{x}$ 的向量构成的集合。

- **行空间**：$A$ 的行向量张成的 $\mathbb{R}^n$ 的子空间，记 $\operatorname{Row}A$。

- **零空间与列空间的关系**：齐次方程 $A\mathbf{x}=\mathbf{0}$ 的解集就是 $\operatorname{Nul}A$；方程 $A\mathbf{x}=\mathbf{b}$ 有解等价于 $\mathbf{b}\in\operatorname{Col}A$。

**例 2.1** 证明集合 $H = \{(x,y,z)^T \mid x + 2y - z = 0\}$ 是 $\mathbb{R}^3$ 的子空间，并求其一组基。

解：$H$ 是齐次线性方程 $x+2y-z=0$ 的解集，即矩阵 $(1,2,-1)$ 的零空间，因此是子空间。求解 $x+2y-z=0$，可写 $x = -2y + z$。令 $y=s,\ z=t$，则
$$
\mathbf{x} = \begin{pmatrix}-2s+t\\ s\\ t\end{pmatrix}
= s\begin{pmatrix}-2\\1\\0\end{pmatrix} + t\begin{pmatrix}1\\0\\1\end{pmatrix}.
$$
故 $H = \operatorname{span}\{(-2,1,0)^T,\ (1,0,1)^T\}$，维数为 2。

**例 2.2** 下列集合是否为子空间？  
(a) $W = \{(x,y)\mid y=x+1\}$  
(b) $Z = \{(x,y)\mid x\ge0,\ y\ge0\}$  

解：(a) 不含零向量 (0,0)，且对加法不封闭（两个满足的点之和一般不满足），故不是子空间。  
(b) 对数乘不封闭：$(1,1)\in Z$，但 $-1\cdot(1,1)=(-1,-1)\notin Z$，故不是子空间。

### 2.2 线性无关与基

#### 2.2.1 线性无关的深入讨论

**定义回顾**：向量组 $\{\mathbf{v}_1,\dots,\mathbf{v}_p\}$ 线性无关，若方程 $\sum_{i=1}^p c_i \mathbf{v}_i = \mathbf{0}$ 仅有平凡解 $c_i=0$。否则称线性相关。

**等价的表述**：向量组线性无关 $\iff$ 没有一个向量可以写成其余向量的线性组合。

**判定矩阵方法**：将向量排成矩阵的列，行化简后检查主元个数。若主元个数等于向量个数 $p$，则列线性无关；否则相关。

**线性相关引理**：若 $\{\mathbf{v}_1,\dots,\mathbf{v}_p\}$ 可由 $\{\mathbf{u}_1,\dots,\mathbf{u}_q\}$ 线性表出，且 $p>q$，则 $\{\mathbf{v}_1,\dots,\mathbf{v}_p\}$ 线性相关。

**证明**：设 $A=[\mathbf{u}_1\ \dots\ \mathbf{u}_q]$，$B=[\mathbf{v}_1\ \dots\ \mathbf{v}_p]$，则存在矩阵 $C$ $(q\times p)$ 使 $B=AC$。齐次方程 $C\mathbf{x}=\mathbf{0}$ 有 $q$ 个方程、$p$ 个未知数，由于 $p>q$，必有非零解 $\mathbf{x}_0$，则 $B\mathbf{x}_0 = AC\mathbf{x}_0 = \mathbf{0}$，说明 $\mathbf{v}_i$ 的线性组合为零，从而线性相关。

这个引理是基的维数不变性的核心。

#### 2.2.2 基的定义与性质

**定义（基）**：向量空间 $V$ 的子集 $\mathcal{B}=\{\mathbf{b}_1,\dots,\mathbf{b}_p\}$ 称为 $V$ 的一组**基**，若

1. $\mathcal{B}$ 线性无关；
2. $\mathcal{B}$ 张成 $V$（即 $V = \operatorname{span}\mathcal{B}$）。

**基的等价刻画**：$\mathcal{B}$ 是 $V$ 的基 $\iff$ $V$ 中每个向量可唯一地表示为 $\mathcal{B}$ 中向量的线性组合。

**例 2.3** 证明 $\{1, t, t^2\}$ 是 $\mathbb{P}_2$（次数不超过 2 的多项式空间）的基。

解：任意多项式 $p(t)=a_0 + a_1 t + a_2 t^2$ 可唯一表示为 $a_0\cdot 1 + a_1\cdot t + a_2\cdot t^2$，系数由多项式本身唯一确定，且 $1, t, t^2$ 线性无关（若对任意 $t$ 都为零多项式，系数必全为零）。故是一组基。

**例 2.4** 求 $\mathbb{R}^3$ 的一组基并验证其线性无关。

**解**：标准基 $\mathbf{e}_1=(1,0,0)^T,\ \mathbf{e}_2=(0,1,0)^T,\ \mathbf{e}_3=(0,0,1)^T$ 是基，因为任何向量可唯一表示为 $a\mathbf{e}_1+b\mathbf{e}_2+c\mathbf{e}_3$，且它们线性无关。

不过，并非所有基都是标准的，例如 $\mathcal{B}=\{(1,2)^T,(3,4)^T\}$ 也是 $\mathbb{R}^2$ 的一组基，因为行列式 $\det\begin{pmatrix}1&3\\2&4\end{pmatrix} = -2\neq0$，列线性无关且个数等于维数 2，故必张成 $\mathbb{R}^2$。

### 2.3 维数与秩

#### 2.3.1 子空间的维数

**定理 2.1（基的基数不变性）**：若向量空间 $V$ 有两组基 $\mathcal{B}_1$ 和 $\mathcal{B}_2$，则它们所含向量个数相等。

**证明**：设 $\mathcal{B}_1$ 有 $p$ 个向量，$\mathcal{B}_2$ 有 $q$ 个向量。因为 $\mathcal{B}_1$ 张成 $V$，$\mathcal{B}_2$ 中的每个向量均可由 $\mathcal{B}_1$ 线性表出；同理 $\mathcal{B}_1$ 可由 $\mathcal{B}_2$ 线性表出。若 $p>q$，则由线性相关引理，$\mathcal{B}_1$（$p$ 个）可由 $\mathcal{B}_2$（$q$ 个）表出，则 $\mathcal{B}_1$ 线性相关，矛盾。故 $p\le q$。对称得 $q\le p$，因此 $p=q$。

据此，定义子空间 $H$ 的**维数** $\dim H$ 为其任一组基所含向量个数。约定 $\{\mathbf{0}\}$ 的维数为 0。

**常见维数**：

- $\dim \mathbb{R}^n = n$。
- $\dim M_{m\times n} = mn$（基：$E_{ij}$ 在 $(i,j)$ 位置为 1，其余为 0）。
- $\dim \mathbb{P}_n = n+1$。

**基的扩充定理**：在 $n$ 维空间 $V$ 中，任何 $k$ 个线性无关的向量（$k<n$）都可以扩充为一组基。

#### 2.3.2 矩阵的秩与零空间维数

**定义**：矩阵 $A$ 的**秩** $\operatorname{rank}A$ 定义为 $\dim \operatorname{Col}A$（列空间的维数），即极大线性无关列向量组的向量个数。

行化简后，主元所在列的位置对应的原矩阵列向量构成列空间的一组基。因此，秩等于主元个数。

**定理 2.2（秩定理）**：若 $A$ 是 $m\times n$ 矩阵，则
$$
\operatorname{rank}A + \dim \operatorname{Nul}A = n.
$$
即列排列数 $n$ = 秩 + 零空间的维数。

**证明**：将 $A$ 行化简为行阶梯形 $U$，设主元个数为 $r$，则 $\operatorname{rank}A = r$。解 $A\mathbf{x}=\mathbf{0}$，等价于解 $U\mathbf{x}=\mathbf{0}$；自由变量个数为 $n-r$，每个自由变量对应零空间的一个基向量，故 $\dim \operatorname{Nul}A = n-r$。相加得证。

**例 2.5** 求 $A = \begin{pmatrix}1&3&5\\2&4&6\end{pmatrix}$ 的秩和零空间的基。

**解**：行化简：
$$
A \sim \begin{pmatrix}
1 & 3 & 5 \\
0 & -2 & -4
\end{pmatrix}
\sim \begin{pmatrix}
1 & 0 & -1 \\
0 & 1 & 2
\end{pmatrix}.
$$
秩 $r=2$，自由变量 $x_3$。令 $x_3 = 1$，回代得 $x_1 = 1,\ x_2 = -2$，所以零空间基向量为 $(1,-2,1)^T$，$\dim \operatorname{Nul}A = 1$。验证 $r + \dim = 2+1 = 3 = n$。

**行秩等于列秩**：实际上，$A$ 的行秩（$\dim \operatorname{Row}A$）也等于 $r$。因为行初等变换不改变行空间，行阶梯形的非零行构成行空间的一组基，非零行数为 $r$。所以 $\operatorname{rank}A = \operatorname{rank}A^T$。

#### 2.3.3 可逆矩阵定理中的秩

$n\times n$ 矩阵 $A$ 可逆 $\iff$ $\operatorname{rank}A = n$ $\iff$ $A$ 的列是 $\mathbb{R}^n$ 的基 $\iff$ $\det A \neq 0$ $\iff$ $A\mathbf{x}=\mathbf{0}$ 只有零解。

#### 2.3.4 秩的估计与不等式

- $\operatorname{rank}(A+B) \le \operatorname{rank}A + \operatorname{rank}B$
- $\operatorname{rank}(AB) \le \min(\operatorname{rank}A,\operatorname{rank}B)$
- 若 $A$ 列满秩，则 $\operatorname{rank}(AB) = \operatorname{rank}B$。

**例 2.6** 证明 $\operatorname{rank}(AB) \le \operatorname{rank}A$。

证明：$AB$ 的每一列是 $A$ 列向量的线性组合，因此 $\operatorname{Col}(AB) \subseteq \operatorname{Col}A$，从而维数减少或相等。

### 2.4 坐标系与基变换

#### 2.4.1 坐标映射

设 $\mathcal{B} = \{\mathbf{b}_1,\dots,\mathbf{b}_n\}$ 是 $V$ 的一组基。对任意 $\mathbf{v}\in V$，存在唯一标量 $c_1,\dots,c_n$ 使得
$$
\mathbf{v} = c_1\mathbf{b}_1 + \cdots + c_n\mathbf{b}_n.
$$
称系数构成的列向量 $[\mathbf{v}]_{\mathcal{B}} = (c_1,\dots,c_n)^T$ 为 $\mathbf{v}$ 关于基 $\mathcal{B}$ 的**坐标向量**。

坐标映射 $\mathbf{v} \mapsto [\mathbf{v}]_{\mathcal{B}}$ 是从 $V$ 到 $\mathbb{R}^n$ 的一一对应线性变换，保持向量运算。

**例 2.7** 设 $\mathcal{B} = \{(1,2)^T,(3,4)^T\}$ 是 $\mathbb{R}^2$ 的基，求 $\mathbf{v} = (5,6)^T$ 关于 $\mathcal{B}$ 的坐标。

解：解 $c_1\begin{pmatrix}1\\2\end{pmatrix} + c_2\begin{pmatrix}3\\4\end{pmatrix} = \begin{pmatrix}5\\6\end{pmatrix}$，即
$$
\begin{pmatrix}1&3\\2&4\end{pmatrix}\begin{pmatrix}c_1\\c_2\end{pmatrix} = \begin{pmatrix}5\\6\end{pmatrix}.
$$
解得 $c_1 = -1,\ c_2 = 2$，所以 $[\mathbf{v}]_{\mathcal{B}} = (-1,2)^T$。

#### 2.4.2 基变换矩阵

若 $V$ 有两组基 $\mathcal{B} = \{\mathbf{b}_1,\dots,\mathbf{b}_n\}$ 和 $\mathcal{C} = \{\mathbf{c}_1,\dots,\mathbf{c}_n\}$。对每个 $\mathbf{b}_j$，它可被 $\mathcal{C}$ 线性表出，设
$$
\mathbf{b}_j = \sum_{i=1}^n p_{ij} \mathbf{c}_i.
$$
则矩阵 $P = (p_{ij})$ 的列就是各个 $\mathbf{b}_j$ 在基 $\mathcal{C}$ 下的坐标。称 $P$ 为从 $\mathcal{B}$ 到 $\mathcal{C}$ 的**基变换矩阵**，记为 $P_{\mathcal{C}\leftarrow\mathcal{B}}$。

对任意 $\mathbf{v}\in V$，有 **坐标变换公式**：
$$
[\mathbf{v}]_{\mathcal{C}} = P_{\mathcal{C}\leftarrow\mathcal{B}} [\mathbf{v}]_{\mathcal{B}}.
$$

特别地，若 $V = \mathbb{R}^n$，且 $\mathcal{E}$ 为标准基，则 $[\mathbf{v}]_{\mathcal{E}} = \mathbf{v}$ 本身。若记 $P_{\mathcal{B}} = [\mathbf{b}_1 \ \mathbf{b}_2 \ \cdots \ \mathbf{b}_n]$ 为基 $\mathcal{B}$ 按列组成的矩阵，则 $\mathbf{v} = P_{\mathcal{B}}[\mathbf{v}]_{\mathcal{B}}$。从标准基到 $\mathcal{B}$ 的坐标变换矩阵为 $P_{\mathcal{B}}$。

**基变换矩阵的性质**：

- $P_{\mathcal{C}\leftarrow\mathcal{B}}$ 可逆，且 $P_{\mathcal{B}\leftarrow\mathcal{C}} = (P_{\mathcal{C}\leftarrow\mathcal{B}})^{-1}$。
- 若 $\mathcal{B},\mathcal{C},\mathcal{D}$ 是三组基，则 $P_{\mathcal{D}\leftarrow\mathcal{B}} = P_{\mathcal{D}\leftarrow\mathcal{C}} P_{\mathcal{C}\leftarrow\mathcal{B}}$。

**例 2.8** 在 $\mathbb{R}^2$ 中，$\mathcal{B}=\{\mathbf{b}_1,\mathbf{b}_2\}$ 其中 $\mathbf{b}_1=(1,2)^T,\mathbf{b}_2=(3,4)^T$；$\mathcal{C}=\{\mathbf{c}_1,\mathbf{c}_2\}$ 其中 $\mathbf{c}_1=(1,0)^T,\mathbf{c}_2=(1,1)^T$。求 $P_{\mathcal{C}\leftarrow\mathcal{B}}$。

解：法一：直接求 $\mathbf{b}_1,\mathbf{b}_2$ 在基 $\mathcal{C}$ 下的坐标。
设 $\mathbf{b}_1 = a\mathbf{c}_1 + b\mathbf{c}_2$，即 $\begin{pmatrix}1&1\\0&1\end{pmatrix}\begin{pmatrix}a\\b\end{pmatrix} = \begin{pmatrix}1\\2\end{pmatrix}$，解得 $a=-1,b=2$，故第一列为 $(-1,2)^T$。同理解 $\mathbf{b}_2 = (3,4)^T$，得 $c=-1,d=4$，第二列 $(-1,4)^T$。所以
$$
P_{\mathcal{C}\leftarrow\mathcal{B}} = \begin{pmatrix}-1&-1\\2&4\end{pmatrix}.
$$

法二：利用公式 $P_{\mathcal{C}} = [\mathbf{c}_1\ \mathbf{c}_2] = \begin{pmatrix}1&1\\0&1\end{pmatrix}$，$P_{\mathcal{B}} = \begin{pmatrix}1&3\\2&4\end{pmatrix}$。则对任意 $\mathbf{v}$，$P_{\mathcal{C}}[\mathbf{v}]_{\mathcal{C}} = \mathbf{v} = P_{\mathcal{B}}[\mathbf{v}]_{\mathcal{B}}$，故 $[\mathbf{v}]_{\mathcal{C}} = P_{\mathcal{C}}^{-1} P_{\mathcal{B}} [\mathbf{v}]_{\mathcal{B}}$。因此
$$
P_{\mathcal{C}\leftarrow\mathcal{B}} = P_{\mathcal{C}}^{-1} P_{\mathcal{B}} = \begin{pmatrix}1&1\\0&1\end{pmatrix}^{-1}\begin{pmatrix}1&3\\2&4\end{pmatrix} = \begin{pmatrix}1&-1\\0&1\end{pmatrix}\begin{pmatrix}1&3\\2&4\end{pmatrix} = \begin{pmatrix}-1&-1\\2&4\end{pmatrix}.
$$

#### 2.4.3 相似矩阵

**定义**：$A$ 与 $B$ 称为相似，若存在可逆矩阵 $P$ 使得 $A = PBP^{-1}$。

相似矩阵可视为同一线性变换在不同基下的表示。将在 2.5 节详细阐述。

### 2.5 线性变换的矩阵表示

#### 2.5.1 线性变换回顾

设 $T: V \to W$ 是线性变换。我们重点考虑 $V=\mathbb{R}^n, W=\mathbb{R}^m$ 的情形，此时每个线性变换都由一个 $m\times n$ 矩阵 $A$ 通过 $T(\mathbf{x}) = A\mathbf{x}$ 确定。$A$ 的第 $j$ 列是 $T(\mathbf{e}_j)$。

**核与像**：

- **核（零空间）**：$\ker T = \{\mathbf{v}\in V \mid T(\mathbf{v}) = \mathbf{0}\}$，是 $V$ 的子空间。
- **像（值域）**：$\operatorname{im} T = \{T(\mathbf{v}) \mid \mathbf{v}\in V\}$，是 $W$ 的子空间。

在矩阵变换下，$\ker T = \operatorname{Nul}A$，$\operatorname{im} T = \operatorname{Col}A$。

**例 2.9** 投影变换：$T:\mathbb{R}^3\to\mathbb{R}^2$，$T(x,y,z) = (x,y)$。求核与像。

解：核为 $\{(x,y,z)\mid x=0,y=0\}$ 即 $z$ 轴，维数 1。像为 $\mathbb{R}^2$，维数 2。

#### 2.5.2 线性变换在一般基下的矩阵

当 $V$ 和 $W$ 不限于标准基时，需要刻画线性变换的矩阵表示。

设 $\mathcal{B} = \{\mathbf{b}_1,\dots,\mathbf{b}_n\}$ 是 $V$ 的基，$\mathcal{C}$ 是 $W$ 的基。定义 $T$ 关于基 $\mathcal{B}$ 和 $\mathcal{C}$ 的矩阵 $M = [T]_{\mathcal{B},\mathcal{C}}$，其第 $j$ 列为 $[T(\mathbf{b}_j)]_{\mathcal{C}}$，即对每个基向量 $\mathbf{b}_j$，将其像在 $W$ 的基 $\mathcal{C}$ 下的坐标作为矩阵的一列。

那么对于任何 $\mathbf{v}\in V$，有
$$
[T(\mathbf{v})]_{\mathcal{C}} = M [\mathbf{v}]_{\mathcal{B}}.
$$

**特殊情况**：若 $T: V \to V$ 是自同态，$\mathcal{B}$ 是一组基，$T$ 关于 $\mathcal{B}$ 的矩阵简记为 $[T]_{\mathcal{B}}$。

**定理 2.3**：若 $T: V \to V$ 是线性变换，$\mathcal{B}$ 和 $\mathcal{C}$ 是 $V$ 的两组基，且 $P = P_{\mathcal{C}\leftarrow\mathcal{B}}$ 为基变换矩阵，则
$$
[T]_{\mathcal{B}} = P^{-1} [T]_{\mathcal{C}} P.
$$
因此，同一线性变换在不同基下的矩阵是相似的。

**例 2.10** 设 $T:\mathbb{R}^2\to\mathbb{R}^2$ 是旋转变换 $\theta=90^\circ$。在标准基下矩阵为 $A = \begin{pmatrix}0&-1\\1&0\end{pmatrix}$。取基 $\mathcal{B} = \{(1,1)^T,(2,1)^T\}$，求 $[T]_{\mathcal{B}}$。

解：$\mathcal{B}$ 到标准基的变换矩阵 $P = \begin{pmatrix}1&2\\1&1\end{pmatrix}$，于是 $[T]_{\mathcal{B}} = P^{-1}AP$。计算得：
$$
P^{-1} = \begin{pmatrix}-1&2\\1&-1\end{pmatrix},\quad
P^{-1}AP = \begin{pmatrix}-1&2\\1&-1\end{pmatrix}
\begin{pmatrix}0&-1\\1&0\end{pmatrix}
\begin{pmatrix}1&2\\1&1\end{pmatrix} = \begin{pmatrix}2&3\\-2&-3\end{pmatrix}.
$$
（具体可验算）

#### 2.5.3 线性变换的几何例子

- **伸缩变换**：$T(x,y) = (kx,ky)$，矩阵 $\begin{pmatrix}k&0\\0&k\end{pmatrix}$。
- **反射**：关于 $x$ 轴反射，矩阵 $\begin{pmatrix}1&0\\0&-1\end{pmatrix}$。
- **投影**：投影到 $x$ 轴，矩阵 $\begin{pmatrix}1&0\\0&0\end{pmatrix}$。
- **切变**：$T(x,y) = (x+ky, y)$，矩阵 $\begin{pmatrix}1&k\\0&1\end{pmatrix}$。

这些均可用于计算机图形学中的齐次坐标变换（平移不是线性变换，但可通过齐次坐标表示为线性）。

### 2.6 差分方程

线性差分方程是描述离散时间系统的重要工具，在经济学、生物学、数字信号处理等领域有广泛应用。

#### 2.6.1 一阶递推与矩阵形式

许多高阶递推可化为一阶系统。例如，二阶线性递推
$$
x_{k+2} = a x_{k+1} + b x_k
$$
可通过引入向量 $\mathbf{u}_k = \begin{pmatrix}x_{k+1} \\ x_k\end{pmatrix}$ 化为一阶系统：
$$
\mathbf{u}_{k+1} = \begin{pmatrix} a & b \\ 1 & 0 \end{pmatrix} \mathbf{u}_k.
$$
更一般地，$n$ 阶递推可化为 $n$ 维一阶系统。

令 $A$ 为系数矩阵，则系统 $\mathbf{x}_{k+1} = A\mathbf{x}_k$ 的解为 $\mathbf{x}_k = A^k \mathbf{x}_0$。

#### 2.6.2 利用对角化求解（简述）

若 $A$ 可对角化，即存在可逆矩阵 $P$ 和对角矩阵 $D$ 使得 $A = PDP^{-1}$，则
$$
A^k = PD^kP^{-1},
$$
其中 $D^k = \operatorname{diag}(\lambda_1^k,\dots,\lambda_n^k)$。因此通解为
$$
\mathbf{x}_k = \sum_{i=1}^n c_i \lambda_i^k \mathbf{v}_i,
$$
其中 $c_i$ 由初始条件确定。对角化和特征值的详细理论见第三章。

**例 2.11（斐波那契数列）**
数列 $F_0=0,\ F_1=1$，满足 $F_{k+2}=F_{k+1}+F_k$。求通项公式。

**解**：设 $\mathbf{u}_k = \begin{pmatrix}F_{k+1}\\F_k\end{pmatrix}$，则 $\mathbf{u}_{k+1} = A\mathbf{u}_k$，其中 $A = \begin{pmatrix}1&1\\1&0\end{pmatrix}$。特征方程 $\lambda^2 - \lambda - 1 = 0$，解得
$$
\lambda_1 = \frac{1+\sqrt5}{2},\quad \lambda_2 = \frac{1-\sqrt5}{2}.
$$
对应特征向量可求出，对角化后可得通项（过程在下章详述）。最终得到：
$$
F_k = \frac{1}{\sqrt5}\left(\frac{1+\sqrt5}{2}\right)^k - \frac{1}{\sqrt5}\left(\frac{1-\sqrt5}{2}\right)^k.
$$

#### 2.6.3 长期行为

系统 $\mathbf{x}_{k+1} = A\mathbf{x}_k$ 的长期行为由特征值决定：

- 若所有 $|\lambda_i| < 1$，则 $\mathbf{x}_k \to \mathbf{0}$（稳定）。
- 若存在 $|\lambda_i| = 1$（且其他 $<1$），可能趋向某个非零稳态。
- 若存在 $|\lambda_i| > 1$，则系统发散（不稳定）。

### 2.7 马尔可夫链

马尔可夫链是研究状态转移的一类随机过程模型，特征值为 1 的随机矩阵起关键作用。

#### 2.7.1 随机矩阵与概率向量

**定义**：向量 $\mathbf{x}\in\mathbb{R}^n$ 称为**概率向量**，若其分量非负且和为 1。矩阵 $P$ 称为**随机矩阵**（或转移矩阵），若每列都是概率向量。

**马尔可夫过程**：状态向量 $\mathbf{x}_k$ 满足 $\mathbf{x}_{k+1} = P\mathbf{x}_k$，其中 $P$ 为列随机矩阵。$P$ 的最大特征值为 1（证明：1 是 $P^T$ 的特征值，因 $P^T$ 每行和为 1，故 $(1,\dots,1)^T$ 是 $P^T$ 的特征向量）。

#### 2.7.2 稳态分布

若 $\mathbf{x}_{k+1} = P\mathbf{x}_k$ 收敛到某个极限向量 $\mathbf{q}$，则必然有 $P\mathbf{q} = \mathbf{q}$，即 $\mathbf{q}$ 是特征值 1 的特征向量。在良好条件下（如 $P$ 是正则随机矩阵，即某个幂 $P^m$ 所有元素为正），马尔可夫链收敛到唯一的稳态分布 $\mathbf{q}$，且 $\mathbf{q}$ 是 $P$ 的属于 1 的归一化特征向量。

**例 2.12（人口迁移模型）**
某地每年城市人口中有 5% 迁往郊区，郊区人口有 3% 迁往城市。设初始城市人口 60 万，郊区 40 万，求长期分布。

**解**：转移矩阵 $P = \begin{pmatrix}0.95 & 0.03 \\ 0.05 & 0.97\end{pmatrix}$。求稳态：解 $(P-I)\mathbf{q}=\mathbf{0}$，即
$$
\begin{pmatrix}-0.05 & 0.03 \\ 0.05 & -0.03\end{pmatrix} \begin{pmatrix}q_1\\q_2\end{pmatrix} = \mathbf{0}.
$$
这等价于 $-0.05q_1 + 0.03q_2 = 0$，取 $q_1=3,\ q_2=5$，归一化得 $\mathbf{q} = \begin{pmatrix}3/8 \\ 5/8\end{pmatrix} = \begin{pmatrix}0.375 \\ 0.625\end{pmatrix}$。即长期城市 37.5%，郊区 62.5%。

**证明**：验证 $P\mathbf{q}=\mathbf{q}$，且 $P$ 所有元素为正，故马尔可夫链收敛到 $\mathbf{q}$。（注意实际初始向量的演化也会趋向该分布，无论初始分布如何。）

#### 2.7.3 应用：网页排序（PageRank）

PageRank 算法本质上是一个大规模马尔可夫链的稳态计算，矩阵 $P$ 为链接结构的随机游走矩阵的变形，求解 $P\mathbf{x} = \mathbf{x}$ 的问题。

---


## 第一章 特征值与特征向量（深入）

### 1.1 基本概念与计算

#### 1.1.1 定义

设 $A$ 是 $n\times n$ 方阵。若存在数 $\lambda$ 和非零向量 $\mathbf{x}$ 满足
$$
A\mathbf{x} = \lambda \mathbf{x},
$$
则称 $\lambda$ 为 $A$ 的一个**特征值**，$\mathbf{x}$ 为 $\lambda$ 对应的**特征向量**。

注：特征向量必须非零；特征值可以是实数或复数。

**几何意义**：$A$ 作用于其特征向量时，仅将其伸缩（长度乘以 $|\lambda|$），方向可能反向（若 $\lambda<0$）或不变（若 $\lambda>0$）。

#### 1.1.2 特征方程

重写 $A\mathbf{x} = \lambda\mathbf{x}$ 为 $(A - \lambda I)\mathbf{x} = \mathbf{0}$，这是齐次线性方程组，有非零解当且仅当系数矩阵 $A-\lambda I$ 不可逆，即
$$
\det(A - \lambda I) = 0.
$$
称 $\det(A-\lambda I)$ 为 $A$ 的**特征多项式**，它是关于 $\lambda$ 的 $n$ 次多项式。特征方程 $\det(A-\lambda I)=0$ 的根就是特征值。

代数学基本定理：在复数域上，$n$ 次多项式恰有 $n$ 个根（重数计）。故 $n$ 阶方阵有 $n$ 个特征值（包括重根，可能有复数）。

**代数重数**：特征值 $\lambda_0$ 作为特征多项式根的重数。

**几何重数**：属于 $\lambda_0$ 的线性无关特征向量的最大个数，即特征子空间 $\operatorname{Nul}(A-\lambda_0 I)$ 的维数。

**定理 1.1**：对任意特征值，$1 \le \text{几何重数} \le \text{代数重数}$。

*证明*：设几何重数为 $r$，取 $\operatorname{Nul}(A-\lambda_0 I)$ 的一组基 $\mathbf{v}_1,\dots,\mathbf{v}_r$，并将其扩充为 $\mathbb{C}^n$ 的基 $\mathbf{v}_1,\dots,\mathbf{v}_r,\mathbf{w}_{r+1},\dots,\mathbf{w}_n$。令 $P$ 是以这些向量为列的矩阵，则
$$
P^{-1}AP = \begin{pmatrix} \lambda_0 I_r & * \\ 0 & B \end{pmatrix},
$$
其中 $B$ 是 $(n-r)\times(n-r)$ 矩阵。所以 $A$ 的特征多项式为 $(\lambda-\lambda_0)^r \det(B-\lambda I)$，故 $\lambda_0$ 的代数重数至少为 $r$。∎

#### 1.1.3 求特征值与特征向量的步骤

1. 计算特征多项式 $\det(A-\lambda I)$。
2. 求解特征方程，得特征值。
3. 对每一个特征值 $\lambda_j$，解齐次方程组 $(A-\lambda_j I)\mathbf{x}=\mathbf{0}$，求非零解即为对应特征向量。取基础解系构成特征空间的基。

**例 1.1** 求 $A = \begin{pmatrix}2 & 1 \\ 1 & 2\end{pmatrix}$ 的特征值与特征向量。

解：特征多项式
$$
\det\begin{pmatrix}2-\lambda & 1 \\ 1 & 2-\lambda\end{pmatrix} = (2-\lambda)^2 - 1 = \lambda^2 - 4\lambda + 3 = (\lambda-1)(\lambda-3).
$$
特征值 $\lambda_1=1,\ \lambda_2=3$。

- 对于 $\lambda_1=1$：解 $(A-I)\mathbf{x}=\mathbf{0}$，$\begin{pmatrix}1&1\\1&1\end{pmatrix}\mathbf{x}=\mathbf{0}$，得 $\mathbf{x}=t\begin{pmatrix}1\\-1\end{pmatrix}$，特征空间由 $\begin{pmatrix}1\\-1\end{pmatrix}$ 生成。
- 对于 $\lambda_2=3$：解 $(A-3I)\mathbf{x}=\mathbf{0}$，$\begin{pmatrix}-1&1\\1&-1\end{pmatrix}\mathbf{x}=\mathbf{0}$，得 $\mathbf{x}=s\begin{pmatrix}1\\1\end{pmatrix}$。

### 1.2 特征值的性质

- 矩阵 $A$ 的迹 $\operatorname{tr}A = \sum_{i=1}^n a_{ii} = \sum_{i=1}^n \lambda_i$（特征值之和，重数计）。
- 行列式 $\det A = \prod_{i=1}^n \lambda_i$。
- $A$ 可逆 $\iff$ 所有特征值非零。
- 若 $A$ 可逆，则 $A^{-1}$ 的特征值为 $1/\lambda_i$，且对应相同的特征向量。
- $\lambda^2$ 是 $A^2$ 的特征值，$(A+cI)$ 的特征值为 $\lambda+c$。
- 实对称矩阵的特征值均为实数（见后文谱定理）。

**例 1.2** 利用特征值求 $A = \begin{pmatrix}1&2\\2&1\end{pmatrix}$ 的行列式。
解：特征方程 $\lambda^2-2\lambda-3=0$，特征值 $3,-1$，故 $\det A = 3\cdot(-1) = -3$。

### 1.3 对角化

#### 1.3.1 相似与对角化条件

**定义**：矩阵 $A$ 与 $B$ 相似，若存在可逆矩阵 $P$ 使 $A = PBP^{-1}$。

相似矩阵有相同的特征多项式、特征值、迹、行列式、秩。

**定义**：若 $A$ 相似于对角矩阵 $\Lambda = \operatorname{diag}(\lambda_1,\dots,\lambda_n)$，则称 $A$ **可对角化**。此时有 $A = P\Lambda P^{-1}$，其中 $P$ 的列是 $n$ 个线性无关的特征向量，对角元为对应特征值。

**可对角化定理**：$n\times n$ 矩阵 $A$ 可对角化 $\iff$ $A$ 有 $n$ 个线性无关的特征向量。此时，$P$ 可取为这些特征向量构成的矩阵。

等价地：每个特征值的几何重数等于其代数重数（当特征多项式在基域上分解为一次因式）。

**证明**：“⇐”若有 $n$ 个线性无关的特征向量 $\mathbf{v}_1,\dots,\mathbf{v}_n$，对应特征值 $\lambda_1,\dots,\lambda_n$，令 $P = [\mathbf{v}_1\ \cdots\ \mathbf{v}_n]$。则 $AP = [\lambda_1\mathbf{v}_1\ \cdots\ \lambda_n\mathbf{v}_n] = P\Lambda$，故 $P^{-1}AP = \Lambda$。

“⇒”若 $A = P\Lambda P^{-1}$，则 $P$ 可逆，其列线性无关。且 $AP = P\Lambda$，即 $A\mathbf{p}_j = \lambda_j \mathbf{p}_j$，故列的每一列都是特征向量。∎

#### 1.3.2 对角化的计算

1. 求 $A$ 的特征值。
2. 对每个特征值求特征空间的一组基。
3. 若所有基向量总数等于 $n$，则它们构成 $P$；否则不可对角化。

**例 1.3** 对角化 $A = \begin{pmatrix}4&1\\2&3\end{pmatrix}$，并计算 $A^{10}$。

解：特征多项式 $\det\begin{pmatrix}4-\lambda&1\\2&3-\lambda\end{pmatrix} = \lambda^2-7\lambda+10 = (\lambda-2)(\lambda-5)$。特征值 $\lambda_1=2,\lambda_2=5$。

- $\lambda_1=2$：$(A-2I)\mathbf{x}=\begin{pmatrix}2&1\\2&1\end{pmatrix}\mathbf{x}=\mathbf{0}$，得特征向量 $\mathbf{v}_1=\begin{pmatrix}1\\-2\end{pmatrix}$。
- $\lambda_2=5$：$(A-5I)\mathbf{x}=\begin{pmatrix}-1&1\\2&-2\end{pmatrix}\mathbf{x}=\mathbf{0}$，得 $\mathbf{v}_2=\begin{pmatrix}1\\1\end{pmatrix}$。

两向量线性无关，故可对角化。取 $P = \begin{pmatrix}1&1\\-2&1\end{pmatrix}$，则 $P^{-1}=\frac13\begin{pmatrix}1&-1\\2&1\end{pmatrix}$，$\Lambda = \begin{pmatrix}2&0\\0&5\end{pmatrix}$。

计算 $A^{10} = P\Lambda^{10}P^{-1} = \frac13\begin{pmatrix}1&1\\-2&1\end{pmatrix}\begin{pmatrix}2^{10}&0\\0&5^{10}\end{pmatrix}\begin{pmatrix}1&-1\\2&1\end{pmatrix}$，具体数值代入即可。

### 1.4 复特征值

实矩阵可能具有共轭复数对特征值。处理方式与实特征值相同，但 $P$ 和 $\Lambda$ 进入复数域。对于 $2\times 2$ 实矩阵有复特征值 $a\pm bi$ 时，可相似于实分块对角形 $\begin{pmatrix}a&-b\\b&a\end{pmatrix}$，用于分析旋转伸缩系统。

**例 1.4** 求 $A = \begin{pmatrix}1 & -1 \\ 5 & -1\end{pmatrix}$ 的特征值，并给出实相似标准形。

解：特征多项式 $\lambda^2 - 0\lambda + 4 = \lambda^2+4 = 0$，特征值 $\pm 2i$。这里 $a=0,b=2$，实相似于 $\begin{pmatrix}0&-2\\2&0\end{pmatrix}$。

### 1.5 线性微分方程组

#### 1.5.1 一阶线性系统

微分方程组 $\mathbf{x}'(t) = A\mathbf{x}(t)$，其中 $A$ 为 $n\times n$ 常矩阵。其解为 $\mathbf{x}(t) = e^{At}\mathbf{x}_0$，其中矩阵指数 $e^{At} = I + At + \frac{1}{2!}A^2 t^2 + \cdots$。若 $A$ 可对角化，则解可写为特征值的指数函数的线性组合：
$$
\mathbf{x}(t) = \sum_{i=1}^n c_i e^{\lambda_i t} \mathbf{v}_i.
$$
系数 $c_i$ 由初始条件 $[c_1,\dots,c_n]^T = P^{-1}\mathbf{x}_0$ 确定。

对于复特征值 $a\pm bi$，对应解含 $e^{at}(\cos bt, \sin bt)$ 项，产生振荡。

**例 1.5** 求解 $\mathbf{x}' = \begin{pmatrix}1&-1\\5&-1\end{pmatrix}\mathbf{x}$，$\mathbf{x}(0)=\begin{pmatrix}1\\0\end{pmatrix}$。

解：特征值 $\pm2i$，特征向量可求得，最终解含 $\cos 2t,\sin 2t$。

#### 1.5.2 高阶微分方程

线性常系数微分方程 $y^{(n)} + a_{n-1}y^{(n-1)} + \dots + a_0 y = 0$ 可化为一阶系统，利用特征值求解。方法与差分方程类似。

### 1.6 特征值的迭代估计

**幂迭代法**：用于求矩阵按模最大的特征值（主特征值）及其特征向量。

设 $A$ 有唯一的主特征值 $\lambda_1$（即 $|\lambda_1| > |\lambda_2| \ge \cdots \ge |\lambda_n|$）。任取初始向量 $\mathbf{x}_0$（假设在特征向量方向有分量），迭代：
$$
\mathbf{y}_{k+1} = A \mathbf{x}_k,\qquad \mathbf{x}_{k+1} = \frac{\mathbf{y}_{k+1}}{\|\mathbf{y}_{k+1}\|}.
$$
则 $\mathbf{x}_k$ 收敛到 $\lambda_1$ 对应的单位特征向量，且瑞丽商 $R(\mathbf{x}_k) = \frac{\mathbf{x}_k^T A \mathbf{x}_k}{\mathbf{x}_k^T \mathbf{x}_k}$ 收敛到 $\lambda_1$。

收敛速率取决于 $|\lambda_2/\lambda_1|$。

**反幂迭代**：对 $(A-\alpha I)^{-1}$ 应用幂迭代，可求最接近 $\alpha$ 的特征值。

**Rayleigh 商迭代**：动态更新 $\alpha_k = R(\mathbf{x}_k)$ 并求解 $(A-\alpha_k I)\mathbf{y} = \mathbf{x}_k$，收敛极快（立方收敛）。

---

## 第二章 正交性与最小二乘法

### 2.1 内积、长度与正交

#### 2.1.1 标准内积

在 $\mathbb{R}^n$ 中，向量 $\mathbf{u}, \mathbf{v}$ 的内积定义为
$$
\langle \mathbf{u}, \mathbf{v} \rangle = \mathbf{u}^T \mathbf{v} = u_1v_1 + \cdots + u_nv_n.
$$
内积满足对称性、线性性、正定性（$\langle \mathbf{u}, \mathbf{u} \rangle \ge 0$，等号当且仅当 $\mathbf{u}=0$）。

**欧几里得长度**（范数）：
$$
\|\mathbf{u}\| = \sqrt{\langle \mathbf{u}, \mathbf{u} \rangle}.
$$

**距离**：$\operatorname{dist}(\mathbf{u},\mathbf{v}) = \|\mathbf{u}-\mathbf{v}\|$。

#### 2.1.2 正交

向量 $\mathbf{u}$ 与 $\mathbf{v}$ 正交，记作 $\mathbf{u}\perp\mathbf{v}$，若 $\langle \mathbf{u},\mathbf{v}\rangle = 0$。

**柯西-施瓦茨不等式**：
$$
|\langle \mathbf{u},\mathbf{v} \rangle| \le \|\mathbf{u}\| \|\mathbf{v}\|.
$$
等号成立当且仅当两向量线性相关。

**三角不等式**：
$$
\|\mathbf{u}+\mathbf{v}\| \le \|\mathbf{u}\| + \|\mathbf{v}\|.
$$

**毕达哥拉斯定理**：若 $\mathbf{u}\perp\mathbf{v}$，则 $\|\mathbf{u}+\mathbf{v}\|^2 = \|\mathbf{u}\|^2 + \|\mathbf{v}\|^2$。

**正交向量组**：若集合中向量两两正交且均为非零向量，则它们必线性无关。

**例 2.1** 验证向量 $\mathbf{u}=(1,2,3)^T$ 与 $\mathbf{v}=(1,1,-1)^T$ 正交。
解：点乘 $1\cdot1 + 2\cdot1 + 3\cdot(-1) = 0$，故正交。

### 2.2 正交集与正交投影

#### 2.2.1 正交基与单位正交基

向量空间 $W$ 的基 $\{\mathbf{u}_1,\dots,\mathbf{u}_p\}$ 称为**正交基**，若向量两两正交。若还满足 $\|\mathbf{u}_i\|=1$ 对所有 $i$，则称为**单位正交基**（或规范正交基）。

在正交基下，坐标系数极易求得：
$$
\mathbf{y} = \sum_{i=1}^p \frac{\langle \mathbf{y}, \mathbf{u}_i \rangle}{\langle \mathbf{u}_i, \mathbf{u}_i \rangle} \mathbf{u}_i.
$$

**定理 2.1**：非零有限维内积空间必存在正交基，且可通过 Gram-Schmidt 方法构造。

#### 2.2.2 Gram-Schmidt 正交化

**算法**：从线性无关向量组 $\{\mathbf{x}_1,\dots,\mathbf{x}_p\}$ 开始，构造正交组 $\{\mathbf{v}_1,\dots,\mathbf{v}_p\}$：

- $\mathbf{v}_1 = \mathbf{x}_1$。
- 对 $k=2,\dots,p$，
  $$
  \mathbf{v}_k = \mathbf{x}_k - \sum_{j=1}^{k-1} \frac{\langle \mathbf{x}_k, \mathbf{v}_j \rangle}{\langle \mathbf{v}_j, \mathbf{v}_j \rangle} \mathbf{v}_j.
  $$
  单位化即得单位正交基。

**QR 分解**：若 $A$ 为 $m\times n$ 列满秩矩阵，则存在列正交矩阵 $Q$ 和上三角可逆矩阵 $R$，使得 $A = QR$。$Q$ 的列由 $A$ 的列施密特正交化再单位化得到，$R_{ij} = \langle \mathbf{q}_i, \mathbf{a}_j \rangle$（$i\le j$）。

**例 2.2** 求 $A = \begin{pmatrix}1&1\\1&0\\0&1\end{pmatrix}$ 的 QR 分解。

解：令 $\mathbf{a}_1=(1,1,0)^T,\mathbf{a}_2=(1,0,1)^T$。正交化：$\mathbf{v}_1=\mathbf{a}_1$；$\mathbf{v}_2 = \mathbf{a}_2 - \frac{1}{2}\mathbf{v}_1 = (\frac12,-\frac12,1)^T$。单位化：$\mathbf{q}_1 = \frac{1}{\sqrt2}(1,1,0)^T$，$\mathbf{q}_2 = \sqrt{\frac{2}{3}}(\frac12,-\frac12,1)^T = \frac{1}{\sqrt6}(1,-1,2)^T$。计算 $R$：$r_{11}=\|\mathbf{a}_1\|=\sqrt2$，$r_{12}=\langle \mathbf{q}_1,\mathbf{a}_2\rangle = \frac{1}{\sqrt2}$，$r_{22}=\|\mathbf{v}_2\| = \sqrt{\frac32}$。故
$$
Q = \begin{pmatrix} 1/\sqrt2 & 1/\sqrt6 \\ 1/\sqrt2 & -1/\sqrt6 \\ 0 & 2/\sqrt6 \end{pmatrix},\quad
R = \begin{pmatrix} \sqrt2 & 1/\sqrt2 \\ 0 & \sqrt{3/2} \end{pmatrix}.
$$

### 2.3 正交投影

#### 2.3.1 投影定理

设 $W$ 是 $\mathbb{R}^n$ 的子空间，$\mathbf{y}\in\mathbb{R}^n$。则存在唯一的 $\hat{\mathbf{y}}\in W$，使得 $\mathbf{y} - \hat{\mathbf{y}} \in W^\perp$。这个 $\hat{\mathbf{y}}$ 称为 $\mathbf{y}$ 在 $W$ 上的**正交投影**。它是 $W$ 中与 $\mathbf{y}$ 距离最近的点，即
$$
\|\mathbf{y} - \hat{\mathbf{y}}\| = \min_{\mathbf{w}\in W} \|\mathbf{y} - \mathbf{w}\|.
$$

**计算公式**：若 $\{\mathbf{u}_1,\dots,\mathbf{u}_p\}$ 是 $W$ 的正交基，则
$$
\hat{\mathbf{y}} = \sum_{i=1}^p \frac{\langle \mathbf{y}, \mathbf{u}_i \rangle}{\langle \mathbf{u}_i, \mathbf{u}_i \rangle} \mathbf{u}_i.
$$
若基为单位正交，则 $\hat{\mathbf{y}} = \sum \langle \mathbf{y}, \mathbf{u}_i \rangle \mathbf{u}_i$。

**投影矩阵**：设单位正交基为 $U = [\mathbf{u}_1\ \cdots\ \mathbf{u}_p]$，则投影矩阵 $P_W = UU^T$，满足 $\hat{\mathbf{y}} = P_W\mathbf{y}$。性质：$P_W^2=P_W$（幂等），$P_W^T = P_W$（对称）。

#### 2.3.2 正交补

$W^\perp = \{\mathbf{z}\mid \mathbf{z}\perp W\}$。有 $\mathbb{R}^n = W \oplus W^\perp$，且 $\dim W + \dim W^\perp = n$。零空间与行空间互为正交补（对于矩阵 $A$），即 $(\operatorname{Row}A)^\perp = \operatorname{Nul}A$。

**例 2.3** $W = \operatorname{span}\{(1,1,0)^T\}$，求 $\mathbf{y}=(2,3,4)^T$ 在 $W$ 上的投影。
解：$\mathbf{u}=(1,1,0)^T$，$\hat{\mathbf{y}} = \frac{2\cdot1+3\cdot1}{1+1}(1,1,0)^T = \frac52 (1,1,0)^T$。

### 2.4 最小二乘问题

#### 2.4.1 问题提出

对于不相容方程组 $A\mathbf{x}=\mathbf{b}$（$\mathbf{b}\notin\operatorname{Col}A$），寻找 $\hat{\mathbf{x}}$ 使误差 $\|A\mathbf{x} - \mathbf{b}\|$ 最小。等价于求 $\mathbf{b}$ 在 $\operatorname{Col}A$ 上的正交投影 $\hat{\mathbf{b}} = A\hat{\mathbf{x}}$。则 $\hat{\mathbf{x}}$ 满足正规方程：
$$
A^T A \hat{\mathbf{x}} = A^T \mathbf{b}.
$$
若 $A$ 列满秩（即 $A^T A$ 可逆），则 $\hat{\mathbf{x}} = (A^T A)^{-1}A^T \mathbf{b}$。

**几何解释**：残差向量 $\mathbf{b}-A\hat{\mathbf{x}}$ 正交于 $\operatorname{Col}A$。

#### 2.4.2 应用：回归分析

线性模型 $y = \beta_0 + \beta_1 t$，数据点 $(t_i,y_i)$。最小二乘解 $\boldsymbol{\beta}=(\beta_0,\beta_1)^T$ 由正规方程给出。对于多项式拟合，设计矩阵 $A$ 包含 $t$ 的各次幂。

**例 2.4** 数据 $(0,1),(1,3),(2,2),(3,4)$，求最小二乘直线 $y=\beta_0+\beta_1 t$。

解：$A = \begin{pmatrix}1&0\\1&1\\1&2\\1&3\end{pmatrix}$，$\mathbf{b}=(1,3,2,4)^T$。$A^T A = \begin{pmatrix}4&6\\6&14\end{pmatrix}$，$A^T\mathbf{b} = \begin{pmatrix}10\\21\end{pmatrix}$。解正规方程得 $\beta_0=0.7,\beta_1=1.2$，即 $y=0.7+1.2t$。

#### 2.4.3 内积空间中的投影

在更一般的内积空间（如连续函数空间 $C[a,b]$，内积 $\langle f,g\rangle = \int_a^b f(x)g(x)dx$）中，正交投影用于函数逼近（如傅里叶级数截断）。最小二乘原理统一线性方程组和函数逼近。

---

## 第三章 对称矩阵与二次型

### 3.1 实对称矩阵的谱定理

**定理 3.1（谱定理）**：若 $A$ 为 $n\times n$ 实对称矩阵，则

- $A$ 的所有特征值都是实数；
- 存在正交矩阵 $Q$（$Q^T Q = I$），使得
  $$
  Q^T A Q = \Lambda = \operatorname{diag}(\lambda_1,\dots,\lambda_n).
  $$
  即 $A$ 可被**正交对角化**。$Q$ 的列是两两正交的单位特征向量。

**证明**：（简要）

*第一步（特征值实数）*：设 $\lambda$ 是特征值，$\mathbf{x}$ 为特征向量（可能复数）。考虑
$$
\lambda \|\mathbf{x}\|^2 = \lambda \overline{\mathbf{x}}^T \mathbf{x} = \overline{\mathbf{x}}^T A \mathbf{x}.
$$
取共轭转置并利用 $A$ 对称，可证 $\lambda$ 为实数，且 $\mathbf{x}$ 可取为实向量。（详细：因为 $\overline{\lambda}\|\mathbf{x}\|^2 = \overline{\mathbf{x}}^T A^T \mathbf{x} = \overline{\mathbf{x}}^T A \mathbf{x}$，而 $\overline{\mathbf{x}}^T A \mathbf{x} = \overline{\lambda}\|\mathbf{x}\|^2$，又左端为 $\lambda\|\mathbf{x}\|^2$ 的共轭，故 $\lambda=\overline{\lambda}$。）

*第二步（不同特征值正交）*：设 $\lambda_i\neq\lambda_j$，对应特征向量 $\mathbf{v}_i,\mathbf{v}_j$。则
$$
\lambda_i \langle \mathbf{v}_i,\mathbf{v}_j \rangle = \langle A\mathbf{v}_i,\mathbf{v}_j \rangle = \langle \mathbf{v}_i, A\mathbf{v}_j \rangle = \lambda_j \langle \mathbf{v}_i,\mathbf{v}_j \rangle,
$$
故 $(\lambda_i-\lambda_j)\langle \mathbf{v}_i,\mathbf{v}_j \rangle = 0$，因此 $\mathbf{v}_i\perp\mathbf{v}_j$。

*第三步（完全正交对角化）*：对矩阵的阶数归纳，或利用 Schur 分解：存在正交矩阵 $Q$ 和上三角矩阵 $T$ 使 $Q^T A Q = T$。由 $A$ 对称，$T$ 也对称，故 $T$ 必为对角阵。此即正交对角化。∎

**谱分解**：
$$
A = \sum_{i=1}^n \lambda_i \mathbf{q}_i \mathbf{q}_i^T,
$$
其中 $\mathbf{q}_i$ 是 $Q$ 的第 $i$ 列。

**推论**：对称矩阵可对角化，且特征空间的几何重数等于代数重数。

### 3.2 二次型

#### 3.2.1 定义与矩阵表示

二次型 $Q(\mathbf{x}) = \mathbf{x}^T A \mathbf{x}$，其中 $A$ 为实对称矩阵。若无特别说明，$A$ 取为对称矩阵（总能通过取平均值使 $A$ 对称）。展开即
$$
Q(\mathbf{x}) = \sum_{i,j} a_{ij} x_i x_j.
$$

**例 3.1** 写出二次型 $Q(\mathbf{x}) = 2x_1^2 + 3x_2^2 + 4x_1x_2$ 的对称矩阵。
解：对角线 $(2,3)$，交叉项平分系数：$a_{12}=a_{21}=2$。故 $A = \begin{pmatrix}2&2\\2&3\end{pmatrix}$。

#### 3.2.2 主轴定理

通过正交变换 $\mathbf{x} = Q\mathbf{y}$（即坐标旋转），二次型化为标准型（无交叉项）：
$$
Q(\mathbf{x}) = \mathbf{y}^T \Lambda \mathbf{y} = \lambda_1 y_1^2 + \cdots + \lambda_n y_n^2.
$$
其中 $\lambda_i$ 是 $A$ 的特征值。这称为**主轴形式**。

**正定性**：$A$ 称为

- **正定**，若对所有 $\mathbf{x}\neq\mathbf{0}$，$Q(\mathbf{x}) > 0$。
- **半正定**，若 $Q(\mathbf{x})\ge 0$。
- 负定、不定类似。

**判定定理**（Sylvester 准则）：实对称矩阵 $A$ 正定 $\iff$ 其所有顺序主子式 $>0$。也等价于所有特征值 $>0$。

**例 3.2** 判定 $A = \begin{pmatrix}2&-1&0\\-1&2&-1\\0&-1&2\end{pmatrix}$ 是否正定。
解：顺序主子式 $D_1=2>0$，$D_2=\begin{vmatrix}2&-1\\-1&2\end{vmatrix}=3>0$，$D_3=\det A = 4>0$，故正定。特征值计算也可验证。

### 3.3 瑞丽商（Rayleigh Quotient）

**定义**：对实对称矩阵 $A$ 和非零向量 $\mathbf{x}$，瑞丽商定义为
$$
R(\mathbf{x}) = \frac{\mathbf{x}^T A \mathbf{x}}{\mathbf{x}^T \mathbf{x}}.
$$

**性质**：

1. 若 $\mathbf{x}$ 是特征向量（特征值 $\lambda$），则 $R(\mathbf{x}) = \lambda$。
2. 瑞丽商的值域是整个实数区间 $[\lambda_{\min}, \lambda_{\max}]$，其中 $\lambda_{\min}$ 和 $\lambda_{\max}$ 分别为最小和最大特征值。
3. $\max_{\mathbf{x}\neq\mathbf{0}} R(\mathbf{x}) = \lambda_{\max}$，在对应的单位特征向量处取得；$\min = \lambda_{\min}$。
4. 若 $\mathbf{x}$ 正交于前 $k$ 个最小的特征向量，则 $R(\mathbf{x}) \ge \lambda_{k+1}$，等等。由此导出 **Courant-Fischer 极小极大原理**。

**Courant-Fischer 定理**：
设特征值排序 $\lambda_1 \ge \lambda_2 \ge \cdots \ge \lambda_n$。则
$$
\lambda_k = \max_{\dim W = k} \ \min_{\substack{\mathbf{x}\in W \\ \mathbf{x}\neq\mathbf{0}}} R(\mathbf{x})
       = \min_{\dim W = n-k+1} \ \max_{\substack{\mathbf{x}\in W \\ \mathbf{x}\neq\mathbf{0}}} R(\mathbf{x}).
$$

**证明思路**：考虑子空间 $W = \operatorname{span}\{\mathbf{q}_k,\dots,\mathbf{q}_n\}$（特征向量空间），可得 $R(\mathbf{x})\le \lambda_k$；另一半类似。

**瑞丽商的应用**：用于特征值的变分特征、摄动分析、数值估计（如前幂迭代中的瑞丽商加速）。

**例 3.3** 用瑞丽商估计 $A = \begin{pmatrix}3&1\\1&3\end{pmatrix}$ 的最大最小特征值。
解：任意 $\mathbf{x}$，$R(\mathbf{x}) = \frac{3x_1^2+3x_2^2+2x_1x_2}{x_1^2+x_2^2}$。配方法或求导可得最大特征值 $4$（当 $x_1=x_2$），最小 $2$（当 $x_1=-x_2$），与实际特征值 $4$ 和 $2$ 相符。

### 3.4 条件优化

问题：在约束 $\|\mathbf{x}\| = 1$ 或其他二次型约束下，求二次型 $Q(\mathbf{x})$ 的最值。

**定理 3.2**：在单位球面 $\|\mathbf{x}\|=1$ 上，$\mathbf{x}^T A \mathbf{x}$ 的最大值和最小值分别是 $A$ 的最大和最小特征值，且在对应的单位特征向量处取得。

推广到一般约束 $\mathbf{x}^T B \mathbf{x} = 1$（$B$ 正定）：最值问题等价于广义特征值问题 $A\mathbf{x} = \lambda B\mathbf{x}$。

**例 3.4** 求 $f(x,y)=3x^2+2y^2+2xy$ 在 $x^2+y^2=1$ 下的最大值。
解：矩阵 $A=\begin{pmatrix}3&1\\1&2\end{pmatrix}$，特征值 $\frac{5\pm\sqrt5}{2}$，故最大值为 $\frac{5+\sqrt5}{2}$，对应特征向量给出极值点方向。

### 3.5 奇异值分解（SVD）

虽然前面章节已出现，这里完整表述作为对称矩阵和正交性的综合应用。

**定理 3.3（奇异值分解）**：设 $A$ 为 $m\times n$ 实矩阵，秩为 $r$。则存在正交矩阵 $U\in\mathbb{R}^{m\times m}$ 和 $V\in\mathbb{R}^{n\times n}$，使
$$
A = U \Sigma V^T,
$$
其中 $\Sigma$ 为 $m\times n$ 矩阵，其主对角线元素为 $\sigma_1 \ge \sigma_2 \ge \cdots \ge \sigma_r > 0$，其余元素为 $0$。$\sigma_i$ 称为 $A$ 的**奇异值**，等于 $A^T A$（或 $AA^T$）的正特征值的平方根。

**证明概要**：

1. $A^T A$ 是 $n\times n$ 对称半正定矩阵，可正交对角化：存在正交矩阵 $V$ 使 $V^T (A^T A) V = \operatorname{diag}(\lambda_1,\dots,\lambda_n)$，特征值 $\lambda_i \ge 0$。设非零特征值 $\lambda_1,\dots,\lambda_r > 0$，定义 $\sigma_i = \sqrt{\lambda_i}$。
2. 对 $i=1,\dots,r$，令 $\mathbf{u}_i = \frac{1}{\sigma_i} A \mathbf{v}_i$。可验证 $\mathbf{u}_i$ 互为正交单位向量。扩充为 $\mathbb{R}^m$ 的一组单位正交基 $\mathbf{u}_1,\dots,\mathbf{u}_m$。
3. 取 $U = [\mathbf{u}_1\ \cdots\ \mathbf{u}_m]$，直接计算可得 $AV = U\Sigma$，从而 $A = U\Sigma V^T$。

**奇异值的性质**：

- 非零奇异值的个数等于 $\operatorname{rank}A$。
- $A$ 的算子范数（2-范数）$\|A\|_2 = \sigma_1$。
- $A$ 的 Moore-Penrose 广义逆 $A^+ = V \Sigma^+ U^T$，其中 $\Sigma^+$ 将 $\Sigma$ 的非零奇异值取倒数并转置。
- 低秩逼近：若取前 $k$ 个最大的奇异值及相关奇异向量，则 $\hat{A}_k = \sum_{i=1}^k \sigma_i \mathbf{u}_i \mathbf{v}_i^T$ 是秩 $k$ 矩阵中在 Frobenius 范数下对 $A$ 的最佳逼近（Eckart-Young 定理）。

**例 3.5** 求 $A = \begin{pmatrix}1&0\\0&1\\1&1\end{pmatrix}$ 的 SVD。

解：$A^T A = \begin{pmatrix}2&1\\1&2\end{pmatrix}$，特征值 $3,1$，故 $\sigma_1=\sqrt3,\sigma_2=1$。相应特征向量 $\mathbf{v}_1=\frac1{\sqrt2}(1,1)^T,\mathbf{v}_2=\frac1{\sqrt2}(1,-1)^T$。计算 $\mathbf{u}_1 = \frac1{\sigma_1}A\mathbf{v}_1 = \frac1{\sqrt6}(1,1,2)^T$，$\mathbf{u}_2 = \frac1{\sigma_2}A\mathbf{v}_2 = \frac1{\sqrt2}(1,-1,0)^T$。扩充 $\mathbf{u}_3$ 正交于前两者（例如 $(1,1,-1)^T$ 单位化）。可得完整分解。

**应用**：图像压缩、主成分分析、求解最小二乘问题（利用伪逆）、信号处理等。

---

