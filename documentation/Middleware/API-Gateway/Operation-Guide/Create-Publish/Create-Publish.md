# Release API Groups

The information of API group can be used via publishing after creation. Currently, the JD Cloud provides 3 sets of publishing environment: Test, pre-launch, online. You can publish and test the API group in test and pre-publish environment, and down load the SDK and documents; and officially publish the SDK and documents of on-line API group in on-line environment.

API caller can access and call the API through custom domain or secondary domain after publishing.

Please note that:
- If selecting Mock backend in publishing, directly return to normal constant result instead of requesting the real back service when commissioning. This method applies to test if the request link of API is correct and skip the APP authentication and signature verification;
- The gateway will actually request the backend service if selecting the unique backend and recording the backend address.
- Make sure you have properly configured the traffic control policy, backend signature, authorized access and other information of API group before publishing, otherwise the access may be affected.


## Operation Steps:

### STEP1: select the group to be published

Firstly, enter the **API Group Management** page and find the group to be published

![APIgroup list](https://github.com/jdcloudcom/cn/blob/edit/image/Internet-Middleware/API-Gateway/apigroup-rp-apigroup-list.png)




### STEP2: click the **Publish**:

![Publish](https://github.com/jdcloudcom/cn/blob/edit/image/Internet-Middleware/API-Gateway/apigroup-fb.png)


Description:





1) Select the version to be published. API gateway supports the version management of group, so you need to pay attention to select the version to be published when publishing. Subsequently, you can switch or log off different versions in environment management.

2) Select the environment to be published. API gateway provides three environments: Test, pre-launch, online.

3) Select the publishing type of backend service. Support Mock backend and real backend at present. When commissioning, if selecting Mock backend to publish, then do not request the real backend service, but return to constant result. This method applies to test if the request link of API is correct and skip the APP authentication and signature verification.



### STEP3: Manage the versions published in different environments in the deployment management:
The deployment of different environments can be seen in the page of deployment management after publishing.
![Deployment list](https://github.com/jdcloudcom/cn/blob/edit/image/Internet-Middleware/API-Gateway/bslb-list.png)

API gateway supports to manage the API version used for test/online, so you can publish or log off the API and switch the version in real time.
![Switch Version](https://github.com/jdcloudcom/cn/blob/edit/image/Internet-Middleware/API-Gateway/bslb-qhbb.png)

### STEP4: logoff
Directly click the “logoff” if required. Take effect in real time.

![Logoff](https://github.com/jdcloudcom/cn/blob/edit/image/Internet-Middleware/API-Gateway/bslb-xx.png)


