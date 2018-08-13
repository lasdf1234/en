# Benefits

## High Availability

集群部署与主从自动切换技术，承诺服务可用性高达 99.95%。
Adopt cluster deployment and primary/secondary automatic switching technology, and the Service Availability Guarantee is up to 99.95%.

## High Reliability

引入Raft 算法实现数据高可靠性，同步写入，三副本数据备份，数据可靠性高达 99.999999%，并且默认消息持久化存储 3 天，支持重置消费位点消费3天之内任何时间点的消息。
Raft algorithm is introduced to achieve high reliability of data, synchronous writing, and three copies of data backup. The data reliability is up to 99.999999%, and the default message persistent storage is 3 days. MQ supports messages of resetting consumer offset at any time within 3 days.

## High Performance

支持每秒千万级的消息收发和推送，无并发限制，海量消息堆积，容量不设上限，消息写入延迟在 10ms 以内。
Supports receiving and sending messages of tens of millions per second, without concurrency restrictions and massive message accumulation, the capacity is unlimited and the message writing delay is within 10 ms.


## Multiple Types

支撑多种消息类型，包括普通消息、顺序消息和延时消息，以满足不同业务情景的需要。
Support a variety of message types, including general messages, scheduled messages, and delayed messages, to meet the needs of different business scenarios.


## Low Cost

为满足业务之间的消息收发需求，Topic数量可弹性扩展，集群规模可弹性扩缩，对用户完全透明，按需收费，提高资源利用率，降低冗余费用。
In order to meet the demand of sending and receiving messages among services, the quantity of Topic can be flexibly scaled, the cluster size can be flexibly scaled, which is transparent to users and charged on demand, improves resource utilization and reduces redundancy costs.

## Convenient Operations

提供多维度的资源运行状况和性能的监控，多终端的预警通知，降低日常维护工作量，提前提示风险、快速定位和解决问题。
Provide multi-dimensional monitoring of resource operation status and performance, and also notification of multi-terminal warning, reduces routine maintenance workload, can point out early warning of risks, position rapidly and solve the problems.
