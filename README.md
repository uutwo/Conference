﻿Conference
==========

A conference example to explain how to use enode to develop ddd+cqrs+event sourcing style application.  

本项目是展示如何使用ENode开发基于DDD,CQRS,ES架构的应用程序。  

共分为三个Bounded Context：  
1.ConferenceManagement，负责会议位置后台管理  
2.Registration，负责处理用户下单  
3.Payments，负责处理支付  

运行步骤：  
1.新建一个数据库Conference，执行Scripts目录下的CreateConferenceTables脚本，创建该数据库中的相关表；  
2.新建一个数据库Conference_ENode，执行Scripts目录下的CreateENodeTables脚本，创建该数据库中的相关表；  
3.修改Hosts目录下每个顶层宿主工程里的App.config或Web.config里的数据库连接字符串，确保数据库连接是正确的；  
4.逐个启动所有的宿主工程，启动顺序可以如下：  
1）Conference.MessageNameServer
2）Conference.MessageBroker  
3）ConferenceManagement.ProcessorHost  
4）Payments.ProcessorHost  
5）Registration.ProcessorHost  
6）ConferenceManagement.Web  
7）Registration.Web  

OK，到这里，整个案例运行就完成了。
第一步，先在ConferenceManagement.Web网站的首页上点击Create Conference按钮创建第一个Conference，创建成功后，才能通过Login按钮登录访问管理你之前创建的Conference哦。
