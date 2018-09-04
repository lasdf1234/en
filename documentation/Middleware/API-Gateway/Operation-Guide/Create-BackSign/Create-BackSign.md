# Backend Service Signature


Currently, the API gateway configures security protection settings for you, providing two security measures: Backend signature key pair and traffic control policy. This paper will introduce the backend signature.

The key pair of backend signature adopts JD Cloud User AK/SK(Access Key/Access Key Secret), which will protect your backend through verification of backend signature when the gateway requests your real backend.

After you associate the AK/SK key pair of JD Cloud user to API, this AK/SK will be added and showed when the gateway requests this API, and your backend will verify the identity of gateway through verification of string of signature.


## Operational Steps

Click **Backend Signature** at left side to perform the configure and associate

1. Enter the page of backend signature list

![Backend signature list](https://github.com/jdcloudcom/cn/blob/edit/image/Internet-Middleware/API-Gateway/hdqm-list.png)


2. Add backend signature

![Add backend signature](https://github.com/jdcloudcom/cn/blob/edit/image/Internet-Middleware/API-Gateway/hdqm-add.png)


3. Associate the signature to group

![Associate signature](https://github.com/jdcloudcom/cn/blob/edit/image/Internet-Middleware/API-Gateway/hdqm-bd.png)



  
