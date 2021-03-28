# Docker Registry 镜像使用帮助

## 镜像地址
```
https://docker-registry.mirrors.byrio.org
```

## 使用方法

**临时使用** 使用 `--registry-mirror` 参数启动 `dockerd`
```
docker --registry-mirror=https://docker-registry.mirrors.byrio.org daemon
```

**长期保持** 编辑 `/etc/docker/daemon.json` **添加** `registry-mirrors` 键值
```
{
  "registry-mirrors": ["https://docker-registry.mirrors.byrio.org"]
}
```
保存后重启`docker`服务
```
systemctl restart docker
```

## 常见问题

1. 如果您无法访问，请尝试关闭代理或设置 `mirrors.byrio.org` 为直连域名。
2. 如果您没有外网权限，使用该镜像后仍可能无法拉取镜像。