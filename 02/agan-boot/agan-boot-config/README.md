##一、本课程目标
在前面《SpringBoot的入门例子》的课程基础上，我们继续来讲解springboot常用配置
 即讲解resources包下的application.properties如何使用

##二、最常用的配置1：改端口
在application.properties文件修改
```$xslt
server.port=9090
```

##三、最常用的配置2：改随机端口
思考问题：固定端口为什么不能用？为什么要改随机端口
1.如果在用一台机器上，多个服务如果用一个端口会造成端口冲突
2.在现实的微服务(springcloud、dubbo)开发中，开发人员是不需要记住ip和端口的
故，我们一般在真实开发环境下，是设置一个随机端口，就不用管理端口了，也不会造成端口冲突
```$xslt
server.port=${random.int{1024,9999}}
```