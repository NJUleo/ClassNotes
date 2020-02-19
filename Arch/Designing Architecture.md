# Designing Architecture

### Design Strategies

分解

抽象

频繁小步迭代（分而治之）

generate & Test

递归

复用

#### Decomposition

需求的分解

通过分解降低复杂度。

Arranged the decomposition so that ir will accommodate the constraints

为什么开发系统这种高抽象的到责任

#### Designing to ASRs

与架构相关的，高优先的需求。

这个需求是否对架构产生影响。

##### 可能情况：为ASRs设计的架构

1. 仍然满足其他需求
2. 为了满足非ASRs做一些调整
3. 当前设计无法满足其他需求
   1. 接近于满足其他需求，
   2. ASRs选的不对，revisit the design，重新排序，检查设计
   3. 需求无法满足。如彼此矛盾，资源争夺。改变需求。

##### 一次生成完整设计或者一个ASRs？

有的时候可能是完成一次设计，更多时候是通过某个pattern解决一个。

某个pattern可能带来一些负面影响，而要通过更多的来解决，影响多个的质量需求。每次引入新的tactic都要引入新的架构元素而让架构越发复杂。迭代深度变大

#### Generate & Test

初始设计当作一个假设，来进行验证。

经过检验后进行修正，成为新的hypothesis，再test

##### 初始设计如何生成？

* 现有系统

  * 个别需求发生变化，原有系统就是一个hypothesis，进行修正

* 打算使用的框架

  * 某一种风格的架构设计，提供了一个结构。

* pattern和tactics

* design checklists

  * 职责分配
  * 组件间通信
  * 数据模型
  * 元素映射 Mapping among Architectural Elements
  * 资源管理
  * 绑定时间

  可以作为初始，也可以作为test

##### test

Analysis techniques

Design checklists

##### 下一个假设的生成

测试之后出现问题，生成下一个版本的假设

##### 结束

* 满足所有ASRs
* 资源耗尽
  * 新的架构元素的实现，增加系统复杂度和成本，知道无法负担系统的开发
  * 时间耗尽

### Attribute-Driven Design 指导性方法：属性驱动

设计依据，从需求而来

需求文档、ASRs（加工后）、沟通分析，排序后的需求

#### Step 1：是否足够开始设计

已经被排序，识别优先级高低

设计的范畴到底有多大。

对质量需求，以刺激响应模式来描述，若不能说明提供的信息不足

落实成concrete scenario

哪些是需要考虑的，如新的需求只影响现有的一部分

#### Step 2： 选择某个元素进行拆分

选择设计焦点

先玩曾小的局部的设计，在选择其他的设计。直到完成完整的

* greenfield
  * 全新的
  * 选择整个系统作为焦点
* ploughed field
  * 已经分割的架构元素，选择为焦点

#### Step 3：选出相关ASRs设计焦点

对设计焦点，看输入的ASRs哪些和它相关

不是照顾整个系统，而是某个元素，重新排序

项目数

第一个对于用户的重要程度，

第二个是对开发者，难度多大，对其他需求造成什么影响，先后实现这个需求产生不同架构

使用和开发两个角度产生一个完整的评价

都是高就优先解决。

生成一个ASRs的子集

#### Step 4：生成设计

step 4内迭代

通过设计焦点完成一个局部的设计

产生架构视图

##### 解决这些ASRs有哪些思路 Design concern

concerns分割成sub-concerns

通过哪个tactic用什么

##### 找到可选的pattern/tactics

估计取值，如heartbeat的时间间隔

##### 查看这些patterns能造成什么影响

每个pattern对每个ASR的影响

因为有的pattern是不考虑全局的，所以要综合考虑

影响也要量化

##### 选择特定的组合

选择最佳的满足当前设计焦点的

##### 反映到架构上

使用pattern后会让系统变成什么样

架构增加一组新的elements

结构性视图、部署视图

##### 针对设计焦点看是否是完整的设计

设计焦点上的设计是否满足

类似一个test，在设计焦点上做一个局部的检查，

是否照顾所有ASRs

是否有哪个会更好。

当前设计是否与其他elements产生影响

发现问题就迭代

#### Step 5：

实例化，落实到软件上

