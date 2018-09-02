#Best practice of advanced Anti-DDoS-application security gateway


**Combine Advanced Anti-DDoS with Application Security Gateway**

**Plan description:**

Advanced Anti-DDoS+Application Security Gateway provide comprehensive security protection for JD Cloud users without additional performance overhead.

 

**Deployment plan:**

![img](https://img1.jcloudcs.com/cms/c7a75244-9169-43a6-9059-70ff4240947920180413181942.png) 

​                                                  

Best deployment architecture of Advanced Anti-DDoS+Best Application Security Gateway Practice is as follows:

Ø  The security scheduling center of JD Cloud resolves the user domain name to Advanced Anti-DDoS CNAME through DNS resolution.

Ø  User normal access traffic and DDoS attack traffic cleaned through Advanced Anti-DDoS are backed to the source to JD Cloud Virtual Private Cloud Network Load Balancer Cluster.

Ø  Application security gateway is deployed on the load balancer to be responsible for Web application layer security protection.

Ø  Application security gateway is associated with the load balancer, so that it can be used to defense attacks from Internet and internal attacks from VPC.

 

**Plan advantage:**

1.     Application security gateway provides the user exclusive resources, dynamic expansion, whose rules are subject to independent customization, without mutual influence.

2.     Application security gateway does not need to depend on DNS scheduling, without additional bandwidth resource consumption, and the network delay is lower than 1ms.

3.     HTTPS Certificate is saved inside the user VPC, and Internet cannot listen and thieve it.

 