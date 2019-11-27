# Usage

## array_convert_to_image.py

![](..\assets\img\array_to_image.png)

将一维数组转换为图片并显示

```
# 替换这个
image = [38,64,17, ... ,124,128,173,118]
```

## image_convert_to_array.py

![](..\assets\img\image_convert_array.png)

注意：脚本image_convert_to_array.py仅支持32*32的彩色图像

去[CIFAR-10数据集官网下载图片](https://www.cs.toronto.edu/~kriz/cifar.html)然后使用脚本image_convert_to_array.py将图像转换为一维数组，将该一维数组复制到STM32项目中的arm_nnexamples_cifar10_inputs.h文件中。

```
python image_convert_to_array.py path_to_image
```

## resize_image_and_to_array.py

![](..\assets\img\resize_and_convert_array.png)

去互联网下载图片，然后使用脚本resize_image_and_to_array.py将图像转换为32*32大小的图像，并得到图像的一维数组，将该一维数组复制到STM32项目中的arm_nnexamples_cifar10_inputs.h文件中。

```
python resize_image_and_to_array.py path_to_image
```