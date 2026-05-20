# 线性代数（复习笔记）

[TOC]

## 第1章 线性方程组

### 1.1 线性方程组与矩阵

含 $n$ 个未知量 $x_1,\dots,x_n$ 的**线性方程**：
$$
a_1x_1 + a_2x_2 + \dots + a_nx_n = b,
$$
其中 $a_i$ 为系数，$b$ 为常数项。

线性方程组（$m$ 个方程、$n$ 个未知量）：
$$
\begin{cases}
a_{11}x_1 + a_{12}x_2 + \dots + a_{1n}x_n = b_1 \\
a_{21}x_1 + a_{22}x_2 + \dots + a_{2n}x_n = b_2 \\
\qquad \vdots \\
a_{m1}x_1 + a_{m2}x_2 + \dots + a_{mn}x_n = b_m
\end{cases}
$$

解集的三种可能：**无解**、**唯一解**、**无穷多解**。

#### 矩阵表示


系数矩阵 $A$ 与增广矩阵 $\tilde A = [A \mid \mathbf b]$：
$$
A = \begin{pmatrix}
a_{11} & \dots & a_{1n} \\
\vdots & \ddots & \vdots \\
a_{m1} & \dots & a_{mn}
\end{pmatrix},\qquad
\tilde A = \left(\begin{array}{ccc|c}
a_{11} & \dots & a_{1n} & b_1 \\
\vdots & \ddots & \vdots & \vdots \\
a_{m1} & \dots & a_{mn} & b_m
\end{array}\right).
$$

求解线性方程组的基本方法：**初等行变换**（高斯消元法），将增广矩阵化为**行阶梯形**或**简化行阶梯形**。

### 1.2 行化简与行阶梯形

**行等价**：两个矩阵可通过初等行变换相互转化。

初等行变换：

1. 交换两行；
2. 某行乘以非零常数；
3. 一行的倍数加到另一行。

**行阶梯形**（REF）：


- 全零行在矩阵底部；
- 每一行的主元（第一个非零元）在上一行主元的右侧；
- 主元为 1（有时不要求为 1，称为简化阶梯形时才要求）。

**简化行阶梯形**（RREF）：

- 满足 REF；
- 主元为 1；
- 主元所在列其余元素全为 0。

每个矩阵行等价于唯一的简化行阶梯形。

**基本变量与自由变量**：

- 主元对应的变量为基本变量；
- 其余变量为自由变量。
自由变量的个数等于未知量个数减去主元个数，决定解的维度。

### 1.3 向量方程与矩阵方程

向量 $\mathbf v \in \mathbb R^n$ 的线性组合：$c_1\mathbf v_1 + \dots + c_p\mathbf v_p$。

向量方程 $\displaystyle\sum_{j=1}^n x_j \mathbf a_j = \mathbf b$ 等价于线性方程组 $A\mathbf x = \mathbf b$，其中 $A$ 的列是 $\mathbf a_1,\dots,\mathbf a_n$。

**矩阵方程**：$A\mathbf x = \mathbf b$，$A\in\mathbb R^{m\times n}$。

解的存在性：$\mathbf b$ 属于 $A$ 的列空间（$\operatorname{Col}A$），即 $\mathbf b$ 可表为 $A$ 的列向量的线性组合。

### 1.4 齐次方程组

$A\mathbf x = \mathbf 0$ 称为**齐次**方程组。它总有**平凡解** $\mathbf x = \mathbf 0$。
存在非平凡解 $\iff$ 方程组有自由变量 $\iff$ 方程个数小于未知量个数时（不定系统）一定有非平凡解（但并非充要条件，具体要看秩）。

解的结构：齐次方程的解集是 $\mathbb R^n$ 的一个子空间，非齐次方程的通解可写为**特解 + 齐次解**。

### 1.5 线性无关

向量组 $\{\mathbf v_1,\dots,\mathbf v_p\}$ 称为**线性无关**，若方程 $c_1\mathbf v_1+\dots+c_p\mathbf v_p = \mathbf 0$ 只有平凡解 $c_1=\dots=c_p=0$；否则**线性相关**。

判别方法：将向量作为矩阵的列，行化简后看是否有自由变量（或主元个数是否等于向量个数）。主元个数等于向量个数 $\implies$ 线性无关。

### 1.6 线性变换简介

从 $\mathbb R^n$ 到 $\mathbb R^m$ 的线性变换 $T$ 满足：对任意标量 $c$ 和向量 $\mathbf u,\mathbf v$，
$$
T(c\mathbf u) = c\,T(\mathbf u),\qquad T(\mathbf u+\mathbf v) = T(\mathbf u)+T(\mathbf v).
$$
每个 $m\times n$ 矩阵 $A$ 通过 $T(\mathbf x)=A\mathbf x$ 定义一个从 $\mathbb R^n$ 到 $\mathbb R^m$ 的线性变换。

---

### 典型例题

**例1**
解方程组，视解集为参数向量形式：
$$
\begin{cases}
x_1 + 2x_2 - x_3 = 4 \\
2x_1 - x_2 + 3x_3 = 1
\end{cases}
$$

**解**：增广矩阵行化简：
$$
\left(\begin{array}{ccc|c}
1 & 2 & -1 & 4\\
2 & -1 & 3 & 1
\end{array}\right)
\sim
\left(\begin{array}{ccc|c}
1 & 2 & -1 & 4\\
0 & -5 & 5 & -7
\end{array}\right)
\sim
\left(\begin{array}{ccc|c}
1 & 0 & 1 & \frac{6}{5}\\
0 & 1 & -1 & \frac{7}{5}
\end{array}\right).
$$
基本变量 $x_1,x_2$，自由变量 $x_3$。解：
$$
\begin{cases}
x_1 = \frac{6}{5} - x_3,\\
x_2 = \frac{7}{5} + x_3,\\
x_3 \text{ 自由}.
\end{cases}
$$
参数向量形式：$\mathbf x = \begin{pmatrix}6/5\\7/5\\0\end{pmatrix} + t\begin{pmatrix}-1\\1\\1\end{pmatrix}$。

**例2**
$A = \begin{pmatrix}1 & 2 & 3\\4 & 5 & 6\end{pmatrix}$ 的列是否线性无关？
**解**：矩阵有 3 列，但只有 2 行，行化简后最多 2 个主元，因此一定有自由变量，三列必然线性相关。

---

## 第2章 矩阵代数

### 2.1 矩阵运算

加法和数乘：对应元素相加减、乘以常数。

矩阵乘法 $C = AB$（$A$ 为 $m\times n$，$B$ 为 $n\times p$）：

