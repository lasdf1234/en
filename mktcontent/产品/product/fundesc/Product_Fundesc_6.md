[
	{
		"funcName":"Multi-protocol Support",
		"funcContent":[
			{
				"funcName":"",
				"funcTitle":"Multi-protocol support to meet the demands for different businesses",
				"funcP":"Load balancer provides load balancer services based on Layer 4 (TCP protocol) and Layer 7 (HTTP). It can set the listening protocol and port independently to meet different business demands."
			}
		]
	},
	{
		"funcName":"Physical Checkup",
		"funcContent":[
			{
				"funcName":"",
				"funcTitle":"Automatic health check to ensure availability",
				"funcP":"Load balancer periodically detects the running status of the back-end VM. You can customize the detection frequency; Once the VM is detected to be abnormal, traffic will not be allocated to these abnormal instances to ensure service availability."
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
		"funcName":"Deployment of Internal Network",
		"funcContent":[
			{
				"funcName":"",
				"funcTitle":"Associate EIP for flexible switching between internal and external networks",
				"funcP":"You can choose whether to bind the EIP, and flexibly set up the private network and the public network load balancer and switch freely to meet the service demands in different scenarios; It could hide the internal network structure and improve system security through EIP binding method."
			}
		]
	},
	{
		"funcName":"Session Persistence",
		"funcContent":[
			{
				"funcName":"",
				"funcTitle":"Session retention to meet individual needs",
				"funcP":"The load balancer is forwarded by the source IP, and the Layer 7 Cookie session is maintained. The request from the same source is forwarded to the same server at the back end for processing, which satisfies the service requirements in different scenarios."
			}
		]
	},
	{
		"funcName":"High Availability",
		"funcContent":[
			{
				"funcName":"",
				"funcTitle":"Redundant configuration and multi-availability zone deployment to provide highly available services",
				"funcP":"Load balancer instance resources automatically redundant configuration could provide services in a clustered manner. At the same time, resources can be deployed in multiple availability zones to ensure high availability of services."
			}
		]
	}
]