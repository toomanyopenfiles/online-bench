# online-bench 简介

online-bench是一个高性能、分布式的企业级线上引流压测平台，它能够方便的将线上服务的流量引流到压测集群，并具备高度可扩展性。引流方面，相比tcpcopy，它更加便于部署和控制流量。压测方面，相比jmeter/http_load等单机版压测工具，online-bench是一个分布式压测平台，压测集群可以方便的水平伸缩。压测数据的收集支持open-falcon和jmeter jtl，可以通过open-falcon或jmeter图形化查看压测结果。

## 社区：
- QQ群：287987089

## 主要功能：
- 简单、可配置的压测界面
	- 主控机web界面支持灵活控制线上服务节点的流量录制开关、录制规则等	
	- 主控机web界面配置压测任务，下发任务到起压机
	- 主控机web界面支持灵活启动、关停、增减压测机
	- 方便的查看压测任务的QPS及压测状态
- 清晰的图表能够反映压测的各项结果指标
	- 压测的qps/rt/sla信息自动上报给open-falcon
	- 可以通过open-falcon采集起压机/目标机的更多系统负载信息以定位压测瓶颈
	- 支持jtl文件导出，可以通过jmeter查看集群压测结果
- 压测来源可定制，例如压测文件、线上引流等
	- 可以对引流数据进行动态内容替换或过滤，可以对引流进行流控
	- 引流数据/压测文件 写入redis list，起压机将内容替换或过滤后进行压测
- 压测框架方便扩展及定制
	- 线上流量录制模块，总控模块、起压模块都通过restful API进行通讯，每个模块可以根据需求情况定制开发甚至替换

## 系统架构：

![alt text](https://raw.githubusercontent.com/toomanyopenfiles/online-bench/master/docs/arch.png "architecture")

