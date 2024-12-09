---
title: "常微分方程组的解法"
date: 2023-08-03
tags: ["常微分方程组"]
categories: ["一点点数学"]
draft: false
---

求解三能级 Raman 跃迁问题时不可避免地要用到常微分方程的相关知识，这里给出常系数齐次线性微分方程组的一种解法。

### 常系数线性微分方程组

常系数齐次线性微分方程组的一般形式为：

{{< math >}}$$
    \left\{ \begin{array}{l}
    {\dot x_1} = {a_{11}}{x_1} + {a_{12}}{x_2}\\
    {\dot x_2} = {a_{21}}{x_1} + {a_{22}}{x_2}
    \end{array} \right.
$${{< /math >}}

写成矩阵形式为：

{{< math >}}$$
\frac{d}{d t}\left[\begin{array}{l}
x_1 \\
x_2
\end{array}\right]=\left[\begin{array}{ll}
a_{11} & a_{12} \\
a_{21} & a_{22}
\end{array}\right]\left[\begin{array}{l}
x_1 \\
x_2
\end{array}\right]
$${{< /math >}}

从而得到：

{{< math >}}$$
{\left[\begin{array}{cc}
a_{11}-D & a_{12} \\
a_{21} & a_{22}-D
\end{array}\right]\left[\begin{array}{l}
x_1 \\
x_2
\end{array}\right]=0} 
$${{< /math >}}

$D = \frac{d}{{dt}}$ 是微分算符，要得到非零解，则令：

{{< math >}}$$
\left|\begin{array}{cc}
a_{11}-D & a_{12} \\
a_{21} & a_{22}-D
\end{array}\right|=0
$${{< /math >}}

解得：

{{< math >}}$$
    \Rightarrow \left\{ \begin{array}{l}
    {D_1} = \frac{1}{2}\left[ {{a_{11}} + {a_{22}} + \sqrt {{{\left( {{a_{11}} -
    {a_{22}}} \right)}^2} + 4{a_{12}}{a_{21}}} } \right] = {\lambda _1}\\
    {D_2} = \frac{1}{2}\left[ {{a_{11}} + {a_{22}} - \sqrt {{{\left( {{a_{11}} -
    {a_{22}}} \right)}^2} + 4{a_{12}}{a_{21}}} } \right] = {\lambda _2}
    \end{array} \right.
$${{< /math >}}

将 ${D_1}$、${D_2}$ 代回矩阵方程 ，得到两个线性无关的解：

{{< math >}}$$
    \left\{\begin{array}{l}
    \Phi_1=\left[\begin{array}{c}
    1 \\
    \frac{\lambda_1-a_{11}}{a_{12}}
    \end{array}\right] c_1(t), \frac{d}{d t} c_1=\lambda_1 c_1 \\
    \Phi_2=\left[\begin{array}{c}
    1 \\
    \frac{\lambda_2-a_{11}}{a_{12}}
    \end{array}\right] c_2(t), \frac{d}{d t} c_2=\lambda_2 c_2
    \end{array}\right.
$${{< /math >}}

由此推出：

{{< math >}}$$
    \left\{\begin{array}{l}
    \Phi_1=\left[\begin{array}{c}
    1 \\
    \frac{\lambda_1-a_{11}}{a_{12}}
    \end{array}\right] e^{\lambda_1\left(t-t_0\right)} c_1\left(t_0\right) \\
    \Phi_2=\left[\begin{array}{c}
    1 \\
    \frac{\lambda_2-a_{11}}{a_{12}}
    \end{array}\right] e^{\lambda_2\left(t-t_0\right)} c_2\left(t_0\right)
    \end{array}\right.
$${{< /math >}}

注：其中 ${\lambda_1}$ 、 ${\lambda_2}$ 是矩阵 {{< math >}}$\begin{bmatrix}
  a_{11}&a_{12}   \\
  a_{21}&a_{22}
\end{bmatrix}${{< /math >}} 的本征值，{{< math >}}$\begin{bmatrix}
1  \\
\frac{\lambda_1 - a_{11}}{a_{12}}
\end{bmatrix}${{< /math >}} 、{{< math >}}$\begin{bmatrix}
1  \\
\frac{\lambda_2 - a_{11}}{a_{12}}
\end{bmatrix}${{< /math >}}  是该矩阵的相应的本征值对应的本征矢量。

这样我们便可以得到 ${x_1}$，${x_2}$ 的通解：

{{< math >}}$$
\left[\begin{array}{l}x_{1} \\x_{2}\end{array}\right]=\left[\begin{array}{c}1 \\\frac{\lambda_{1}-a_{11}}{a_{12}}\end{array}\right] e^{\lambda_{1}\left(t-t_{0}\right)} c_{1}\left(t_{0}\right)+\left[\begin{array}{c}1 \\\frac{\lambda_{2}-a_{11}}{a_{12}}\end{array}\right] e^{\lambda_{2}\left(t-t_{0}\right)} c_{2}\left(t_{0}\right)
$${{< /math >}}

即：

{{< math >}}$$
\left[\begin{array}{l}x_{1} \\x_{2}\end{array}\right]=\left[\begin{array}{cc}e^{\lambda_{1}\left(t-t_{0}\right)} & e^{\lambda_{2}\left(t-t_{0}\right)} \\\frac{\lambda_{1}-a_{11}}{a_{12}} e^{\lambda_{1}\left(t-t_{0}\right)} & \frac{\lambda_{2}-a_{11}}{a_{12}} e^{\lambda_{2}\left(t-t_{0}\right)}\end{array}\right]\left[\begin{array}{l}c_{1}\left(t_{0}\right) \\c_{2}\left(t_{0}\right)\end{array}\right]
$${{< /math >}}

将上式简写为：

{{< math >}}$$
X(t) = \Phi (t)C({t_0})
$${{< /math >}}

代入${x_1}$，${x_2}$的初始条件得到：

{{< math >}}$$
\begin{array}{l}
\Phi ({t_0})C({t_0}) = X({t_0})
\Rightarrow C({t_0}) = {\Phi ^{ - 1}}({t_0})X({t_0})
\end{array}
$${{< /math >}}

将此结果代回便得到：

{{< math >}}$$
X(t) = \Phi (t){\Phi ^{ - 1}}({t_0})X({t_0})
$${{< /math >}}

其中

{{< math >}}$$
\Phi(t)=\left[\begin{array}{cc}e^{\lambda_{1}\left(t-t_{0}\right)} & e^{\lambda_{2}\left(t-t_{0}\right)} \\\frac{\lambda_{1}-a_{11}}{a_{12}} e^{\lambda_{1}\left(t-t_{0}\right)} & \frac{\lambda_{2}-a_{11}}{a_{12}} e^{\lambda_{2}\left(t-t_{0}\right)}\end{array}\right]
$${{< /math >}}

若 $\lambda_1$ 是重根，利用公式

{{< math >}}$$
X(t) = \sum \limits_{j = 1}^k e^{\lambda_j t} \{ \sum\limits_{i = 0}^{n_j - 1} {(A - \lambda_j E)}^i \frac{t^i}{i!}\} {v_j}
$${{< /math >}}

计算，其中 ${v_j}$ 是系数矩阵的本征值 $\lambda_j$ 满足初始条件对应的本征矢量，${n_j}$ 为根 $\lambda_j$ 对应的重数。

对非齐次常系数微分方程组，利用公式

{{< math >}}$$
X(t) = \Phi (t)\Phi^{-1}({t_0})X({t_0}) + \Phi (t)\int_{t_0}^t \Phi^{-1}(s)f(s) ds
$${{< /math >}}

进行计算。

{{< admonition tip >}}
事实上，当我们求解 Raman 跃迁问题时，遇到的方程组不一定是常系数的，所以一般需要先将其处理成常系数方程组再进行求解，常用的方法是同乘或同除以相关因子，以及对某对称项进行微分，等等。
