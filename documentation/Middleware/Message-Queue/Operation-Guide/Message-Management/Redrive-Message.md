# Redrive Messages (Dead Letter Queue)
Send the message to the dead letter queue after the maximum number of pushing attempts. It can be used as a queue for messages that cannot be processed successfully.

We can keep and isolate these messages in the dead letter queue to determine the causes of their failure. Distinguish the message types (general or ordered). You can search according to Topic and ConsumerGroup ID.
## Prerequisites
The message of consumption failed is in the message life cycle (3 days).
## Considerations
* The upper limit of sending failed messages of the dead letter queue storage is 10000.
* After reaching the upper limit of the dead letter queue, topic will suspend the sending message function and wait for the user to handle the exception of the subscriber.
## Procedure

1. Enter the "Dead Letter Queue" page.
 
2. Input "topic ID" or "ConsumerGroup ID" to search.

Resend or delete all the dead letters.
  

You can choose to resend all the dead letters or delete all the dead letters.
*	Resend All: Dead letters will be reentered the topic and sent to the subscriber related to the subscription.
*	Delete All: Dead letters will be deleted all, and will not be resent.
You can also click "Total Dead Letters" to enter the "Dead Letter Details", and delete or resend single dead letter.
