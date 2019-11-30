# STM32图像分类

![](https://github.com/edgeML/cifar10_image_classifier_on_stm32/blob/master/assets/img/stm32_image_classifier.png)


## 项目简介

本项目实现了在STM32上进行图像分类的任务。使用CIFAR-10数据集，通过Caffe机器学习框架搭建和训练神经网络模型，然后将所得模型进行转换，使其能够运行在STM32上。本项目运行在Keil的模拟器中，所以无需开发板也能体验机器学习在STM32上的应用效果。

## 目录说明

|目录|描述|
|----|----|
|arm_nnexamples_cifar10|STM32图像分类MDK项目源码|
|script|图片预处理脚本|
|test_images_from_cifar10|来自CIFAR-10数据集的测试图片|
|test_images_from_internet|来自互联网的测试图片|

## 项目的输入

![](https://github.com/edgeML/cifar10_image_classifier_on_stm32/blob/master/assets/img/input_image.png)

一幅宽32像素高32像素的彩色图像，为方便STM32实验操作，
事先将图像转换为像素值数组，存放在arm_nnexamples_cifar10_inputs.h中。

## 项目的输出

输出是测试图像所属的类别的概率，概率值最大的就是目标图像的所属类，输出结果如下图所示：

![](https://github.com/edgeML/cifar10_image_classifier_on_stm32/blob/master/assets/img/stm32_image_classifier_output_result.png)

细心的同学可能要问了，为什么这里的输出是127，而不是一个0~1之间的数？

这个跟我们使用的Softmax函数有关，一般Softmax函数的公式是这样的：
```
y_i = e^(x_i) / sum(e^x_j)
```
而在STM32上我们采用的是以2为底Softmax函数，所以其输出会有所不同。
```
y_i = 2^(x_i) / sum(2^x_j)
```
众所周知，微控制器的计算性能有限，这样做可以大大减小计算量，并且从数学上来讲梯度是一样的，我们依然能够很好地分辨出目标图像的所属类别。

## 使用说明：

编译 -> Debug调试运行 ->  打开Debug (printf) Viewer (View->Serial Windows->Debug (printf) Viewer)

![](https://github.com/edgeML/cifar10_image_classifier_on_stm32/blob/master/assets/img/arm_nn_cifar_debug.png)

## 参考链接

* https://github.com/BVLC/caffe
* https://github.com/ARM-software/ML-examples/tree/master/cmsisnn-cifar10
* https://github.com/ARM-software/CMSIS_5/tree/develop/CMSIS/NN/Examples/ARM/arm_nn_examples/cifar10

