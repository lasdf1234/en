# Billing Overview

## Billing Item
The billing items of JD Cloud advanced anti-DDoS include: minimum protection, elastic protection, and business bandwidth.

### Minimum Protection
Advanced anti-DDoS provides fixed defense capabilities, including fixed attack protection peak value (Gbps) and CC protection peak value (QPS). Monthly package.
The price of minimum protection varies with the IP provider selected. The optional IP providers are Telecom, Telecom + Unicom, and Telecom + Unicom + CMCC line,

### Elastic Protection
The elastic protection refers to the extended DDoS protective capability provided when the actual attack traffic exceeds the protective capability of minimum protection, including the extension of the of DDoS attack protection peak value (Gbps) and the CC protection peak value (QPS).
The elastic protection can be upgraded and degraded. If the attack traffic does not exceed the protection peak value of the minimum protection, no cost will be charged.

### Business Bandwidth
Refers to the consumption bandwidth of normal service in non-DDoS attack state. Unit: Mbps. By fault, 100 Mbps is gifted. You can buy larger business bandwidth if needed.

## Payment Method
### Pay-In-Advance
Includes minimum protection + business bandwidth, charged according to the unified billing method of monthly package. Can only be upgraded, and cannot be degraded.
### Pay-As-You-Go
The elastic protection part is charged daily according to the larger actual billing interval of the attack peak value exceeding the minimum protective capability (Gbps) or CC protective capability (QPS) of the day before,
then a bill of Pay-As-You-Go will be generated.
If the attack does not exceed the defense peak value of minimum protection, you will not be charged for the elastic protection .


 ## Renewal Rules
Monthly package renewal: extends the expiration time of advanced anti-DDoS instance. The renewal duration can be from 1 month to 9 months, 1 year, 2 years and 3 years. If the renewal is made before the expiration date, the start time of the new order is the expiration date of the original order. If the renewal is made after the expiration, the start time of the new order is the day of renewal;
Batch renewal: Batch renewal for multiple advanced anti-DDoS instances will extend the usage duration of the selected resources according to the selected renewal duration by the user.


## Arrear/Expiration Instructions
### Monthly Package
After the instance expires, the billing status will be marked as expiration, and the advanced anti-DDoS service will be degraded to the basic protective capability for 2G. If the renewal is not made within 7 days, the instance will be deleted 7 days later, and all data configurations of the instance as well. Once deleted, the instance data cannot be recovered.
If the renewal is made within 7 days, the minimum bandwidth protective capability and elastic protective capability can be back to normal right after renewal. Before your advanced anti-DDoS instance expires, JD Cloud will send you reminds in form of mail and text message. Please check and renew in time; When your advanced anti-DDoS instance expires, you will be sent a mail and text message to notify that your resources have expired. Be sure to view the notification and renew in time to avoid unnecessary losses.

### Pay-As-You-Go of Elastic Traffic
Your advanced anti-DDoS status will be changed to "arrear" when the balance in your account plus the sum of coupon that can be used to pay that resource is insufficient to pay the charges of elastic traffic of the previous billing period (24 hours). The elastic protective capability of advanced anti-DDoS instance will be deactivated and the minimum protective capacity will be reduced to 2G.


## Related Reference

- [Billing Rules] (Billing-Rules.md)
- [Price Overview] (Price-Overview.md)
