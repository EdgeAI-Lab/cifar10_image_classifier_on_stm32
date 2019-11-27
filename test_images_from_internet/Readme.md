# Usage

去互联网下载图片，然后使用脚本resize_image_and_to_array.py将图像转换为32*32大小的图像，并得到图像的一维数组，将该一维数组复制到STM32项目中的arm_nnexamples_cifar10_inputs.h文件中。

```
python resize_image_and_to_array.py path_to_image
```