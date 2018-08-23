# Create Resource
In MQ, the production and consumption of messages need to be in the form of topic subscription, so the user first needs to create a message topic, sends the message to a specified message topic, and the consumer consumes the message by subscribing to the consumer body. 
## Prerequisites
- 已注册京东云账号，并完成实名认证，且保证账户处于正常状态，没有在黑名单中。如果还没有账号请 [注册](https://accounts.jdcloud.com/p/regPage?source=jdcloud&ReturnUrl=%2f%2fuc.jdcloud.com%2fpassport%2fcomplete%3freturnUrl%3dhttp%3A%2F%2Fuc.jdcloud.com%2Fredirect%2FloginRouter%3FreturnUrl%3Dhttps%253A%252F%252Fwww.jdcloud.com%252Fhelp%252Fdetail%252F734%252FisCatalog%252F1)，并 [实名认证](https://uc.jdcloud.com/account/certify)。
- 因为产品的计费类型为按用量计费，请确认您的账户不能处于欠费状态。

## 注意事项
- 公测期间用户最多只能创建5个topics。
- 对于某个topic的订阅Consumer Group数量没有限制。


## Step 1: Create Consumption Topic
1.	Sign in to the JD Cloud console, the menu is “Middleware > MQ > Topic Management”.
2.	Choose the region of creating resources, and then click Create button to create topic. 
3.	You need to fill in Topic Name, Message Type and Remarks during creating topic. 
### Note:
1.	The Topic Name must be globally unique, if a name already exists; you are not able to create a Topic Name any more. The topic only contains letters, numbers, hyphens (-), underscores (_), waveforms (~) or sign (+), and the length is 3~64 characters.
2.	The message type includes unordered messages and global ordered messages. 
•	Unordered Message: It does not guarantee the order consumption of first in first out (FIFO), including general and delayed messages. 
•	Global Ordered Message: The production and consumption of the message is published according to FIFO. 
## Step 2: Add Subscription 
1.	In “Topic Management” page, find the topic you want to subscribe, and you can subscribe in the operations.
2.	To add a subscriber, you need to create / bind an existing Consumer Group ID, select the transport type, and add a tag. 

### Note:
1. The Consumer Group ID must be globally unique. If a name already exists, you are not able to create a Consumer Group ID with that name any more. The Consumer Group ID only contains letters, numbers, hyphens (-), underscores (_), and the length is 7~64 characters.
2. The relationship between Consumer Group ID and topic is N:M; that is the same Consumer Group ID can subscribe multiple topics, and the same topic can be bound with multiple Consumer Group ID.
3. Choose the message type to send, including SDK method and HTTP method.
4. Subscriber tag rules: tag is a message subscriber for message filtering, when the subscriber sets the tag, the same tag message can be consumed by the subscriber, if not set the tag, the subscriber does not filter the message. A single subscriber can add up to five tags, a single tag is a string of no more than 64 characters, separated by a','sign. 

*	For message 1, if there is no message tag and the subscriber has a tag, the subscriber does not match and cannot receive the message. 
*	For message 2, the message has a tag, the subscriber does not have a tag, the message does not need to match when delivered, and the subscriber all can receive the message.
*	For message 3, the message has a tag, when the subscriber has a tag, the two match to receive the message.
*	For Message 4, there is no tag for the message, and no tag for the subscriber. After delivery, all subscribers can receive the message. 

## Step 3: Create AccessKey and SecretKey
When calling the SDK or openAPI of MQ to send, consume, and manage messages, you need to verify the user’s identity information, that is, you need to create AccessKey and SecretKey in the console. 

### Create method:
Apply for AccessKey and SecretKey key pairs (AK / SK for short) on AccessKey management pages under account management of JD Cloud User Center. AK / SK information should be kept properly, if lost, it may lead illegal users to use this information to manipulate your resources in the cloud, cause your data and property losses. AK / SK key pairs are allowed to be enabled, disabled, and can be used to call the OpenAPI when enabled, but cannot be used to call the OpenAPI when disabled. 



