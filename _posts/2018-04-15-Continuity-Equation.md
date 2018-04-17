---
layout: post
title: 连续性方程
date: 2018-04-15 08:00:00.000000000 +09:00
categories: blog
tags: [流体力学,连续性方程,FM,Continuity Equation]
description: 流体力学推导
---

# 基本概念
## [质量流量](https://baike.baidu.com/item/质量流量/5137923)
- 概念 单位时间里流体通过封闭管道或敞开槽有效截面的流体质量
- 单位 kg/h,kg/s
- 与体积流量(单位时间流体通过的体积)对应,可表示为体积流量与流体密度的乘积

# 推导
## 空间位置固定的有限控制体模型
### 思想
- 通过S流出控制体的净质量流量(B)等于控制体质量减少的时间变化率(C)
- 图示
### 净质量流量(B)
- 质量流量=密度 \\(*\\) 表面面积 * 垂直与表面的速度分量
    - \\(\rho\vec{V} _nds = \rho \vec{V} \cdot d\vec{S} = \rho|\vec{V}||d\vec{S}|\cdot \cos\theta\\)
    - 其中\\(d\vec{S}\\)总是指向外，
    - \\(\vec{V}\\)指向外，则\\(\rho \vec{V} \cdot d\vec{S}\\)为正，表示流出
    - \\(\vec{V}\\)指向内，则\\(\rho \vec{V} \cdot d\vec{S}\\)为负，表示流入
- B=\\(\iint_S \rho \vec{V}\cdot d\vec{S}\\)

### 控制体质量减少的时间变化率(C)
- 包含体积微元\\(d\mathscr{V}$$ 中的质量为$$\rho d\mathscr{V}\\)
- 控制体的总质量为\\(\iiint_{\mathscr{V}}\rho d\mathscr{V}\\)
- 质量的增加率为\\(\frac{\partial}{\partial t}\iiint_{\mathscr{V}}\rho d\mathscr{V}\\)
- \\(C=-\frac{\partial}{\partial t}\iiint_{\mathscr{V}}\rho d\mathscr{V}\\)

### B=C

- \\(\iint_S \rho \vec{V}\cdot d\vec{S} = -\frac{\partial}{\partial t}\iiint_{\mathscr{V}}\rho d\mathscr{V}\\)
- 空间位置固定的流体模型导出的控制方程为守恒型方程
- **守恒 积分形式**如下
    - \\(\frac{\partial}{\partial t}\iiint_{\mathscr{V}}\rho d\mathscr{V}+\iint_S \rho \vec{V}\cdot d\vec{S}=0$$ 


## 随流体运动的有限控制体模型
### 思想
- 控制体总是有相同的、可辨认的质量微团组成，即控制体有固定不变的质量
- 当固定不变的质量流动时，控制体的形状和体积一般都发生变化
### 质量
- 考察控制体内一个无穷小体积微元```$d\mathscr{V}$```
- 微元质量为```$\rho d\mathscr{V}$```，其中```$\rho$```是当地密度
- 有限控制体的总质量为
    - \\(m=\iiint_{\mathscr{V}}\rho d\mathscr{V}\\)
    - 整个积分域是\\(\mathscr{V}\\),但是在流动的过程中\\(\mathscr{V}\\)是变化的
- **物质导数所表达的是流体微团随流体运动时，其任何属性对时间的变化率**
- 因控制体是由无数个无穷小流体微团组成，并且有固定不变的总质量，则物质导数为0
    - **非守恒形式的积分形式**
    - \\(\frac{D}{Dt}\iiint_{\mathscr{V}}\rho d\mathscr{V}=0\\)

## 空间位置固定的无穷小微团模型
### 思想
- 流出微团的净质量流量等于微团内质量的减少
- 规定净流出量为正
### 净流出量
- x方向的净流出量
    - \\([\rho u+\frac{\partial(\rho u)}{\partial x}dx]dydz-(\rho u)dydz=\frac{\partial(\rho u)}{\partial{x}}dxdydz\\)
- y方向的净流出量
    - \\([\rho v+\frac{\partial(\rho v)}{\partial y}dy]dxdz-(\rho v)dxdz=\frac{\partial(\rho v)}{\partial{y}}dxdydz\\)
- z方向的净流出量
    - \\([\rho w+\frac{\partial(\rho w)}{\partial z}dz]dxdy-(\rho w)dxdy=\frac{\partial(\rho w)}{\partial{z}}dxdydz\\)
- 净质量流量
    - \\((\frac{\partial(\rho u)}{\partial{x}}+\frac{\partial(\rho v)}{\partial{y}}+\frac{\partial(\rho w)}{\partial{z}})dxdydz\\)
### 质量增加的时间变化率
- 无穷小微团内流体的总质量为\\(\rho dxdydz\\)
- 质量增加的时间变化率
    - \\(\frac{\partial{\rho }}{\partial{t}}(dxdydz)\\)
### 守恒微分形式
- \\((\frac{\partial(\rho u)}{\partial{x}}+\frac{\partial(\rho v)}{\partial{y}}+\frac{\partial(\rho w)}{\partial{z}})dxdydz = -\frac{\partial{(\rho )}}{\partial{t}}(dxdydz) \\)
- \\(\frac{\partial{(\rho )}}{\partial{t}} + (\frac{\partial(\rho u)}{\partial{x}}+\frac{\partial(\rho v)}{\partial{y}}+\frac{\partial(\rho w)}{\partial{z}}) = 0 \\)
- \\(\frac{\partial{\rho}}{\partial{t}}+\nabla\cdot(\rho \vec{V})=0\\)

## 随流体运动的无穷小微团模型
### 思想

# 总结

基本思想 | 空间位置固定 | 随流体移动
---|---|---
有限控制体 | 通过面S流出控制体的净质量流量等于控制体质量减少的时间变化率 | 具有固定不变的质量，其物质导数为0
无穷小流体微团 | 流出微团的净质量流量等于微团内质量减少的时间变化率 | 具有固定的质量，物质导数为0


基本思想 | 空间位置固定 | 随流体移动
---|---|---
有限控制体 | \\(\frac{\partial}{\partial t}\iiint_{\mathscr{V}}\rho d\mathscr{V}+\iint_S \rho \vec{V}\cdot d\vec{S}=0\\) | \\(\frac{D}{Dt}\iiint_{\mathscr{V}}\rho d \mathscr{V}=0\\)
无穷小流体微团 | \\(\frac{\partial\rho}{\partial t}+\nabla\cdot (\rho\vec{V})=0\\) | \\(\frac{D\rho}{Dt}+\rho\nabla\cdot\vec{V}=0\\)



# 方程不同形式的转化

