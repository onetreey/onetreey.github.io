---
title: "光学锁相环（OPLL）"
date: 2023-08-30
tags: ["OPLL"]
categories: ["激光的奥秘"]
draft: false
---

基于受激 Raman 跃迁的原子干涉仪的输出相位与两束 Raman 光的相位差有关，因此需要两束 Raman 光相位差固定。光学锁相环是被广泛应用的成熟的技术。

## 基本原理

激光器经过电光调制器后可以表示为 $\omega=\omega_0+$ $\beta \cos \left(\omega_{\mathrm{m}} t\right)$, 其中 $\omega$ 为激光器瞬时频率, $\omega_0$ 为激光器中心频率, $\omega_{\mathrm{m}}$ 为调制频率, $\beta$ 为频率调制幅度。
经过调制后光场可以表示为

{{< math >}}$$
\begin{gathered}
E(t)=E_0 \exp \left\{\mathrm{i}\left[\omega_0+\beta \cos \left(\omega_{\mathrm{m}} t\right)\right] t\right\} \approx \\
E_0 \exp \left\{\mathrm{i}\left[\omega_0 t+M \sin \left(\omega_{\mathrm{m}} t\right)\right]\right\}, \\
M=\pi \ln _{\mathrm{e}}^3 r_{33} V / \lambda h,
\end{gathered}
$${{< /math >}}

式中: $E_0$ 为光场振幅; $l$ 为调制晶体长度; $n_e$ 为调制 晶体对 $e$ 光折射率; $r_{33}$ 为调制晶体介电常数; $V$ 为 调制频率幅度; $h$ 为调制晶体高度; $M$ 为调制深度。
则上式可以用贝塞尔函数表示为

{{< math >}}$$
E(t)=E_0 \exp \left(\mathrm{i} \omega_0 t\right) \sum_{n=-\infty}^{n=\infty} J_n(M) \exp \left(\mathrm{i} n \omega_{\mathrm{m}} t\right) 。
$${{< /math >}}

经过调制的否浦光和末经调制的探测光在原子气室共线方向传播, 当满足亚多普勒共振条件时, 发生类四波混频效应，在弱探测光上产生调制, 探测光经过原子气室后进入光电探测器。探测器探测到的信号和本地振荡混频后得到的信号如下,

{{< math >}}$$
\begin{gathered}
S\left(\omega_{\mathrm{m}}\right)=\frac{C}{\sqrt{\Gamma^2+\omega_{\mathrm{m}}^2}} \sum_{n=-\infty}^{\infty} J_n(M) J_{n-1}(M) \times \\
{\left[\left(L_{(n+1) / 2}+L_{(n-2) / 2}\right) \cos \left(\omega_{\mathrm{m}} t+\varphi\right)+\right.} \\
\left.\left(D_{(n+1) / 2}-D_{(n-2) / 2}\right) \sin \left(\omega_{\mathrm{m}} \iota+\varphi\right)\right],
\end{gathered}
$${{< /math >}}

式中: $J_n(M)$ 为 $n$ 阶贝塞尔函数; $\varphi$ 为作用在泵浦光的调制相位; $C$ 为信号幅度的参数, 主要取决于探测器的参数及激光强度; $L_n$ 为洛伦兹线性 (吸收线性) ; $D_n$ 为色散线性。

{{< math >}}$$
\begin{aligned}
& L_n=\frac{\Gamma^2}{\Gamma^2+\left(\Delta-n \omega_{\mathrm{m}}\right)^2}, \\
& D_n=\frac{\Gamma\left(\Delta-n \omega_{\mathrm{m}}\right)}{\Gamma^2+\left(\Delta-n \omega_{\mathrm{m}}\right)^2},
\end{aligned}
$${{< /math >}}

式中: $\Delta$ 为激光频率相对共振频率的失谐; $\Gamma$ 为原子自然线宽; 对于 $\mathrm{Rb}^{87}$ 原子, 其 $\mathrm{D}_2$ 跃迁线的自然线宽为 $6 \mathrm{MHz}$ 。当调制深度 $M<1$, 上式可以简化为

{{< math >}}$$
\begin{gathered}
S\left(\omega_{\mathrm{m}}\right)=\frac{C}{\sqrt{\Gamma^2+\omega_{\mathrm{m}}^2}} J_0(M) J_1(M) \times \\
{\left[\left(L_{-1}-L_{-1 / 2}+L_{1 / 2}-L_1\right) \cos \left(\omega_{\mathrm{m}} t+\varphi\right)+\right.} \\
\left.\left(D_1-D_{1 / 2}-D_{-1 / 2}+D_{-1}\right) \sin \left(\omega_{\mathrm{m}} t+\varphi\right)\right] 。
\end{gathered}
$${{< /math >}}

