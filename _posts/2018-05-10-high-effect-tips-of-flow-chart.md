---
title: "[ 高效能系列 ] 之绘制流程图基本技巧"
layout: post
date: '2018-05-10 12:08:00 +0800'
categories: 高效能系列
tag: 流程图
---

* content
{:toc}


> 本文将按照黄金圈法则介绍绘制流程图的技巧，即从以下 4 个方面展开介绍：
> 
> 1. 什么是流程图？（ what ）
> 2. 为什么要使用流程图？ （ why ）
> 3. 怎样绘制流程图？ （ how ）
> 4. 使用流程图能干什么？（ what ）
> 

## 一、什么是流程图？（ what ）
流程图是展现过程步骤和决策点顺序的图形文档，是将一个过程的步骤用图的形式表示出来的一种图示技术。

一个好的流程图可以直观地描述整个活动中所有过程的物流、信息流，让人很容易知悉整个过程。

同时，作为诊断工具，它能够辅助决策制定，让管理者清楚知道，问题可能出现的地方，从而确定出可供选择的行动方案。


## 二、为什么要使用流程图？ （ why ）
### 作用

1. 将工作过程的复杂性、有问题的地方、重复部分、多余环节以及可以简化和标准化的地方都显示出来。

2. 将实际的和想象的过程流程进行比较和对照，以便寻求改进过程的机会。

3. 使项目小组在过程步骤方面统一意见并检查出对过程进展有重要影响的环节或活动。
识别可以调查收集额外资料的地方。

4. 提供了一个直观而通俗地展示复杂过程的工具。

### 优点

5. 工作更换人手，按图索骥，容易上手。

6. 采用简单规范的符号，画法简单

7. 便于描述，容易理解

8. 结构清晰，逻辑性强


## 三、怎样绘制流程图？ （ how ）
### 符号规范
![guifan2](https://user-images.githubusercontent.com/13688310/40122207-dddd4d04-5955-11e8-8640-94f89b9deb78.png)
![guifan1](https://user-images.githubusercontent.com/13688310/40122319-19ce8f8a-5956-11e8-89e2-fed82a89d9b0.png)

### 画流程图步骤
分析问题，确定问题解决需要哪几步，中间过程都涉及哪些元素（动作输入、动作环节、输出结果等）。

### 基本要求
1. 流程图符号绘制顺序，应从上至下，从左到右。

2. 流程图须以单一入口，单一出口特征绘制。
![shili1](https://user-images.githubusercontent.com/13688310/40122408-520e632a-5956-11e8-947b-dc9662336f1b.png)

3. 路径符号应避免相互交叉。
![shili2](https://user-images.githubusercontent.com/13688310/40122435-660e232e-5956-11e8-8cee-a6b78d0ddb59.png)

4. 一个流程应该只有一个起点，有时候多个流程图融合在一起，可以有多个起点。这里注意结束符号不限。

5. 需要反馈的流程要形成闭环。

6. 同一路径符号的指示箭头应只有一个。

7. 选择结构及重复结构的选择条件或决策条件，文字叙述应简明清晰，路径应标识“是”及“否”或其他相对性文字指示说明。

8. 相同流程图符号应尽量大小一致。

9. 流程图中若参考到其他已定义流程，可使用已定义处理程序符号，不必重复绘制。
![shili3](https://user-images.githubusercontent.com/13688310/40122112-a326f11a-5955-11e8-86e6-00be8e48531c.png)

### 工具推荐

1. OmniGraffle

1. Gliffy Diagrams

2. ProcessOn.com

2. Microsoft Visio 

3. TikZ ( LaTeX 党 )

4. 亿图 Edraw

5. 迅捷流程图制作软件 

3. SmartDraw

6. ...

### 示例

#### 示例一 决策流程图
![default](https://user-images.githubusercontent.com/13688310/40121933-3aed351e-5955-11e8-99b9-96f742e6acf6.png)

#### 示例二 基础泳道流程图
![flowchartdemo](https://user-images.githubusercontent.com/13688310/40121681-b348ac10-5954-11e8-8e2a-48dc3429eb11.png)



## 四、使用流程图能干什么？（ what ）
1. 系统结构设计
2. 产品设计
2. 业务需求流程
3. 研发／开发过程引导
4. ... ...

## 后记
### 2018.06.21
> 没系统学习流程图之前，写代码总是从上到下的一大坨，阅读起来非常困难。现在写代码，首先，会花费一定的时间思考总体流程框架，想清楚代码包括哪几大模块（如读取数据、解析数据、处理数据、存储结果），每个大模块中可细分为哪几个小模块；然后，一个大模块对应一个类／函数，一个小模块对应一个函数；最后，一个个开发。这样写出来的代码美观易读，fix bug 也变得容易很多。很享受这种感觉！
