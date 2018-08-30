[
	{
		"funcName":"Management of Service Connection",
		"funcContent":[
			{
				"funcName":"",
				"funcTitle":"Data source connection",
				"funcP":"The data factory natively supports a variety of common data sources, which can connect and collect data from different data sources in cloud service and user's local environment, and accelerate the data integration process. Currently, it supports cloud storage, Cloud Database, data computing service, SQL Server, Oracle, MySQL, DB2, FTP and other services."
			},
			{
				"funcName":"",
				"funcTitle":"Computing resource connection",
				"funcP":"As a data integration service on the cloud, the data factory needs to perform ETL processing on the data accessing the data source. By connecting different analysis services, the data factory cleans, transforms and analyzes the accessed data in the form of workflow to achieve ETL. The current data factory supports access to data computing services, and services such as JMR, streaming data bus, stream computing, machine learning platforms will be added subsequently."
			}
		]
	},
	{
		"funcName":"Data Synchronization",
		"funcContent":[
			{
				"funcName":"",
				"funcTitle":"Data access and distribution",
				"funcP":"Data synchronization of the data factory supports synchronization of data from multiple local and cloud data sources, supporting the users with different synchronization strategies such as full-scale synchronization, incremental synchronization and so on. It can be used for data access to enterprise data warehouse to collect multi-source data; It can also distribute the processed data in the data warehouse to production system to support online business such as database system, through data synchronization function of the data factory."
			}
		]
	},
	{
		"funcName":"Data Workflow",
		"funcContent":[
			{
				"funcName":"",
				"funcTitle":"Data synchronization and processing arrangement and scheduling",
				"funcP":"Analysis tasks such as data access, data cleaning, data aggregation analysis, data distribution and so on are arranged and organized through a unified workStreaming Management module, and users can formulate scheduling strategies according to different periods based on such as a month, a week, a day or an hour as required by the service."
			}
		]
	},
	{
		"funcName":"Operation and maintenance for the work",
		"funcContent":[
			{
				"funcName":"",
				"funcTitle":"Job setting alarm notification rule",
				"funcP":"The workflow of the data factory can be set up with multiple alarm notification strategies to enable the user to know the critical running status of the task immediately."
			},
			{
				"funcName":"",
				"funcTitle":"Job operation monitoring",
				"funcP":"Provide a record of the execution status and history of the workflow. Users can view the execution results and detailed execution logs of each job, and track the detailed logs of each execution link of each workflow, which is convenient for the operation and maintenance personnel to diagnose and analyze problems."
			}
		]
	}
]