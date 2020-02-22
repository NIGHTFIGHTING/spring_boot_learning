##一、本课程目标
学习springboot日志的框架，学完后会设置日志级别，设置日志的存储路径，设置日志的格式等

##二、剖析springboot的日志框架
slf4j
logback、log4j
从springboot的底层框架spring-boot-starter-logging可以看出，它依赖了3个框架而别为：slf4j、logback、log4j

###分析1：slf4j、logback、log4j的区别
1.logback、log4j：是日志实现框架，就是实现怎么记录日志的
2.slf4j：提供了java中所有的日志框架的简单抽象（日志的门面设计模式），说白了就是一个日志API(没有实现类)，它不能单独使用
故：必须结合logback或log4j日志框架来实现。

###分析2：sprintboot的日志搭配
sprintboot2.0默认采用slf4f+logback的日志搭配
在开发过程中，我们都是采用了slf4j的api去记录日志，底层的实现就是根据配置logback或log4j日志框架

##为什么控制台的日志指输出了 info warn error？
因为springboot默认是jinfo级别的
```
logging.level.com.agan.boot=trace  
```                                              