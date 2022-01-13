# Python

## Basic

#### *NameError*

- **错误原因：** 变量名书写错误或者未定义

- **样例：** 

  ```python
  >>> print(a)
  Traceback (most recent call last):
    File "<pyshell#0>", line 1, in <module>
      print(a)
  NameError: name 'a' is not defined
  ```

- **解决办法：** 先给a赋值，才能使用它。当出现`NameError`时，绝大多数情况不是没被赋值，而是我们将单词拼错，或大小写没注意到。因此要回头好好检查下哪里错了

  

#### *SyntaxError*

- **错误原因：** 语法错误，代码形式错误

- **样例：** 

  ```python
  #错误1
  >>> a = 1
  >>> if a:
  print(1)
  SyntaxError: expected an indented block
  IndentationError: excepted an indented block
  ```

  ```python
  #错误2
  >>> if a<b ：
  SyntaxError: invalid character in identifier
  ```

  ```python
  #错误3
  >>> print('a)
        
  SyntaxError: EOL while scanning string literal
  ```

- **解决办法：** 

  - 错误1：没有缩进或者缩进格式错误。最常见的问题就是在于Tab和Space的混用。其实在多数编辑器上转行是会自动补好缩进的，如果实在不确定，可以手动按一下Tab或敲4下Space(更建议后者)。切记Tab和Space不要同时按或混着多按
  - 错误2：绝大多数情况下出现这个错误是因为写代码时混用了中文标点，在不经意时按了Shift切换成了中文字符。在敲代码时，要多注意注意输入法是不是不小心改变了
  - 错误3：出现错误3，真的是非常不小心了。多出现在引号不对称或缺少引号的情况下。这时你应该检查下你的代码哪里的颜色有点奇怪。在多数编辑器中，输入单个引号后，如果没有另一个引号与之对应，")"的颜色或者代码的颜色会显得很奇怪



#### *AttributeError*

- **错误原因：** 属性错误

- **样例：** 

  ```python
  >>> a = list()
  >>> a.add('1')
  Traceback (most recent call last):
    File "<pyshell#21>", line 1, in <module>
      a.add('1')
  AttributeError: 'list' object has no attribute 'add'
  ```

- **解决办法：** 出现这种错误主要是因为混用了语法。如上例：a是一个空列表，而往列表中添加元素是append，即本应用`a.append('1')`。而`a.add()`是用于往集合中添加元素的，这种语法的混用，导致了AttributeError

  

#### *TypeError*

- **错误原因：** 类型错误

- **样例：** 

  ```python
  #错误1
  >>>a = input('Enter a number:')
  >>>print(a/2)
  
  
  Enter a number:1
  Traceback (most recent call last):
    File "C:\Users\acer\Desktop\测试1.py", line 2, in <module>
      print(a/2)
  TypeError: unsupported operand type(s) for /: 'str' and 'int'
  ```

  ```python
  #错误2
  >>> for i in range(1,2,2,3):
  	print(i)
  
  	
  Traceback (most recent call last):
    File "<pyshell#29>", line 1, in <module>
      for i in range(1,2,2,3):
  TypeError: range expected at most 3 arguments, got 4
  ```

- **解决办法：** 

  - 错误1：如上例，input()返回的是一个字符串类型的值，而字符串显而易见是不能直接与数字进行运算，因此出现了TypeError。解决该问题的关键在于你需要得到的是什么类型的值。若需要数值型，可在input()前加上eval()，即可返回数值型。若只需要整型，可加上int()。以此类推
  - 错误2：参数个数错误。range()最多只能有三个参数(start,end,index)，但输入了4个参数，因此出现TypeError。该问题主要出现于对函数的不熟悉上。可通过help()先查看函数的具体用法，再添加合适的参数进行使用
    

#### *IndexError*

- **错误原因：** 索引错误

- **样例：** 

  ```python
  >>> a = list()
  >>> a.append('1,2,3,a,b');a
  ['1,2,3,a,b']
  >>> a[5]
  Traceback (most recent call last):
    File "<pyshell#41>", line 1, in <module>
      a[5]
  IndexError: list index out of range
  ```

- **解决办法：** 出现该错误主要原因在于索引不存在或超过序列范围。如上例：列表a只有5个元素(**切记：Python中索引都是从0开始**)，因此`a[6]`需要返回的是第6个元素，而总共只有5个元素。故出现该错误。多数情况是因为忘记了“从0开始”这个原则导致出现这种错误，改变下索引值便可解决



#### *ValueError*

- **错误原因：** 值错误

- **样例：** 

  ```python
  >>> a = "abc"
  >>> int(a)
  Traceback (most recent call last):
    File "<pyshell#46>", line 1, in <module>
      int(a)
  ValueError: invalid literal for int() with base 10: 'abc'
  ```

