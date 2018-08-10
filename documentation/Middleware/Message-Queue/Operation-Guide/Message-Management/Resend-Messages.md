# Resend Messages(Dead Letter Queue)

在超过最大尝试推送次数后会将消息发送到死信队列。可将其作为无法成功处理 (使用) 的消息的目标的队列。  
可以在死信队列中留出和隔离这些消息以确定其处理失败的原因。区分消息类型(普通、顺序)。可按照Topic和ConsumerGroup ID进行搜索。
## Procedure
1. Enter the "Dead Letter Queue" page.

![死信队列1](https://github.com/jdcloudcom/cn/blob/edit/image/Internet-Middleware/Message-Queue/死信队列-01.png)

2. Input "topic ID" or "ConsumerGroup ID" to search.

3. Resend or delete all the dead letters.
![死信队列2](https://github.com/jdcloudcom/cn/blob/edit/image/Internet-Middleware/Message-Queue/死信队列-02.png)  

You can choose to resend all the dead letters or delete all the dead letters.
- Resend All: Dead letters will reenter the topic and be sent to the subscriber related to the subscription.
- Delete All: Dead letters will be deleted all, and will not be resent.

You can also click "Total Dead Letters" to enter the "Dead Letter Details", and delete or resend single dead letter.
