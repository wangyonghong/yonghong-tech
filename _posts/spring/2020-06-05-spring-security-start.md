---
title: Springboot 系列（1）：Spring Security 入门
key: springboot-1
permalink: /springboot/1/
tags:
- Springboot
- Spring Security
description: Springboot 系列（1）：Spring Security 入门。
---

## Spring Security 是什么？

> Spring Security is a framework that provides authentication, authorization, and protection against common attacks. With first class support for both imperative and reactive applications, it is the de-facto standard for securing Spring-based applications.

> Spring Security 是一个框架，它提供了身份验证、授权和防止常见攻击的保护。它是基于 Spring 的应用程序的安全标准。

## 身份验证和授权（authentication & authorization）

> Spring Security provides comprehensive support for authentication. Authentication is how we verify the identity of who is trying to access a particular resource. A common way to authenticate users is by requiring the user to enter a username and password. Once authentication is performed we know the identity and can perform authorization.

> Spring Security 提供了对身份验证的全面支持。身份验证是我们验证试图访问特定资源的用户身份的方式。验证用户身份的一种常见方法是要求用户输入用户名和密码。身份验证完成后，我们知道了身份，就可以进行授权。

简单来说：
- authentication 验证 - 是指 who you are (你是谁), 所以需要用到 username 和 password 进行身份验证。
- authorization 授权 - 是指 what can you do (你可以做什么), 而且这个发生在验证通过后。比如对资源的访问需要查询权限，对资源的修改则需要修改权限。

<!--more-->

## 
