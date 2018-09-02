# Associate and disassociate load balancer

​	 Application security gateway must associate with the load balancer of 7 layers (ALB) so as to protect HTTP/HTTPs business subject to the load balancer.

​	During the application security gateway creation process, it can select to associate with load balancer, if there is no available load balancer, it may firstly create an application security gateway instance, and associate with the load balancer instance after successful creation.

​	After completion of instance creation, it may select to associate different load balancers through [Associated Load Balancer] on the instance management page and disassociate through [Disassociate Load Balancer]. The load balancer has two types, load of 7 layers and load of 4 layers, the associated load balancer currently supported is the load balancer of 7 layers, the load balancer of 4 layers is not supported now.