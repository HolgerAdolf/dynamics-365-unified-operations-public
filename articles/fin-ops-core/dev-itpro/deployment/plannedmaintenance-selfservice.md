---
# required metadata

title: Maintenance in self-service environments FAQ
description: This article provides answers to frequently asked questions about the Microsoft planned maintenance in self-service environments.
author: matapg007
ms.date: 09/08/2022
ms.topic: article
audience: Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: matgupta
ms.search.validFrom: 2021-05-13

---

# Maintenance in self-service environments FAQ
Because of the changing nature of technology, the continual appearance of new security threats, and compliance requirements, environments must be updated with all critical security and quality updates. Microsoft has built the framework for performing all maintenance activity, such as operating system patching, deployment of security hotfixes, and deployment of quality updates, during the dark hours of the geographic region where your environment is deployed. To minimize application downtime, upgrades will occur in batches. Therefore, most capacity is always online, and only a subset is upgraded at a time. This approach enables servicing that involves a small window of service degradation instead of complete downtime.

## Infrastructure maintenance in self-service environments
Infrastructure maintenance is the process of updating the environments with the latest security updates and critical hotfixes. Microsoft must complete this process on your environments to ensure security, availability, reliability. This article provides answers to frequently asked questions about Microsoft planned maintenance in self-service environments.

## What are the types of planned maintenance activities that are performed on an environment?
Some of the common planned maintenance activities performed by Microsoft are:

- Operating system (OS) security updates
- Security hotfixes
- Microsoft quality updates

## <a name="windows"></a>What are the planned maintenance windows?
A planned maintenance window is typically during the dark hours of the geographic region that your environment is deployed in. The following table lists the maintenance windows for each geography in Coordinated Universal Time (UTC).

|Geo | Maintenance window |
|----|--------------------|
|Australia |1:00 PM to 7:00 PM UTC|
|Asia   |4:00 PM to 10:00 PM UTC|
|Brazil |4:00 AM to 10:00 AM UTC |
|Canada	|4:00 AM to 10:00 AM UTC |
|China	|4:00 PM to 10:00 PM UTC|
|Europe	|10:00 PM to 4:00 AM UTC|
|France	|10:00 PM to 4:00 AM UTC|
|India	|6:30 PM to 00:30 AM UTC|
|Japan	|4:00 PM to 10:00 PM UTC|
|Norway	|10:00 PM to 4:00 AM UTC|
|South Africa	|10:00 PM to 4:00 AM UTC|
|Switzerland	|10:00 PM to 4:00 AM UTC|
|United Arab Emirates	|6:00 PM to 12:00 AM UTC|
|United Kingdom	|10:00 PM to 4:00 AM UTC|
|United States	|4:00 AM to 10:00 AM UTC |

## What is the schedule for operating system maintenance?

| Month and year | Americas (5:00 AM–8:00 AM UTC) | EMEA (2:00 AM–5:00 AM UTC) | APAC (6:00 PM–9:00 PM UTC) |
|----------|--------------------------|----------------------|----------------------|
| May 2022 | May 22, 2022 | May 21, 2022 | May 21, 2022 |
| June 2022 | June 26, 2022 | June 25, 2022 | June 25, 2022 |
| July 2022 | July 24, 2022 | July 23, 2022 | July 23, 2022 |
| August 2022 | August 21, 2022 | August 20, 2022 | August 20, 2022 |
| September 2022 | September 25, 2022 | September 24, 2022 | September 24, 2022 |
| October 2022 | October 23, 2022 | October 22, 2022 | October 22, 2022 |

## What is the schedule for proactive quality updates?

### Proactive quality update release: 10.0.28
##### App version: 10.0.1265.89
##### Corresponding Latest KB article: 745340
| Station | Regions | Current major version | Sandbox Schedule 1 | Sandbox Schedule 2
|---|---|---|---|---|
| Station 1 | Canada Central, Canada East, France Central, India Central, Norway East, Switzerland West | Service Update 10.0.28 | September 15 to September 18, 2022, and September 19 to September 22, 2022 | October 7 to October 10, 2022 |
| Station 2 | France South, India South, Norway West, Switzerland North, South Africa North, Australia East, UK South, UAE North, Japan East, Australia South East, South East Asia | Service Update 10.0.28 | September 25 to September 28, 2022 | October 7 to October 10, 2022 |
| Station 3 | East Asia, UK West, Japan West, Brazil South, West Europe, East US, UAE Central | Service Update 10.0.28 | September 26 to September 29, 2022 | October 7 to October 10, 2022 |
| Station 4 | North Europe, Central US, West US | Service Update 10.0.28 | September 28 to October 1, 2022 | October 7 to October 10, 2022 |
| Station 5 | DoD, Government Community Cloud, China | Service Update 10.0.28 | Not Scheduled | Not Scheduled |

