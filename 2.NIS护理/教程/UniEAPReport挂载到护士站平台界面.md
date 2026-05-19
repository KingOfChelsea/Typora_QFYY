# UniEAPReport挂载到护士站平台界面

## 1.后台增加报表菜单

- 登录时，需要选择带有**管理员角色**的账号登录

- 菜单选择**基础数据维护** 如**图1-1**所示

![image-20251201101749724](https://gitee.com/HavertzPlatform/worker-picgo/raw/master/image-20251201101749724.png)

<center>图1-1</center

- 选择**护士站平台资源维护**,如**图1-2**所示

![image-20251201103407578](https://gitee.com/HavertzPlatform/worker-picgo/raw/master/image-20251201103407578.png)

<center>图1-2</center>

- 增加新菜单可以参考**图1-3**进行维护资源

  参数解析：

  1. 标签页名称：**如果是挂在现有根菜单中则需要参考根节点的写法** 如：其他
  2. 一层组名称：一般默认填写01
  3. 一层组名称：可空
  4. 一层组样式：纵向
  5. 二层组编码：01
  6. 二层组样式:横向
  7. 按钮名称：**根据需要的名字填写** 如：RRT查询
  8. 按钮样式：默认
  9. 调用控件名称：如果是UniEAReport，在调用程序集右侧的三个小点的按钮，进行选择对应的`DLL文件`
  10. 调用程序集：参考**第9条**
  11. 顺序号：**不填写**
  12. Excel路径: 默认
  13. 启动参数（key）：默认
  14. 启动参数（value）：默认
  15. 使用权限：根据实际需求进行调整
  16. 患者卡片关联操作：默认
  17. 其他勾选：是否显示树需要取消勾选

<img src="https://gitee.com/HavertzPlatform/worker-picgo/raw/master/image-20251201103946033.png" alt="image-20251201103946033" style="zoom: 80%;" />

<center>图1-3</center>

## 2.护士站报表调整

- 使用管理员账号登录正常病区的护士站，参考**图2-1**

![image-20251201105851401](https://gitee.com/HavertzPlatform/worker-picgo/raw/master/image-20251201105851401.png)

<center>图2-1</center>

- 进入护士站平台，选择刚刚创建的菜单,如选择**RRT查询**，如下图**图2-2**所示

![image-20251201110106376](https://gitee.com/HavertzPlatform/worker-picgo/raw/master/image-20251201110106376.png)

<center>图2-2</center>

- 选择界面右下角的设置按钮，调出菜单属性界面，如图**图2-3**

![image-20251201110239681](https://gitee.com/HavertzPlatform/worker-picgo/raw/master/image-20251201110239681.png)

<center>图2-4</center>

- 维护参数如下：参考**图2-5、图2-6、图2-7**

<img src="https://gitee.com/HavertzPlatform/worker-picgo/raw/master/image-20251201110430300.png" alt="image-20251201110430300" style="zoom:80%;" />

<center>图2-5</center>

- 选择系统控件中右下角的属性值

<img src="https://gitee.com/HavertzPlatform/worker-picgo/raw/master/image-20251201110953433.png" alt="image-20251201110953433" style="zoom:80%;" />

<center>图2-6</center>

- 维护报表ID值

![image-20251201111114437](https://gitee.com/HavertzPlatform/worker-picgo/raw/master/image-20251201111114437.png)

<center>图2-7</center>

注意如何查询报表ID: 参考 **图2-8**

<img src="https://gitee.com/HavertzPlatform/worker-picgo/raw/master/image-20251201111951409.png" alt="image-20251201111951409" style="zoom:80%;" />

<center>图2-8</center>

维护正常后显示如**图2-9**

![image-20251201112229837](https://gitee.com/HavertzPlatform/worker-picgo/raw/master/image-20251201112229837.png)

<center>图2-9</center>





