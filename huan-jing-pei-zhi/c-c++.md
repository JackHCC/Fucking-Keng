# C/C++

## 报错信息解决

---

#### *Error: member access within misaligned address 0x000000000031 for type 'struct ListNode', which requires 8 byte alignmen*

- **错误原因：**
  - 由于结构体内存在next指针，而申请结构体空间后同时定义了next指针，此时next指针未指向任何空间，故在测试时可能导致上述错误。

- **解决办法：**
  - 增加代码使next指针指向空

- **相关知识点**
  - 结构体内存初始化
  - [知识点链接](https://blog.csdn.net/yiziweiyang/article/details/52228386?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522164221808516780265471728%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=164221808516780265471728&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-52228386.first_rank_v2_pc_rank_v29&utm_term=%E7%BB%93%E6%9E%84%E4%BD%93%E5%86%85%E5%AD%98%E5%88%9D%E5%A7%8B%E5%8C%96&spm=1018.2226.3001.4187)
- **参考链接**
  - [链接](https://blog.csdn.net/lv1224/article/details/54675703)
