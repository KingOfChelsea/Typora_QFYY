# FileBrowser使用Docker部署

## 1.安装Docker容器

## 2.拉去镜像容器

```bat
# 拉取镜像最新版本
docker pull filebrowser/filebrowser 

# 查看是否拉取成功
docker images 
```

## 3.创建对照文件夹并更改最高权限

```bat
# 创建文件夹
mkdir -p /docker/filebrowser/{srv,config,db}

# 更改更高权限
chmod 777 /docker/filebrowser/srv/ 
```

## 4.部署FileBrowser

`name` 参数 镜像名称 

```bat
docker run -d \
  --name filebrowser \  
  --restart always \
  -v /docker/filebrowser/srv:/srv \
  -v /docker/filebrowser/config/config.json:/etc/config.json \
  -v /docker/filebrowser/db/database.db:/etc/database.db \
  -p 8080:80 \
  filebrowser/filebrowser
```

## 5.部署portainer

```bat
# 拉取镜像
docker pull portainer/portainer-ce
#启动镜像  portainer默认端口是9000 
docker run -d -p 9000:9000 -v /var/run/docker.sock:/var/run/docker.sock -v /dockerData/portainer:/data --restart=always --name portainer portainer/portainer-ce:latest 
```

portainer默认端口是9000 

–restart=always: 代表在容器退出时总是重启容器，还有其他几种重启策略：no、on-failure、on-failuer:n、unless-stopped

`启动完成后，访问http://ip:9000`

## 6.查看`filebroswer`容器的日志

查看日志如下(图1)

![image-20251025190146741](https://gitee.com/HavertzPlatform/worker-picgo/raw/master/image-20251025190146741.png)

<center>图6-1</center>

查看日志(图2)

![image-20251025190314156](https://gitee.com/HavertzPlatform/worker-picgo/raw/master/image-20251025190314156.png)

<center>图6-2</center>

## 7.登录filebroswer

默认用户名 admin 密码 ==请查看日志== 

![image-20251025190443598](https://gitee.com/HavertzPlatform/worker-picgo/raw/master/image-20251025190443598.png)

<center>图7-1</center>