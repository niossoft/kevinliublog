---
author: "Kevin Liu"
title: "The SpringBoot Starters Conflict in pom.xml"
date: 2022-04-13T20:08:06+09:00
description: "facing issue about JPA HikariPool Shutdown completed in intellij configuration"
draft: false
hideToc: false
enableToc: true
enableTocContent: false
author: Kevin Liu
authorEmoji: 👻
tags: 
- spring-boot
- conflict
- pom
image: images/logo/spring-icon-svgrepo-com.svg
---

To open eclipse project in the **Intellij** IDE, I'm getting no-error when trying to Build it up. But when I am trying run using **Maven** to run this project start getting message below.
> Closing JPA EntityManagerFactory for persistence unit 'default' HikariPool-1 - Shutdown initiated, HikariPool-1 - Shutdown completed

I find the solution on stackoverflow.

Maybe you can check your pom.xml, if it contains **BOTH** the spring-boot-starter-web and spring-boot-starter-tomcat dependencies. This is redundant as the former has a default embedded tomcat. e.g.

{{< highlight html >}}
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-web</artifactId>
</dependency>
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-tomcat</artifactId>
</dependency>
{{< /highlight >}}

***

Read more here on stackoverflow: 
[spring-boot-starter-tomcat vs spring-boot-starter-web](https://stackoverflow.com/questions/33419823/spring-boot-starter-tomcat-vs-spring-boot-starter-web)
