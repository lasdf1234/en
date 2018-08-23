# Create Topic
You can create topic on the Topic Management page. 
 ## Prerequisites
- You have created a JD Cloud account and finished real-name verification. Your account is usable and doesn't exist in the black list. 
If you don't have an account, please [Register](https://accounts.jdcloud.com/p/regPage?source=jdcloud&ReturnUrl=%2f%2fuc.jdcloud.com%2fpassport%2fcomplete%3freturnUrl%3dhttp%3A%2F%2Fuc.jdcloud.com%2Fredirect%2FloginRouter%3FreturnUrl%3Dhttps%253A%252F%252Fwww.jdcloud.com%252Fhelp%252Fdetail%252F734%252FisCatalog%252F1), and [verify real-name](https://uc.jdcloud.com/account/certify)。
- Because the billing type of the product is charged by amount, please confirm that your account cannot be overdued.

## Considerations
During public beta, the user can create at most 5 topics.


## Procedure
1. Sign in to [the MQ console]().
2. On the left navigation, choose “Middleware > MQ > Topic Management”, and pop up the “Topic Management” page.
3. Click New on the “Topic Management” page.  
4. When you finish inputting the Topic information, click **Create** button.
5. Refresh the page, and complete the topic creating. 
  

* The topic name can be entered according to the prompt information, and cannot be modified.
* Message types are divided into unordered messages and global ordered messages：
  *	Unordered messages: Cannot guarantee first in first out (FIFO) ordered consumption, including general messages and delayed messages.
  *	Global ordered messages: The production and consumption of messages are carried out according to the publishing order of messages (FIFO).
* You should enter the remarks according to the requirements, and cannot exceed 255 bytes.