- $C$ 的元素 $(i,j)$ 是 $A$ 的第 $i$ 行与 $B$ 的第 $j$ 列的内积。
- 矩阵乘法不满足交换律（一般 $AB \neq BA$）。
- 满足结合律 $(AB)C = A(BC)$，分配律 $A(B+C)=AB+AC$。

**注意**：乘积 $AB$ 可逆 $\iff$ $A$ 和 $B$ 均可逆？

### 2.2 矩阵的逆

方阵 $A$ 若存在 $B$ 使得 $AB = BA = I$，则称 $A$ **可逆**，$B = A^{-1}$ 是 $A$ 的**逆矩阵**。

**$2\times 2$ 矩阵求逆公式**：
$$
A = \begin{pmatrix} a & b \\ c & d \end{pmatrix} \;\Longrightarrow\; 
A^{-1} = \frac{1}{ad-bc} \begin{pmatrix} d & -b \\ -c & a \end{pmatrix},\quad \text{要求 } ad-bc \neq 0.
$$
$ad-bc = \det A$。

**可逆矩阵定理**（$n\times n$ 矩阵 $A$）：以下等价：


1. $A$ 可逆；
2. $\det A \neq 0$；
3. $A$ 行等价于 $I_n$；
4. $A\mathbf x=\mathbf 0$ 只有平凡解；
5. $A$ 的列线性无关；
6. $A\mathbf x = \mathbf b$ 对任意 $\mathbf b$ 有唯一解；
7. $A^T$ 可逆；
8. $\operatorname{rank}A = n$；
… 等等。

求逆的一般方法：对 $(A\mid I)$ 进行行化简至 $(I\mid A^{-1})$。

### 2.3 分块矩阵

矩阵可按分块方式相乘（按行列分块），遵循类似普通乘法的规则，但要求分块尺寸相容。

### 2.4 矩阵的转置


$(A^T)_{ij} = A_{ji}$。性质：

- $(A^T)^T = A$；
- $(A+B)^T = A^T + B^T$；
- $(AB)^T = B^T A^T$。

对称矩阵：$A^T = A$。反对称矩阵：$A^T = -A$。

---

### 典型例题

**例1**
若 $A = \begin{pmatrix}1 & 2\\3 & 4\end{pmatrix}$，求 $A^{-1}$。
**解**：$\det A = -2$，利用公式：
$$
A^{-1} = -\frac{1}{2} \begin{pmatrix}4 & -2\\-3 & 1\end{pmatrix}
= \begin{pmatrix}-2 & 1\\1.5 & -0.5\end{pmatrix}.
$$

**例2**
证明若 $A$ 可逆，则 $(A^{-1})^T = (A^T)^{-1}$。
**证**：由 $AA^{-1}=I$，转置得 $(A^{-1})^T A^T = I$，故 $(A^{-1})^T = (A^T)^{-1}$。



---

## 第3章 行列式

### 3.1 行列式的定义与计算

**$2\times2$ 矩阵的行列式**：
$$
\det\begin{pmatrix} a & b \\ c & d \end{pmatrix} = ad - bc.
$$

**$n\times n$ 矩阵的行列式**（递归定义）：
设 $A=(a_{ij})$，记 $A_{ij}$ 为划去第 $i$ 行和第 $j$ 列后得到的 $(n-1)\times(n-1)$ 子式。
按第 $i$ 行展开：
$$
\det A = \sum_{j=1}^{n} (-1)^{i+j} a_{ij} \det A_{ij}.
$$
按第 $j$ 列展开类似。展开结果与行或列的选择无关。

**常用性质**（简化计算）：

1. 若 $A$ 为三角阵，则 $\det A = \prod a_{ii}$。
2. 交换两行，行列式变号。
3. 某行乘以常数 $c$，则行列式乘以 $c$。
4. 一行的倍数加到另一行，行列式不变。
5. $\det A^T = \det A$。
6. 若两行相等或成比例，则 $\det A = 0$。
7. 对 $n\times n$ 矩阵 $A$ 和 $B$，$\det(AB) = (\det A)(\det B)$。

**证明（乘积定理概要）**：
可借助初等矩阵：任何方阵可分解为初等矩阵的乘积。初等矩阵的行列式容易计算：交换两行的初等矩阵行列式为 $-1$；倍乘行为 $c$ 的初等矩阵行列式为 $c$；倍加行为 $1$。利用 $\det(EA) = (\det E)(\det A)$（初等矩阵作用相当于上述性质），以及 $\det(AB) = \det(E_k\dots E_1 B) = (\det E_k)\dots(\det E_1) \det B = \det A \det B$（当 $A$ 可逆时）。若 $A$ 不可逆，则两边均为 $0$。详细展开略。

### 3.2 克拉默法则与伴随矩阵

**克拉默法则**（仅当 $A$ 可逆，即 $\det A \neq 0$）：
方程组 $A\mathbf x = \mathbf b$ 的唯一解为
$$
x_j = \frac{\det A_j(\mathbf b)}{\det A},
$$
其中 $A_j(\mathbf b)$ 是将 $A$ 的第 $j$ 列替换为 $\mathbf b$ 所得的矩阵。

**伴随矩阵**（古典伴随）：
$$
\operatorname{adj} A = (C_{ij})^T,\quad C_{ij} = (-1)^{i+j} \det A_{ij}.
$$
则 $A^{-1} = \frac{1}{\det A}\operatorname{adj}A$。

**几何意义**：$\det A$ 表示由 $A$ 的列向量张成的平行 $n$ 面体的有向体积。特别地，$\det A=0$ 意味着这些向量线性相关。

---

### 典型例题

**例1** 计算 $A = \begin{pmatrix} 2 & 1 & 3 \\ -1 & 5 & 0 \\ 4 & -2 & 6 \end{pmatrix}$ 的行列式。
**解**：先利用行变换化简：将第1行加到第2行，再将第1行乘以 $-2$ 加到第3行，然后按列展开。
$$
\begin{aligned}
\det A &= \begin{vmatrix} 2 & 1 & 3 \\ -1 & 5 & 0 \\ 4 & -2 & 6 \end{vmatrix}
= \begin{vmatrix} 2 & 1 & 3 \\ 1 & 6 & 3 \\ 0 & -4 & 0 \end{vmatrix} \quad (\text{第1行加到第2行, 第1行乘-2加到第3行}) \\
&= -(-4) \begin{vmatrix} 2 & 3 \\ 1 & 3 \end{vmatrix} \quad (\text{按第3行展开}) = 4(6-3) = 12.
\end{aligned}
$$

