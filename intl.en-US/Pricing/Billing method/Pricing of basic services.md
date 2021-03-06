---
keyword: [Alibaba Cloud CDN billing, Alibaba Cloud CDN billing rules]
---

# Pricing of basic services

This topic describes the metering methods and considerations for basic services of Alibaba Cloud Content Delivery Network \(CDN\).

## Data transfer plans for Alibaba Cloud CDN

You can purchase data transfer plans for Alibaba Cloud CDN. For more information, see [CDN Resource Plan](https://common-buy-intl.aliyun.com/?commodityCode=%20cdn_bag_intl#/buy).

![Banner](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/6690011061/p65851.png)

## Purchase basic services of Alibaba Cloud CDN

Basic services of Alibaba Cloud CDN support two metering methods: pay-by-data-transfer and pay-by-bandwidth. For more information, see [Alibaba Cloud CDN Pricing](https://www.alibabacloud.com/product/cdn/pricing).

## Metering methods

|Metering method|Description|Scenario|
|:--------------|:----------|:-------|
|Pay-by-bandwidth|You are charged for basic services based on the daily peak bandwidth. A bandwidth value is collected at an interval of 5 minutes. 288 values are collected every day. The greatest bandwidth value is used as the daily peak bandwidth.|Your traffic curve is relatively flat, and the daily bandwidth usage exceeds 30%.|
|Pay-by-data-transfer|Basic services of Alibaba Cloud CDN are billed based on the amount of daily outbound data of CDN nodes.|Your traffic curve shows large fluctuations and bandwidth spikes. The daily bandwidth usage is lower than 30%.|
|Data transfer plans|You can make a one-off payment for a data transfer plan. The validity period of a data transfer plan is one year.|Data transfer plans support only the pay-by-data-transfer metering method. If the current metering method is pay-by-bandwidth, the remaining quota in the data transfer plan is suspended. The remaining quota is available only after you change the metering method to pay-by-data-transfer.|

**Note:**

-   The bandwidth usage is calculated based on the following formula: Bandwidth usage = Data usage \(GB\)/\[Peak bandwidth \(Mbit/s\) × 10.54\]. If the bandwidth is 1 Mbit/s and the daily bandwidth usage is 100%, the data usage is 10.54 GB.
-   You are charged for basic services based on the amount of only outbound data transfer of CDN nodes.
-   Alibaba Cloud CDN retains logs within the last three months. If you have questions about the logs or bills, submit an application before the log data expires to check the billing statements with Alibaba Cloud. Expired log data is released and cannot be restored. Billing statements of expired log data cannot be provided.

## Considerations

The data transfer that is actually charged is higher than the data transfer recorded in logs. The amount of data recorded in CDN logs equals the amount of data captured at the application layer. However, an extra amount of data is consumed to transmit the additional bytes inserted to TCP/IP packet headers and to retransmit TCP packets. Therefore, the actual amount of data is higher than the amount of data captured at the application layer. For more information, see [Why is the actual billed network traffic different from the network traffic reported by the logging feature?]()

