## Product deployment

#### What shall be done before creating an application security gateway?

Before creating an application security gateway, it is recommended to create a load balancer, and forward Web server traffic through load balancer.

Application security gateway needs to associate with the load balancer so as to protect traffic of HTTP/HTTPS.

#### How to manage after the original site is accessed into the load balancer?

New listening ports can be added at the load balancer to map SSH or remote desktop.

At the same time, you can purchase an EIP to manage the server. You can only open specific management ports through setting up security groups to ensure the security of the web server.

#### To enable the application security gateway, does it need to modify CNAME? And how to modify?

#### To access the application security gateway, it does not need to modify CNAME. Application security belongs to JD Cloud VPC network, so that only traffic can reach JD application security gateway, it can be protected.

#### When HTTP Service is not set with domain name, whether application security gateway can support protection?

It supports. The application security gateway supports protection to IP, and it can be done by associating the corresponding IP on load balancer.

#### I only have one Virtual Machine and one EIP, can I use the application security gateway without use of the load balancer?

No, it cannot. The application security gateway can be used through associating with the load balancer. Currently, the load balancer is provided free, it is suggested that the application security gateway is used after creating the load balancer and associating with it.

#### What is the amount of protection traffic supported in an application security gateway instance?

The maximum protection traffic supported by default in an application security gateway instance is 100M, if the traffic exceeds 100M, the application security gateway will expand its capacity, which will not influence business traffic and do not require users’ actions.