# Usage

注意：脚本image_convert_to_array.py仅支持32*32的彩色图像

去[CIFAR-10数据集官网下载图片](https://www.cs.toronto.edu/~kriz/cifar.html)然后使用脚本image_convert_to_array.py将图像转换为一维数组，将该一维数组复制到STM32项目中的arm_nnexamples_cifar10_inputs.h文件中。

```
python image_convert_to_array.py path_to_image
```