**例2** 用克拉默法则解 $x_1 + 2x_2 = 6,\; 3x_1 + 4x_2 = 10$。
**解**：$\det A = \begin{vmatrix}1&2\\3&4\end{vmatrix} = -2$，
$x_1 = \frac{\begin{vmatrix}6&2\\10&4\end{vmatrix}}{-2} = \frac{24-20}{-2} = -2$，
$x_2 = \frac{\begin{vmatrix}1&6\\3&10\end{vmatrix}}{-2} = \frac{10-18}{-2} = 4$。

---

## 第4章 向量空间

### 4.1 向量空间与子空间

**定义**：一个非空集合 $V$ 称为（实）向量空间，若定义了加法和标量乘法，且满足八条公理（交换、结合、零元、负元、标量分配等）。常见的例子：$\mathbb R^n$，$m\times n$ 矩阵空间 $M_{m\times n}$，多项式空间 $\mathbb P_n$。

**子空间**：向量空间 $V$ 的非空子集 $H$ 是子空间，若对任意 $\mathbf u,\mathbf v\in H$ 和标量 $c$，有 $\mathbf u+\mathbf v\in H,\; c\mathbf u\in H$。
等价地，$H$ 包含零向量，且对加法和数乘封闭。

**列空间与零空间**：
对于 $m\times n$ 矩阵 $A$，

- 列空间 $\operatorname{Col}A = \operatorname{span}\{\mathbf a_1,\dots,\mathbf a_n\} \subseteq \mathbb R^m$。
- 零空间 $\operatorname{Nul}A = \{\mathbf x\in\mathbb R^n : A\mathbf x = \mathbf 0\} \subseteq \mathbb R^n$。

两者都是子空间（分别属于 $\mathbb R^m$ 和 $\mathbb R^n$）。

### 4.2 基与维数

向量组 $\mathcal{B} = \{\mathbf b_1,\dots,\mathbf b_p\}$ 是子空间 $H$ 的**基**，若 $\mathcal{B}$ 线性无关且生成 $H$。

**定理**：子空间的任意两个基含有相同个数的向量。这个个数称为子空间的**维数**，记 $\dim H$。

**证明梗概**（基的个数不变性）：设 $\mathcal{B}_1,\mathcal{B}_2$ 是 $H$ 的两个基，大小分别为 $p$ 和 $q$。若 $p>q$，则 $\mathcal{B}_1$ 可由 $\mathcal{B}_2$ 线性表示，将导致 $\mathcal{B}_1$ 线性相关（通过构造系数矩阵的齐次方程有非零解），矛盾。故 $p\le q$；由对称性 $q\le p$，因此 $p=q$。详细证明利用“线性相关引理”：若向量组 $\{\mathbf v_1,\dots,\mathbf v_p\}$ 可由 $\{\mathbf u_1,\dots,\mathbf u_q\}$ 生成且 $p>q$，则前者线性相关。

**常见的基和维数**：


- $\mathbb R^n$ 的标准基 $\mathbf e_1,\dots,\mathbf e_n$，$\dim \mathbb R^n = n$。
- $M_{2\times 2}$ 的基：$\begin{pmatrix}1&0\\0&0\end{pmatrix},\begin{pmatrix}0&1\\0&0\end{pmatrix},\begin{pmatrix}0&0\\1&0\end{pmatrix},\begin{pmatrix}0&0\\0&1\end{pmatrix}$，$\dim M_{2\times 2}=4$。
- $n$ 次多项式空间 $\mathbb P_n$ 的基 $\{1,t,t^2,\dots,t^n\}$，$\dim \mathbb P_n = n+1$。

**矩阵的秩**：$\operatorname{rank} A = \dim \operatorname{Col}A$（列空间的维数）。同时也等于 $\dim \operatorname{Row}A$（行空间的维数）。
**秩定理**：对于 $m\times n$ 矩阵 $A$，
$$
\operatorname{rank} A + \dim \operatorname{Nul}A = n.
$$
**证明**：通过行化简为行阶梯形，设主元个数 $r$ 为秩。则自由变量个数为 $n-r$，而自由变量的个数正等于零空间的维数（因为每个自由变量对应一个解空间的基向量）。故结论成立。

### 4.3 线性变换的矩阵表示

设 $T:V\rightarrow W$ 是线性变换，$\mathcal{B}=\{\mathbf b_1,\dots,\mathbf b_n\}$ 是 $V$ 的基，$\mathcal{C}$ 是 $W$ 的基。$T$ 关于这两组基的矩阵 $M$ 满足：
$$
T(\mathbf b_j) = \sum_{i=1}^m m_{ij} \mathbf c_i,
$$
即 $M$ 的第 $j$ 列是 $T(\mathbf b_j)$ 在基 $\mathcal{C}$ 下的坐标。从而对任意 $\mathbf v = \sum x_j \mathbf b_j$，其像的坐标为 $M\mathbf x$（其中 $\mathbf x$ 为 $\mathbf v$ 在基 $\mathcal{B}$ 下的坐标向量）。

当 $V=W$ 且 $\mathcal{B}=\mathcal{C}$ 时，得到方阵表示，进而可研究相似性。

### 4.4 基变换与坐标变换

设 $\mathcal{B},\mathcal{C}$ 是 $V$ 的基，则存在可逆矩阵 $P_{\mathcal{C}\leftarrow\mathcal{B}}$，使得对任意 $\mathbf v\in V$，
$$
[\mathbf v]_{\mathcal{C}} = P_{\mathcal{C}\leftarrow\mathcal{B}} [\mathbf v]_{\mathcal{B}}.
$$
该矩阵的列是 $\mathcal{B}$ 中的向量在 $\mathcal{C}$ 基下的坐标。

---

### 典型例题

**例1** 求矩阵 $A = \begin{pmatrix} 1 & 2 & 3 \\ 4 & 5 & 6 \\ 7 & 8 & 9 \end{pmatrix}$ 的秩和零空间维数。
**解**：行化简：
$$
A \sim \begin{pmatrix} 1 & 2 & 3 \\ 0 & -3 & -6 \\ 0 & -6 & -12 \end{pmatrix} \sim \begin{pmatrix} 1 & 2 & 3 \\ 0 & 1 & 2 \\ 0 & 0 & 0 \end{pmatrix}.
$$
秩 $r=2$，$\dim \operatorname{Nul}A = 3 - 2 = 1$。

