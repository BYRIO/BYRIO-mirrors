# Docker CE 镜像使用帮助

**这里是Docker CE安装镜像，如果您需要 Docker Registry 请[移步此处]()**

> 假设你已经在使用北邮源
> 并且是时钟已正确同步，可以正常使用`HTTPS`

### Ubuntu / Debian

如果你过去安装过 docker，先删掉:
```
sudo apt-get remove docker docker-engine docker.io
```
首先安装依赖:
```
sudo apt-get install apt-transport-https ca-certificates curl gnupg2 software-properties-common 
```

> **如果你使用的是`Debian`, 请将`ubuntu`替换为`debian`**

信任 Docker 的 GPG 公钥:
```
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
如果你没有外网权限
curl -fsSL https://mirrors.byrio.org/docker-ce/linux/ubuntu/gpg | sudo apt-key add -
```
对于 amd64 架构的计算机，添加软件仓库:
```
sudo add-apt-repository \
    "deb [arch=amd64] https://mirrors.byrio.org/docker-ce/linux/ubuntu \
    $(lsb_release -cs) \
    stable"
```

如果你是树莓派或其它ARM架构计算机，请运行:
```
echo "deb [arch=armhf] https://mirrors.byrio.org/docker-ce/linux/ubuntu \
    $(lsb_release -cs) stable" | \
    sudo tee /etc/apt/sources.list.d/docker.list
```
如果你使用 `arm64` , `ppc64el`等架构版本，请自行查阅镜像仓库有无对应支持。

最后安装
```
sudo apt-get update
sudo apt-get install docker-ce
```

### Fedora / CentOS / RHEL

如果你之前安装过 docker，请先删掉
```
sudo yum remove docker docker-common docker-selinux docker-engine
```
安装一些依赖
```
sudo yum install -y yum-utils device-mapper-persistent-data lvm2
```

> **如果你使用的是`Fedora`, 请将`centos`替换为`fedora`**

根据你的发行版下载repo文件

```
wget -O /etc/yum.repos.d/docker-ce.repo https://download.docker.com/linux/centos/docker-ce.repo
如果你没有外网权限
wget -O /etc/yum.repos.d/docker-ce.repo https://mirrors.byrio.org/linux/centos/docker-ce.repo
```

把软件仓库地址替换为 BYRIO:

```
sudo sed -i 's+download.docker.com+mirrors.byrio.org/docker-ce+' /etc/yum.repos.d/docker-ce.repo
```
最后安装:
```
sudo yum makecache fast
sudo yum install docker-ce
```

## 镜像情况

1. IPv4解析校园网内网地址，IPv6解析到校外可访问的校园网v6地址。
2. 镜像地址 https://mirrors.byrio.org/docker-ce/

## 常见问题

如果您无法访问，请尝试关闭代理或设置 `mirrors.byrio.org` 为直连域名。