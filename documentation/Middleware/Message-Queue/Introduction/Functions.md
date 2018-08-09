# Features
## Core Features
### Publishing and Subscription
Producers can create Topic to publish multiple types of messages, and consumers can subscribe Topic for on-demand consumption.
### View Messages
Users can view message status and content through Topic ID and Message ID.
### Dead Letter Queue
You can view and re-consume the consumption messages which are failed to deliver and placed on the dead letter queue.
### Reset Consumer Offset
Reset the message consumption schedule within the duration of the message persistence store (default 3 days).
## Diversity
### General Messages
解决业务间异步解耦，流量的削峰填谷，消息通讯等。

### Scheduled Messages
按照消息的发布顺序进行顺序消费（FIFO）。

### Delayed Messages
在消息发送时间（当前时间）之后的指定延迟时间点进行投递，比如指定消息发送时间的 5 分钟之后进行投递。

## Multi protocol access
### Support HTTP Protocol

Support RESTFul API simple and convenient access.

### Support TCP Protocol

Provide SDK access which is more professional, reliable and stable TCP protocol.

## Easy to Use
### Smooth Extension
支持弹性扩展，可根据业务情况按需增加或者减少资源，提高资源利用率，降低使用成本。

### Easy to Develop
提供 Web端控制台、API 访问接口和 java SDK，开发简单，易于业务支持和业务迁移。

## Safety Precautions
### Overall Monitoring
提供多维度的资源运行状况和性能的监控、稳定性维护等功能，提前预警通知，降低日常维护工作量

### VPC
实例运行在私有网络（VPC）中，增强了安全性和隔离性。提供了子网、访问控制策略等限制访问的功能，抵御网络攻击，保护您的业务隐私
