---
title: 使用又拍云加速你的静态网站
key: 2020-05-16-speed-up-your-website
permalink: /article/speed-up-your-website/
date: 2020-06-01
tags:
- 加速
- 静态网站
- 又拍云
- jekyll
description: 本文描述了如何使用又拍云加速静态网站，以使用 jekyll 搭建的本站为例，从静态资源到全站加速，一步一步提升网站的访问速度。
---

> 本文参加又拍云原创技术征文活动 [地址一](https://www.upyun.com/tech/article/551/%E6%9C%89%E5%A5%96%E5%BE%81%E6%96%87%EF%BD%9C%E5%8F%88%E6%8B%8D%E4%BA%91%E5%8E%9F%E5%88%9B%E6%8A%80%E6%9C%AF%E5%BE%81%E6%96%87%E5%A4%A7%E8%B5%9B%EF%BC%8CFILCO%E9%94%AE%E7%9B%98%E3%80%81%E5%B0%8F%E7%B1%B3%E6%89%8B%E7%8E%AF%E3%80%81%E4%BB%A3%E9%87%91%E5%88%B8%E7%AD%89%E4%BD%A0%E6%9D%A5%E6%8B%BF.html) [地址二](https://mp.weixin.qq.com/s/NmK93WxEZ02b9saND0OAsg)

## 0. 从静态托管的jekyll静态网站说起

目前很多网站都提供了jekyll网站的托管服务，比如最知名的 [GitHub](https://github.com/)，还有 [GitLab](https://gitlab.com/)，以及国内的 [腾讯云 - Coding](https://coding.net/)、[开源中国 - 码云gitee](https://gitee.com/) 都可以部署jekyll静态网站。

相比之下国外的GitHub服务比较稳定，GitLab我很少用不太了解，但是访问速度就很慢了。国内的码云和Coding目前来看也是越来越稳定的，但是仍然有时候访问比较慢。

<!--more-->

由于GitHub本身访问比较慢，所以我把代码仓库建在了Coding上，使用Coding的静态网站托管服务。

![16-12-48-截屏2020-05-16下午12.46.54-g0YrF8](https://up-img.yonghong.tech/pic/2020/05/16-12-48-截屏2020-05-16%20下午12.46.54-g0YrF8.png)

![16-12-48-截屏2020-05-16下午12.47.12-zUmXVP](https://up-img.yonghong.tech/pic/2020/05/16-12-48-截屏2020-05-16%20下午12.47.12-zUmXVP.png)

设置好之后每次push代码就会部署

![16-12-48-截屏2020-05-16下午12.47.34-mGrrxm](https://up-img.yonghong.tech/pic/2020/05/16-12-48-截屏2020-05-16%20下午12.47.34-mGrrxm.png)

## 1. 静态资源的处理——uPic

代码仓库本身不适合存储大文件，而且在写文章的时候，也不太好管理图片，试想一下一篇文章中有大量的截图，需要手动把图片放到指定的文件夹，再把文件的地址拼接好，那也太慢了。

而且图片资源push到GitHub或者Coding上，或者从GitHub或者Coding上的静态网站加载，那都是很慢的。

所以我推荐使用 [uPic](https://github.com/gee1k/uPic) 来上传图片文件，uPic(upload Picture) 是一款 Mac 端的图床(文件)上传客户端。

💡 特点： 无论是本地文件、或者屏幕截图都可自动上传，菜单栏显示实时上传进度。上传完成后文件链接自动复制到剪切板，让你无论是在写博客、灌水聊天都能快速插入图片。 连接格式可以是普通 URL、HTML 或者 Markdown，仍由你掌控。

**🔋 支持图床：** [smms](https://sm.ms/)、 [又拍云 USS](https://www.upyun.com/products/file-storage)、[七牛云 KODO](https://www.qiniu.com/products/kodo)、 [阿里云 OSS](https://www.aliyun.com/product/oss/)、 [腾讯云 COS](https://cloud.tencent.com/product/cos)、 [百度云 BOS](https://cloud.baidu.com/product/bos.html)、[微博](https://weibo.com/)、[Github](https://github.com/settings/tokens)、 [Gitee](https://gitee.com/profile/personal_access_tokens)、 [Amazon S3](https://aws.amazon.com/cn/s3/)、[Imgur](https://imgur.com/)、[自定义上传接口](https://blog.svend.cc/upic/tutorials/custom)、...

### 🚀 如何安装

#### 1.Homebrew(推荐):
```
brew cask install upic
```
#### 2.手动
从 [Github release](https://github.com/gee1k/uPic/releases) 下载。

**如果在国内访问 Github 下载困难的，可以从[Gitee release](https://gitee.com/gee1k/uPic/releases)下载。**

### 📂 检查 Finder 扩展权限

- 1.打开 uPic

- 2.打开`系统偏好设置` - `扩展` - `访达扩展` 确保 `uPicFinderExtension`是勾选状态

  <center>
    <img src="https://up-img.yonghong.tech/pic/2020/05/16-12-55-bOylqI-HR6y3e.jpg" height="300">
  </center>

### 🕹 使用方式


| 功能 | 描述 | 预览 |
| --- | --- | --- |
| **🖥 选择文件上传** | 从`Finder`选择文件上传。`可设置全局快捷键` | ![16-12-56-oz1R9w-YVYrwk](https://up-img.yonghong.tech/pic/2020/05/16-12-56-oz1R9w-YVYrwk.jpg) |
| **⌨️ 复制文件上传** | 上传已拷贝到剪切板的文件。`可设置全局快捷键` | ![16-12-56-li6rwd-fpcp6w](https://up-img.yonghong.tech/pic/2020/05/16-12-56-li6rwd-fpcp6w.jpg) |
| **📸 截图上传** | 直接拉框截图上传。`可设置全局快捷键` | ![16-12-57-rjrfno-QePiPw](https://up-img.yonghong.tech/pic/2020/05/16-12-57-rjrfno-QePiPw.jpg) |
| **🖱 拖拽本地文件上传** | 拖拽文件到状态栏上传 | ![16-12-57-KZdZIh-6DSpYG](https://up-img.yonghong.tech/pic/2020/05/16-12-57-KZdZIh-6DSpYG.jpg) |
| **🖱 拖拽浏览器图片上传** | 从浏览器拖拽图片到状态栏上传 | ![16-12-57-mcK1XR-EG6e7M](https://up-img.yonghong.tech/pic/2020/05/16-12-57-mcK1XR-EG6e7M.jpg) |
| **📂 Finder 中右键上传** | 右击文件上传 | ![16-12-57-yVDy8C-06otTH](https://up-img.yonghong.tech/pic/2020/05/16-12-57-yVDy8C-06otTH.gif) |
| **⌨️ 命令行上传** | 通过执行命令调用 uPic 上传文件 | ![16-12-57-Absy9T-qsQiBj](https://up-img.yonghong.tech/pic/2020/05/16-12-57-Absy9T-qsQiBj.jpg) |

![又拍云配置](https://up-img.yonghong.tech/pic/2020/05/16-13-01-upyun-host-MwBLPJ.png)

### 📝 又拍云配置项说明

这个静态资源使用的是又拍云的[云存储 USS 服务](https://www.upyun.com/products/file-storage)。

- `空间名称`: 对象储存空间名称，可在又拍云控制台查看。
- `操作员`: 当前空间授权过的操作员。
- `操作员密码`: 对应的操作员密码。
- `域名`: 使用又拍云默认提供的测试域名或者你的自定义域名。测试域名可在控制台查看。`域名需以http://或者https://开头`。
- `保存路径`: 文件储存的路径（包括文件夹）。 `支持 {year} {month} {day} {hour} {minute} {second} {since_second} {since_millisecond} {random} {filename} {.suffix} 等变量。比如：上传的图片为 uPic.jpg，设定为 “uPic/{filename}{.suffix}”，则会保存到 “uPic/uPic.jpg”。`
- 在`保存路径`输入框后面的是`网址后缀`: 用于自定义图片处理。在又拍云对象储存中可以配置`图片处理-自定义版本`。例如：规则名称为`w`的规则来标识水印版本，分隔符为`!`，则可以在网址后缀中填写`!w`。之后每次上传的图片生成连接后面都会追加上`-w`，即表示访问水印版本。

### 🧰 空间名称、域名信息获取

**进入 [云存储](https://console.upyun.com/services/file/) 控制台查看**
![又拍云控制台](https://up-img.yonghong.tech/pic/2020/05/16-13-01-upyun-info-kWEXyr.png)



### 🔑 操作人员配置

![操作人员配置](https://up-img.yonghong.tech/pic/2020/05/16-13-01-upyun-operator-HWWbXt.png)


## 3. 全站加速

下面来解决Coding时不时访问不了的问题。

全站加速使用的是又拍云的[云分发 CDN 服务](https://www.upyun.com/products/cdn)。

1.在又拍云的控制台中创建一个新的 CDN 服务。

- 服务名称：随便填
- 加速域名：最终访问的网址
- 应用场景：全站加速
- 源站设置：coding托管的网址，可以用自己的域名
- 加速区域：可以选全球加速或者是国内加速

![16-13-17-截屏2020-05-16下午1.16.18-TZf3rY](https://up-img.yonghong.tech/pic/2020/05/16-13-17-截屏2020-05-16%20下午1.16.18-TZf3rY.png)

2.配置CNAME

![16-13-21-截屏2020-05-16下午1.16.28-pyxHs4](https://up-img.yonghong.tech/pic/2020/05/16-13-21-截屏2020-05-16%20下午1.16.28-pyxHs4.png)

3.配置回源host

回源HOST指CDN节点在回源过程中，在源站访问的站点域名。当您的源站有多个业务共用的情况时，可以通过用户回源请求里面携带的回源HOST来区分不同的业务。

> 说明: 如果您的源站绑定了多个域名或站点，则您需要在自定义域名中，指定具体域名，否则回源会失败。

源站和回源HOST的区别：
- 源站：源站决定了回源时请求到的具体IP地址。
- 回源HOST：回源HOST决定了回源请求访问到该IP地址上的具体站点。

![16-13-21-截屏2020-05-16下午1.17.16-HquEZz](https://up-img.yonghong.tech/pic/2020/05/16-13-21-截屏2020-05-16%20下午1.17.16-HquEZz.png)


## 4. 又拍云的细节配置

### 针对CDN

#### 设置缓存规则

缓存规则可以设置成首页 1小时，目录页 1天，当然你也可以自己去设定合适的缓存规则。

![16-13-25-截屏2020-05-16下午1.23.55-NHbTj3](https://up-img.yonghong.tech/pic/2020/05/16-13-25-截屏2020-05-16%20下午1.23.55-NHbTj3.png)

### 云存储和CDN

#### 设置HTTPS，开启 TLS1.3、HTTP/2

又拍云可以免费申请域名证书。

![16-13-26-截屏2020-05-16下午1.24.35-TlTgnk](https://up-img.yonghong.tech/pic/2020/05/16-13-26-截屏2020-05-16%20下午1.24.35-TlTgnk.png)

#### 设置WebP自适应

![16-13-28-截屏2020-05-16下午1.24.58-zMxFmh](https://up-img.yonghong.tech/pic/2020/05/16-13-28-截屏2020-05-16%20下午1.24.58-zMxFmh.png)

## 5. 又拍云联盟

拍云推出的开发者帮助计划：为开发者提供专业、免费、稳定的 CDN 及云存储服务，加速个人网站及 APP 等项目

又拍云联盟用户每月独享优惠：加入又拍云联盟，按步骤完成申请即可获得：10GB 免费存储空间 + 15GB 免费 CDN 流量(HTTP/HTTPS 均可用)

审核通过后又拍云联盟将一次性赠送 12 个月的云服务资源，并折算成代金券发放到您的账户，福利次年自动赠送

[加入又拍云联盟 —— 地址直达](https://www.upyun.com/league)

![16-13-33-截屏2020-05-16下午1.32.29-ed5kcN](https://up-img.yonghong.tech/pic/2020/05/16-13-33-截屏2020-05-16%20下午1.32.29-ed5kcN.png)

![16-13-33-截屏2020-05-16下午1.32.40-opKpM5](https://up-img.yonghong.tech/pic/2020/05/16-13-33-截屏2020-05-16%20下午1.32.40-opKpM5.png)

![16-13-33-截屏2020-05-16下午1.32.50-Z2W928](https://up-img.yonghong.tech/pic/2020/05/16-13-33-截屏2020-05-16%20下午1.32.50-Z2W928.png)



