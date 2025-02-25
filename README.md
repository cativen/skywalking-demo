## [Skywalking](https://zhida.zhihu.com/search?content_id=240567513&content_type=Article&match_order=1&q=Skywalking&zhida_source=entity)基础入门

Skywalking是分布式系统的应用程序性能监视工具，专为微服务，云原生架构和基于容器（Docker，K8S,Mesos）架构而设计，它是一款优秀的APM（Application Performance Management）工具，包括了[分布式追踪](https://zhida.zhihu.com/search?content_id=240567513&content_type=Article&match_order=1&q=分布式追踪&zhida_source=entity)，[性能指标分析](https://zhida.zhihu.com/search?content_id=240567513&content_type=Article&match_order=1&q=性能指标分析&zhida_source=entity)和[服务依赖分析](https://zhida.zhihu.com/search?content_id=240567513&content_type=Article&match_order=1&q=服务依赖分析&zhida_source=entity)等。

### 简介

Skywalking是一个国产的开源框架，2015年有吴晟个人开源，2017年加入Apache孵化器，国人开源的产品，主要开发人员来自于华为，2019年4月17日Apache董事会批准SkyWalking成为顶级项目，支持Java、.Net、NodeJs等[探针](https://zhida.zhihu.com/search?content_id=240567513&content_type=Article&match_order=1&q=探针&zhida_source=entity)，数据[存储](https://zhida.zhihu.com/search?content_id=240567513&content_type=Article&match_order=1&q=存储&zhida_source=entity)支持Mysql、Elasticsearch等，跟Pinpoint一样采用[字节码注入](https://zhida.zhihu.com/search?content_id=240567513&content_type=Article&match_order=1&q=字节码注入&zhida_source=entity)的方式实现代码的无侵入，探针采集数据粒度粗，但性能表现优秀，且对云原生支持，目前增长势头强劲，社区活跃。

Skywalking是分布式系统的应用程序性能监视工具，专为微服务，云原生架构和基于容器（Docker，K8S,Mesos）架构而设计，它是一款优秀的APM（Application Performance Management）工具，包括了分布式追踪，性能指标分析和服务依赖分析等。

### 核心功能

SkyWalking是一个开源的应用性能监控（APM）系统，用于监控和管理分布式系统的性能。它提供了实时的性能指标、事务追踪、服务依赖分析等功能，帮助开发人员和运维团队快速定位和解决性能问题。

SkyWalking的核心功能包括：

分布式追踪：SkyWalking可以追踪分布式系统中的请求流程，记录每个请求经过的服务和组件，以及请求在每个组件中的耗时情况。通过分析追踪数据，可以了解系统中各个组件之间的调用关系和性能瓶颈，帮助开发人员快速定位和解决问题。

实时监控：SkyWalking提供实时的性能监控指标，包括各个服务的请求量、响应时间、错误率等。通过监控数据，可以及时发现系统的性能问题，并进行调优和优化。

服务依赖分析：SkyWalking可以分析系统中各个服务之间的依赖关系，包括调用关系和数据流向。通过可视化的方式展示服务之间的依赖关系，可以帮助开发人员理解系统的架构和流程，从而更好地进行系统设计和优化。

告警和报警：SkyWalking可以设置各种告警规则，当系统出现异常或性能下降时，可以及时发送告警通知。这样可以帮助运维人员快速响应和解决问题，保证系统的稳定性和可靠性。

数据可视化：SkyWalking提供丰富的数据可视化功能，可以将监控数据以图表的形式展示，帮助用户更直观地了解系统的性能和运行情况。同时，还可以根据需求自定义仪表盘，将关键指标集中展示，方便用户监控和管理系统。

- 服务、服务实例、端点指标分析
- 根本原因分析。在运行时分析代码
- 服务拓扑图分析
- 服务、服务实例和端点依赖分析
- 缓慢的服务和端点检测
- 性能优化
- 分布式跟踪和上下文传播
- 数据库访问指标。检测慢速数据库访问语句（包括SQL语句）
- 消息队列性能和消耗延迟监控
- 警报
- 浏览器性能监控
- 基础设施（VM、网络、磁盘等）监控
- 跨指标、跟踪和日志的协作 Skywalking 支持多种语言和框架，包括 Java、Go、Node.js 和 Python。它使用分布式追踪技术来监控应用程序内部和外部的所有调用，从而获得关于应用程序性能的完整见解。

### 如何使用

1、到官网下载https://archive.apache.org/dist/skywalking/，适合自己的版本

2、解压打开，以`apache-skywalking-apm-es7-8.5.0.tar.gz`为例

![image-20250225164302705](https://codegym.oss-cn-shenzhen.aliyuncs.com/uiiujhj/202502251643365.png)

其中`agent`文件夹下面的`skywalking-agent.jar`文件就是skywalking的探针

![image-20250225164430473](https://codegym.oss-cn-shenzhen.aliyuncs.com/uiiujhj/202502251644006.png)

`bin`下面的`startup.bat`可以为windows启动



![image-20250225164548915](https://codegym.oss-cn-shenzhen.aliyuncs.com/uiiujhj/202502251645601.png)

config下面的application.yml文件，就是关于skywalking的基础配置信息



![image-20250225164651504](https://codegym.oss-cn-shenzhen.aliyuncs.com/uiiujhj/202502251646918.png)

`log`文件夹下面的都是skywalking的启动过程的所有日志信息



![image-20250225164734998](https://codegym.oss-cn-shenzhen.aliyuncs.com/uiiujhj/202502251647545.png)

`oap-libs`代表的是本地依赖的jar包

![image-20250225164822571](https://codegym.oss-cn-shenzhen.aliyuncs.com/uiiujhj/202502251648188.png)

`webapp`文件夹下面的webapp.yml文件可以修改skywalking的ui页面启动端口和路径等



https://zhuanlan.zhihu.com/p/710425701，这个是skywalking的ui界面介绍



### 接入微服务

需要在每个服务的vm中配置

```bash
-javaagent:D:\soft\apache-skywalking-apm-es7-8.5.0\apache-skywalking-apm-bin-es7\agent\skywalking-agent.jar -DSW_AGENT_NAME=xiaozhou-order -DSW_AGENT_COLLECTOR_BACKEND_SERVICES=127.0.0.1:11800
```



启动之后，skywalking就会自动探针到每个服务的情况

![image-20250225165146047](https://codegym.oss-cn-shenzhen.aliyuncs.com/uiiujhj/202502251651607.png)



### mysql持久化

![image-20250225165334474](https://codegym.oss-cn-shenzhen.aliyuncs.com/uiiujhj/202502251653907.png)

在`oap-libs`下面加入mysql的驱动

![image-20250225165453098](https://codegym.oss-cn-shenzhen.aliyuncs.com/uiiujhj/202502251654574.png)

把`application.yml`文件修改成

![image-20250225165533428](https://codegym.oss-cn-shenzhen.aliyuncs.com/uiiujhj/202502251655836.png)

再重启skywalking，这时skywalking会自动在mysql创建数据库表，并把收集到的信息存入mysql



### 自定义链路追踪

引入依赖

```
		<dependency>
			<groupId>org.apache.skywalking</groupId>
			<artifactId>apm-toolkit-trace</artifactId>
			<version>8.5.0</version>
		</dependency>
```

使用@Trace注解，可以记录方法的链路情况

@Tag注解，代表收集的key，和返回值

![image-20250225165841221](https://codegym.oss-cn-shenzhen.aliyuncs.com/uiiujhj/202502251658744.png)

![image-20250225165954936](https://codegym.oss-cn-shenzhen.aliyuncs.com/uiiujhj/202502251659976.png)

### 性能剖析

![image-20250225170121693](https://codegym.oss-cn-shenzhen.aliyuncs.com/uiiujhj/202502251701854.png)

新建任务之后，就会对对应的路径和服务进行追踪，假设性能过慢的话，会被记录下来，且可以进行分析

![image-20250225170237827](https://codegym.oss-cn-shenzhen.aliyuncs.com/uiiujhj/202502251702322.png)

![image-20250225170255298](https://codegym.oss-cn-shenzhen.aliyuncs.com/uiiujhj/202502251702077.png)

### 日志

logback-spring.xml

```bash
<?xml version="1.0" encoding="UTF-8"?>
<configuration>
    <!-- 引入 Spring Boot 默认的 logback XML 配置文件  -->
    <include resource="org/springframework/boot/logging/logback/defaults.xml"/>

    <!-- 控制台 Appender -->
    <property name="CONSOLE_LOG_PATTERN" value="%clr(%d{${LOG_DATEFORMAT_PATTERN:-yyyy-MM-dd HH:mm:ss.SSS}}){faint} %clr(${LOG_LEVEL_PATTERN:-%5p}) %clr(${PID:- }){magenta} %tid %clr(---){faint} %clr([%15.15t]){faint} %clr(%-40.40logger{39}){cyan} %clr(:){faint} %m%n${LOG_EXCEPTION_CONVERSION_WORD:-%wEx}"/>
    <appender name="console" class="ch.qos.logback.core.ConsoleAppender">
        <!-- 日志的格式化 -->
        <encoder class="ch.qos.logback.core.encoder.LayoutWrappingEncoder">
            <layout class="org.apache.skywalking.apm.toolkit.log.logback.v1.x.TraceIdPatternLogbackLayout">
                <Pattern>${CONSOLE_LOG_PATTERN}</Pattern>
            </layout>
        </encoder>
    </appender>


    <appender name="grpc-log" class="org.apache.skywalking.apm.toolkit.log.logback.v1.x.log.GRPCLogClientAppender">
        <encoder class="ch.qos.logback.core.encoder.LayoutWrappingEncoder">
            <layout class="org.apache.skywalking.apm.toolkit.log.logback.v1.x.mdc.TraceIdMDCPatternLogbackLayout">
                <Pattern>%d{yyyy-MM-dd HH:mm:ss.SSS} [%X{tid}] [%thread] %-5level %logger{36} -%msg%n</Pattern>
            </layout>
        </encoder>
    </appender>


    <!-- 设置 Appender -->
    <root level="INFO">
        <appender-ref ref="console"/>
        <appender-ref ref="grpc-log"/>
    </root>

</configuration>

```



引入skywalking的日志依赖

```
		<dependency>
			<groupId>org.apache.skywalking</groupId>
			<artifactId>apm-toolkit-logback-1.x</artifactId>
			<version>8.5.0</version>
		</dependency>
```



![image-20250225170451253](https://codegym.oss-cn-shenzhen.aliyuncs.com/uiiujhj/202502251704276.png)



### 告警

假设调用的接口响应比较的慢的情况下，就会有告警信息

![image-20250225170516828](https://codegym.oss-cn-shenzhen.aliyuncs.com/uiiujhj/202502251705077.png)

其中config下面的`alarm-settings.yml`文件是关于告警的配置，在这里我们是可以配置告警回调的，例如当服务和接口响应异常的情况下，我们可以通过告警发送到邮箱或者钉钉上

![image-20250225170623123](upload%5Cimage-20250225170623123.png)

![image-20250225170756513](https://codegym.oss-cn-shenzhen.aliyuncs.com/uiiujhj/202502251707871.png)

```
package com.xiaozhou.xiaozhouproduct.controller;

import org.springframework.web.bind.annotation.RequestBody;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.RestController;

@RestController
@RequestMapping("/sw/alarm")
public class SkywalkingAlarmController {

    /**
     * Skywalking告警通知回调接口：http://127.0.0.1:18081/sw/alarm/notify/
     *
     * @param obj
     * @return
     */
    @RequestMapping("/notify")
    public String notify(@RequestBody Object obj) {
        // TODO 将告警信息通知给负责人。比如：通过发短信，钉钉消息，邮件，微信通知等方式发送给技术负责人
        System.err.println("收到Skywalking告警信息：" + obj.toString());
        return "notify successfully";
    }

}
```

项目的参考地址：

```
https://github.com/cativen/skywalking-demo
```



