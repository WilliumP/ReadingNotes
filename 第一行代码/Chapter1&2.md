# Chapter 1 概述
1、Android大致分为四层架构：**Linux内核层、系统运行库层、应用框架层、应用层**。

2、Android系统四大组件：活动、服务、广播接收器、内容提供器。

3、使用Log而不是System.out，因为System.out日志级别不区分、不能加过滤器等。Log日志级别：verbose, debug, info, warn, error.

# Chapter 2 活动（重点）
1、所有活动都要在AndroidManifest.xml文件中注册才能生效。

2、Toast将短小的信息通知给用户，一段时间后会消失。

3、Intent是各组件之间交互的一种方式，可以指明当前组件要执行的动作以及组件之间传递数据。用法分为显式Intent和隐式Intent