**例2** 判断下列集合是否构成 $\mathbb R^3$ 的子空间：$H = \{ (x,y,z) : x + 2y - z = 0 \}$。
**解**：是。该集合是齐次线性方程组的解集，即矩阵 $(1,2,-1)$ 的零空间，自动为 $\mathbb R^3$ 的子空间。

---

## 第5章 特征值与特征向量

### 5.1 特征值与特征向量的定义

设 $A$ 为 $n\times n$ 方阵。若存在非零向量 $\mathbf x$ 和标量 $\lambda$ 满足
$$
A\mathbf x = \lambda \mathbf x,
$$
则称 $\lambda$ 为 $A$ 的**特征值** (eigenvalue)，$\mathbf x$ 为属于 $\lambda$ 的**特征向量** (eigenvector)。

几何意义：$A$ 作用于 $\mathbf x$ 仅仅拉伸或压缩 $\mathbf x$（不改变方向，可能反向）。

**特征空间**：属于同一特征值 $\lambda$ 的全体特征向量连同 $\mathbf 0$ 构成 $\mathbb R^n$ 的子空间，称为 $\lambda$ 的特征空间，即 $\operatorname{Nul}(A-\lambda I)$。

### 5.2 特征方程

$\lambda$ 是 $A$ 的特征值 $\iff$ $\det(A-\lambda I) = 0$。
称 $\det(A-\lambda I)$ 为 $A$ 的**特征多项式** (characteristic polynomial)，是关于 $\lambda$ 的 $n$ 次多项式。

**定理**：$n\times n$ 矩阵的特征方程在复数域内有 $n$ 个根（重数按代数重数计算）。
**代数重数**：特征值作为特征多项式根的重数。
**几何重数**：对应特征空间的维数（即 $\dim\operatorname{Nul}(A-\lambda I)$）。必有 **$1 \le$ 几何重数 $\le$ 代数重数**。

**证明**（几何重数 $\le$ 代数重数）：设 $\lambda_0$ 的特征空间维数为 $r$，取其一组基扩充为 $\mathbb C^n$ 的基，在此基下 $A$ 可表示成 $\begin{pmatrix}\lambda_0 I_r & * \\ 0 & B\end{pmatrix}$，从而特征多项式含有因子 $(\lambda-\lambda_0)^r$，故代数重数至少为 $r$。

### 5.3 相似性与对角化

矩阵 $A$ 与 $B$ 称为**相似**，若存在可逆矩阵 $P$ 使得 $A = PBP^{-1}$。相似矩阵具有相同的特征多项式、特征值、行列式、迹和秩。

**对角化**：若方阵 $A$ 相似于一个对角矩阵 $\Lambda = \operatorname{diag}(\lambda_1,\dots,\lambda_n)$，则称 $A$ 可对角化。等价地，存在可逆矩阵 $P$ 使得 $P^{-1}AP = \Lambda$。此时 $P$ 的列是 $A$ 的 $n$ 个线性无关的特征向量，对角元为对应的特征值。

**可对角化定理**：$A$ 可对角化 $\iff$ $A$ 有 $n$ 个线性无关的特征向量。
该条件等价于：每个特征值的几何重数等于其代数重数（对特征多项式在复数域上完全分解的情况）。

**证明**：若 $A$ 可对角化，则 $P^{-1}AP = \Lambda$，$P$ 的列就是 $n$ 个特征向量且可逆，故线性无关。反之，若有 $n$ 个线性无关的特征向量，将它们构成 $P$，则 $AP = A[\mathbf v_1,\dots,\mathbf v_n] = [\lambda_1\mathbf v_1,\dots,\lambda_n\mathbf v_n] = P\Lambda$，即 $P^{-1}AP = \Lambda$。

**应用：矩阵幂**。若 $A = PDP^{-1}$，则 $A^k = PD^kP^{-1}$，便于计算。

### 5.4 复特征值

实矩阵可能有复特征值，它们以共轭对出现。对于实矩阵的复特征值，可通过对角化（在复数域中）或实相似块对角化处理。特别是 $2\times 2$ 实矩阵若有复特征值 $a\pm bi$，则可相似于旋转－伸缩矩阵 $\begin{pmatrix} a & -b \\ b & a \end{pmatrix}$。

### 5.5 离散动力系统

递推关系 $\mathbf x_{k+1} = A\mathbf x_k$ 描述一个离散动力系统。其解为 $\mathbf x_k = A^k\mathbf x_0$。若 $A$ 可对角化，则可写出通解 $\mathbf x_k = \sum c_i \lambda_i^k \mathbf v_i$。系统的长期行为取决于特征值的模长：$|\lambda|<1$ 的分量衰减，$|\lambda|>1$ 的分量增长。

---

### 典型例题

**例1** 求 $A = \begin{pmatrix} 2 & 1 \\ 1 & 2 \end{pmatrix}$ 的特征值与特征向量，并判断是否可对角化。
**解**：特征方程 $\det\begin{pmatrix}2-\lambda & 1\\1 & 2-\lambda\end{pmatrix} = (2-\lambda)^2 - 1 = \lambda^2-4\lambda+3 = (\lambda-1)(\lambda-3)=0$，特征值 $\lambda_1=1,\lambda_2=3$。
$\lambda_1=1$：解 $(A-I)\mathbf x=\mathbf 0$，得 $\mathbf v_1 = \begin{pmatrix}-1\\1\end{pmatrix}$。
$\lambda_2=3$：解 $(A-3I)\mathbf x=\mathbf 0$，得 $\mathbf v_2 = \begin{pmatrix}1\\1\end{pmatrix}$。
两向量线性无关，故可对角化：$P = \begin{pmatrix}-1&1\\1&1\end{pmatrix}$，$P^{-1}AP = \begin{pmatrix}1&0\\0&3\end{pmatrix}$。

