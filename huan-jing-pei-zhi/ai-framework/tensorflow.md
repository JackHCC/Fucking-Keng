# Tensorflow



## Colab

#### *KeyWord: cd命令无法切换目录*

- **描述：** 使用了`!cd <path>`工作目录并没有切换
- **原因：** 每个`!`-prefixed命令都在其自己的子Shell中运行-因此`!cd`启动了一个新的Shell，切换目录，然后杀死该外壳程序。在`!ls`随后重新开始在当前目录中
- **解决办法：** 将`!cd`改为`%cd`
- **参考链接：**
  - [链接一](https://qastack.cn/programming/48298146/changing-directory-in-google-colab-breaking-out-of-the-python-interpreter)







