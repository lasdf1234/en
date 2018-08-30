[
	{
		"funcName":"Core Function",
		"funcContent":[
			{
				"funcName":"",
				"funcTitle":"Publish subscription",
				"funcP":"Producers can create Topic to publish multiple types of messages, and consumers can subscribe to Topic for consumption on demand."
			},
			{
				"funcName":"",
				"funcTitle":"Message view",
				"funcP":"Users can view message status and content through TopicID and MessageID."
			},
			{
				"funcName":"",
				"funcTitle":"Dead Letter Queue",
				"funcP":"Messages that cannot be successfully delivered due to various reasons are placed on the Dead Letter Queue which can be viewed and delivered for consumption again."
			},
			{
				"funcName":"",
				"funcTitle":"Reset consumption point",
				"funcP":"Reset the message consumption progress within the time of persistent storage (3 days by default)."
			}
		]
	},
	{
		"funcName":"Diversity",
		"funcContent":[
			{
				"funcName":"",
				"funcTitle":"Ordinary message",
				"funcP":"Solve asynchronous decoupling between businesses, peaking and filling of traffic, message communication, etc."
			},
			{
				"funcName":"",
				"funcTitle":"Sequential message",
				"funcP":"Sequential consumption (FIFO) shall be performed in the order of messages' release."
			},
			{
				"funcName":"",
				"funcTitle":"Delay message",
				"funcP":"The delivery is performed at a specified delay time point after the message-sending time (current time), for example, the delivery is performed 5 minutes after the sending time of the specified message."
			}
		]
	},
	{
		"funcName":"Multi-protocol Access",
		"funcContent":[
			{
				"funcName":"",
				"funcTitle":"Support HTTP protocol access",
				"funcP":"Support Restful API, easy and convenient to access."
			},
			{
				"funcName":"",
				"funcTitle":"Support TCP protocol access",
				"funcP":"Provide SDK access of a more professional, reliable and stable SDK protocol. \t"
			}
		]
	},
	{
		"funcName":"Simple and Easy-to-use",
		"funcContent":[
			{
				"funcName":"",
				"funcTitle":"Smooth extension",
				"funcP":"Support elastic expansion which can increase or decrease resources as needed according to service conditions, to improve resource utilization rate and reduce the cost of consumption."
			},
			{
				"funcName":"",
				"funcTitle":"Development convenience",
				"funcP":"Provide a web console, API access interface and java SDK, easy to develop. It is also convenient for service support and service migration."
			}
		]
	},
	{
		"funcName":"Security Protection",
		"funcContent":[
			{
				"funcName":"",
				"funcTitle":"Comprehensive monitoring ",
				"funcP":"Provide functions such as multi-dimensional monitoring for the running status and performance of resources, stability maintenance and so on. It also provides early warning notification to reduce daily maintenance workload"
			},
			{
				"funcName":"",
				"funcTitle":"VPC",
				"funcP":"Instances run in Virtual Private Cloud (VPC), enhancing security and isolation. Provide access restrictions such as subnets and Identity and Access Management policies to protect against network attacks and safeguard your service privacy"
			}
		]
	}
]