**例2** 计算 $A^k$，其中 $A = \begin{pmatrix} 2 & 1 \\ 1 & 2 \end{pmatrix}$，并求 $\mathbf x_{k+1}=A\mathbf x_k$ 满足 $\mathbf x_0 = (3,1)^T$ 的解。
**解**：由例1，$A = PDP^{-1}$，$D=\begin{pmatrix}1&0\\0&3\end{pmatrix}$，$P=\begin{pmatrix}-1&1\\1&1\end{pmatrix}$，$P^{-1}=\frac{1}{2}\begin{pmatrix}-1&1\\1&1\end{pmatrix}$。
$A^k = PD^kP^{-1} = \frac{1}{2}\begin{pmatrix}-1&1\\1&1\end{pmatrix}\begin{pmatrix}1^k&0\\0&3^k\end{pmatrix}\begin{pmatrix}-1&1\\1&1\end{pmatrix} = \frac{1}{2}\begin{pmatrix}1+3^k & -1+3^k \\ -1+3^k & 1+3^k\end{pmatrix}$。
$\mathbf x_0 = \begin{pmatrix}3\\1\end{pmatrix}$，坐标变换：$P^{-1}\mathbf x_0 = \frac{1}{2}\begin{pmatrix}-1&1\\1&1\end{pmatrix}\begin{pmatrix}3\\1\end{pmatrix} = \begin{pmatrix}-1\\2\end{pmatrix}$。
故 $\mathbf x_k = A^k\mathbf x_0 = PD^k(P^{-1}\mathbf x_0) = \begin{pmatrix}-1&1\\1&1\end{pmatrix} \begin{pmatrix}1^k\cdot(-1)\\3^k\cdot2\end{pmatrix} = \begin{pmatrix} -(-1) + 2\cdot 3^k \\ (-1) + 2\cdot 3^k \end{pmatrix} = \begin{pmatrix} 1 + 2\cdot 3^k \\ -1 + 2\cdot 3^k \end{pmatrix}$。

---

## 第6章 正交性与最小二乘法

### 6.1 内积、长度与正交性

$\mathbb R^n$ 上标准内积（点积）：$\langle \mathbf u, \mathbf v \rangle = \mathbf u^T\mathbf v$。

向量的长度（范数）：$\|\mathbf v\| = \sqrt{\langle \mathbf v,\mathbf v \rangle}$。
**柯西-施瓦茨不等式**：$|\langle \mathbf u,\mathbf v\rangle| \le \|\mathbf u\|\|\mathbf v\|$。等号成立当且仅当 $\mathbf u$ 与 $\mathbf v$ 线性相关。

**正交**：$\mathbf u$ 与 $\mathbf v$ 正交 $\iff \langle \mathbf u,\mathbf v \rangle = 0$。
若向量集合中任意两个不同向量正交，则称该集合为正交集。不含零向量的正交集是线性无关的。

**单位正交基（标准正交基）**：基中向量两两正交且均为单位长度。典型例子：$\mathbb R^n$ 的标准基。

### 6.2 正交投影

设 $W$ 是 $\mathbb R^n$ 的子空间，$\{\mathbf u_1,\dots,\mathbf u_p\}$ 是 $W$ 的一组正交基。对任意 $\mathbf y \in \mathbb R^n$，$\mathbf y$ 在 $W$ 上的**正交投影** $\hat{\mathbf y}$ 唯一存在且可表示为：
$$
\hat{\mathbf y} = \sum_{i=1}^p \frac{\langle \mathbf y, \mathbf u_i \rangle}{\langle \mathbf u_i, \mathbf u_i \rangle} \mathbf u_i.
$$
若基是单位正交的，则简化为 $\hat{\mathbf y} = \sum_{i=1}^p \langle \mathbf y, \mathbf u_i \rangle \mathbf u_i$。

正交投影满足：$\hat{\mathbf y} \in W$ 且 $\mathbf y - \hat{\mathbf y} \perp W$。$\hat{\mathbf y}$ 是 $W$ 中最接近 $\mathbf y$ 的点（最佳逼近），即 $\|\mathbf y - \hat{\mathbf y}\| \le \|\mathbf y - \mathbf w\|$ 对所有 $\mathbf w \in W$ 成立。

### 6.3 Gram-Schmidt 正交化

**定理**：任何非零有限维内积空间存在正交基，且可通过 Gram-Schmidt 过程构造。

**Gram-Schmidt 过程**（从基 $\{\mathbf x_1,\dots,\mathbf x_p\}$ 构造正交基 $\{\mathbf v_1,\dots,\mathbf v_p\}$）：

- $\mathbf v_1 = \mathbf x_1$；
- 对于 $k = 2,\dots,p$，
  $$\mathbf v_k = \mathbf x_k - \sum_{j=1}^{k-1} \frac{\langle \mathbf x_k, \mathbf v_j \rangle}{\langle \mathbf v_j, \mathbf v_j \rangle} \mathbf v_j.$$
  若需单位正交基，再对每个 $\mathbf v_i$ 单位化：$\mathbf u_i = \mathbf v_i / \|\mathbf v_i\|$。

**QR 分解**：若 $A$ 为 $m\times n$ 列满秩矩阵（列线性无关），则 $A = QR$，其中 $Q$ 为 $m\times n$ 列正交矩阵（$Q^TQ = I_n$），$R$ 为 $n\times n$ 上三角可逆矩阵。该分解可通过 Gram-Schmidt 得到：$A$ 的列是 $\mathbf x_1,\dots,\mathbf x_n$，正交化得到 $\mathbf u_1,\dots,\mathbf u_n$，则 $Q = [\mathbf u_1 \dots \mathbf u_n]$，$r_{ij} = \langle \mathbf u_i, \mathbf x_j \rangle$（$i\le j$）或 $0$（$i>j$）。

### 6.4 最小二乘问题

对于矛盾方程组 $A\mathbf x = \mathbf b$（无解），寻找 $\hat{\mathbf x}$ 使得 $\| A\hat{\mathbf x} - \mathbf b \|$ 最小。这样的 $\hat{\mathbf x}$ 称为**最小二乘解**。

**正规方程**：最小二乘解 $\hat{\mathbf x}$ 满足 $A^T A \hat{\mathbf x} = A^T \mathbf b$。
若 $A$ 列满秩，则 $A^T A$ 可逆，唯一最小二乘解为 $\hat{\mathbf x} = (A^T A)^{-1}A^T \mathbf b$。

**投影解释**：$\hat{\mathbf b} = A\hat{\mathbf x}$ 是 $\mathbf b$ 在 $\operatorname{Col}A$ 上的正交投影，最小二乘解即满足 $A\hat{\mathbf x} = \hat{\mathbf b}$ 的解。

**应用**：数据拟合（线性回归）。给定数据点 $(t_i, y_i)$，寻求直线 $y = \beta_0 + \beta_1 t$ 最小化残差平方和 $\sum (y_i - (\beta_0 + \beta_1 t_i))^2$。将数据代入正规方程可求解 $\boldsymbol \beta = (\beta_0,\beta_1)^T$。

### 6.5 正交矩阵与对称矩阵的对角化

**正交矩阵**：$Q^TQ = I$，即 $Q$ 的列构成 $\mathbb R^n$ 的一组单位正交基。性质：$Q^{-1}=Q^T$，且保持长度不变（$\|Q\mathbf x\| = \|\mathbf x\|$）。

