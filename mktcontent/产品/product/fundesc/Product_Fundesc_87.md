[
	{
		"funcName":"High Availability",
		"funcContent":[
			{
				"funcName":"",
				"funcTitle":"Redundant configuration and multi-availability zone deployment to provide highly available services",
				"funcP":"Network load balancer instance resources are redundantly configured automatically and provide services in a clustered manner. At the same time, resources can be deployed in multiple availability zones to ensure high availability of services."
			}
		]
	},
	{
		"funcName":"Deployment of internal and external network and flexible switching",
		"funcContent":[
			{
				"funcName":"",
				"funcTitle":"Associate EIP for flexible switching between internal and external networks",
				"funcP":"You can choose whether to bind the EIP, and flexibly set up the private network and the public network load balancer and switch freely to meet the service demands in different scenarios; It could hide the internal network structure and improve system security through EIP binding method."
			}
		]
	},
	{
		"funcName":"Multi-scheduling Algorithm",
		"funcContent":[
			{
				"funcName":"",
				"funcTitle":"Support multiple scheduling algorithms to achieve more reasonable traffic distribution",
				"funcP":"Load balancer supports three types of scheduling algorithms: polling, minimum connection number, and source IP. It can select a appropriate algorithm based on your own business demands. For example, if the performance of the back-end machine is not significantly different, you can select the polling algorithm to evenly distribute the back-end machine traffic allocation and improve external service capabilities. At the same time, it could configure weight according to back-end server performance. The high-configuration server can set a higher weight and carrying more access traffic."
			}
		]
	},
	{
		"funcName":"Session Persistence",
		"funcContent":[
			{
				"funcName":"",
				"funcTitle":"Support session maintenance based on TCP connection",
				"funcP":"The default timeout period for the session is 1,440s, which is the minimum guaranteed time for the session. During this period, regardless of how the NLB and the backend services are elastically extended, all packets with the same source and destination IP addresses are forwarded to the same back-end server. When the session hold time expires, it can’t guarantee the message would be forwarded to the same back-end server."
			}
		]
	},
	{
		"funcName":"Running Out of Connection",
		"funcContent":[
			{
				"funcName":"",
				"funcTitle":"Back-end server gracefully exits service",
				"funcP":"Connection draining is a way for back-end servers to gracefully exit the service. When a server is removed from the \"virtual server group\" or the high availability group (AG), the connection exhaustion timer will be started. After that, only the established TCP connection message will continue forwarding to the server until the connection exhaustion time expires. So far, the newly established TCP connection will not be forwarded to the server."
			}
		]
	},
	{
		"funcName":"Source IP Passthrough",
		"funcContent":[
			{
				"funcName":"",
				"funcTitle":"Client source IP transparent transmission",
				"funcP":"NLB can transmit the source IP from the client-end to the back-end server without special intervention and configuration and without special processing by the server application."
			}
		]
	}
]