### Proactive quality update release: 10.0.29
| Station | Regions | Current major version | Sandbox Schedule 1 |
|---|---|---|---|
| Station 1 | Canada Central, Canada East, France Central, India Central, Norway East, Switzerland West | Service Update 10.0.29 | October 14 to October 17, 2022 |
| Station 2 | France South, India South, Norway West, Switzerland North, South Africa North, Australia East, UK South, UAE North, Japan East, Australia South East, South East Asia | Service Update 10.0.29 | October 15 to October 18, 2022 |
| Station 3 | East Asia, UK West, Japan West, Brazil South, West Europe, East US, UAE Central | Service Update 10.0.29 | October 16 to October 19, 2022 |
| Station 4 | North Europe, Central US, West US | Service Update 10.0.29 |October 17 to October 20, 2022 |
| Station 5 | DoD, Government Community Cloud, China | Service Update 10.0.29 | Not Scheduled |

> [!IMPORTANT] 
> Five business days in advance, Microsoft will update the preceding schedule and send email notifications to the set of environments that are scheduled to receive [proactive quality updates](../../fin-ops/get-started/quality-updates.md). The preceding schedule is applicable only to environments that have been notified about an upcoming update. For information about the dark hours for every region, see the [What are the planned maintenance windows?](#windows) section.
>
> For each region group, or *station*, where a quality update is currently scheduled to be rolled out, the schedule shows a range of four days. Quality updates will start with only sandbox environments. Then, as the percentage of successfully deployed sandboxes increases, deployment to production environments will begin with advance notifications to customers.
> 
> Quality updates will always occur in a rolling manner that enables us to target a set of environments per schedule and complete all the sets by the end of the fourth day for a station. However, this doesn't mean that an environment update will span four days. It just means that we can't pre-determine which set of environments will be updated on a given day within the four-day range. All updates will be done during dark hours, with near-zero downtime. Updates will definitively end within the dark-hour window of a given region.

> [!NOTE] 
> Effective August 2022 through October 2022, Microsoft will start to roll out updates to the production environment during any weekend, and outside of normal business hours, to help minimize any potential impact on your environments. All sandbox environments will be updated during any night, outside of business hours.
> 
> All the maintenance activity (system updates, security hotfixes, and quality updates) will be performed during the dark-hour window to provide a near-zero-downtime experience.

## What does near-zero-downtime maintenance mean?
Customers can continue to operate the system during the maintenance activity. They may experience brief interruptions or disconnects during this window, but will not need to take a full downtime.

## What is the experience during the near-zero-downtime maintenance window?
Upgrades will occur in batches. Therefore, most capacity is always online, and only a subset is upgraded at a time to help eliminate complete downtime. We recommend that customers adopt [priority-based scheduling](../sysadmin/priority-based-batch-scheduling.md) of batch jobs. In this way, they can eliminate the stickiness of batch jobs that are associated with a batch server and enable near-zero-downtime servicing for security patching and quality updates. By design, all Tier 2 and Tier 3 environments might experience approximately 30 minutes of downtime during the servicing.

### Interactive usage
Users who are connected to the environment might experience a brief disconnection of less than 60 seconds a few times during the servicing window. After recovery, users might experience one of the following outcomes:

- The session is gracefully recovered, and the user either goes to the page that they were working on, or is redirected to the root/workspace/home page and receives the following message: "Something went wrong. But we were able to recover your session."
- Session recovery fails, and the user who is working on a details page is redirected to the root/workspace/home page and receives the following message: "Something went wrong, and we were unable to recover your session. You've been redirected."

For example, the user may be working on a sales order creating lines or posting. After the interruption, the user might return to the Sales workspace, but the new order and lines should still be available. We recommend that users go back to the main form and check their work. 

### Batch service
Individual batch servers will not be available for up to 30 minutes. The following activities will occur: 

- Any executing batch jobs will be terminated.
- Jobs that were terminated will be automatically restarted when the batch service recovers. Set the maximum number of retries to zero for any jobs that should not be restarted automatically.
  - Check printing 
  - Statement posting

For more information, see [Can I change the maximum number of retries and the retry interval?](../sysadmin/retryable-batch.md#can-i-change-the-maximum-number-of-retries-and-the-retry-interval) to learn more about batch retry.

### Priority-based scheduling
- If priority-based scheduling is enabled, users will experience reduced Application Object Server (AOS) capacity during the maintenance window. Batch jobs will be served by the available AOS instances. Therefore, there will eventually be no complete downtime during the servicing window.
- If priority-based scheduling isn't enabled, any batch groups that are configured with AOS instances will experience downtime until the associated AOS instance is updated and back in rotation.

> [!NOTE] 
> We are working to reduce the downtime for batch service to a few minutes. This will require customers to adopt priority-based scheduling of batch jobs.

## Is it possible to reschedule near-zero-downtime operating system maintenance?
No. To meet regulatory and security compliance standards, Microsoft will perform the planned maintenance during the dark hours of the geographic region where your environment is deployed. The main objective of planned maintenance is to regularly patch environments to remediate security vulnerabilities and apply critical quality updates. If you delay updates, you will put data security, availability, and reliability at risk. 

