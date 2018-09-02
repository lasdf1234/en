## Create an application security gateway

**Function description**   

​    Application security gateway can be created through JD Cloud Gateway Product-Cloud Security-Application Security Gateway Home Page, or it can be created by entering the console on Application Security Gateway Instance Management Page under Cloud Security Directory.

​    During the creation process, it only needs to fill in Application Security Gateway Name, designate HTTP or HTTPS Business required to be protected. Application Security Gateway can implement HTTP or HTTPS Business Association through associating with the load balancer, it requires manual association during the creation process or after the creation. Business association can be implemented without adjusting and modifying information such as CNAME during associating with the load balancer.

​    For websites not accessed into the load balancer, it is recommended to access into the load balancer upon modifying configuration. Current load balancer products are provided for free. For actions of load balancer, please refer to the help documents of load balancer or consult by JD Cloud 400 customer service telephone.

**Action steps**

​    Steps for creating application security gateway instance are as below: (create via console)

​    1. Enter the security gateway instance management page via "Console-Cloud Security-Application Security Gateway-Instance Management".

​    2. Select region which should be consistent with the region of web server.

​    3. Click “Create” to enter the application security gateway instance creating page.

![image.png](https://img1.jcloudcs.com/cms/b5e03c75-9d4c-4e05-8403-6d00b6c4851a20180815151830.png)

​    4. Enter order creating page and select package type from experience version and basic version currently supported; fill in name (application security gateway name). At this point, if there is a load balancer instance, choose to associate with the load balancer instance or choose not to associate but do so after creation is completed.

![image.png](https://img1.jcloudcs.com/cms/b56ee557-458e-427d-90e4-a82c19d8d94e20180815152101.png)

5. Click [Buy Now] till the end.

6. Return to Instance Management page; click Refresh so that the previously created application security gateway instance can be seen.