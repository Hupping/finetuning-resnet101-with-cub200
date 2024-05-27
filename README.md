# resnet101微调任务
在任务一中，本组选取了cnn模型中的resnet101进行实验。我们从torchvision中加载resnet101模型结构并修改了其输出层以适应CUB-200-2011数据集后，分别尝试了全量微调（以较大的学习率训练输出层，以较小的学习率训练其他网络参数）和从零开始训练两种方式，比较了两种方式在测试集上的效果，完成了实验。

## 文件目录
```
finetune/
├── readme.md/                  # 文件说明
├── __pycache__/                # 缓存   
└── fine_tuning/                # 全量微调
    ├── __pycache__/            # 缓存
    ├── figures                 # 存放了tensorboard绘制出的训练与测试集上的loss与accuracy
    │   ├── test_accuracy.png   # 测试集accuracy
    │   ├── test_loss.png       # 测试集loss
    │   ├── train_accuracy.png  # 训练集accuracy
    │   ├── train_loss.png      # 训练集loss
    ├── runs/                   # tensorboard文件
    ├── fun.py                  # 实验要用到的函数定义
    ├── train_cub.py            # 实验主入口，训练文件
└── training_from_0/            # 从零开始训练
    ├── __pycache__/            # 缓存
    ├── figures                 # 存放了tensorboard绘制出的训练与测试集上的loss与accuracy
    │   ├── test_accuracy.png   # 测试集accuracy
    │   ├── test_loss.png       # 测试集loss
    │   ├── train_accuracy.png  # 训练集accuracy
    │   ├── train_loss.png      # 训练集loss
    ├── runs/                   # tensorboard文件
    ├── fun.py                  # 实验要用到的函数定义
    ├── train_cub.py            # 实验主入口，训练文件
```

## 结论
1. 微调的效果远好于从零开始训练，从零开始训练即使训练50轮，在测试集上的准确率也仅达到12%左右。
2. 在微调实验中，尝试了不同超参数组合，发现训练论数为25轮，学习率为0.001时效果最好，此时在测试集上准确率能达到81%。

## 模型权重链接
链接: https://pan.baidu.com/s/1cbCcM4Gg5EJ8SCTAwAD22w?pwd=wsaz 提取码: wsaz

## 代码链接
clone zip文件然后解压即可：https://github.com/Hupping/finetuning-resnet101-with-cub200
