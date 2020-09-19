---
title: Arthas In Action
key: 2020-07-03-arthas-in-action
tags:
- Arthas
- Springboot
- Java
- jvm
---

## 0.Arthas 是什么

![_images/arthas.png](https://up-img.yonghong.tech/pic/2020/07/02-18-41-arthas-fqGKvW.png)

`Arthas` 是Alibaba开源的Java诊断工具，深受开发者喜爱。

当你遇到以下类似问题而束手无策时，`Arthas`可以帮助你解决：

1. 这个类从哪个 jar 包加载的？为什么会报各种类相关的 Exception？
2. 我改的代码为什么没有执行到？难道是我没 commit？分支搞错了？
3. 遇到问题无法在线上 debug，难道只能通过加日志再重新发布吗？
4. 线上遇到某个用户的数据处理有问题，但线上同样无法 debug，线下无法重现！
5. 是否有一个全局视角来查看系统的运行状况？
6. 有什么办法可以监控到JVM的实时运行状态？
7. 怎么快速定位应用的热点，生成火焰图？

## 1.Arthas 怎么用

### 1.1.Arthas 的安装

我是在docker中使用的，docker 中只有 java-headless 版本，直接运行的话会报错找不到 tools.jar，因此要安装完整版的 jdk

```shell
$ curl -O https://alibaba.github.io/arthas/arthas-boot.jar
# docker 容器中 java 线程的 PID 为1，可以直接将 PID 传给 arthas
$ java -jar arthas-boot.jar 1
[INFO] arthas-boot version: 3.3.3
[INFO] Start download arthas from remote server: https://maven.aliyun.com/repository/public/com/taobao/arthas/arthas-packaging/3.3.6/arthas-packaging-3.3.6-bin.zip
[INFO] Download arthas success.
[INFO] arthas home: /root/.arthas/lib/3.3.6/arthas
[INFO] Try to attach process 1
Exception in thread "main" java.lang.IllegalArgumentException: Can not find tools.jar under java home: /usr/lib/jvm/java-1.8.0-openjdk-1.8.0.252.b09-2.el7_8.x86_64/jre, please try to start arthas-boot with full path java. Such as /opt/jdk/bin/java -jar arthas-boot.jar
	at com.taobao.arthas.boot.ProcessUtils.findJavaHome(ProcessUtils.java:222)
	at com.taobao.arthas.boot.ProcessUtils.startArthasCore(ProcessUtils.java:233)
	at com.taobao.arthas.boot.Bootstrap.main(Bootstrap.java:515)
```

为了不发生错误，我们使用相同的版本

```shell
$ yum search java-1.8.0-openjdk --showduplicate
```

安装

```shell
$ yum install java-1.8.0-openjdk-devel-1.8.0.252.b09-2.el7_8.x86_64
```

重新运行

```shell
$ java -jar arthas-boot.jar 1
[INFO] arthas-boot version: 3.3.3
[INFO] arthas home: /root/.arthas/lib/3.3.6/arthas
[INFO] Try to attach process 1
[INFO] Attach process 1 success.
[INFO] arthas-client connect 127.0.0.1 3658
  ,---.  ,------. ,--------.,--.  ,--.  ,---.   ,---.
 /  O  \ |  .--. ''--.  .--'|  '--'  | /  O  \ '   .-'
|  .-.  ||  '--'.'   |  |   |  .--.  ||  .-.  |`.  `-.
|  | |  ||  |\  \    |  |   |  |  |  ||  | |  |.-'    |
`--' `--'`--' '--'   `--'   `--'  `--'`--' `--'`-----'


wiki      https://alibaba.github.io/arthas
tutorials https://alibaba.github.io/arthas/arthas-tutorials
version   3.3.6
pid       1
time      2020-07-02 17:46:29

[arthas@1]$
```

### 1.2.Arthas的使用

参考文档：[https://alibaba.github.io/arthas/](https://alibaba.github.io/arthas/)



#### 1.2.1.查看 dashboard

```shell
[arthas@1]$ dashboard
# 每隔 1000ms 刷新一次
[arthas@1]$ dashboard -i 1000
```

![09-19-53-截屏2020-07-09下午7.51.48-1XO1rN](https://up-img.yonghong.tech/pic/2020/07/09-19-53-09-19-53-截屏2020-07-09%20下午7.51.48-1XO1rN-CjZpdk.png)

#### 1.2.2.查看系统环境变量

```shell
[arthas@1]$ sysenv
 KEY                         VALUE
--------------------------------------------------------
 PATH                        /usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
 TZ                          Asia/Shanghai
 ……
```

#### 1.2.3.查看jvm信息

```shell
[arthas@1]$ jvm
 RUNTIME
--------------------------------------------------------
 MACHINE-NAME                            1@test
 JVM-START-TIME                          2020-07-09 13:39:45
 MANAGEMENT-SPEC-VERSION                 1.2
 SPEC-NAME                               Java Virtual Machine Specification
 SPEC-VENDOR                             Oracle Corporation
 SPEC-VERSION                            1.8
 VM-NAME                                 OpenJDK 64-Bit Server VM
 VM-VENDOR                               Oracle Corporation
 VM-VERSION                              25.252-b09
 INPUT-ARGUMENTS                         -Xmx2G
                                         -Xss1M
                                         -XX:+HeapDumpOnOutOfMemoryError
                                         -Dspring.profiles.active=dev
                                         -Dfile.encoding=UTF-8
                                         -Duser.timezone=GMT+8

```

#### 1.2.4.heapdump

```shell
# 类似 jmap 命令的 heap dump 功能
# dump到指定文件
[arthas@58205]$ heapdump /tmp/dump.hprof
Dumping heap to /tmp/dump.hprof...
Heap dump file created
# 只dump live对象
[arthas@58205]$ heapdump --live /tmp/dump.hprof
Dumping heap to /tmp/dump.hprof...
Heap dump file created
```

## 2.高阶用法

