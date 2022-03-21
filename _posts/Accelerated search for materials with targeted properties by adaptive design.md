# Accelerated search for materials with targeted properties by adaptive design

## intro

机器学习的问题是，小数据集，模型和预测的不确定性，可探索空间太大

提出一种方法，既寻找可能具有最佳属性值的材料，又兼具了对未知空间的探索

提出的方法能够平衡对最佳属性的可能搜索和对较小的搜索成本

本文目标是找新的多组成的NiTi基型的记忆合金

## result

### design loop 

迭代反馈环包含：推断，不确定性，全局最优，实验反馈

这个循环的关键要素有：

1）训练集

2）推断模型（回归算法），联系不确定性

3）训练好的模型去探索搜索空间

4）全局最优（选择器）提供下一个实验的候选者，平衡开发和探索

5）从实验中获取反馈信息，改进模型

### data set

训练集大小，22

### features

我们使用Waber-Cromer假势半径、Pauling电负性、金属半径、价电子数（VEN）、Clementi原子半径和Pettifor化学尺度作为推理模型的特征

### inference

Gaussian process model (GPM):给出的结果是可能性分布，既包括均值，又包括不确定性

SVR 与 bootstrap：SVR给出预测值，用自助法来给出不确定性

这些回归模型，非凸函数可能有多个局部最佳值，因此仅依靠回归是不够的

### design

EGO,KG,贪心算法

平衡探索和利用

## discussion

首先这些值不是偶然找到的；

其次这些值也不是在原始数据分布上找出的大于均值的值，而是在对未知的最佳属性寻找中得到的值
