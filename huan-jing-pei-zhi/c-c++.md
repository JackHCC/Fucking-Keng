# C/C++

## 报错信息解决

***

#### _Error: member access within misaligned address 0x000000000031 for type 'struct ListNode', which requires 8 byte alignmen_

* **错误原因：**
  * 由于结构体内存在next指针，而申请结构体空间后同时定义了next指针，此时next指针未指向任何空间，故在测试时可能导致上述错误。
* **解决办法：**
  * 增加代码使next指针指向空
* **相关知识点**
  * [结构体内存初始化](https://blog.csdn.net/yiziweiyang/article/details/52228386?ops\_request\_misc=%257B%2522request%255Fid%2522%253A%2522164221808516780265471728%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D\&request\_id=164221808516780265471728\&biz\_id=0\&spm=1018.2226.3001.4187)
* **参考链接**
  * [链接](https://blog.csdn.net/lv1224/article/details/54675703)