架构元素进行Mapping，赋予责任

把设计焦点的工作分配给架构元素

设计焦点的element被代替，其职责也被分配

#### Step 6 ： Define interfaces for instantiated elements

确定如何协作

ASR质量上的需求转化为，子元素上功能化需求。

原本的质量需求转化为element，成为功能需求

需求转换

#### Step 7：检查

设计焦点上的需求是否全部赋予新生成的elemets

翻译成新的子元素的functional requirements

#### Step 8 ： 迭代直到满足

2 - 7迭代

设计焦点的选择，可以是从第一次或者第二次

有限选择更重要的，更有影响的

再选择下一次迭代的设计焦点

全局的ASRs解决

### ADD输出

* software element

  elements，每次迭代不断拆分的新生成elements，承担角色 负担责任，关系，确定属性

* role：相关职责的集合

* 责任：软件元素提供的功能、数据、信息

* 属性：软件元素的额外信息

* 关系：两个元素的如何联系和交互

### ADD实例

Transparency	屏蔽失效，让client不必知道谁失效了

都能满足的情况下考虑实现的难度

##### Alternative Data Integrity Tactics

2 3 代价太高，要保证50%空闲。网络代价

4 5

5其实也可以，不过4更容易实现。是否需要快速恢复。

x小于2就可以，满足要求。尚未考虑所有的Concerns。

恢复到checkpoints，再把所有剩下的log恢复，得到状态

##### Alternative Health Monitoring Tactics

1 2 都涉及到moniter

3 4 不需要moniter的elements。

Ping/Echo占用带宽

4 非周期性，如果是定期就是类似Ping/echo，非定期的就不可以

3 两者连接异步，无确认，单向的。

始终是保持监控的就要用heartbeat

heartbeat要保证发现错误之后能够在需求的时间内恢复

##### Alternative Transparency Tactics

发送转化如何处理

client 不需要新的element

proxy得到真正工作的信息

通讯基础设施

本没有的infrastructure本没有再添加是不好

client变复杂，如果增加新element，client也要修改，porxy可以屏蔽这种情况

#### Step 4.4 

选择之间的相互关系

##### Mapping Tactics and ASRs

senario

design concerns(high level)

#### Step 4.5

11-16，通过新架构元素，处理承担原有的元素。

是根据选择的pattern决定新的elemtn

放在视图里面

###### 架构元素视图

结构和相互关系

###### 顺序视图

关于时间的展开

#### Step 4.6

是否满足本次迭代要求的ASRs

不是立刻知道，而是下次heartbeat时发现。小于等于heartbeat的时间间隔

刚开始工作的时候，前面的积累的工作还没有做，需要去把之前处理的log处理掉，这段时间负载非常大。

直到完成之后，工作正常。

原来的primary成为新的备份。

##### 问题：2秒钟是否满足

* 两秒钟记录LogFile。最差的情况是，刚要开始记录，前面的两秒都没有记录。
* 过0.25秒才发现
* ……

最后发现恢复时间超过了2秒，无法满足设计，需要调整

##### Possible Timing Resolutions

降低log的时间

……

##### Timing Decisions

调整与时间相关的参数

#### Step 5

实例化，分配给新生成的elements

#### Step 6

新生成的element的关系，如果有定义interface

可能存在关系的组合表

传递什么内容，时间

#### Step 7

当前需求是否都有实现

子元素变成功能化需求

考虑新元素加入是否满足50%空闲

网络通讯

如何实现绑定 proxy

#### outputs of ADD 

下次的选择就可以选择别的ASRs了，针对与不同的元素，比如说

* element
  * 视图的方式组织在一起
* role
* responsibility
* property
* relationship

### 作业

使用ADD方法架构设计

表现形式使用架构设计文档

设计方法的练习，以及文档化的组织。过程和组织形式

3-4人小组

###### 20分 ADD方法使用

至少两次ADD迭代

分析ASRs

给出选择ASRs和解释

设计过程

###### 15分 文档

###### 5分 使用ADD的经验和问题

查阅文献解决问题，收获、经验

personal contribution

采纳的idea💡

##### 其他

可以做一些合理的假设

总共20页

moodle上有参考材料

##### C4 System

抽取需求

重点关注challenge

















