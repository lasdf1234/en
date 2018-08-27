# Billing Rules

The Elastic IP supports three billing types:
 * Monthly Package Billing
 * Pay by Configuration
 * Pay by Consumption

## Monthly Package

### Introduction
The monthly package is Pay-In-Advance type, with a one-time fee of one month, several months or many years. It is suitable for the scenario of pre-estimation of Elastic IP bandwidth demand, and the cost is cheaper than pay by configuration.
### Example
If you purchase 1 month 1M bandwidth BGP Elastic IP at 2017-8-2 10:00:00, the monthly unit price is RMB 23, then you need to pay RMB 23=23*1, you can use this resources to 2018-2-2 23:59:59.
### Detailed Description
- Costs for months or years are paid in advance, and current purchased time period supports 1 month~9 months, 1 year, 2 years, and 3 years; costs are deducted at one time when creating the resources;

- The resources of the monthly package do not support deletion before it expires. To guarantee your use rights, please confirm the business needs and then purchase.

- The expiration time of monthly package billing order is at 23:59:59 in the Nth natural month or natural year from the start date of the order;
For example: the start time of the order is January 1, 2016 at 15:00:00, the purchase duration is 1 month, and the expiration time is February 1, 2016 at 23:59:59.

## Pay by Configuration

### Introduction
Pay by configuration is a Pay-As-You-Go type. The billing period is one hour. According to the Elastic IP configuration you purchased and the actual usage time (accurate to the second) in the billing cycle, the cost of the previous period is calculated and deducted at each hour.
### Example
The BGP Elastic IP you purchased at 10:30:00 on 2017-8-2 is charged according to the pay by configuration. The bandwidth is 1M and the cost per hour is RMB 0.06/hour. Then the fee (0.06*0.5=RMB 0.03) for the last hour (half hour actually used) will be settled at 11:00:00 on 2017-8-2, and settle the cost (RMB 0.06) per hour later, and settle the balance cost of the cycle when you delete the Elastic IP.
### Detailed Description
- Billing by the actual purchase configuration of the resources, the statistical time is accurate to the second, suitable for scenarios with large fluctuations in business volume;

- Turn-on instruction: To ensure your normal use, your account balance shall not be less than RMB 50 when pay by configuration for resources is turned on. If the account balance is less than RMB 50, you need to recharge before use.

- Paying mode: Adopting the Pay-As-You-Go mode, the bill will be generated in the wee hours by resources configuration and actual use duration and the cost shall be settled.

## Pay by Consumption

### Introduction
Pay by consumption is a Pay-As-You-Go type. The billing cycle is one day. Each Elastic IP is charged with the retention cost every day, and the traffic cost is settled at the actual outbound traffic per day.
### Example
The BGP Elastic IP you purchased at 10:30:00 on 2017-8-2 is charged according to pay by consumption. Assuming the traffic is 1GB on the day, the cost for the previous day is settled at 00:00:00 on 2017-8-3 (0.48+0.8*1=RMB 1.28).The period balance payment will be settled when you delete the Elastic IP.
### Detailed Description
- Billing by the actual traffic usage of the EIP, the statistical time is accurate to the second, suitable for scenarios with large fluctuations in business volume in a single day;

- Turn-on instruction: To ensure your normal use, your account balance shall not be less than RMB 50 when pay by consumption for EIP is turned on. If the account balance is less than RMB 50, you need to recharge before use.

- The billing adopts the Pay-As-You-Go mode. There is no charge for the opening. And at the 00:00:00 of each natural day after the creation, the cost will be billed and settled according to the resources retention time and the actual traffic usage．

- When deleting EIP, bill and settle costs according to the actual retention time and traffic usage within the billing cycle.

- Pay by consumption EIP does not support renewal.
