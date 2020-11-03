# 预测


## 目录
- [简介](#简介)
- [环境](#环境)
- [解决方案](#解决方案)

## 简介

训练数据集：15万

测试数据集：5万

数据集包含特征和模型评价指标如下：
![字段](https://github.com/xumoremore/project_one/blob/main/data/readme_img/columns.png)
![评价指标](https://github.com/xumoremore/project_one/blob/main/data/readme_img/loss.png)


## 环境
    python3.6
    numpy>1.15
    pandas==1.1.3
    sklearn==0.19.1
    matplotlib==3.3.2
    torch==1.1.0

## 解决方案


```
flow
st=>start: 开始
e=>end: 登录
io1=>inputoutput: 输入用户名密码
sub1=>subroutine: 数据库查询子类
cond=>condition: 是否有此用户
cond2=>condition: 密码是否正确
op=>operation: 读入用户信息

st->io1->sub1->cond
cond(yes,right)->cond2
cond(no)->io1(right)
cond2(yes,right)->op->e
cond2(no)->io1
```


**完成情况：**
- [x] 数据探索
- [x] 数据预处理
- [x] 特征工程
- [ ] 特征筛选
- [x] 模型训练
- [x] 模型融合
- [ ] 分析报告

**技术栈：**`特征工程` , `神经网络`, `lightGBM` , `交叉验证`


