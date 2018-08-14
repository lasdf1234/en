# Basic Infrastructure
消息队列 JCQ的集群结构，同步写入三副本备份，保证服务的高可靠性和高可用性，自主研发的的框架保证服务的高性能，来满足不同业务的需求。
The cluster structure of MQ synchronizes writing three copies of backup, ensures high reliability and high availability of the service. The framework of independent research ensures the high performance of services to meet the needs of different businesses.

## Service Structure
The service structure is as follows:
![Service Structure](https://github.com/jdcloudcom/en/blob/ancuihong/image/MQ/%E5%9F%BA%E7%A1%80%E6%9E%B6%E6%9E%84-en.png)

| Term | Description |
| :- | :- |
| Broker Group | Broker Group is the core component of MQ, which is responsible for message storage, subscription management, consumption management, and data statistics. |	
| Meta Manager Cluster | The core components of MQ are responsible for message route, authorization, and control events. 消息队列 JCQ核心组件，负责消息路由、授权、控制事务等功能 |
| 控制服务 Control Service | Deal with the request tasks from users and back-ends, the tasks include creating, deleting, searching, modifying configuration, and resetting consumer offset.处理来自用户和后端的请求任务，主要有创建、删除、查询、配置修改、重置消费位点等任务 |
| 监控服务 Monitoring Service | Gather the information of JCQ Topic and Consumer Group for users and console display 收集消息队列 JCQ Topic和Consumer Group的信息，供用户和控制台展现 |
| 日志服务 Logs Service | Gather the log information of MQ. 收集消息队列 JCQ日志信息 |
| 计费服务 Billing Service | Responsible for calculating user's request amount. 负责统计用户的请求量计算费用 |


## 相关参考

- [Benefits](../Introduction/Benefits.md)
- [Functions](../Introduction/Functions.md)
- [Price Overview](../Pricing/Price-Overview.md)
- [Billing Rules](../Pricing/Billing-Rules.md)
- [Create an Instance](../Getting-Started/Create-Instance.md)