**实对称矩阵**：$A^T = A$。
**谱定理**：实对称矩阵的特征值皆为实数，且存在一组由特征向量组成的单位正交基。从而 $A$ 可**正交对角化**：存在正交矩阵 $Q$ 使得 $Q^T A Q = \Lambda$，其中 $\Lambda = \operatorname{diag}(\lambda_1,\dots,\lambda_n)$。

**证明概要**（谱定理）：首先证对称矩阵的特征值必为实数（利用内积 $\langle A\mathbf x,\mathbf x\rangle = \lambda \|\mathbf x\|^2$ 以及 $\langle A\mathbf x,\mathbf x\rangle$ 为实数）。其次，对应于不同特征值的特征向量正交：若 $\lambda_1\neq \lambda_2$，$\mathbf v_1,\mathbf v_2$ 为特征向量，则 $\lambda_1\langle\mathbf v_1,\mathbf v_2\rangle = \langle A\mathbf v_1,\mathbf v_2\rangle = \langle \mathbf v_1,A\mathbf v_2\rangle = \lambda_2\langle\mathbf v_1,\mathbf v_2\rangle$，故 $\langle\mathbf v_1,\mathbf v_2\rangle=0$。再利用归纳法或 Schur 分解可证存在完备的单位正交特征向量组。

**谱分解**：若 $A = Q\Lambda Q^T$，则 $A = \sum_{i=1}^n \lambda_i \mathbf q_i \mathbf q_i^T$，其中 $\mathbf q_i$ 为 $Q$ 的列。

### 6.6 二次型

二次型 $Q(\mathbf x) = \mathbf x^T A \mathbf x$，其中 $A$ 为实对称矩阵。通过正交变换 $\mathbf x = Q\mathbf y$，可化为标准型 $\sum \lambda_i y_i^2$。

**正定性**：若对所有 $\mathbf x \neq \mathbf 0$ 有 $Q(\mathbf x) > 0$，则称二次型**正定**（矩阵正定）。等价条件：所有特征值 $>0$，或所有顺序主子式 $>0$（Sylvester 准则）。类似有负定、半正定等。

---

### 典型例题

**例1** 利用 Gram-Schmidt 过程将 $\mathbf x_1 = (1,1,0)^T,\; \mathbf x_2 = (1,0,1)^T,\; \mathbf x_3 = (0,1,1)^T$ 化为 $\mathbb R^3$ 的单位正交基。
**解**：$\mathbf v_1 = \mathbf x_1$。
$\mathbf v_2 = \mathbf x_2 - \frac{\langle \mathbf x_2,\mathbf v_1\rangle}{\langle \mathbf v_1,\mathbf v_1\rangle}\mathbf v_1 = (1,0,1)^T - \frac{1}{2}(1,1,0)^T = (\frac12, -\frac12, 1)^T$。
$\mathbf v_3 = \mathbf x_3 - \frac{\langle \mathbf x_3,\mathbf v_1\rangle}{\|\mathbf v_1\|^2}\mathbf v_1 - \frac{\langle \mathbf x_3,\mathbf v_2\rangle}{\|\mathbf v_2\|^2}\mathbf v_2$。
$\langle \mathbf x_3,\mathbf v_1\rangle = 1$，$\langle \mathbf v_1,\mathbf v_1\rangle = 2$；
$\langle \mathbf x_3,\mathbf v_2\rangle = (0)(0.5)+(1)(-0.5)+(1)(1)=0.5$，$\|\mathbf v_2\|^2 = 0.25+0.25+1=1.5$。
所以 $\mathbf v_3 = (0,1,1)^T - \frac{1}{2}(1,1,0)^T - \frac{0.5}{1.5}(\frac12,-\frac12,1)^T = (-\frac23, \frac23, \frac23)^T$（化简后）。
最后单位化：略。

**例2** 求数据点 $(0,1), (1,3), (2,2), (3,4)$ 的最小二乘直线。
**解**：设计矩阵 $X = \begin{pmatrix}1 & 0\\1 & 1\\1 & 2\\1 & 3\end{pmatrix}$，观测向量 $\mathbf y = (1,3,2,4)^T$。正规方程 $X^T X \boldsymbol\beta = X^T\mathbf y$：
$$
\begin{pmatrix}4 & 6\\6 & 14\end{pmatrix}\begin{pmatrix}\beta_0\\\beta_1\end{pmatrix} = \begin{pmatrix}10\\21\end{pmatrix}.
$$
解得 $\beta_1 = \frac{4\cdot21 - 6\cdot10}{4\cdot14 - 36} = \frac{84-60}{20} = 1.2$，$\beta_0 = \frac{10 - 6\cdot1.2}{4} = \frac{10-7.2}{4} = 0.7$。故直线为 $y = 0.7 + 1.2 t$。

**例3** 判断矩阵 $A = \begin{pmatrix}2 & -1 & 0\\-1 & 2 & -1\\0 & -1 & 2\end{pmatrix}$ 是否正定。
**解**：$\det A = 4 > 0$，顺序主子式：$D_1 = 2 > 0$，$D_2 = \begin{vmatrix}2&-1\\-1&2\end{vmatrix}=3>0$，$D_3 = 4>0$，故正定。


## 第7章 对称矩阵与二次型

### 7.1 对称矩阵的对角化（回顾谱定理）

实对称矩阵 $A$（$A^T = A$）具有以下重要性质：

- **所有特征值都是实数**。
- **存在一组单位正交的特征向量基**，从而 $A$ 可正交对角化：存在正交矩阵 $Q$ ($Q^TQ=I$) 使得
  $$
  Q^T A Q = \Lambda = \operatorname{diag}(\lambda_1,\ldots,\lambda_n).
  $$

**证明概要**：

1. 对任意 $\mathbf x\in\mathbb C^n$，$\overline{\mathbf x}^T A \mathbf x$ 是实数，由此推出特征值必为实数（详细略）。
2. 若 $\lambda_1\neq\lambda_2$，对应特征向量 $\mathbf v_1,\mathbf v_2$ 正交：
   $\lambda_1\langle\mathbf v_1,\mathbf v_2\rangle = \langle A\mathbf v_1,\mathbf v_2\rangle = \langle \mathbf v_1,A\mathbf v_2\rangle = \lambda_2\langle\mathbf v_1,\mathbf v_2\rangle$，故 $(\lambda_1-\lambda_2)\langle\mathbf v_1,\mathbf v_2\rangle=0$，得正交。
3. 利用归纳法（或 Schur 三角化）可证明存在完备的单位正交特征向量组。

