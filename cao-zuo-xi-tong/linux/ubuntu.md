# Ubuntu

## Install



## Using

#### *Error: permission denied*

- **错误原因：**操作的文件权限不足，如果你不是管理员，说明不能操作该文件，如果你是管理员修改文件操作权限即可
- **解决办法：**执行下面命令，注意777谁都能操作（读，写，执行）该文件。

```
sudo chmod 777 <file or dir>
```

​	例如：`sudo chmod 777 text.py`，然后再执行即可。

- **相关知识点：** Linux权限管理
  - [Linux权限管理详解](http://c.biancheng.net/linux_tutorial/70/)



## Environment







