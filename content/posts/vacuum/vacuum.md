---
title: "真空"
date: 2024-07-23T15:01:06+08:00
tags: ["真空"]
categories: ["真空空不空"]
draft: false
---

## 一点背景知识

### 平均自由程

- 分子的平均自由程（Mean Free Path，MFP）
  - 定义：气体分子每次碰撞平均飞行过的距离，它取决于分子的大小和分子的密度。
$$\lambda = \frac{1}{\sqrt{2}\pi d^2 n}$$

对常温的空气来说，空气分子的MFP为
$$MFP = \frac{5.1\times 10^{-3}}{P_{Torr}}(cm)$$

常见气体的平均自由程的差别大约在10倍左右。
($He$ 2.8*; $H_2$ 1.8*,$H_2O$ 0.64*)

### 粘滞流，分子流

- 粘滞流：动量在粒子之间通过碰撞传递
    气压 $P > 0.1 Torr$

    $$\frac{\text{平均自由程}}{\text{管道直径}} < 0.01$$

    分子与分子的碰撞 >>分子与壁的碰撞

- 分子流：粒子独立地运动
    气压 $P < 0.1 Torr$

    $$\frac{\text{平均自由程}}{\text{管道直径}} > 1$$

    分子与壁的碰撞 >> 分子与分子的碰撞

粘滞流和分子流之间的称为过渡流，比较复杂。


## 真空基本概念

- 定义
    真空的含义是指在给定的空间内低于一个大气压力的气体状态，是一种物理现象。在“虚空”中，声音因为没有介质而无法传递，但电磁波的传递却不受真空的影响。事实上，在真空技术里，真空系针对大气而言，一特定空间内部之部份物质被排出，使其压力小于一个标准大气压，则我们通称此空间为真空或真空状态。
- 单位
  真空常用帕斯卡（Pascal）或托尔（Torr）作为压力的单位。
  - $ 1 bar = 1.0 \times 10^5 Pa $
  - $ 11 Torr = 133.3224 Pa $
  - $ 1 Pa = 7.5 \times 10^{-3} Torr = 1.0\times 10^{-2} mbar $
  - $ l mbar = 0.75 Torr $
  
- 一个常用单位
  - $1Langmuir = 1\times 10^{-6} Torr \cdot s$

- 真空度
  - 粗真空 $1atm-10^3Torr$
  - 高真空 $10^{-3}-10^{-8} Torr$
  - 超高真空 $10^{-8}-10^{-12} Torr$

