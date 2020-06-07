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

## 开始

新创建一个 Springboot 项目，只引入 Spring Web 和 Spring Security。项目创建成功后，Spring Security 的依赖就添加进来了，在 build.gradle 中引入的是 spring-boot-starter-security。

```gradle
    implementation 'org.springframework.boot:spring-boot-starter-security'
    implementation 'org.springframework.boot:spring-boot-starter-web'
```

最终的依赖是下面这两个：

![03-15-02-pzRDJb-CjWcsD](https://up-img.yonghong.tech/pic/2020/06/03-15-02-pzRDJb-CjWcsD.png)

我们写一个 RestController

```java
// HelloController.java
import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.RestController;

@RestController
public class HelloController {

    @GetMapping("/hello")
    public String hello() {
        return "hello, spring security!";
    }
}
```

然后启动项目，访问 [http://127.0.0.1:8080/hello/](http://127.0.0.1:8080/hello/) 会跳转到登录界面

![03-15-12-tniWpM-KPVVyZ](https://up-img.yonghong.tech/pic/2020/06/03-15-12-tniWpM-KPVVyZ.png)

我们看控制台的输出

```
  .   ____          _            __ _ _
 /\\ / ___'_ __ _ _(_)_ __  __ _ \ \ \ \
( ( )\___ | '_ | '_| | '_ \/ _` | \ \ \ \
 \\/  ___)| |_)| | | | | || (_| |  ) ) ) )
  '  |____| .__|_| |_|_| |_\__, | / / / /
 =========|_|==============|___/=/_/_/_/
 :: Spring Boot ::        (v2.3.0.RELEASE)

2020-06-03 15:08:44.383  INFO 10069 --- [           main] m.y.s.s.SecurityStartApplication         : Starting SecurityStartApplication on monster with PID 10069 (/Users/yonghong/spring-lab/security-start/build/classes/java/main started by yonghong in /Users/yonghong/spring-lab/security-start)
2020-06-03 15:08:44.385  INFO 10069 --- [           main] m.y.s.s.SecurityStartApplication         : No active profile set, falling back to default profiles: default
2020-06-03 15:08:45.282  INFO 10069 --- [           main] o.s.b.w.embedded.tomcat.TomcatWebServer  : Tomcat initialized with port(s): 8080 (http)
2020-06-03 15:08:45.292  INFO 10069 --- [           main] o.apache.catalina.core.StandardService   : Starting service [Tomcat]
2020-06-03 15:08:45.293  INFO 10069 --- [           main] org.apache.catalina.core.StandardEngine  : Starting Servlet engine: [Apache Tomcat/9.0.35]
2020-06-03 15:08:45.379  INFO 10069 --- [           main] o.a.c.c.C.[Tomcat].[localhost].[/]       : Initializing Spring embedded WebApplicationContext
2020-06-03 15:08:45.379  INFO 10069 --- [           main] o.s.web.context.ContextLoader            : Root WebApplicationContext: initialization completed in 952 ms
2020-06-03 15:08:45.645  INFO 10069 --- [           main] o.s.s.concurrent.ThreadPoolTaskExecutor  : Initializing ExecutorService 'applicationTaskExecutor'
2020-06-03 15:08:45.862  INFO 10069 --- [           main] .s.s.UserDetailsServiceAutoConfiguration : 

Using generated security password: b78f65c5-07be-48cb-a68b-8e190c325612

2020-06-03 15:08:45.948  INFO 10069 --- [           main] o.s.s.web.DefaultSecurityFilterChain     : Creating filter chain: any request, [org.springframework.security.web.context.request.async.WebAsyncManagerIntegrationFilter@68699afc, org.springframework.security.web.context.SecurityContextPersistenceFilter@3d0cac1f, org.springframework.security.web.header.HeaderWriterFilter@3c66b7d8, org.springframework.security.web.csrf.CsrfFilter@705a8dbc, org.springframework.security.web.authentication.logout.LogoutFilter@1b13467c, org.springframework.security.web.authentication.UsernamePasswordAuthenticationFilter@6e03db1f, org.springframework.security.web.authentication.ui.DefaultLoginPageGeneratingFilter@3ba348ca, org.springframework.security.web.authentication.ui.DefaultLogoutPageGeneratingFilter@273a5a8a, org.springframework.security.web.authentication.www.BasicAuthenticationFilter@55fee662, org.springframework.security.web.savedrequest.RequestCacheAwareFilter@d257579, org.springframework.security.web.servletapi.SecurityContextHolderAwareRequestFilter@39ffda4a, org.springframework.security.web.authentication.AnonymousAuthenticationFilter@1823b9c4, org.springframework.security.web.session.SessionManagementFilter@5c7dfc05, org.springframework.security.web.access.ExceptionTranslationFilter@60c1663c, org.springframework.security.web.access.intercept.FilterSecurityInterceptor@79d82f66]
2020-06-03 15:08:46.048  INFO 10069 --- [           main] o.s.b.w.embedded.tomcat.TomcatWebServer  : Tomcat started on port(s): 8080 (http) with context path ''
2020-06-03 15:08:46.062  INFO 10069 --- [           main] m.y.s.s.SecurityStartApplication         : Started SecurityStartApplication in 2.044 seconds (JVM running for 3.47)
```

用户名是 `user`，密码是 `b78f65c5-07be-48cb-a68b-8e190c325612`，登录成功。

![03-15-15-37PvNr-JpNl3L](https://up-img.yonghong.tech/pic/2020/06/03-15-15-37PvNr-JpNl3L.png)

## 为什么用户密码是这个？

这是 Spring Security 为默认用户 user 生成的临时密码，是一个 UUID 字符串。

我们找一下用户相关的自动化配置类，在 UserDetailsServiceAutoConfiguration 里边，在该类的 getOrDeducePassword 方法中，我们看到如下一行日志：

```java
package org.springframework.boot.autoconfigure.security.servlet;

public class UserDetailsServiceAutoConfiguration {
    private String getOrDeducePassword(SecurityProperties.User user, PasswordEncoder encoder) {
        String password = user.getPassword();
        if (user.isPasswordGenerated()) {
            logger.info(String.format("%n%nUsing generated security password: %s%n", user.getPassword()));
        }
        if (encoder != null || PASSWORD_ALGORITHM_PATTERN.matcher(password).matches()) {
            return password;
        }
        return NOOP_PASSWORD_PREFIX + password;
    }
}
```

然后再看 SecurityProperties.User 类的定义

```java
package org.springframework.boot.autoconfigure.security;

public static class User {

    /**
     * Default user name.
     */
    private String name = "user";

    /**
     * Password for the default user name.
     */
    private String password = UUID.randomUUID().toString();
    private boolean passwordGenerated = true;

}
```

可以看到，默认的用户名就是 `user`，默认的密码则是 `UUID`，而默认情况下，`passwordGenerated` 也为 `true`。

## 配置默认的用户名和密码

### 使用配置文件

还是和这个类相关 SecurityProperties 

```java
@ConfigurationProperties(prefix = "spring.security")
public class SecurityProperties {
}
```

我们只需要在 application.properties 中配置如下两行，即可覆盖默认的用户名和密码。

```
spring.security.user.name=spring
spring.security.user.password=123
```

此时重启项目，就可以使用自己定义的用户名/密码登录了。

### 使用配置类

