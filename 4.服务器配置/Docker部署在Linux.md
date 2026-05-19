# Docker部署

## 1.卸载旧版本

首先如果系统中已经存在旧的Docker，则先卸载：

```shell
yum remove docker \
    docker-client \
    docker-client-latest \
    docker-common \
    docker-latest \
    docker-latest-logrotate \
    docker-logrotate \
    docker-engine \
    docker-selinux 
```

