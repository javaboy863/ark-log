# 1.什么是ark-log？
&emsp;&emsp;ark-leaf是ark系列框架中的日志框架。
# 2.ark-log解决了什么问题？
&emsp;&emsp;日志是发现和定位问题的基础，绝大部分稳定性相关的工作都是在围绕着日志工作进行的。方法的核心出入参，是监控的关键。如果每个业务研发要穿插在业务代码中打印，总是容易遗漏，且侵入性非常强。
因此，我开发了一套日志框架，抽象出日志注解模块，无侵入的打印方法的出入参，请求路径，全链路url，耗时，并可以用作日志分级等。
# 3.使用场景及功能
- a、统一日志格式输出
    - trace id、压测标志，时间，IP地址，线程，请求参数，请求路径，响应时间等业务无关的必要信息，由日志框架层统一解决
    - 统一数仓部门处理日志格式约定
    - 统一前端部门处理日志格式约定
- b、日志文件分级
    - 按日志级别划分文件
    - http 和 dubbo请求单独存放
- c、不侵入业务代码
    - 业务无感知接入日志框架
- d、集成线上异常播报功能，和异常播报服务联动，可在播报菜单里播报出异常链路pinpoint url
- e、全链路ID支持多线程，线程池，spring@Async异步场景
# 4.ark-log组件如何使用？
> 1. 引入jar包
> ```
> <dependency>
>     <groupId>com.ark.log</groupId>
>     <artifactId>ark-log</artifactId>
>     <version>1.1</version>
>     </dependency>
>```
> 2. 配置日志参数
> ```
> #日志文件名称
> ark.log.name=wdshop-new
> #设置日志的root level，默认值：INFO
> ark.log.root.level=INFO
>```
# 4.ark-log 功能截图
http日志输出：<br/>
![http日志输出](https://github.com/javaboy863/ark-log/img/1.png "http日志输出")<br/>
dubbo日志输出：<br/>
![dubbo日志输出](https://github.com/javaboy863/ark-log/img/2.png "dubbo日志输出")<br/>
日志分级：<br/>
![日志分级](https://github.com/javaboy863/ark-log/img/3.png "日志分级")<br/>
error日志输出：<br/>
![error日志输出](https://github.com/javaboy863/ark-log/img/4.png "error日志输出")<br/>
