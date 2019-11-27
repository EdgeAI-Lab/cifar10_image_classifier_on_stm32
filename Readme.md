# STM32图像分类


## 项目简介
本项目实现了在STM32上进行图像分类的任务。使用CIFAR-10数据集，通过Caffe机器学习框架搭建和训练
神经网络模型，然后将所得模型进行转换，使其能够运行在STM32上。本项目运行在Keil的模拟器中，
所以无需开发板即可体验机器学习在STM32上的应用效果。

## 项目的输入
一幅宽32像素高32像素的彩色图像（来自于CIFAR-10数据集），为方便STM32实验操作，
事先将图像转换为像素值数组，存放在arm_nnexamples_cifar10_inputs.h中。

## 项目的输出
测试图像所属的类别

## 使用说明：
编译 -> Debug调试运行 ->  打开Debug (printf) Viewer (View->Serial Windows->Debug (printf) Viewer)

## 参考
* https://github.com/BVLC/caffe
* https://github.com/ARM-software/ML-examples/tree/master/cmsisnn-cifar10
* https://github.com/ARM-software/CMSIS_5/tree/develop/CMSIS/NN/Examples/ARM/arm_nn_examples/cifar10
 

