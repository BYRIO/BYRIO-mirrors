# Ubuntu 镜像使用帮助

> [本镜像](https://mirrors.byrio.org/ubuntu/)仅包含 32/64 位 x86 架构处理器的软件包，在 ARM(arm64, armhf)、PowerPC(ppc64el)、RISC-V(riscv64) 和 S390x 等架构的设备上（对应官方源为 `ports.ubuntu.com`）请使用 [ubuntu-ports](https://mirrors.byrio.org/ubuntu-ports/) 镜像。  
PS: 如果仅使用**替换命令**，则不影响

## 备份镜像

```bash
sudo /etc/apt/sources.list /etc/apt/sources.list.bak
```

## 替换镜像源

```bash
sudo sed -i "s/cn.archive.ubuntu.com/mirrors.byrio.org/g" /etc/apt/sources.list
sed -i "s/archive.ubuntu.com/mirrors.byrio.org/g" /etc/apt/sources.list
sed -i "s/security.ubuntu.com/mirrors.byrio.org/g" /etc/apt/sources.list
```

如果系统时间正确建议启用 `https`
```bash
sudo sed -i "s/http\:/https\:/g" /etc/apt/sources.list
```

更新包管理器并完成
```bash
sudo apt update
```


## 镜像情况

1. IPv4解析校园网内网地址，IPv6解析到校外可访问的校园网v6地址。
2. 镜像地址 https://mirrors.byrio.org/ubuntu/
3. 如果你需要安装镜像，请访问 [ubuntu-releases](https://mirrors.byrio.org/ubuntu-release/)
4. 如果你需要衍生版镜像，请访问 [ubuntu-cdimage](https://mirrors.byrio.org/ubuntu-cdimage/)
5. 镜像地址示例 *for x86/x86_64 Ubuntu 20.04 LTS*

    ```
    # 默认注释了源码镜像以提高 apt update 速度，如有需要可自行取消注释
    deb https://mirrors.byrio.org/ubuntu/ focal main restricted universe multiverse
    # deb-src https://mirrors.byrio.org/ubuntu/ focal main restricted universe multiverse
    deb https://mirrors.byrio.org/ubuntu/ focal-updates main restricted universe multiverse
    # deb-src https://mirrors.byrio.org/ubuntu/ focal-updates main restricted universe multiverse
    deb https://mirrors.byrio.org/ubuntu/ focal-backports main restricted universe multiverse
    # deb-src https://mirrors.byrio.org/ubuntu/ focal-backports main restricted universe multiverse
    deb https://mirrors.byrio.org/ubuntu/ focal-security main restricted universe multiverse
    # deb-src https://mirrors.byrio.org/ubuntu/ focal-security main restricted universe multiverse

    # 预发布软件源，不建议启用
    # deb https://mirrors.byrio.org/ubuntu/ focal-proposed main restricted universe multiverse
    # deb-src https://mirrors.byrio.org/ubuntu/ focal-proposed main restricted universe multiverse
    ```

## 常见问题

如果您无法访问，请尝试关闭代理或设置 `mirrors.byrio.org` 为直连域名。

