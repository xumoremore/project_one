# 预测


## 目录
- [简介](#简介)
- [环境](#环境)
- [解决方案](#解决方案)

## 简介

训练数据集：15万

测试数据集：5万

数据集包含特征和模型评价指标如下：
![字段](https://github.com/xumoremore/project_one/blob/main/docs/columns.png)
![评价指标](https://github.com/xumoremore/project_one/blob/main/docs/loss.png)


## 环境
    python3.6
    numpy>1.15
    pandas==1.1.3
    sklearn==0.19.1
    matplotlib==3.3.2
    torch==1.1.0

## 解决方案

### 神经网络

**完成情况：**
- [x] 数据探索
- [x] 数据预处理
- [x] 特征工程
- [ ] 特征筛选
- [x] 模型训练
- [x] 模型融合
- [ ] 分析报告

数据方面，原始数据字段30个，剔除掉部份无用字段后对剩下原始特征做特征组合，交叉，变换等构造出1792个特征，然后使用五层的全连接神经网络对该特征进行学习。模型结构如下。
网络参数：

    learning_rate=0.0001,
    epochs=400,
    batch_size=128
    参数初始化：if self.i_fold == 0:
                nn.init.normal_(m.weight)
            if self.i_fold ==1:  
                nn.init.xavier_normal_(m.weight)
            else:
                nn.init.kaiming_normal_(m.weight)
            if m.bias is not None:
                nn.init.constant_(m.bias, 0)
    
![全连接网络结构](https://github.com/xumoremore/project_one/blob/main/docs/fcn.png)

对所有的数据分成4折，采用交叉验证融合模型最终得分，图为其中一折的测试集MAE得分。

![测试集mae得分](https://github.com/xumoremore/project_one/blob/main/docs/MAE.png)






**技术栈：**`特征工程` , `神经网络`, `lightGBM` , `交叉验证`


