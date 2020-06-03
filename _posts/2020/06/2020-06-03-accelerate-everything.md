---
title: 加速一切 - 配置国内镜像 - Ubuntu apt、Debian apt、CentOS yum、Alpine apk、macOS brew、Docker、Kubernetes、Python Conda、Maven、Gradle、npm、Ruby
key: 2020-06-03-accelerate-everything
permalink: /article/accelerate-everything
date: 2020-06-03
tags:
- 阿里云
- Aliyun
- 清华源
- Tsinghua
- 华为云
- huaweicloud
- Ubuntu
- Debian
- apt
- CentOS
- yum
- Alpine
- apk
- macOS
- brew
- Docker
- Kubernetes
- k8s
- Python
- Conda
- Anaconda
- Maven
- Gradle
- nodejs
- npm
- Ruby
---

此文仅列出一部分，如果需要其他的镜像，可以参考如下几个链接。
{:.info}

## 常用稳定源

- 阿里源：[https://developer.aliyun.com/mirror/](https://developer.aliyun.com/mirror/)
- 清华源：[https://mirrors.tuna.tsinghua.edu.cn/](https://mirrors.tuna.tsinghua.edu.cn/)
- 华为源：[https://mirrors.huaweicloud.com/](https://mirrors.huaweicloud.com/)
- 中科大源：[http://mirrors.ustc.edu.cn/](http://mirrors.ustc.edu.cn/)
- 网易源：[http://mirrors.163.com/](http://mirrors.163.com/)

<!--more-->

---

## Ubuntu /etc/apt/sources.list

### 镜像来源

- 阿里源：[https://developer.aliyun.com/mirror/ubuntu](https://developer.aliyun.com/mirror/ubuntu)
- 清华源：[https://mirrors.tuna.tsinghua.edu.cn/help/ubuntu/](https://mirrors.tuna.tsinghua.edu.cn/help/ubuntu/)
- 华为源：[https://mirrors.huaweicloud.com/](https://mirrors.huaweicloud.com/)

### Ubuntu 14.04 LTS

#### 阿里源

```
deb https://mirrors.aliyun.com/ubuntu/ trusty main restricted universe multiverse
deb-src https://mirrors.aliyun.com/ubuntu/ trusty main restricted universe multiverse
deb https://mirrors.aliyun.com/ubuntu/ trusty-security main restricted universe multiverse
deb-src https://mirrors.aliyun.com/ubuntu/ trusty-security main restricted universe multiverse

deb https://mirrors.aliyun.com/ubuntu/ trusty-updates main restricted universe multiverse
deb-src https://mirrors.aliyun.com/ubuntu/ trusty-updates main restricted universe multiverse

deb https://mirrors.aliyun.com/ubuntu/ trusty-backports main restricted universe multiverse
deb-src https://mirrors.aliyun.com/ubuntu/ trusty-backports main restricted universe multiverse

## Not recommended
# deb https://mirrors.aliyun.com/ubuntu/ trusty-proposed main restricted universe multiverse
# deb-src https://mirrors.aliyun.com/ubuntu/ trusty-proposed main restricted universe multiverse
```

#### 清华源

```
# 默认注释了源码镜像以提高 apt update 速度，如有需要可自行取消注释
deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ trusty main restricted universe multiverse
# deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ trusty main restricted universe multiverse
deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ trusty-updates main restricted universe multiverse
# deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ trusty-updates main restricted universe multiverse
deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ trusty-backports main restricted universe multiverse
# deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ trusty-backports main restricted universe multiverse
deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ trusty-security main restricted universe multiverse
# deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ trusty-security main restricted universe multiverse

# 预发布软件源，不建议启用
# deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ trusty-proposed main restricted universe multiverse
# deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ trusty-proposed main restricted universe multiverse
```

#### 华为源

```
deb http://mirrors.huaweicloud.com/ubuntu/ trusty main restricted universe multiverse
deb-src http://mirrors.huaweicloud.com/ubuntu/ trusty main restricted universe multiverse
deb http://mirrors.huaweicloud.com/ubuntu/ trusty-security main restricted universe multiverse
deb-src http://mirrors.huaweicloud.com/ubuntu/ trusty-security main restricted universe multiverse

deb http://mirrors.huaweicloud.com/ubuntu/ trusty-updates main restricted universe multiverse
deb-src http://mirrors.huaweicloud.com/ubuntu/ trusty-updates main restricted universe multiverse

deb http://mirrors.huaweicloud.com/ubuntu/ trusty-backports main restricted universe multiverse
deb-src http://mirrors.huaweicloud.com/ubuntu/ trusty-backports main restricted universe multiverse

## Not recommended
# deb http://mirrors.huaweicloud.com/ubuntu/ trusty-proposed main restricted universe multiverse
# deb-src http://mirrors.huaweicloud.com/ubuntu/ trusty-proposed main restricted universe multiverse
```

---

### Ubuntu 16.04 LTS

#### 阿里源

```
deb http://mirrors.aliyun.com/ubuntu/ xenial main
deb-src http://mirrors.aliyun.com/ubuntu/ xenial main

deb http://mirrors.aliyun.com/ubuntu/ xenial-updates main
deb-src http://mirrors.aliyun.com/ubuntu/ xenial-updates main

deb http://mirrors.aliyun.com/ubuntu/ xenial universe
deb-src http://mirrors.aliyun.com/ubuntu/ xenial universe
deb http://mirrors.aliyun.com/ubuntu/ xenial-updates universe
deb-src http://mirrors.aliyun.com/ubuntu/ xenial-updates universe

deb http://mirrors.aliyun.com/ubuntu/ xenial-security main
deb-src http://mirrors.aliyun.com/ubuntu/ xenial-security main
deb http://mirrors.aliyun.com/ubuntu/ xenial-security universe
deb-src http://mirrors.aliyun.com/ubuntu/ xenial-security universe
```

#### 清华源

```
# 默认注释了源码镜像以提高 apt update 速度，如有需要可自行取消注释
deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ xenial main restricted universe multiverse
# deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ xenial main restricted universe multiverse
deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ xenial-updates main restricted universe multiverse
# deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ xenial-updates main restricted universe multiverse
deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ xenial-backports main restricted universe multiverse
# deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ xenial-backports main restricted universe multiverse
deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ xenial-security main restricted universe multiverse
# deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ xenial-security main restricted universe multiverse

# 预发布软件源，不建议启用
# deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ xenial-proposed main restricted universe multiverse
# deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ xenial-proposed main restricted universe multiverse
```

#### 华为源

```
deb http://mirrors.huaweicloud.com/ubuntu/ xenial main
deb-src http://mirrors.huaweicloud.com/ubuntu/ xenial main

deb http://mirrors.huaweicloud.com/ubuntu/ xenial-updates main
deb-src http://mirrors.huaweicloud.com/ubuntu/ xenial-updates main

deb http://mirrors.huaweicloud.com/ubuntu/ xenial universe
deb-src http://mirrors.huaweicloud.com/ubuntu/ xenial universe
deb http://mirrors.huaweicloud.com/ubuntu/ xenial-updates universe
deb-src http://mirrors.huaweicloud.com/ubuntu/ xenial-updates universe

deb http://mirrors.huaweicloud.com/ubuntu/ xenial-security main
deb-src http://mirrors.huaweicloud.com/ubuntu/ xenial-security main
deb http://mirrors.huaweicloud.com/ubuntu/ xenial-security universe
deb-src http://mirrors.huaweicloud.com/ubuntu/ xenial-security universe
```

---

### Ubuntu 18.04 LTS

#### 阿里源

```
deb http://mirrors.aliyun.com/ubuntu/ bionic main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ bionic main restricted universe multiverse

deb http://mirrors.aliyun.com/ubuntu/ bionic-security main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ bionic-security main restricted universe multiverse

deb http://mirrors.aliyun.com/ubuntu/ bionic-updates main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ bionic-updates main restricted universe multiverse

deb http://mirrors.aliyun.com/ubuntu/ bionic-proposed main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ bionic-proposed main restricted universe multiverse

deb http://mirrors.aliyun.com/ubuntu/ bionic-backports main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ bionic-backports main restricted universe multiverse
```


#### 清华源

```
# 默认注释了源码镜像以提高 apt update 速度，如有需要可自行取消注释
deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic main restricted universe multiverse
# deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic main restricted universe multiverse
deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-updates main restricted universe multiverse
# deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-updates main restricted universe multiverse
deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-backports main restricted universe multiverse
# deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-backports main restricted universe multiverse
deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-security main restricted universe multiverse
# deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-security main restricted universe multiverse

# 预发布软件源，不建议启用
# deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-proposed main restricted universe multiverse
# deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-proposed main restricted universe multiverse
```

#### 华为源

```
deb http://mirrors.huaweicloud.com/ubuntu/ bionic main restricted universe multiverse
deb-src http://mirrors.huaweicloud.com/ubuntu/ bionic main restricted universe multiverse

deb http://mirrors.huaweicloud.com/ubuntu/ bionic-security main restricted universe multiverse
deb-src http://mirrors.huaweicloud.com/ubuntu/ bionic-security main restricted universe multiverse

deb http://mirrors.huaweicloud.com/ubuntu/ bionic-updates main restricted universe multiverse
deb-src http://mirrors.huaweicloud.com/ubuntu/ bionic-updates main restricted universe multiverse

deb http://mirrors.huaweicloud.com/ubuntu/ bionic-proposed main restricted universe multiverse
deb-src http://mirrors.huaweicloud.com/ubuntu/ bionic-proposed main restricted universe multiverse

deb http://mirrors.huaweicloud.com/ubuntu/ bionic-backports main restricted universe multiverse
deb-src http://mirrors.huaweicloud.com/ubuntu/ bionic-backports main restricted universe multiverse
```

---

### Ubuntu 20.04 LTS

#### 阿里源

```
deb http://mirrors.aliyun.com/ubuntu/ focal main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ focal main restricted universe multiverse

deb http://mirrors.aliyun.com/ubuntu/ focal-security main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ focal-security main restricted universe multiverse

deb http://mirrors.aliyun.com/ubuntu/ focal-updates main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ focal-updates main restricted universe multiverse

deb http://mirrors.aliyun.com/ubuntu/ focal-proposed main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ focal-proposed main restricted universe multiverse

deb http://mirrors.aliyun.com/ubuntu/ focal-backports main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ focal-backports main restricted universe multiverse
```

#### 清华源

```
# 默认注释了源码镜像以提高 apt update 速度，如有需要可自行取消注释
deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ focal main restricted universe multiverse
# deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ focal main restricted universe multiverse
deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ focal-updates main restricted universe multiverse
# deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ focal-updates main restricted universe multiverse
deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ focal-backports main restricted universe multiverse
# deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ focal-backports main restricted universe multiverse
deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ focal-security main restricted universe multiverse
# deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ focal-security main restricted universe multiverse

# 预发布软件源，不建议启用
# deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ focal-proposed main restricted universe multiverse
# deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ focal-proposed main restricted universe multiverse
```

#### 华为源

```
deb http://mirrors.huaweicloud.com/ubuntu/ focal main restricted universe multiverse
deb-src http://mirrors.huaweicloud.com/ubuntu/ focal main restricted universe multiverse

deb http://mirrors.huaweicloud.com/ubuntu/ focal-security main restricted universe multiverse
deb-src http://mirrors.huaweicloud.com/ubuntu/ focal-security main restricted universe multiverse

deb http://mirrors.huaweicloud.com/ubuntu/ focal-updates main restricted universe multiverse
deb-src http://mirrors.huaweicloud.com/ubuntu/ focal-updates main restricted universe multiverse

deb http://mirrors.huaweicloud.com/ubuntu/ focal-proposed main restricted universe multiverse
deb-src http://mirrors.huaweicloud.com/ubuntu/ focal-proposed main restricted universe multiverse

deb http://mirrors.huaweicloud.com/ubuntu/ focal-backports main restricted universe multiverse
deb-src http://mirrors.huaweicloud.com/ubuntu/ focal-backports main restricted universe multiverse
```

---

## Debian /etc/apt/sources.list

### 镜像来源

- 阿里源：[https://developer.aliyun.com/mirror/debian](https://developer.aliyun.com/mirror/debian)
- 清华源：[https://mirrors.tuna.tsinghua.edu.cn/help/debian/](https://mirrors.tuna.tsinghua.edu.cn/help/debian/)
- 华为源：[https://mirrors.huaweicloud.com/](https://mirrors.huaweicloud.com/)

---

### Debian 8 jessie

#### 阿里源

```
deb http://mirrors.aliyun.com/debian/ jessie main non-free contrib
deb http://mirrors.aliyun.com/debian/ jessie-proposed-updates main non-free contrib
deb-src http://mirrors.aliyun.com/debian/ jessie main non-free contrib
deb-src http://mirrors.aliyun.com/debian/ jessie-proposed-updates main non-free contrib
```

#### 清华源

```
# 默认注释了源码镜像以提高 apt update 速度，如有需要可自行取消注释
deb https://mirrors.tuna.tsinghua.edu.cn/debian/ jessie main contrib non-free
# deb-src https://mirrors.tuna.tsinghua.edu.cn/debian/ jessie main contrib non-free
deb https://mirrors.tuna.tsinghua.edu.cn/debian/ jessie-updates main contrib non-free
# deb-src https://mirrors.tuna.tsinghua.edu.cn/debian/ jessie-updates main contrib non-free
deb https://mirrors.tuna.tsinghua.edu.cn/debian/ jessie-backports main contrib non-free
# deb-src https://mirrors.tuna.tsinghua.edu.cn/debian/ jessie-backports main contrib non-free
deb https://mirrors.tuna.tsinghua.edu.cn/debian-security jessie/updates main contrib non-free
# deb-src https://mirrors.tuna.tsinghua.edu.cn/debian-security jessie/updates main contrib non-free
```

#### 华为源

```
deb http://mirrors.huaweicloud.com/debian/ jessie main non-free contrib
deb http://mirrors.huaweicloud.com/debian/ jessie-proposed-updates main non-free contrib
deb-src http://mirrors.huaweicloud.com/debian/ jessie main non-free contrib
deb-src http://mirrors.huaweicloud.com/debian/ jessie-proposed-updates main non-free contrib
```

---

### Debian 9 stretch

#### 阿里源

```
deb http://mirrors.aliyun.com/debian/ stretch main non-free contrib
deb-src http://mirrors.aliyun.com/debian/ stretch main non-free contrib
deb http://mirrors.aliyun.com/debian-security stretch/updates main
deb-src http://mirrors.aliyun.com/debian-security stretch/updates main
deb http://mirrors.aliyun.com/debian/ stretch-updates main non-free contrib
deb-src http://mirrors.aliyun.com/debian/ stretch-updates main non-free contrib
deb http://mirrors.aliyun.com/debian/ stretch-backports main non-free contrib
deb-src http://mirrors.aliyun.com/debian/ stretch-backports main non-free contrib
```

#### 清华源

```
# 默认注释了源码镜像以提高 apt update 速度，如有需要可自行取消注释
deb https://mirrors.tuna.tsinghua.edu.cn/debian/ stretch main contrib non-free
# deb-src https://mirrors.tuna.tsinghua.edu.cn/debian/ stretch main contrib non-free
deb https://mirrors.tuna.tsinghua.edu.cn/debian/ stretch-updates main contrib non-free
# deb-src https://mirrors.tuna.tsinghua.edu.cn/debian/ stretch-updates main contrib non-free
deb https://mirrors.tuna.tsinghua.edu.cn/debian/ stretch-backports main contrib non-free
# deb-src https://mirrors.tuna.tsinghua.edu.cn/debian/ stretch-backports main contrib non-free
deb https://mirrors.tuna.tsinghua.edu.cn/debian-security stretch/updates main contrib non-free
# deb-src https://mirrors.tuna.tsinghua.edu.cn/debian-security stretch/updates main contrib non-free
```

#### 华为源

```
deb http://mirrors.huaweicloud.com/debian/ stretch main non-free contrib
deb-src http://mirrors.huaweicloud.com/debian/ stretch main non-free contrib
deb http://mirrors.huaweicloud.com/debian-security stretch/updates main
deb-src http://mirrors.huaweicloud.com/debian-security stretch/updates main
deb http://mirrors.huaweicloud.com/debian/ stretch-updates main non-free contrib
deb-src http://mirrors.huaweicloud.com/debian/ stretch-updates main non-free contrib
deb http://mirrors.huaweicloud.com/debian/ stretch-backports main non-free contrib
deb-src http://mirrors.huaweicloud.com/debian/ stretch-backports main non-free contrib
```

---

### Debian 10 buster

#### 阿里源

```
deb http://mirrors.aliyun.com/debian/ buster main non-free contrib
deb-src http://mirrors.aliyun.com/debian/ buster main non-free contrib
deb http://mirrors.aliyun.com/debian-security buster/updates main
deb-src http://mirrors.aliyun.com/debian-security buster/updates main
deb http://mirrors.aliyun.com/debian/ buster-updates main non-free contrib
deb-src http://mirrors.aliyun.com/debian/ buster-updates main non-free contrib
deb http://mirrors.aliyun.com/debian/ buster-backports main non-free contrib
deb-src http://mirrors.aliyun.com/debian/ buster-backports main non-free contrib
```

#### 清华源

```
# 默认注释了源码镜像以提高 apt update 速度，如有需要可自行取消注释
deb https://mirrors.tuna.tsinghua.edu.cn/debian/ buster main contrib non-free
# deb-src https://mirrors.tuna.tsinghua.edu.cn/debian/ buster main contrib non-free
deb https://mirrors.tuna.tsinghua.edu.cn/debian/ buster-updates main contrib non-free
# deb-src https://mirrors.tuna.tsinghua.edu.cn/debian/ buster-updates main contrib non-free
deb https://mirrors.tuna.tsinghua.edu.cn/debian/ buster-backports main contrib non-free
# deb-src https://mirrors.tuna.tsinghua.edu.cn/debian/ buster-backports main contrib non-free
deb https://mirrors.tuna.tsinghua.edu.cn/debian-security buster/updates main contrib non-free
# deb-src https://mirrors.tuna.tsinghua.edu.cn/debian-security buster/updates main contrib non-free
```

#### 华为源

```
deb http://mirrors.huaweicloud.com/debian/ buster main non-free contrib
deb-src http://mirrors.huaweicloud.com/debian/ buster main non-free contrib
deb http://mirrors.huaweicloud.com/debian-security buster/updates main
deb-src http://mirrors.huaweicloud.com/debian-security buster/updates main
deb http://mirrors.huaweicloud.com/debian/ buster-updates main non-free contrib
deb-src http://mirrors.huaweicloud.com/debian/ buster-updates main non-free contrib
deb http://mirrors.huaweicloud.com/debian/ buster-backports main non-free contrib
deb-src http://mirrors.huaweicloud.com/debian/ buster-backports main non-free contrib
```


---

## CentOS /etc/yum.repos.d/CentOS-Base.repo

### 镜像来源

- 阿里源：[https://developer.aliyun.com/mirror/centos](https://developer.aliyun.com/mirror/centos)
- 清华源：[https://mirrors.tuna.tsinghua.edu.cn/help/centos/](https://mirrors.tuna.tsinghua.edu.cn/help/centos/)
- 华为源：[https://mirrors.huaweicloud.com/](https://mirrors.huaweicloud.com/)

### CentOS 6

#### 阿里源

```
# CentOS-Base.repo
#
# The mirror system uses the connecting IP address of the client and the
# update status of each mirror to pick mirrors that are updated to and
# geographically close to the client.  You should use this for CentOS updates
# unless you are manually picking other mirrors.
#
# If the mirrorlist= does not work for you, as a fall back you can try the
# remarked out baseurl= line instead.
#
#

[base]
name=CentOS-$releasever - Base - mirrors.aliyun.com
failovermethod=priority
baseurl=http://mirrors.aliyun.com/centos/$releasever/os/$basearch/
        http://mirrors.aliyuncs.com/centos/$releasever/os/$basearch/
        http://mirrors.cloud.aliyuncs.com/centos/$releasever/os/$basearch/
gpgcheck=1
gpgkey=http://mirrors.aliyun.com/centos/RPM-GPG-KEY-CentOS-6

#released updates
[updates]
name=CentOS-$releasever - Updates - mirrors.aliyun.com
failovermethod=priority
baseurl=http://mirrors.aliyun.com/centos/$releasever/updates/$basearch/
        http://mirrors.aliyuncs.com/centos/$releasever/updates/$basearch/
        http://mirrors.cloud.aliyuncs.com/centos/$releasever/updates/$basearch/
gpgcheck=1
gpgkey=http://mirrors.aliyun.com/centos/RPM-GPG-KEY-CentOS-6

#additional packages that may be useful
[extras]
name=CentOS-$releasever - Extras - mirrors.aliyun.com
failovermethod=priority
baseurl=http://mirrors.aliyun.com/centos/$releasever/extras/$basearch/
        http://mirrors.aliyuncs.com/centos/$releasever/extras/$basearch/
        http://mirrors.cloud.aliyuncs.com/centos/$releasever/extras/$basearch/
gpgcheck=1
gpgkey=http://mirrors.aliyun.com/centos/RPM-GPG-KEY-CentOS-6

#additional packages that extend functionality of existing packages
[centosplus]
name=CentOS-$releasever - Plus - mirrors.aliyun.com
failovermethod=priority
baseurl=http://mirrors.aliyun.com/centos/$releasever/centosplus/$basearch/
        http://mirrors.aliyuncs.com/centos/$releasever/centosplus/$basearch/
        http://mirrors.cloud.aliyuncs.com/centos/$releasever/centosplus/$basearch/
gpgcheck=1
enabled=0
gpgkey=http://mirrors.aliyun.com/centos/RPM-GPG-KEY-CentOS-6

#contrib - packages by Centos Users
[contrib]
name=CentOS-$releasever - Contrib - mirrors.aliyun.com
failovermethod=priority
baseurl=http://mirrors.aliyun.com/centos/$releasever/contrib/$basearch/
        http://mirrors.aliyuncs.com/centos/$releasever/contrib/$basearch/
        http://mirrors.cloud.aliyuncs.com/centos/$releasever/contrib/$basearch/
gpgcheck=1
enabled=0
gpgkey=http://mirrors.aliyun.com/centos/RPM-GPG-KEY-CentOS-6
```

#### 清华源

```
# CentOS-Base.repo
#
# The mirror system uses the connecting IP address of the client and the
# update status of each mirror to pick mirrors that are updated to and
# geographically close to the client.  You should use this for CentOS updates
# unless you are manually picking other mirrors.
#
# If the mirrorlist= does not work for you, as a fall back you can try the
# remarked out baseurl= line instead.
#
#


[base]
name=CentOS-$releasever - Base
baseurl=https://mirrors.tuna.tsinghua.edu.cn/centos/$releasever/os/$basearch/
#mirrorlist=http://mirrorlist.centos.org/?release=$releasever&arch=$basearch&repo=os
enabled=1
gpgcheck=1
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-6

#released updates
[updates]
name=CentOS-$releasever - Updates
baseurl=https://mirrors.tuna.tsinghua.edu.cn/centos/$releasever/updates/$basearch/
#mirrorlist=http://mirrorlist.centos.org/?release=$releasever&arch=$basearch&repo=updates
enabled=1
gpgcheck=1
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-6



#additional packages that may be useful
[extras]
name=CentOS-$releasever - Extras
baseurl=https://mirrors.tuna.tsinghua.edu.cn/centos/$releasever/extras/$basearch/
#mirrorlist=http://mirrorlist.centos.org/?release=$releasever&arch=$basearch&repo=extras
enabled=1
gpgcheck=1
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-6



#additional packages that extend functionality of existing packages
[centosplus]
name=CentOS-$releasever - Plus
baseurl=https://mirrors.tuna.tsinghua.edu.cn/centos/$releasever/centosplus/$basearch/
#mirrorlist=http://mirrorlist.centos.org/?release=$releasever&arch=$basearch&repo=centosplus
gpgcheck=1
enabled=0
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-6


#contrib - packages by Centos Users
[contrib]
name=CentOS-$releasever - Contrib
baseurl=https://mirrors.tuna.tsinghua.edu.cn/centos/$releasever/contrib/$basearch/
#mirrorlist=http://mirrorlist.centos.org/?release=$releasever&arch=$basearch&repo=contrib
gpgcheck=1
enabled=0
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-6
```

#### 华为源

```
# CentOS-Base.repo
#
# The mirror system uses the connecting IP address of the client and the
# update status of each mirror to pick mirrors that are updated to and
# geographically close to the client.  You should use this for CentOS updates
# unless you are manually picking other mirrors.
#
# If the mirrorlist= does not work for you, as a fall back you can try the
# remarked out baseurl= line instead.
#
#

[base]
name=CentOS-$releasever - Base - mirrors.huaweicloud.com
baseurl=https://mirrors.huaweicloud.com/centos/$releasever/os/$basearch/
#mirrorlist=https://mirrorlist.centos.org/?release=$releasever&arch=$basearch&repo=os
gpgcheck=1
gpgkey=https://mirrors.huaweicloud.com/centos/RPM-GPG-KEY-CentOS-6

#released updates
[updates]
name=CentOS-$releasever - Updates - mirrors.huaweicloud.com
baseurl=https://mirrors.huaweicloud.com/centos/$releasever/updates/$basearch/
#mirrorlist=https://mirrorlist.centos.org/?release=$releasever&arch=$basearch&repo=updates
gpgcheck=1
gpgkey=https://mirrors.huaweicloud.com/centos/RPM-GPG-KEY-CentOS-6

#additional packages that may be useful
[extras]
name=CentOS-$releasever - Extras - mirrors.huaweicloud.com
baseurl=https://mirrors.huaweicloud.com/centos/$releasever/extras/$basearch/
#mirrorlist=https://mirrorlist.centos.org/?release=$releasever&arch=$basearch&repo=extras
gpgcheck=1
gpgkey=https://mirrors.huaweicloud.com/centos/RPM-GPG-KEY-CentOS-6

#additional packages that extend functionality of existing packages
[centosplus]
name=CentOS-$releasever - Plus - mirrors.huaweicloud.com
baseurl=https://mirrors.huaweicloud.com/centos/$releasever/centosplus/$basearch/
#mirrorlist=https://mirrorlist.centos.org/?release=$releasever&arch=$basearch&repo=centosplus
gpgcheck=1
enabled=0
gpgkey=https://mirrors.huaweicloud.com/centos/RPM-GPG-KEY-CentOS-6

#contrib - packages by Centos Users
[contrib]
name=CentOS-$releasever - Contrib - mirrors.huaweicloud.com
baseurl=https://mirrors.huaweicloud.com/centos/$releasever/contrib/$basearch/
#mirrorlist=https://mirrorlist.centos.org/?release=$releasever&arch=$basearch&repo=contrib
gpgcheck=1
enabled=0
gpgkey=https://mirrors.huaweicloud.com/centos/RPM-GPG-KEY-CentOS-6
```

---

### CentOS 7

#### 阿里源

```
# CentOS-Base.repo
#
# The mirror system uses the connecting IP address of the client and the
# update status of each mirror to pick mirrors that are updated to and
# geographically close to the client.  You should use this for CentOS updates
# unless you are manually picking other mirrors.
#
# If the mirrorlist= does not work for you, as a fall back you can try the
# remarked out baseurl= line instead.
#
#

[base]
name=CentOS-$releasever - Base - mirrors.aliyun.com
failovermethod=priority
baseurl=http://mirrors.aliyun.com/centos/$releasever/os/$basearch/
        http://mirrors.aliyuncs.com/centos/$releasever/os/$basearch/
        http://mirrors.cloud.aliyuncs.com/centos/$releasever/os/$basearch/
gpgcheck=1
gpgkey=http://mirrors.aliyun.com/centos/RPM-GPG-KEY-CentOS-7

#released updates
[updates]
name=CentOS-$releasever - Updates - mirrors.aliyun.com
failovermethod=priority
baseurl=http://mirrors.aliyun.com/centos/$releasever/updates/$basearch/
        http://mirrors.aliyuncs.com/centos/$releasever/updates/$basearch/
        http://mirrors.cloud.aliyuncs.com/centos/$releasever/updates/$basearch/
gpgcheck=1
gpgkey=http://mirrors.aliyun.com/centos/RPM-GPG-KEY-CentOS-7

#additional packages that may be useful
[extras]
name=CentOS-$releasever - Extras - mirrors.aliyun.com
failovermethod=priority
baseurl=http://mirrors.aliyun.com/centos/$releasever/extras/$basearch/
        http://mirrors.aliyuncs.com/centos/$releasever/extras/$basearch/
        http://mirrors.cloud.aliyuncs.com/centos/$releasever/extras/$basearch/
gpgcheck=1
gpgkey=http://mirrors.aliyun.com/centos/RPM-GPG-KEY-CentOS-7

#additional packages that extend functionality of existing packages
[centosplus]
name=CentOS-$releasever - Plus - mirrors.aliyun.com
failovermethod=priority
baseurl=http://mirrors.aliyun.com/centos/$releasever/centosplus/$basearch/
        http://mirrors.aliyuncs.com/centos/$releasever/centosplus/$basearch/
        http://mirrors.cloud.aliyuncs.com/centos/$releasever/centosplus/$basearch/
gpgcheck=1
enabled=0
gpgkey=http://mirrors.aliyun.com/centos/RPM-GPG-KEY-CentOS-7

#contrib - packages by Centos Users
[contrib]
name=CentOS-$releasever - Contrib - mirrors.aliyun.com
failovermethod=priority
baseurl=http://mirrors.aliyun.com/centos/$releasever/contrib/$basearch/
        http://mirrors.aliyuncs.com/centos/$releasever/contrib/$basearch/
        http://mirrors.cloud.aliyuncs.com/centos/$releasever/contrib/$basearch/
gpgcheck=1
enabled=0
gpgkey=http://mirrors.aliyun.com/centos/RPM-GPG-KEY-CentOS-7
```

#### 清华源

```
# CentOS-Base.repo
#
# The mirror system uses the connecting IP address of the client and the
# update status of each mirror to pick mirrors that are updated to and
# geographically close to the client.  You should use this for CentOS updates
# unless you are manually picking other mirrors.
#
# If the mirrorlist= does not work for you, as a fall back you can try the
# remarked out baseurl= line instead.
#
#


[base]
name=CentOS-$releasever - Base
baseurl=https://mirrors.tuna.tsinghua.edu.cn/centos/$releasever/os/$basearch/
#mirrorlist=http://mirrorlist.centos.org/?release=$releasever&arch=$basearch&repo=os
enabled=1
gpgcheck=1
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-7

#released updates
[updates]
name=CentOS-$releasever - Updates
baseurl=https://mirrors.tuna.tsinghua.edu.cn/centos/$releasever/updates/$basearch/
#mirrorlist=http://mirrorlist.centos.org/?release=$releasever&arch=$basearch&repo=updates
enabled=1
gpgcheck=1
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-7



#additional packages that may be useful
[extras]
name=CentOS-$releasever - Extras
baseurl=https://mirrors.tuna.tsinghua.edu.cn/centos/$releasever/extras/$basearch/
#mirrorlist=http://mirrorlist.centos.org/?release=$releasever&arch=$basearch&repo=extras
enabled=1
gpgcheck=1
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-7



#additional packages that extend functionality of existing packages
[centosplus]
name=CentOS-$releasever - Plus
baseurl=https://mirrors.tuna.tsinghua.edu.cn/centos/$releasever/centosplus/$basearch/
#mirrorlist=http://mirrorlist.centos.org/?release=$releasever&arch=$basearch&repo=centosplus
gpgcheck=1
enabled=0
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-7
```

#### 华为源

```
# CentOS-Base.repo
#
# The mirror system uses the connecting IP address of the client and the
# update status of each mirror to pick mirrors that are updated to and
# geographically close to the client.  You should use this for CentOS updates
# unless you are manually picking other mirrors.
#
# If the mirrorlist= does not work for you, as a fall back you can try the
# remarked out baseurl= line instead.
#
#

[base]
name=CentOS-$releasever - Base - mirrors.huaweicloud.com
baseurl=https://mirrors.huaweicloud.com/centos/$releasever/os/$basearch/
#mirrorlist=https://mirrorlist.centos.org/?release=$releasever&arch=$basearch&repo=os
gpgcheck=1
gpgkey=https://mirrors.huaweicloud.com/centos/RPM-GPG-KEY-CentOS-7

#released updates
[updates]
name=CentOS-$releasever - Updates - mirrors.huaweicloud.com
baseurl=https://mirrors.huaweicloud.com/centos/$releasever/updates/$basearch/
#mirrorlist=https://mirrorlist.centos.org/?release=$releasever&arch=$basearch&repo=updates
gpgcheck=1
gpgkey=https://mirrors.huaweicloud.com/centos/RPM-GPG-KEY-CentOS-7

#additional packages that may be useful
[extras]
name=CentOS-$releasever - Extras - mirrors.huaweicloud.com
baseurl=https://mirrors.huaweicloud.com/centos/$releasever/extras/$basearch/
#mirrorlist=https://mirrorlist.centos.org/?release=$releasever&arch=$basearch&repo=extras
gpgcheck=1
gpgkey=https://mirrors.huaweicloud.com/centos/RPM-GPG-KEY-CentOS-7

#additional packages that extend functionality of existing packages
[centosplus]
name=CentOS-$releasever - Plus - mirrors.huaweicloud.com
baseurl=https://mirrors.huaweicloud.com/centos/$releasever/centosplus/$basearch/
#mirrorlist=https://mirrorlist.centos.org/?release=$releasever&arch=$basearch&repo=centosplus
gpgcheck=1
enabled=0
gpgkey=https://mirrors.huaweicloud.com/centos/RPM-GPG-KEY-CentOS-7
```

---

### CentOS 8

#### 阿里源

```
# CentOS-Base.repo
#
# The mirror system uses the connecting IP address of the client and the
# update status of each mirror to pick mirrors that are updated to and
# geographically close to the client.  You should use this for CentOS updates
# unless you are manually picking other mirrors.
#
# If the mirrorlist= does not work for you, as a fall back you can try the
# remarked out baseurl= line instead.
#
#

[base]
name=CentOS-$releasever - Base - mirrors.aliyun.com
failovermethod=priority
baseurl=https://mirrors.aliyun.com/centos/$releasever/BaseOS/$basearch/os/
        http://mirrors.aliyuncs.com/centos/$releasever/BaseOS/$basearch/os/
        http://mirrors.cloud.aliyuncs.com/centos/$releasever/BaseOS/$basearch/os/
gpgcheck=1
gpgkey=https://mirrors.aliyun.com/centos/RPM-GPG-KEY-CentOS-Official

#additional packages that may be useful
[extras]
name=CentOS-$releasever - Extras - mirrors.aliyun.com
failovermethod=priority
baseurl=https://mirrors.aliyun.com/centos/$releasever/extras/$basearch/os/
        http://mirrors.aliyuncs.com/centos/$releasever/extras/$basearch/os/
        http://mirrors.cloud.aliyuncs.com/centos/$releasever/extras/$basearch/os/
gpgcheck=1
gpgkey=https://mirrors.aliyun.com/centos/RPM-GPG-KEY-CentOS-Official

#additional packages that extend functionality of existing packages
[centosplus]
name=CentOS-$releasever - Plus - mirrors.aliyun.com
failovermethod=priority
baseurl=https://mirrors.aliyun.com/centos/$releasever/centosplus/$basearch/os/
        http://mirrors.aliyuncs.com/centos/$releasever/centosplus/$basearch/os/
        http://mirrors.cloud.aliyuncs.com/centos/$releasever/centosplus/$basearch/os/
gpgcheck=1
enabled=0
gpgkey=https://mirrors.aliyun.com/centos/RPM-GPG-KEY-CentOS-Official

[PowerTools]
name=CentOS-$releasever - PowerTools - mirrors.aliyun.com
failovermethod=priority
baseurl=https://mirrors.aliyun.com/centos/$releasever/PowerTools/$basearch/os/
        http://mirrors.aliyuncs.com/centos/$releasever/PowerTools/$basearch/os/
        http://mirrors.cloud.aliyuncs.com/centos/$releasever/PowerTools/$basearch/os/
gpgcheck=1
enabled=0
gpgkey=https://mirrors.aliyun.com/centos/RPM-GPG-KEY-CentOS-Official


[AppStream]
name=CentOS-$releasever - AppStream - mirrors.aliyun.com
failovermethod=priority
baseurl=https://mirrors.aliyun.com/centos/$releasever/AppStream/$basearch/os/
        http://mirrors.aliyuncs.com/centos/$releasever/AppStream/$basearch/os/
        http://mirrors.cloud.aliyuncs.com/centos/$releasever/AppStream/$basearch/os/
gpgcheck=1
gpgkey=https://mirrors.aliyun.com/centos/RPM-GPG-KEY-CentOS-Official
```

#### 清华源

```
# CentOS-Base.repo
#
# The mirror system uses the connecting IP address of the client and the
# update status of each mirror to pick mirrors that are updated to and
# geographically close to the client.  You should use this for CentOS updates
# unless you are manually picking other mirrors.
#
# If the mirrorlist= does not work for you, as a fall back you can try the
# remarked out baseurl= line instead.
#
#



[BaseOS]
name=CentOS-$releasever - Base
baseurl=https://mirrors.tuna.tsinghua.edu.cn/centos/$releasever/BaseOS/$basearch/os/
#mirrorlist=http://mirrorlist.centos.org/?release=$releasever&arch=$basearch&repo=BaseOS&infra=$infra
enabled=1
gpgcheck=1
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-centosofficial

[AppStream]
name=CentOS-$releasever - AppStream
baseurl=https://mirrors.tuna.tsinghua.edu.cn/centos/$releasever/AppStream/$basearch/os/
#mirrorlist=http://mirrorlist.centos.org/?release=$releasever&arch=$basearch&repo=AppStream&infra=$infra
enabled=1
gpgcheck=1
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-centosofficial

[PowerTools]
name=CentOS-$releasever - PowerTools
baseurl=https://mirrors.tuna.tsinghua.edu.cn/centos/$releasever/PowerTools/$basearch/os/
#mirrorlist=http://mirrorlist.centos.org/?release=$releasever&arch=$basearch&repo=PowerTools&infra=$infra
enabled=0
gpgcheck=1
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-centosofficial


#additional packages that may be useful
[extras]
name=CentOS-$releasever - Extras
baseurl=https://mirrors.tuna.tsinghua.edu.cn/centos/$releasever/extras/$basearch/os/
#mirrorlist=http://mirrorlist.centos.org/?release=$releasever&arch=$basearch&repo=extras
enabled=1
gpgcheck=1
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-centosofficial



#additional packages that extend functionality of existing packages
[centosplus]
name=CentOS-$releasever - Plus
baseurl=https://mirrors.tuna.tsinghua.edu.cn/centos/$releasever/centosplus/$basearch/os/
#mirrorlist=http://mirrorlist.centos.org/?release=$releasever&arch=$basearch&repo=centosplus
gpgcheck=1
enabled=0
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-centosofficial
```

#### 华为源

```
# CentOS-Base.repo
#
# The mirror system uses the connecting IP address of the client and the
# update status of each mirror to pick mirrors that are updated to and
# geographically close to the client.  You should use this for CentOS updates
# unless you are manually picking other mirrors.
#
# If the mirrorlist= does not work for you, as a fall back you can try the
# remarked out baseurl= line instead.
#
#

[BaseOS]
name=CentOS-$releasever - Base - mirrors.huaweicloud.com
baseurl=https://mirrors.huaweicloud.com/centos/$releasever/BaseOS/$basearch/os/
#mirrorlist=https://mirrorlist.centos.org/?release=$releasever&arch=$basearch&repo=BaseOS&infra=$infra
gpgcheck=1
gpgkey=https://mirrors.huaweicloud.com/centos/RPM-GPG-KEY-CentOS-Official

#released updates
[AppStream]
name=CentOS-$releasever - AppStream - mirrors.huaweicloud.com
baseurl=https://mirrors.huaweicloud.com/centos/$releasever/AppStream/$basearch/os/
#mirrorlist=https://mirrorlist.centos.org/?release=$releasever&arch=$basearch&repo=AppStream&infra=$infra
gpgcheck=1
gpgkey=https://mirrors.huaweicloud.com/centos/RPM-GPG-KEY-CentOS-Official

[PowerTools]
name=CentOS-$releasever - PowerTools - mirrors.huaweicloud.com
baseurl=https://mirrors.huaweicloud.com/centos/$releasever/PowerTools/$basearch/os/
#mirrorlist=https://mirrorlist.centos.org/?release=$releasever&arch=$basearch&repo=PowerTools&infra=$infra
gpgcheck=1
gpgkey=https://mirrors.huaweicloud.com/centos/RPM-GPG-KEY-CentOS-Official


#additional packages that may be useful
[extras]
name=CentOS-$releasever - Extras - mirrors.huaweicloud.com
baseurl=https://mirrors.huaweicloud.com/centos/$releasever/extras/$basearch/os/
#mirrorlist=https://mirrorlist.centos.org/?release=$releasever&arch=$basearch&repo=extras
gpgcheck=1
gpgkey=https://mirrors.huaweicloud.com/centos/RPM-GPG-KEY-CentOS-Official


#additional packages that extend functionality of existing packages
[centosplus]
name=CentOS-$releasever - Plus - mirrors.huaweicloud.com
baseurl=https://mirrors.huaweicloud.com/centos/$releasever/centosplus/$basearch/os/
#mirrorlist=https://mirrorlist.centos.org/?release=$releasever&arch=$basearch&repo=centosplus
gpgcheck=1
enabled=0
gpgkey=https://mirrors.huaweicloud.com/centos/RPM-GPG-KEY-CentOS-Official
```

---

## CentOS /etc/yum.repos.d/epel.repo

epel 有镜像机制，一般不用自己配置，这里只介绍阿里源的配置

### 镜像来源

- 阿里源：[https://developer.aliyun.com/mirror/epel](https://developer.aliyun.com/mirror/epel)
- 清华源：[https://mirrors.tuna.tsinghua.edu.cn/help/epel/](https://mirrors.tuna.tsinghua.edu.cn/help/epel/)
- 华为源：[https://mirrors.huaweicloud.com/](https://mirrors.huaweicloud.com/)

### CentOS 6

#### 阿里源

```
[epel]
name=Extra Packages for Enterprise Linux 6 - $basearch
baseurl=http://mirrors.aliyun.com/epel/6/$basearch
failovermethod=priority
enabled=1
gpgcheck=0
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-EPEL-6

[epel-debuginfo]
name=Extra Packages for Enterprise Linux 6 - $basearch - Debug
baseurl=http://mirrors.aliyun.com/epel/6/$basearch/debug
failovermethod=priority
enabled=0
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-EPEL-6
gpgcheck=0

[epel-source]
name=Extra Packages for Enterprise Linux 6 - $basearch - Source
baseurl=http://mirrors.aliyun.com/epel/6/SRPMS
failovermethod=priority
enabled=0
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-EPEL-6
gpgcheck=0
```

---

### CentOS 7

#### 阿里源

```
[epel]
name=Extra Packages for Enterprise Linux 7 - $basearch
baseurl=http://mirrors.aliyun.com/epel/7/$basearch
failovermethod=priority
enabled=1
gpgcheck=0
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-EPEL-7

[epel-debuginfo]
name=Extra Packages for Enterprise Linux 7 - $basearch - Debug
baseurl=http://mirrors.aliyun.com/epel/7/$basearch/debug
failovermethod=priority
enabled=0
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-EPEL-7
gpgcheck=0

[epel-source]
name=Extra Packages for Enterprise Linux 7 - $basearch - Source
baseurl=http://mirrors.aliyun.com/epel/7/SRPMS
failovermethod=priority
enabled=0
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-EPEL-7
gpgcheck=0
```

---

### CentOS 8

#### 阿里源

1）安装 epel 配置包

```
yum install -y 
https://mirrors.aliyun.com/epel/epel-release-latest-8.noarch.rpm
```

2）将 repo 配置中的地址替换为阿里云镜像站地址

```
sed -i 's|^#baseurl=https://download.fedoraproject.org/pub|baseurl=https://mirrors.aliyun.com|' /etc/yum.repos.d/epel*
sed -i 's|^metalink|#metalink|' /etc/yum.repos.d/epel*
```

---

## Apline apk

### 镜像来源

- 阿里源：[https://developer.aliyun.com/mirror/alpine](https://developer.aliyun.com/mirror/alpine)
- 清华源：[https://mirrors.tuna.tsinghua.edu.cn/help/alpine/](https://mirrors.tuna.tsinghua.edu.cn/help/alpine/)
- 华为源：[https://mirrors.huaweicloud.com/](https://mirrors.huaweicloud.com/)


### 阿里源

```
sed -i 's/dl-cdn.alpinelinux.org/mirrors.aliyun.com/g' /etc/apk/repositories
```

### 清华源

```
sed -i 's/dl-cdn.alpinelinux.org/mirrors.tuna.tsinghua.edu.cn/g' /etc/apk/repositories
```

### 华为源

```
sed -i 's/dl-cdn.alpinelinux.org/mirrors.huaweicloud.com/g' /etc/apk/repositories
```

---

## macOS brew

### 镜像来源

- 阿里源：[https://developer.aliyun.com/mirror/homebrew](https://developer.aliyun.com/mirror/homebrew)
- 清华源：[https://mirrors.tuna.tsinghua.edu.cn/help/homebrew/](https://mirrors.tuna.tsinghua.edu.cn/help/homebrew/)

### 阿里源

```
# 替换brew.git:
cd "$(brew --repo)"
git remote set-url origin https://mirrors.aliyun.com/homebrew/brew.git
# 替换homebrew-core.git:
cd "$(brew --repo)/Library/Taps/homebrew/homebrew-core"
git remote set-url origin https://mirrors.aliyun.com/homebrew/homebrew-core.git
# 应用生效
brew update
```

```
# 替换homebrew-bottles:
echo 'export HOMEBREW_BOTTLE_DOMAIN=https://mirrors.aliyun.com/homebrew/homebrew-bottles' >> ~/.bash_profile
source ~/.bash_profile
# 或者

echo 'export HOMEBREW_BOTTLE_DOMAIN=https://mirrors.aliyun.com/homebrew/homebrew-bottles' >> ~/.zshrc
source ~/.zshrc
```

### 清华源

```
git -C "$(brew --repo)" remote set-url origin https://mirrors.tuna.tsinghua.edu.cn/git/homebrew/brew.git


git -C "$(brew --repo homebrew/core)" remote set-url origin https://mirrors.tuna.tsinghua.edu.cn/git/homebrew/homebrew-core.git
git -C "$(brew --repo homebrew/cask)" remote set-url origin https://mirrors.tuna.tsinghua.edu.cn/git/homebrew/homebrew-cask.git
git -C "$(brew --repo homebrew/cask-fonts)" remote set-url origin https://mirrors.tuna.tsinghua.edu.cn/git/homebrew/homebrew-cask-fonts.git
git -C "$(brew --repo homebrew/cask-drivers)" remote set-url origin https://mirrors.tuna.tsinghua.edu.cn/git/homebrew/homebrew-cask-drivers.git

# 更换后测试工作是否正常
brew update
```

```
echo 'export HOMEBREW_BOTTLE_DOMAIN=https://mirrors.tuna.tsinghua.edu.cn/homebrew-bottles' >> ~/.bash_profile
source ~/.bash_profile

# 或者
echo 'export HOMEBREW_BOTTLE_DOMAIN=https://mirrors.tuna.tsinghua.edu.cn/homebrew-bottles' >> ~/.zshrc
source ~/.zshrc
```

---

## Docker /etc/docker/daemon.json

### 镜像来源

- 阿里源：[https://cr.console.aliyun.com/](https://cr.console.aliyun.com/)
- 华为源：[https://console.huaweicloud.com/swr/](https://console.huaweicloud.com/swr/)
- 百度源：[https://cloud.baidu.com/doc/CCE/index.html](https://cloud.baidu.com/doc/CCE/index.html)

### 配置

其中 阿里源 和 华为源 需要申请。
{:.info}

```
{
    "registry-mirrors":[
        "https://xxxxxx.mirror.aliyuncs.com",
        "https://mirror.baidubce.com",
        "https://xxxxxx.mirror.swr.myhuaweicloud.com"
    ]
}
```

### 阿里源

容器镜像服务 -> 镜像中心 -> 镜像加速器

[https://cr.console.aliyun.com/](https://cr.console.aliyun.com/)

![03-21-59-aliyun-docker-PaCRrU](https://up-img.yonghong.tech/pic/2020/06/03-21-59-aliyun-docker-PaCRrU.png)


### 华为源

容器镜像服务 -> 镜像中心 -> 镜像加速器

[https://console.huaweicloud.com/swr/](https://console.huaweicloud.com/swr/)

![03-21-59-huaweicloud-docker-9az6BA](https://up-img.yonghong.tech/pic/2020/06/03-21-59-huaweicloud-docker-9az6BA.png)


### 百度源

直接用

https://mirror.baidubce.com

---

## Kubernetes

### 镜像来源

- 阿里源：[https://developer.aliyun.com/mirror/kubernetes](https://developer.aliyun.com/mirror/kubernetes)
- 清华源：[https://mirrors.tuna.tsinghua.edu.cn/help/kubernetes/](https://mirrors.tuna.tsinghua.edu.cn/help/kubernetes/)
- 华为源：[https://mirrors.huaweicloud.com/](https://mirrors.huaweicloud.com/)

kubeadm kubectl kubelet 安装不多说主要说一下 kubeadm init

### kubeadm init 

```
# 通过--image-repository选项可以直接从阿里源下载镜像，但是有可能阿里源比官方慢，不能安装最新的版本
kubeadm init --image-repository=registry.aliyuncs.com/google_containers

# 另一种方式是手动下载，再替换标签
kubeadm config images list | grep k8s.gcr.io | while read line; \
do imageName=${line##*/}; \
docker pull registry.aliyuncs.com/google_containers/$imageName; \
docker tag registry.aliyuncs.com/google_containers/$imageName k8s.gcr.io/$imageName; \
docker rmi registry.aliyuncs.com/google_containers/$imageName; \
done
```

---

## Python Anaconda .condarc

### 镜像来源

- 清华源：[https://mirrors.tuna.tsinghua.edu.cn/help/anaconda/](https://mirrors.tuna.tsinghua.edu.cn/help/anaconda/)

```
channels:
  - defaults
show_channel_urls: true
channel_alias: https://mirrors.tuna.tsinghua.edu.cn/anaconda
default_channels:
  - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main
  - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free
  - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/r
  - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/pro
  - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/msys2
custom_channels:
  conda-forge: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
  msys2: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
  bioconda: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
  menpo: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
  pytorch: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
  simpleitk: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
```

## Maven

### 镜像来源

- 阿里源：[https://developer.aliyun.com/mirror/maven](https://developer.aliyun.com/mirror/maven)
- 华为源：[https://mirrors.huaweicloud.com/](https://mirrors.huaweicloud.com/)


### 配置Maven

打开 Maven 的配置文件(windows机器一般在maven安装目录的conf/settings.xml)，在<mirrors></mirrors>标签中添加 mirror 子节点:

```xml
<mirror>
    <id>aliyunmaven</id>
    <mirrorOf>*</mirrorOf>
    <name>阿里云公共仓库</name>
    <url>https://maven.aliyun.com/repository/public</url>
</mirror>
```

如果想使用其它代理仓库,可在<repositories></repositories>节点中加入对应的仓库使用地址。以使用spring代理仓为例：

```xml
<repository>
    <id>spring</id>
    <url>https://maven.aliyun.com/repository/spring</url>
    <releases>
        <enabled>true</enabled>
    </releases>
    <snapshots>
        <enabled>true</enabled>
    </snapshots>
</repository>
```

### 配置Gradle

在 build.gradle 文件中加入以下代码:

```gradle
allprojects {
    repositories {
        maven { url 'https://maven.aliyun.com/repository/public/' }
        mavenLocal()
        mavenCentral()
    }
}
```

如果想使用 maven.aliyun.com 提供的其它代理仓，以使用 spring 仓为例，代码如下:

```gradle
allprojects {
    repositories {
        maven { url 'https://maven.aliyun.com/repository/public/' }
        maven { url 'https://maven.aliyun.com/repository/spring/'}
        mavenLocal()
        mavenCentral()
    }
}
```

## npm

### 镜像来源

- 阿里源：[https://developer.aliyun.com/mirror/NPM](https://developer.aliyun.com/mirror/NPM)

> 这是一个完整 `npmjs.org` 镜像，你可以用此代替官方版本(只读)，同步频率目前为 **10分钟** 一次以保证尽量与官方服务同步。

- 当前 [registry.npm.taobao.org](https://registry.npm.taobao.org/) 是从 [r.cnpmjs.org](https://r.cnpmjs.org/) 进行全量同步的.
- 当前 [npm.taobao.org](https://developer.aliyun.com/) 运行版本是: [cnpmjs.org](http://cnpmjs.org/)@3.0.0-rc.32
- 本系统运行在 [Node.js](https://nodejs.org/)@v12.8.1 上.
- 开源镜像: http://npm.taobao.org/mirrors
- Node.js 镜像: http://npm.taobao.org/mirrors/node
- alinode 镜像: http://npm.taobao.org/mirrors/alinode
- phantomjs 镜像: http://npm.taobao.org/mirrors/phantomjs
- ChromeDriver 镜像: http://npm.taobao.org/mirrors/chromedriver
- OperaDriver 镜像: http://npm.taobao.org/mirrors/operadriver
- Selenium 镜像: http://npm.taobao.org/mirrors/selenium
- Node.js 文档镜像: http://npm.taobao.org/mirrors/node/latest/docs/api/index.html
- NPM 镜像: https://npm.taobao.org/mirrors/npm/
- electron 镜像: https://npm.taobao.org/mirrors/electron/
- node-inspector 镜像: https://npm.taobao.org/mirrors/node-inspector/

### 使用说明

你可以使用我们定制的 [cnpm](https://github.com/cnpm/cnpm) (gzip 压缩支持) 命令行工具代替默认的 `npm`:

```
$ npm install -g cnpm --registry=https://registry.npm.taobao.org
```

或者你直接通过添加 `npm` 参数 `alias` 一个新命令:

```
alias cnpm="npm --registry=https://registry.npm.taobao.org \
--cache=$HOME/.npm/.cache/cnpm \
--disturl=https://npm.taobao.org/dist \
--userconfig=$HOME/.cnpmrc"

# Or alias it in .bashrc or .zshrc
$ echo '\n#alias for cnpm\nalias cnpm="npm --registry=https://registry.npm.taobao.org \
  --cache=$HOME/.npm/.cache/cnpm \
  --disturl=https://npm.taobao.org/dist \
  --userconfig=$HOME/.cnpmrc"' >> ~/.zshrc && source ~/.zshrc
```

#### 安装模块

从 [registry.npm.taobao.org](https://registry.npm.taobao.org/) 安装所有模块. 当安装的时候发现安装的模块还没有同步过来, 淘宝 NPM 会自动在后台进行同步, 并且会让你从官方 NPM [registry.npmjs.org](https://registry.npmjs.org/) 进行安装. 下次你再安装这个模块的时候, 就会直接从 淘宝 NPM 安装了.

```
$ cnpm install [name]
```

#### 同步模块

直接通过 `sync` 命令马上同步一个模块, 只有 `cnpm` 命令行才有此功能:

```
$ cnpm sync connect
```

当然, 你可以直接通过 web 方式来同步: [/sync/connect](https://developer.aliyun.com/sync/connect)

```
$ open https://npm.taobao.org/sync/connect
```

#### 其它命令

支持 `npm` 除了 `publish` 之外的所有命令, 如:

```
$ cnpm info connect
```


## Ruby Gems

### 镜像来源

- 阿里源：[https://developer.aliyun.com/mirror/rubygems](https://developer.aliyun.com/mirror/rubygems)
- Ruby China：[https://ruby-china.org/](https://ruby-china.org/)

### 配置Ruby Gems

- 查找默认源

```
gem sources
```

- 移除默认源

```
gem sources --remove https://rubygems.org/
```

- 添加新源

```
gem sources -a https://mirrors.aliyun.com/rubygems/
gem sources -a https://gems.ruby-china.com/
```