- **解决办法：** 出现这种错误主要原因是传给对象的参数类型不准确。如上例，a是一个字符串类型，而`int()`需要传入的是数值型，故出现了上述错误。解决起来也很容易，只用改变输入值的类型即可



#### *KeyError*

- **错误原因：** 字典键值错误

- **样例：** 

  ```python
  >>> d={'a':1,'b':2,'c':3}
  >>> d['a']
  1
  >>> d['f']
  Traceback (most recent call last):
    File "<pyshell#49>", line 1, in <module>
      d['f']
  KeyError: 'f'
  ```

- **解决办法：** 常见于字典中。如上例，字典d只有a，b，c三个键及对应的键值。而想得到的是`d['f']`，明显是不存在的，故出现了该错误，可能因为漏填键及键值导致。通过访问已存在的键值(如a，b，c)来解决



#### *FileNotFoundError*

- **错误原因：** 文件不存在错误

- **样例：** 

  ```python
  # 在该目录下并没有hello.py这个文件
  >>> f = open('hello.py')
  Traceback (most recent call last):
    File "<pyshell#54>", line 1, in <module>
      f = open('hello.py')
  FileNotFoundError: [Errno 2] No such file or directory: 'hello.py'
  ```

- **解决办法：** 常用于对文件的处理。由于输入文件名的不存在所导致的错误。查看该目录下是否存在目标文件，或将目标移至该目录下再进行open()



### Python 内置异常层次结构

内置异常文档：[Exceptions](https://docs.python.org/zh-cn/3/library/exceptions.html)

内置异常的类层级结构如下：

```
BaseException
 +-- SystemExit
 +-- KeyboardInterrupt
 +-- GeneratorExit
 +-- Exception
      +-- StopIteration
      +-- StopAsyncIteration
      +-- ArithmeticError
      |    +-- FloatingPointError
      |    +-- OverflowError
      |    +-- ZeroDivisionError
      +-- AssertionError
      +-- AttributeError
      +-- BufferError
      +-- EOFError
      +-- ImportError
      |    +-- ModuleNotFoundError
      +-- LookupError
      |    +-- IndexError
      |    +-- KeyError
      +-- MemoryError
      +-- NameError
      |    +-- UnboundLocalError
      +-- OSError
      |    +-- BlockingIOError
      |    +-- ChildProcessError
      |    +-- ConnectionError
      |    |    +-- BrokenPipeError
      |    |    +-- ConnectionAbortedError
      |    |    +-- ConnectionRefusedError
      |    |    +-- ConnectionResetError
      |    +-- FileExistsError
      |    +-- FileNotFoundError
      |    +-- InterruptedError
      |    +-- IsADirectoryError
      |    +-- NotADirectoryError
      |    +-- PermissionError
      |    +-- ProcessLookupError
      |    +-- TimeoutError
      +-- ReferenceError
      +-- RuntimeError
      |    +-- NotImplementedError
      |    +-- RecursionError
      +-- SyntaxError
      |    +-- IndentationError
      |         +-- TabError
      +-- SystemError
      +-- TypeError
      +-- ValueError
      |    +-- UnicodeError
      |         +-- UnicodeDecodeError
      |         +-- UnicodeEncodeError
      |         +-- UnicodeTranslateError
      +-- Warning
           +-- DeprecationWarning
           +-- PendingDeprecationWarning
           +-- RuntimeWarning
           +-- SyntaxWarning
           +-- UserWarning
           +-- FutureWarning
           +-- ImportWarning
           +-- UnicodeWarning
           +-- BytesWarning
           +-- EncodingWarning
           +-- ResourceWarning
```



## Environment

#### *Error: No module named XXX*

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

- **相关知识点：** 
  
  - [Python模块导入与路径管理](https://zhuanlan.zhihu.com/p/137087714)
  
- **参考链接：** 

  - [链接一](https://blog.csdn.net/yizhou1995/article/details/84788144)



#### *Error: Empty suite*

- **错误原因：** 常见于测试类或测试文件中：（1）类名用包含Test命名，（2）同时代码中使用了main函数调用类中的内容
- **解决办法：** 只要不满足上面的某一条件就行，修改类名，测试用例中不要使用`if __name__ == '__main__':`
- **相关知识点：** 
  - [编写测试用例](https://zhuanlan.zhihu.com/p/73469149)



#### *Error: io.UnsupportedOperation: not writable*

- **错误原因：** 文件权限问题报错
- **解决办法：** 将读取文件的代码改为`f=open("<file>",'w+')`，默认打开文件的方式为只读方式

#### 









