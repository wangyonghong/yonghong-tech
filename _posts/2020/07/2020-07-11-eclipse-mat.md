---
title: 使用 Eclipse MAT 分析 Java 内存泄露
key: 2020-07-04-eclipse-mat
tags:
- mat
- eclipse
- java
---

## 0. Eclipse 和 MAT 的安装

从 Eclipse 官网下载，https://www.eclipse.org/downloads/

最新的 Eclipse（2020-06）安装可能会有些问题，安装完打不开，这时候需要修改一下 `/Applications/Eclipse.app/Contents/Info.plist`，自定义 java 环境

```xml
<array>
      			
  <!-- to use a specific Java version (instead of the platform's default) uncomment one of the following options, or add a VM found via $/usr/libexec/java_home -V
    <string>-vm</string>		
    <string>/System/Library/Java/JavaVirtualMachines/1.6.0.jdk/Contents/Commands/java</string>
    <string>-vm</string><string>/Library/Java/JavaVirtualMachines/1.8.0.jdk/Contents/Home/bin/java</string>
  -->
    <string>-vm</string>
    <string>/Library/Java/JavaVirtualMachines/jdk-11.0.7.jdk/Contents/Home/bin/java</string>
    <string>-keyring</string>
    <string>~/.eclipse_keyring</string>

</array>
```

Java的位置可以使用下面的命令查询

```shell
$ /usr/libexec/java_home -V
Matching Java Virtual Machines (4):
    11.0.7, x86_64:	"Java SE 11.0.7"	/Library/Java/JavaVirtualMachines/jdk-11.0.7.jdk/Contents/Home
    11.0.6, x86_64:	"AdoptOpenJDK 11"	/Library/Java/JavaVirtualMachines/adoptopenjdk-11.jdk/Contents/Home
    1.8.0_252, x86_64:	"AdoptOpenJDK 8"	/Library/Java/JavaVirtualMachines/adoptopenjdk-8.jdk/Contents/Home
    1.8.0_221, x86_64:	"Java SE 8"	/Library/Java/JavaVirtualMachines/jdk1.8.0_221.jdk/Contents/Home

/Library/Java/JavaVirtualMachines/jdk-11.0.7.jdk/Contents/Home
```

安装MAT





## 1.dump 



## 2.分析





