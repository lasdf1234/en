# View Monitoring Information
The MQ console provides rich performance monitoring data; you can always view the running status of subscription relationships. 

## Procedure
1. Sign in to [the MQ console]().
2. On “Topic Management” page, choose the related topic, and enter the “Topic Details” page. 
3. On “Topic Details” page, click **Monitoring**, and view the monitoring information. 
*	You can quickly choose to view data of an hour to 14 days, or you can enter a date range to view data for up to one month.
*	Support for checking the monitoring information of a Consumer Group under Topic and topic. 

  

## Monitoring Item Description
Type | KPI | Description
--- | --- | ---
Topic | Production of TPS (bar / sec) | Number of messages produced per second |
Topic| Number of published messages | The number of messages sent by a producer to a topic |
Topic| The number of requests that have been published (times) | The number of API requests sent by the producer to the subject |
Topic| The size of the published message (byte) | The message size that producers send messages to topic.|
Consumer Group| Consumption of TPS (bar / sec) | Number of messages consumed per second |
Consumer Group| Number of accumulated messages | The number of messages piled up in subscription relationships
Consumer Group| Receiving message request quantity (Times) | Number of requests pulled by consumers in subscription relationship
Consumer Group| Number of messages received | Total number of messages pulled by consumers in subscription relationship |
Consumer Group| Number of messages received successfully | The number of successful messages pulled by consumers in subscription relationships |
Consumer Group| Receiving message size (byte) | Message size of consumer consumption in subscription relationship |
