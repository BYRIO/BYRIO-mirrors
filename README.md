# BYRIO mirrors

* BYRIO x BUPT Network Center


* author FredericDT
* date 2018/09/25

## Available Services

All the service currently are only available inside 
BUPT Campus Network Environment, VPN and WEBVPN are 
able to access the services.

### docker-registry

the most fantastic part

#### registry address

`https://docker-registry.mirrors.byrio.org`

#### usage

You can put the parameter `--registry-mirror` when you boot `dockerd`：

`$ docker --registry-mirror=https://docker-registry.mirrors.byrio.org daemon`


To remain the configuration permanently, you can edit `/etc/docker/daemon.json`, add key `"registry-mirrors"`

```json
{
  "registry-mirrors": ["https://docker-registry.mirrors.byrio.org"]
}
```
then save the file and restart `dockerd`

### ubuntu

#### url

`https://mirrors.byrio.org/ubuntu`

#### usage

make a backup of the file `/etc/apt.sourses.list`

then change the url like the following part, for example the 18.04 LTS version

```text
deb https://mirrors.byrio.org/ubuntu/ bionic main restricted universe multiverse
deb https://mirrors.byrio.org/ubuntu/ bionic-updates main restricted universe multiverse
deb https://mirrors.byrio.org/ubuntu/ bionic-backports main restricted universe multiverse
deb https://mirrors.byrio.org/ubuntu/ bionic-security main restricted universe multiverse
```

#### ubuntu-releases

#### url

[https://mirrors.byrio.org/ubuntu-releases](https://mirrors.byrio.org/ubuntu-releases)
