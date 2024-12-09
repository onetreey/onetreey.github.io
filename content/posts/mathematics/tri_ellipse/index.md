---
title: "三角拟合与椭圆拟合"
date: 2023-08-03
tags: ["三角拟合",“椭圆拟合”]
categories: ["一点点数学"]
draft: false
---
## 三角拟合

我们进行拟合的数据间的理论关系式为

{{< math >}}$$
   y= A+B\cos(x+\phi)
$${{< /math >}}

可将它化为形式

{{< math >}}$$
   y= A+B\cos x \cos \phi - B\sin x\sin \phi
$${{< /math >}}

令，{{< math >}}$C= B\cos x${{< /math >}},{{< math >}}$D= B\sin x${{< /math >}}，则

{{< math >}}$$
   y= A+C \cos \phi - D\sin \phi
$${{< /math >}}

可以利用线性拟合来算出系数{{< math >}}$C,D${{< /math >}}。
定义函数
{{< math >}}$$
    f=\sum_{k}\left[y_{k}-\left(A+C \cos x_{k}-D \sin x_{k}\right)\right]^{2}
$${{< /math >}}

线性拟合系数使得残余误差最小，相应的函数 `f` 也应该取极小值，因此有

{{< math >}}$$
   \frac{\partial f}{\partial A}=0 \quad \frac{\partial f}{\partial C}=0 \quad \frac{\partial f}{\partial D}=0
$${{< /math >}}

由

{{< math >}}$$
   \frac{\partial f}{\partial A}=-2\sum_{k}\left[y_{k}-\left(A+C \cos x_{k}-D \sin x_{k}\right)\right] = 0
$${{< /math >}}

得到关系式

{{< math >}}$$
    \sum_{k}\left(A+C \cos x_{k}-D \sin x_{k}\right) = \sum_{k}y_k
$${{< /math >}}  

同理可由{{< math >}}$\quad \frac{\partial f}{\partial C}=0${{< /math >}} , {{< math >}}$\quad \frac{\partial f}{\partial D}=0${{< /math >}} ,得到另外两组关系式：

{{< math >}}$$
\begin{aligned}A k+C \sum_{k} \cos x_{k}-D \sum_{k} \sin x_{k} & =\sum_{k} y_{k} \\A \sum_{k} \cos x_{k}+C \sum_{k} \cos ^{2} x_{k}-D \sum_{k}\left(\sin x_{k} \cos x_{k}\right) & =\sum_{k}\left(y_{k} \cos x_{k}\right) \\A \sum_{k} \sin x_{k}+C \sum_{k}\left(\sin x_{k} \cos x_{k}\right)-D \sum_{k} \sin ^{2} x_{k} & =\sum_{k}\left(y_{k} \sin x_{k}\right)\end{aligned}
$${{< /math >}}

写成矩阵的形式便是

{{< math >}}$$
   M(x) \begin{bmatrix} A\\ C\\D\end{bmatrix} = N(x,y)
$${{< /math >}}

由此得到

{{< math >}}$$
   \begin{bmatrix} A\\ C\\D\end{bmatrix} = M(x)^{-1} N(x,y)
$${{< /math >}}

从而可求出相位

{{< math >}}$$
   \phi = \arctan \frac{D}{C}
$${{< /math >}}
