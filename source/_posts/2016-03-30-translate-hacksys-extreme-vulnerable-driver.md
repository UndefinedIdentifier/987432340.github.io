---
layout: post
title: 一个windows内核漏洞练习驱动
categories: 漏洞利用
date: 2016-03-30
tags: [翻译,漏洞利用]
---

这篇[博客](http://www.payatu.com/hacksys-extreme-vulnerable-driver/)给了一个驱动练习内核溢出的程序。
<!--more-->

# 介绍

**HackSys Extreme Vulnerable Driver**是为了安全爱好者学习、增强内核溢出技术而故意开发的有漏洞的windows驱动程序。

**HackSys Extreme Vulnerable Driver**提供从简单地缓冲区溢出到复杂的UAF以及 Pool Overflows等广阔漏洞范围，这允许安全研究者从所有实现的漏洞去探索溢出技术。

## 什么是HACKSYS EXTREME VULNERABLE DRIVER？

我已经在 [null Security Community’s Pune Chapter](http://null.co.in/profile/411-ashfaq-ansari)谈论过很多关于windows内核溢出技术。所以我认为，最好能写一个包含所有主要漏洞的驱动程序。这个写驱动的想法提供参与者更好地视角去看到在漏洞代码的背后发生了什么，同时在我讨论、练习时会有很大的帮助。

## 实现的漏洞列表

- **Pool Overflow**
- **Use After Free**
- **Type Confusion**
- **Stack Overflow**
- **Integer Overflow**
- **Stack Overflow GS**
- **Arbitrary Overwrite**
- **Null Pointer Dereference**

## 屏幕截图

- 帮助界面

  ![http://www.payatu.com/wp-content/uploads/2015/05/2015-06-03_22h27_24.png](http://www.payatu.com/wp-content/uploads/2015/05/2015-06-03_22h27_24.png)

  ​

- 溢出

  ​

  ![http://www.payatu.com/wp-content/uploads/2015/05/2015-05-27_20h22_35.png](http://www.payatu.com/wp-content/uploads/2015/05/2015-05-27_20h22_35.png)

  ​

- 驱动调试输出

![http://www.payatu.com/wp-content/uploads/2015/05/2015-05-27_20h28_07.png](http://www.payatu.com/wp-content/uploads/2015/05/2015-05-27_20h28_07.png)



- 源代码

源代码在[github](https://github.com/hacksysteam/HackSysExtremeVulnerableDriver)上可以下载

## 支持的windows版本

驱动在 **Windows XP SP3 (x86)**, **Windows 2003 SP3 (x86)** 和**Windows 7 SP1 (x86)**测试成功, 同样支持**Windows 8/8.1 (x86)** . **Windows 8/8.1**尚未测试。



## WHAT ABOUT EXPLOITS?

溢出和这个工程一起提供。溢出在**Windows 7 SP1 (x86)** 被测试通过，同时稍作调整可以支持其他windows系统。



## 编译驱动

1. 安装[WDK](https://www.microsoft.com/en-in/download/details.aspx?id=11800)
2. 改变在Build_HEVD_Secure.bat or Build_HEVD_Vulnerable.bat中的 %localSymbolServerPath%
3. 运行对应的驱动编译脚本 Build_HEVD_Secure.bat或Build_HEVD_Vulnerable.bat



## 安装驱动

使用[OSR Driver Loader](https://www.osronline.com/article.cfm?article=157)安装**HackSys Extreme Vulnerable Driver**





文章后面给了课程链接，我先注册社区，进去发现课程是现实中的沙龙会议那种，感觉写了也没用就省略了。

