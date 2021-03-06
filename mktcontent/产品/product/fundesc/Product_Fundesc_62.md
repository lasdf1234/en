[
	{
		"funcName":"Alarm Scaling mode",
		"funcContent":[
			{
				"funcName":"",
				"funcTitle":"Alarm Scaling Mode",
				"funcP":"Based on the performance of the VM monitoring performance indicators (such as CPU, memory usage, and network inbound and outbound traffic) to adjust business deployment, and it could customize alarm trigger strategy. When the business load makes indicator reaches the threshold value, the VM instance is automatically added or decreased according to the set strategy, so that the business load changes can be flexibly responded to improve resource utilization rate."
			}
		]
	},
	{
		"funcName":"Timed Scaling Mode",
		"funcContent":[
			{
				"funcName":"",
				"funcTitle":"Timed Scaling Mode",
				"funcP":"If you are predictable of changes in load, you can set up a scheduled task to plan ahead for your resource expansion/reduction activities. You can configure periodic tasks to automatically increase or decrease VM instances periodically, so as to flexibly respond to business load changes and improve resource utilization rate. When the periodic demand fluctuates, the alarm scaling mode can be configured to cope with unpredictable changes."
			}
		]
	},
	{
		"funcName":"Automatically Load Balancer",
		"funcContent":[
			{
				"funcName":"",
				"funcTitle":"Automatically Load Balancer",
				"funcP":"The VM instances added by alarms and timing policies can directly associate with existing load balancer to share service traffic and improve service availability."
			}
		]
	},
	{
		"funcName":"Scaling Activity Record",
		"funcContent":[
			{
				"funcName":"",
				"funcTitle":"Scaling Activity Record",
				"funcP":"If you want to know all the scaling activities that have been performed by the scaling strategy (automatically/manually increase or decrease the machine), you can use this function to view, including the scaling cause, status, result details, time, and supporting query history record by time."
			}
		]
	}
]