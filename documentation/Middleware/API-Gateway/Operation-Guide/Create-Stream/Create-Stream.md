# Traffic Control Policy

Currently, the API gateway configures security protection settings for you, providing two security measures: Backend signature key pair and traffic control policy. This section will introduce the traffic control policy.

The Traffic Control Policy can affect the associated API only after associating the Traffic Control Policy to API group.

- The traffic control policy can limit for API group and the single access key limit. The unit of traffic control is minute and day. Mind that the single access key limit should not be more than the API group limit. That is, single access key limit <= API group traffic limit.
- The default traffic control limit of each API group is considered as 500QPS (this value can be improved by Open Ticket) when you set the API traffic upper limit, because of API gateway limit.

- Associate API group. You can associate the policy to several API groups. The limit of traffic control policy will separately affect each API associated by the policy. When you associate the API, if this API has been associated to a policy, then your operation will replace the previous one and take effect in real time.
- You can perform some basic operations of traffic control policy at API gateway control panel, such as creation, modification, deletion and check. There are also operations such as associate and disassociate of traffic control policy with API group.



## Operational Steps
You need to select Region which can not be changed once selected and can only be applied to the API under the same one Region when you create traffic control policy.

1. Click the **Traffic Control Policy** at left menu to enter the page of traffic control policy list to configure and associate the policy.

![Traffic control policy list page](https://github.com/jdcloudcom/cn/blob/edit/image/Internet-Middleware/API-Gateway/lkcl-list.png)


2. Add new traffic control policy

![Add new policy](https://github.com/jdcloudcom/cn/blob/edit/image/Internet-Middleware/API-Gateway/lkcl-add.png)


3. Associate the policy to group

![Associate policy](https://github.com/jdcloudcom/cn/blob/edit/image/Internet-Middleware/API-Gateway/lkcl-bd.png)



