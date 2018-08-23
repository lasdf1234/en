# Delete and Manage Topic
## Considerations
* For topic owners, they have topic management authority and delete authority.
* For an authorized topic, the authorized user only has the right to delete, but not really delete the topic, just delete the authorization.

## Procedure
1. In topic list of the "Topic Management" page, choose **More** button in the topic located row that ready to delete and choose **Delete**.
 
2. Pop up prompt box, click **Delete**, when the topic is deleted, the MQ will no longer push messages, immediately stop the service, and data cannot be restored. 

3. In the topic list of “Topic Management” page, choose **More** button in the topic located row that need to operate, you can choose **Send Pause**, **Receive Pause** and **All Pause**.
 
4. Pop up the prompt box to confirm the required operation. 
5. You can reset the consumer offset in the "Subscription Management" page.
6. Choose **Reset Consumer Offset** button of the relationship of resetting consumer offset.  
* You can choose “Clear all cumulative messages”, and all unconsumed cumulative messages will be skipped and start to consume the message from the latest next message.
*	You can choose "reset consumer offset by time", choose to reset consumer offset at any time in the message life cycle, and change consumption progress.

