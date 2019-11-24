# Evaluating Architecture

如果有推荐信需求，去找他打工去

评估的输入是架构文档

##### 为什么做架构评估

设计缺陷会繁殖。第一时间修复，可以节约时间和成本。

COTS 

系统之间兼容

##### 何时进行

###### Acquisition

不完全是自己的部分的时候，获得的时候

###### 设计

###### 开发后的产品

完成开发之后，交付的时候，客户是否能接受

##### 早评估

早修复

低成本

competing requirements：竞争的需求，需要更早的决策。哪个需求更重要

##### 如何评估架构

找到一系列问题，并具体化

* risks 为了实现需求，采取的设计，可能会产生的影响。（负面的影响）
* 错误的设计决定。不能够正确的实现ASRs
* 质量属性

###### 评估方法

* 针对于某一个质量属性
  * 依赖于具体的情景。六个元素分析
  * 更偏向于量化的结果。

重要的scenarios是否能被满足

##### how can a method be helpful

###### risks

###### sensitivity points

小的变化会对某个质量属性产生大的影响。

设计敏感的。

###### trade-offs

妥协

一个设计决定影响多个质量属性，且不一致，有的正面有的负面。

在两个方面进行权衡。

也可以导入其他的设计来进行影响。



通过评估，发现设计中的决定和未来的指向特征的关系，朝哪个方向进行调整。

最终尽量避免负面的影响。

#### 分析手段

设计的阶段	哪一种形式的分析方法	带来的成本	输出的可信程度

###### checklist

检查设计是否全面合理

###### 分析模型

静态模型，分析结构之间的关系，静态依赖关系

UML

###### simulation

动态。运行时要求能否被满足

###### Instrumentation

运行时的系统

##### Evaluate Forms

ADD中，generate and tests，就是一个局部的evaluation

由开发团队做evaluation

### ATAM

最常见的架构评估方法

Architecture Trade-off Analysis Method

#### 总体方法

##### Phase-0 准备

各个角色的准备

evaluation team 团队之外的测试者，leadership组织一个团队，架构师

###### 输入：架构文档

###### 输出：评估计划

stakeholders

logistics 什么时间什么地方如何评估

评估报告交给谁

包含的重要内容

##### Phase-1 Evaluation（1）

评价团队和项目的主要决策成员

###### 输出

架构的presentation

risks，设计决定的正面影响和负面影响，负面影响识别为风险。综合起来，如果局部的风险可能不会造成整体的风险，则是nonrisks

##### Phase-2 Evaluation (2)

stakeholders参与

##### Phase-3 Follow-up

生成评估报告，

#### Phase-1

##### Step-1 Present the ATAM

##### Step-2 最高的目标

技术的、管理的约束

成本

业务目标，要达到什么

##### Step-3 展示目前的设计

##### Step-4 

评估团队听完了介绍，询问技术手段

根据前面的内容，把当前使用的设计决定找出来。不完全相信设计人员

##### Step-5

评估团队把最重要的ASRs识别出来，查看当前设计如何实现

项目树，由评估团队对于系统的理解进行生成

##### Step-6

* 现在使用的设计决定
* 识别出来的重要需求

是否match

由项目树识别的最重要的scenarios是否被满足

风险