可以看出, 当调制频率 $\omega_{\mathrm{m}} \leqslant \Gamma$ 时, 吸收项和色散项有着相同的类色散线型, 都可以作为误差信号来稳定激光器。



## 光路实现

调制转移谱的光路实现如图所示。由激光器出射的光先通过光隔离器 (OI), 其作用是阻止激光反射回激光器, 对激光器造成损伤。再经过一个二分之一波片和偏振分束棱镜$\mathrm{PBS1}$, 通过二分之一波片可以调节经过声光调制器 $\mathrm{AOM}$ 的激光的光强。 $\mathrm{AOM}$ 起到光开关的作用, 光经过 AOM 时产生衍射, 形成的 +1 级衍射光通过反射镜 $\mathrm{M1}$ 的作用反射到二分之一波片和偏振分束棱镜 $\left(\mathrm{PBS2}\right), \mathrm{PBS2}$ 将反射光分为两束偏振方向不同的光, 一束为沗浦光, 另一束为 探测光, 通过二分之一波片可以调节百浦光和探测光的光强比例。厡浦光通过反 射镜 $\mathrm{M3}$ 的作用, 反射到电光调制器 EOM, 泵浦光在电光调制器中被相位调制、 产生调制边带, 又通过 $\mathrm{PBS3}$ 反射到铷泡中。探测光经过反射镜 $\mathrm{M2}$, 也反射到铷泡中。泵浦光与相向传输的探测光在铷泡中铷原子的非线性效应下产生四波混频 过程, 加载在泵浦光的调制信号转移到不加调制携带饱和吸收谱信号的探测光上来, 通过光电探测器 PD 将光信号转换为电信号, 然后再对信号进行放大、解调, 得到误差信号。通过 PID 算法得到的反馈电压值用于控制激光器的输出电流大小, 最终实现激光器的频率稳定。



<div align=center>
    <img src=./MTS.png width=90% />
</div>

## 补充知识

### 电光调制器（EOM）

电光调制器用到的是铌酸锂 $\left(\mathrm{LiNbO}_3\right)$ 、砷化稼 (GaAs) 等晶体的电光效应原 理, 这些晶体称为电光晶体。在外加电场中, 这些晶体的折射率将会发生变化, 折射率变化大小与外加的电场强度有关。光通过加有电压的电光晶体时, 光波的 特性将会发生变化, 从而对光信号的相位和幅度等特性进行调制。

调制转移光谱技术作为一种激光光外差探测技术, 其主要原理是两束光线相 向通过非线性介质, 在其中发生近简并四波混频过程。这两束光是同一激光源发射出的, 一束是经过相位调制的, 另一束末经 过调制。四波混频的结果是末经过调制的光束中会产生新的边带, 也就说调制信 号转移到了末经调制的光束上。利用光电探测器将该光束的光信号转换为电信号, 产生光外差拍频电流, 电流的幅度和相位反映了激光与介质的非线性相互作用



### 声光调制器（AOM）

声光调制器用到的原理是声光效应: 当外力作用于晶体时, 晶体会发生弹性 形变, 这会导致晶体折射率的变化。而声波属于弹性波, 当它作用于晶体时, 会 使晶体发生相应的弹性形变, 晶体的密度会疏密相间的交替分布, 因而晶体的折 射率也会呈周期性变化。光通过有声波作用的晶体时, 会产生衍射, 衍射光的频 率、强度以及方向都随着声波的变化而变化。AOM 由两部分构成: 声光介质和 压电换能器。压电换能器在驱动源的特定载波频率下产生某一频率的声波, 传入 声光介质, 使得通过介质的光波发生相应的衍射。利用声光调制器这个特性, 常 使用它作为光路系统中的光开关。

### 四波混频

调制转移光谱技术作为一种激光光外差探测技术, 其主要原理是两束光线相向通过非线性介质，在其中发生近简并四波混频过程。这两束光是同一激光源发射出的, 一束是经过相位调制的, 另一束末经 过调制。四波混频的结果是末经过调制的光束中会产生新的边带, 也就说调制信 号转移到了末经调制的光束上。利用光电探测器将该光束的光信号转换为电信号, 产生光外差拍频电流, 电流的幅度和相位反映了激光与介质的非线性相互作用 。下图是调制光束与末调制的光束发生近简并四波混频的过程以及四波混频过程中的三种光场组合。

<div align=center>
    <img src=./fourwavemixing1.png width=100% />
</div>