# Docker容器部署脚本

## 1.mysql

```shell
docker run -d \
  --name mysql \
  -p 3306:3306 \
  -e MYSQL_ROOT_PASSWORD=996 \
  -v /docker/mysql/data:/var/lib/mysql \
  -v /docker/mysql/conf:/etc/mysql/conf.d \
  --restart=unless-stopped \
  mysql:8.0
```

## 2.文件管理器

```shell
#拉取镜像
docker pull filebrowser/filebrowser
# 创建文件夹
mkdir -p /docker/filebrowser/{srv,config,db}
# 
chmod 777 /docker/filebrowser/srv/

docker run -d \
  --name filebrowser \
  --restart always \
  -v /docker/filebrowser/srv:/srv \
  -v /docker/filebrowser/config/config.json:/etc/config.json \
  -v /docker/filebrowser/db/database.db:/etc/database.db \
  -p 8080:80 \
  filebrowser/filebrowser
```