{{< admonition tip >}}
1654年，马德堡市长奥托·冯·格里克于神圣罗马帝国的雷根斯堡进行了一项科学实验，目的是证明大气压的存在：把两半球的空间抽成真空，需要用十六匹马才能其拉开。而此实验也因格里克的职衔而被称为[“马德堡半球”实验](https://baike.baidu.com/item/%E9%A9%AC%E5%BE%B7%E5%A0%A1%E5%8D%8A%E7%90%83%E5%AE%9E%E9%AA%8C/481682)。
{{< admonition >}} 
  
### 不同真空度的特性

- 粗真空 ($1atm-10^3Torr$)
  - 气体在粘滞流下流动
  - 真空室的容积和真空泵的抽速决定了抽气时间
  - 气氛的组成与大气相同 ($80\% N_2, 20\% O_2$)
  
- 高真空 ($10^{-3}-10^{-8} Torr$)
  - 气体是从容器的内部、表面产生
  - 气体分子在分子流的状态下流动
  - 容器内表面积，材料类型，温度和真空泵的抽速决定了系统的极限真空度和抽气时间
  - 气氛组成是恒定的 ($80\% H_2O$ 和 $20\% : N_2,CO ,CO_2,H_2$)

- 超高真空 ($10^{-8}-10^{-12} Torr$)
  - 气体是从容器的内部、表而产生
    - 从容器材料内部扩散出来
    - 从容器材料内部渗透出来
    - 从超高真空泵的内部扩散出来
  - 气体分子在分子流的状态下流动
  - 容器内表而积，材料类型，温度和真空泵的抽速决定了系统的极限真空度和抽气时间
  - 气氛主要是 $H_2$ ($< 1\times10^{-10}Torr$)

### 真空系统的性能和气载

- 真空系统的性能取决于
  - 系统的设计（容积、流导、表面积、材料）
  - 气载（系统内部的放气和泄露）
  - 真空泵（抽速和压缩比）
- 真空系统的气载取决于：
  - 材料的表面状况（放气、脱附）
  - 真空系统的材质（扩散和渗透）
  - 泄露（真正的泄露，内漏 / 虚漏）
  - 真空泵自身（返流）

### 系统的极限真空

真空系统内的极限压强（P）是由总的气载（Q）和真空机组的有效抽速（S）决定的：

$$P = \frac{Q}{S}$$
其中 P:$Torr$, Q:$Torr\cdot L/s$, S:$L/s$

在真空泵的抽速有限的情况下，要获得好的真空，应尽量减少气载。

例如：要在系统内达到$10^{-8} Torr$，而真空泵的抽速为 $1000 L/s$,
则总气载必须小于 $10^{-5} Torr\cdot L/S$。

- 超高真空中一个手指印惹的祸
    达到可见的程度，指印的厚度至少要达到 100 层分子的程度

    假设污染的面积为 $1cm^2$，那么分子的数量将达到 $10^{17}$.
    此指印暴露在 $10^{-9} Torr$ 的超高真空环境下，真空泵的抽速为$100L/s$．对应的抽气量为$10^{-7} Torr\cdot L/s$(大约 $10^{12}\text{分子}/s$).
    那么，一个指印所需要的抽出时间为

    $$\frac{10^{17}}{10^{12}} s= 10^5 s = 28 h $$

    大气状态下，$1L$ 容积中包含 $10^{22}$ 个分子．
    在 $10^{-9}Torr$ 时，分子密度降低为 $10^{10}$ 分子/s，也就是 $100L$ 中存在$10^{12}$ 个分子

### 表面处理和清洁工艺

- 物理擦拭，打磨抛光
- 清洁剂清洗
- 化学清洗 ( 如酸洗，溶剂／去脂(小件常用酒精清洗))
- 表面喷砂处理
- 超声波清洗
- 电解抛光
- 表面镀镍

### 流导的计算，抽速受流导的影响


### 流导


- 抽速$S$：指在泵入口处，压强为 $P$，单位时间内抽出的气体量为 $Q$，抽速为 $ S= Q/P $，常用单位为: $L/S$
- 流导$C$：真空管道流过气体的能力。等于流过管道的流量与管道两端的压差之比。常用单位为:  $L/s$
- 抽气量$Q$：单位时间流过抽气管道的气体分子总量。 常用单位为: $Torr\cdot L/s$
$$Q = C(P_1-P_2) = P_2 S$$

### 流导的限制

- 有效抽速：
  
$$\frac{1}{S_e} = \frac{1}{S}+\frac{1}{C}$$


- 粘滞流下的流导
$$ C = 135 \frac{D^4}{L}\frac{P_1+P_2}{2} (L/s)$$
其中 $P:mbar$。

则流导与压强有关。

- 分子流下的流导
$$C = 12.1\frac{D^3}{L}(L/s)$$

与压强无关。

- 分子流下小孔的流导
$$ C = 9.1 D^2(L/s) $$

### 真空故障


## 真空测量

## 真空获得

## 真空密封

## 真空设计

# 真空腔设计原则

## 摘要


真空系统的最终压力取决于整套系统的几个因素：

在超高真空范围内，对真空腔体和应用组件的一些要求如下。

### 对于真空腔体的要求

例如一个不锈钢真空腔，不锈钢的一些良好特性，使其成为超高真空应用领域的理想材料。当然还必须做好正确的表面处理，以确保非常低的放气率。
真空腔体上面一般会有一些法兰，可以用来连接观察窗,或连接压力表以测试压力或与抽气系统相连。
把组件或压力表连接到真空腔体之前，先确保他们的洁净与干燥。如果需要接触这些材料，始终戴好无尘手套就很重要。

抽气之前，必须先用蘸有酒精的无尘布将其表面擦拭干净。
这里，我们有一个CF金属法兰，所以需要用金属密封圈，比如无氧铜密封圈。如果要达到低于 $10^{-8}$ hPa 的超高真空，就必须用金属密封圈。
（有一种常见的弹性密封圈，就不适合用于 $10^{-8}$ hPa 的超高真空，因为弹性密封材料有渗透作用。
但如果工作在前级压力状态，就可以用这种材料。比如，把前级泵与涡轮分子泵相连。）