**谱分解**：若 $Q = [\mathbf q_1 \dots \mathbf q_n]$，则
$$
A = Q\Lambda Q^T = \lambda_1 \mathbf q_1 \mathbf q_1^T + \cdots + \lambda_n \mathbf q_n \mathbf q_n^T.
$$

### 7.2 二次型

称 $Q(\mathbf x) = \mathbf x^T A \mathbf x$ 为 **二次型**，其中 $A$ 为 $n\times n$ 对称矩阵。
经正交变量代换 $\mathbf x = Q\mathbf y$，二次型化为标准型（**主轴形式**）：
$$
Q(\mathbf x) = \mathbf y^T \Lambda \mathbf y = \lambda_1 y_1^2 + \cdots + \lambda_n y_n^2.
$$

### 7.3 正定矩阵与判别

若对所有 $\mathbf x \neq \mathbf 0$ 有 $\mathbf x^T A \mathbf x > 0$，则称 $A$ **正定**。
等价条件（$n\times n$ 实对称矩阵）：

1. 所有特征值 $>0$。
2. 所有顺序主子式 $>0$（Sylvester 准则）。
3. 存在可逆矩阵 $P$ 使得 $A = P^T P$。
4. 可通过高斯消元（不换行）将 $A$ 化为上三角且所有主元 $>0$。

类似可定义负定（$<0$）、半正定（$\ge 0$）、不定。

### 7.4 瑞丽商（Rayleigh Quotient）

**定义**：对实对称矩阵 $A$ 和非零向量 $\mathbf x$，
$$
R(\mathbf x) = \frac{\mathbf x^T A \mathbf x}{\mathbf x^T \mathbf x}.
$$
瑞丽商给出了 $A$ 的特征值范围的估计。

**基本性质**：

1. 若 $\mathbf x$ 是 $A$ 的属于 $\lambda$ 的特征向量，则 $R(\mathbf x) = \lambda$。
2. 瑞丽商的值域介于最小特征值 $\lambda_{\min}$ 和最大特征值 $\lambda_{\max}$ 之间：
   $$
   \lambda_{\min} \le R(\mathbf x) \le \lambda_{\max}.
   $$
3. 对于正交对角化 $Q^T A Q = \Lambda$，令 $\mathbf y = Q^T \mathbf x$，则
   $$
   R(\mathbf x) = \frac{\mathbf y^T \Lambda \mathbf y}{\mathbf y^T \mathbf y} = \frac{\sum \lambda_i y_i^2}{\sum y_i^2}.
   $$
   这直接给出了上述上下界。

**极小极大原理（Courant–Fischer）**：
设 $\lambda_1 \le \lambda_2 \le \cdots \le \lambda_n$ 为 $A$ 的特征值。则
$$
\lambda_k = \min_{\dim W = k} \max_{\mathbf x \in W,\; \mathbf x\neq 0} R(\mathbf x),
$$
其中 $W$ 是 $\mathbb R^n$ 的 $k$ 维子空间。特别地，

- 最大特征值 $\lambda_n = \max_{\mathbf x \neq 0} R(\mathbf x)$。
- 最小特征值 $\lambda_1 = \min_{\mathbf x \neq 0} R(\mathbf x)$。
- 第 $k$ 大特征值 $\lambda_{n-k+1} = \max_{\dim W = k} \min_{\mathbf x\in W,\mathbf x\neq0} R(\mathbf x) = \min_{\dim W = n-k+1} \max_{\mathbf x\in W,\mathbf x\neq0} R(\mathbf x)$。

**应用**：通过选取适当的 $\mathbf x$，可以估计特征值的位置，特别是最大最小特征值。

**瑞丽商迭代**：从一个猜测向量开始，通过瑞丽商加速估计特征值（常用于数值计算）。

---

### 典型例题

**例1** 已知 $A = \begin{pmatrix} 2 & -1 & 0 \\ -1 & 2 & -1 \\ 0 & -1 & 2 \end{pmatrix}$，求其瑞丽商的范围并估计最大、最小特征值。
**解**：任意非零 $\mathbf x$，$R(\mathbf x) = \frac{\mathbf x^T A \mathbf x}{\mathbf x^T \mathbf x}$。由于 $A$ 正定（特征值 $>0$），选取 $\mathbf x_1 = (1,0,0)^T$，得 $R = 2$；$\mathbf x_2 = (1,1,1)^T$，计算 $A\mathbf x_2 = (1,0,1)^T$，所以 $\mathbf x_2^T A \mathbf x_2 = (1,0,1)\cdot(1,1,1)^T = 2$，$\|\mathbf x_2\|^2 = 3$，$R = 2/3$；$\mathbf x_3 = (1,-2,1)^T$，$A\mathbf x_3 = (4,-6,4)^T$，点积 $= 4-12+4 = -4$，似乎有误？重算：$A(1,-2,1)^T = (2+2+0, -1-4-1, 0+2+2) = (4, -6, 4)$，与自身点积 $=4 -6(-2)? 不，(4,-6,4)\cdot(1,-2,1) = 4+12+4=20$，分母 $\|\mathbf x_3\|^2 = 1+4+1=6$，$R = 20/6 = 10/3 \approx 3.33$。实际特征值为 $2, 2+\sqrt{2} \approx 3.414, 2-\sqrt{2} \approx 0.586$，所以 $R$ 确实在 $[0.586, 3.414]$ 之间。

**例2**（瑞丽商用于特征值估计）证明：对任意对称矩阵 $A$，其最大特征值 $\lambda_{\max} = \max_{\|\mathbf x\|=1} \mathbf x^T A \mathbf x$，并在单位球面上取到。
**证明**：由于 $A$ 可正交对角化 $A = Q\Lambda Q^T$，令 $\mathbf y = Q^T\mathbf x$，则 $\mathbf x^T A \mathbf x = \mathbf y^T \Lambda \mathbf y \le \lambda_{\max} \|\mathbf y\|^2 = \lambda_{\max} \|\mathbf x\|^2$。当 $\mathbf x$ 取对应的单位特征向量时等号成立。

---

## 第8章 正交性补充与奇异值分解

本章在第6章正交性的基础上，进一步讨论正交补、正交投影矩阵的性质，并介绍矩阵的**奇异值分解**（SVD），它是线性代数中应用最广泛的分解之一。

### 8.1 正交补

设 $W$ 是 $\mathbb R^n$ 的子空间。$W$ 的**正交补**定义为
$$
W^\perp = \{\mathbf z \in \mathbb R^n : \langle \mathbf z, \mathbf w \rangle = 0 \;\forall \mathbf w \in W\}.
$$
性质：

