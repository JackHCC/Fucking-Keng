# Python



#### *Error：No module named XXX*

- **错误原因：**

  - 可能的原因一：没有安装XXX模块
  - 可能的原因二：XXX模块可能是自己写的模块，但是路径找不到

- **解决办法：**

  - 方法一：执行下面语句，注意`XXX`是模块名，如果需要指定安装的版本，可以`XXX==版本号`，例如：`numpy==1.0.0`

  ```
  sudo pip install XXX
  ```

  - 方法二：将未识别到的路径添加到要运行的程序里，在程序中添加路径名称，可以是绝对路径，也可以是相对路径

  ```python
  import sys
  sys.path.append("模块路径")
  ```

- **参考链接：**
  - [链接一](https://blog.csdn.net/yizhou1995/article/details/84788144)



















