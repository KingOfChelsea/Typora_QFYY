# TomCat部署DataViz

## 1.获取安装包

- 解压`jre_X64.zip`后把`jre1.8.0_73`文件夹放置根目录
- 运行`apache-tomcat-8.0.32.exe`如`图1.2-1.7`



<img src="https://gitee.com/HavertzPlatform/worker-picgo/raw/master/image-20260228110617374.png" alt="image-20260228110617374" style="zoom:67%;" />

<center>图1.1</center>

<img src="https://gitee.com/HavertzPlatform/worker-picgo/raw/master/image-20260228111015431.png" alt="image-20260228111015431" style="zoom: 67%;" />

<center>图1.2</center>

<img src="https://gitee.com/HavertzPlatform/worker-picgo/raw/master/image-20260228110926808.png" alt="image-20260228110926808" style="zoom: 67%;" />

<center>图1.3</center>

<img src="https://gitee.com/HavertzPlatform/worker-picgo/raw/master/image-20260228111038574.png" alt="image-20260228111038574" style="zoom:67%;" />

<center>图1.4</center>

![image-20260228111152224](https://gitee.com/HavertzPlatform/worker-picgo/raw/master/image-20260228111152224.png)

<center>图1.5</center>

![image-20260228111510504](https://gitee.com/HavertzPlatform/worker-picgo/raw/master/image-20260228111510504.png)

<center>图1.6</center>

![image-20260228111620998](https://gitee.com/HavertzPlatform/worker-picgo/raw/master/image-20260228111620998.png)

<center>图1.7</center>

- 安装成功后在本机输入地址，`localhost:8080`,打开后如图`图1.8`所示

![image-20260228113149025](https://gitee.com/HavertzPlatform/worker-picgo/raw/master/image-20260228113149025.png)

<center>图1.8</center>

## 2.部署DataViz说明文档

- 找到Tomcat安装路径，如：`E:\Program Files\Apache Software Foundation`
- 进入如下文件夹下路径：`E:\Program Files\Apache Software Foundation\Tomcat 8.0\webapps` 如`图2-1`所示

<img src="https://gitee.com/HavertzPlatform/worker-picgo/raw/master/image-20260228112656814.png" alt="image-20260228112656814" style="zoom: 67%;" />

<center>图2.1</center>

- 停止Tomcat服务，在bin目录下找到`Tomcat8w.exe`,如下图所示

![image-20260228113358696](https://gitee.com/HavertzPlatform/worker-picgo/raw/master/image-20260228113358696.png)

<center>图2.2</center>

- 复制DataVic-Doc的压缩包,解压安装

- 解压完成后输入`访问http://ip:端口/report_doc或http://ip:端口/dataviz_doc 就是tomcat下webapps里面 和程序同级就行`,如下图所示

![image-20260228114916879](https://gitee.com/HavertzPlatform/worker-picgo/raw/master/image-20260228114916879.png)

<center>图2.3</center>