1. $W^\perp$ 是 $\mathbb R^n$ 的子空间。
2. $\dim W + \dim W^\perp = n$。
3. $\mathbb R^n = W \oplus W^\perp$（直和），即任意 $\mathbf x$ 可唯一分解为 $\mathbf x = \operatorname{proj}_W \mathbf x + \mathbf z$，其中 $\mathbf z \in W^\perp$。

### 8.2 正交投影矩阵

将 $\mathbf x$ 映射到其在 $W$ 上的正交投影 $\hat{\mathbf x}$ 的变换是线性变换，可用矩阵表示。若 $W$ 的某组单位正交基构成矩阵 $U = [\mathbf u_1 \dots \mathbf u_p]$，则投影矩阵
$$
P = UU^T.
$$
$P$ 满足：

- $P^T = P$，$P^2 = P$（幂等），且 $\operatorname{Col}P = W$，$\operatorname{Nul}P = W^\perp$。

特别地，若 $A$ 是 $m\times n$ 列满秩矩阵，则其列空间投影矩阵为 $P = A(A^T A)^{-1}A^T$。

### 8.3 奇异值分解（Singular Value Decomposition, SVD）

**定理**：设 $A$ 为 $m\times n$ 实矩阵，且 $\operatorname{rank}A = r$。则存在正交矩阵 $U\in\mathbb R^{m\times m}$ 和 $V\in\mathbb R^{n\times n}$，使得
$$
A = U \Sigma V^T,
$$
其中 $\Sigma$ 为 $m\times n$ “对角”矩阵，形如
$$
\Sigma = \begin{pmatrix} D & 0 \\ 0 & 0 \end{pmatrix},\quad 
D = \operatorname{diag}(\sigma_1,\ldots,\sigma_r),
$$
且 $\sigma_1 \ge \sigma_2 \ge \cdots \ge \sigma_r > 0$。这些 $\sigma_i$ 称为 $A$ 的**奇异值**，等于 $A^TA$（或 $AA^T$）的正特征值的算术平方根。

**证明概要**：

1. 考察 $A^T A$，它是 $n\times n$ 对称半正定矩阵，故存在正交矩阵 $V = [\mathbf v_1 \dots \mathbf v_n]$ 使得 $V^T (A^T A) V = \operatorname{diag}(\lambda_1,\ldots,\lambda_n)$，其中 $\lambda_1 \ge \cdots \ge \lambda_r > 0$，$\lambda_{r+1}=\cdots=\lambda_n = 0$。
2. 定义 $\sigma_i = \sqrt{\lambda_i}$（$i=1,\dots,r$）。
3. 对 $i=1,\dots,r$，令 $\mathbf u_i = \frac{1}{\sigma_i} A \mathbf v_i$。可以验证这些 $\mathbf u_i$ 构成单位正交组，并可扩充为 $\mathbb R^m$ 的单位正交基 $\{\mathbf u_1,\dots,\mathbf u_m\}$，构成 $U$。
4. 由构造可得 $A V = U \Sigma$，即 $A = U \Sigma V^T$。

**奇异值的性质**：

- $\sigma_1 = \max_{\|\mathbf x\|=1} \|A\mathbf x\|$（算子范数）。
- $A$ 的非零奇异值个数等于 $\operatorname{rank}A$。
- $A$ 可以写成 $r$ 个秩-1 矩阵的和：
  $$
  A = \sum_{i=1}^r \sigma_i \mathbf u_i \mathbf v_i^T.
  $$

**应用**：

- **数据压缩**：仅保留前 $k$ 个最大的奇异值及对应向量，得到 $A$ 的最佳低秩近似。
- **主成分分析（PCA）**的基础。
- 求解最小二乘问题：最小范数最小二乘解。
- 计算矩阵的伪逆（Moore-Penrose 广义逆）：$A^+ = V \Sigma^+ U^T$。

---

### 典型例题

**例1** 求矩阵 $A = \begin{pmatrix} 1 & 0 \\ 0 & 1 \\ 1 & 1 \end{pmatrix}$ 的奇异值分解。
**解**：$A^T A = \begin{pmatrix} 2 & 1 \\ 1 & 2 \end{pmatrix}$，特征值 $\lambda_1 = 3,\ \lambda_2 = 1$，对应的单位正交特征向量：
$$
\mathbf v_1 = \frac{1}{\sqrt{2}}\begin{pmatrix}1\\1\end{pmatrix},\quad
\mathbf v_2 = \frac{1}{\sqrt{2}}\begin{pmatrix}1\\-1\end{pmatrix}.
$$
奇异值 $\sigma_1 = \sqrt{3},\ \sigma_2 = 1$。
构造 $U$：
$$
\mathbf u_1 = \frac{1}{\sigma_1}A\mathbf v_1 = \frac{1}{\sqrt{3}}\begin{pmatrix}1 & 0\\0 & 1\\1 & 1\end{pmatrix}\frac{1}{\sqrt{2}}\begin{pmatrix}1\\1\end{pmatrix} = \frac{1}{\sqrt{6}}\begin{pmatrix}1\\1\\2\end{pmatrix},\quad
\mathbf u_2 = \frac{1}{\sigma_2}A\mathbf v_2 = \frac{1}{\sqrt{2}}\begin{pmatrix}1 & 0\\0 & 1\\1 & 1\end{pmatrix}\begin{pmatrix}1\\-1\end{pmatrix} = \frac{1}{\sqrt{2}}\begin{pmatrix}1\\-1\\0\end{pmatrix}.
$$
还需扩充 $\mathbf u_3$ 正交于 $\mathbf u_1,\mathbf u_2$，例如 $\mathbf u_3 = \frac{1}{\sqrt{3}}\begin{pmatrix}1\\1\\-1\end{pmatrix}$（通过叉积或解方程求得）。最后，
$$
\Sigma = \begin{pmatrix} \sqrt{3} & 0 \\ 0 & 1 \\ 0 & 0 \end{pmatrix},\quad
A = [\mathbf u_1\ \mathbf u_2\ \mathbf u_3] \Sigma [\mathbf v_1\ \mathbf v_2]^T.
$$

**例2**（SVD 用于图像压缩）简述：若 $A$ 是表示图像的矩阵，保留前 $k$ 个奇异值，则重构图像占用空间为 $k(m+n+1)$ 字节，远小于 $mn$ 当 $k$ 较小时，且恢复图像误差为 $\sum_{i=k+1}^r \sigma_i^2$。

