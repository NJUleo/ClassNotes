# computer vision

rentw@nju.edu.cn

邮件标题：CV20: ***

## 课程引入

### 教学目标

起源和发展历史

研究方向、前沿进展

入门调研方法和实践方法

无研究性内容

### 参考资料

三顶会 CVPR ICCV ECCV

ECCV在Springer数据库

找到方向，进行了解

不建议看arXiv，建议看三顶会的文章

TPAM有不同学科的

IJCV是纯粹CV的刊物，难度小一些，质量还挺好

BMVC 

ACCV 

WACV

很多东西都由深度学习的方法来进行

## 导论

计算机视觉

* 高层次的视觉（不只是识别出来这是红的那是绿的）
* 代替一些人的工作，比人更好。大规模使用，代替人的工作。

学科层面：理解图像和视频，明白其中的内容。帮助计算机理解

工程角度：替代人眼视觉系统去做一些任务。

### 计算机视觉为什么难

* 逆问题，在信息不足的情况下恢复未知量给出完整的解答
  * 比如，例子中，黑色的鞋和阴影的部分，是难以区分的。
  * 人在看东西的时候会结合常识，这是超出纯粹的图像上的信息
* 不纯粹是感知问题，也涉及认知问题
  * 视觉不仅仅是看，还涉及到想
* 人的视觉系统的原理尚不明确，但实践的需求要求接近和超过人类。

### 计算机视觉发展史

运动边缘对视觉层有刺激

边缘起到巨大的作用

70年代 期望恢复场景的三维结构，更好理解场景

线条标注

边缘检测

非多边形物体的三维建模：广义锥，形成部件，用“弹簧”连接起来

图像分割

##### 计算机视觉研究框架的形成

视觉的层次化表示模型 图像-2D-2.5D-3D 

##### 80年代

采用本征图像理解亮度和阴影变化

立体对应：两个照片对照起来

基于亮度的光流：比如视频前后2帧的变化，通过每个点的运动向量表示变化，变化称为光流，一种基本的方式判断运动

图像金字塔：把图像分为很多层来分析，近的和远的时候，细节不同，但是因该不影响识别，通过不同的采样，形成金字塔，对每一层进行分析，融合起来效果很好。