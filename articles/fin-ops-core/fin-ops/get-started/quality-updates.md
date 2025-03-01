---
# required metadata

title: Proactive quality updates
description: This article provides information about proactive delivery of quality updates.
author: rashmansur
ms.date: 09/12/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: rashmim
ms.search.validFrom: 2022-08-19
ms.search.form:
ms.dyn365.ops.version: 10.0.29
---

# Proactive quality updates

[!include[banner](../includes/banner.md)]

Over the last several years, Microsoft has made continuous progress on what we refer to as [One Version](../../dev-itpro/lifecycle-services/oneversion-overview.md). The premise of One Version is simple: the closer that we can get to having all customers on the same software version, the higher the quality that we can deliver. We find and fix issues once, and we get those solutions into the hands of more customers more quickly.

This premise is confirmed by the results: lower incident counts across our products. When customers aren't on the same version, we consistently see that they are affected by issues that a solution is already available for. We've already made great progress with Dynamics 365 Finance, Dynamics 365 Supply Chain, Dynamics 365 Project Operations, and Dynamics 365 Commerce, and thanks to recent technical advances, it's now possible to take the next step. The following information lays out what we're going to do, what we've already done to set the stage, and how and when we will introduce the new capabilities without disruption.

## Focus on quality updates

We currently provide seven [service updates](public-preview-releases.md) per year. For example, version 10.0.29 is a service update. Until recently, there were eight updates per year. However, we dropped one update in response to customer feedback that revealed a desire to avoid changes near the end of the calendar year.

We won't be changing the cadence of the service updates. Instead, our next step forward in the One Version journey is focused on *quality updates*. Quality updates are cumulative builds of hotfixes. They don't include new features. At any given time, our entire community of customers is spread between the three or four most recent service updates. However, for any given service update, dozens of different quality update versions can be used within the group, depending on the dates when people deployed. In our next step, we will proactively broadcast quality updates. We already use this model for our Dataverse-based applications and have seen the expected results of improved quality and decreased support incidents.

Of course, a reduction in defects could reduce or completely eliminate the need for quality updates. We have multiple initiatives in flight to reduce the defects that require quality updates. Even when payloads are reduced in the quality update, consistency across the customer base will improve supportability, get improvements to customers more quickly, and reduce the frequency of customers encountering issues that solutions already exist for.

## Making proactive distribution possible

Multiple advances have already been deployed that enable proactive delivery of quality updates:

- **Near-zero downtime updating** – To push more frequent environments, it's essential that the impact to environment availability be reduced to preserve Dynamics 365 Service Level Agreements (SLAs). Near-zero downtime updating was originally introduced to help improve monthly operating system patching by using a cluster failover to activate the updated image with minimal disruption. The mechanism for applying updates is being enhanced so that it's even less disruptive, and it will cover both operating system patching and quality update deployment.

    For interactive users, an active session might be interrupted, and the retry will go to the now-updated environment. With the introduction of [priority-based batch scheduling](../../dev-itpro/sysadmin/priority-based-batch-scheduling.md), which is now available on an opt-in basis, batch scheduling and processing recovers and resumes immediately after the update. Priority-based batch scheduling will be in place for customers before they start to participate in proactive distribution of quality updates for their production environments.

- **Dark hours** – Dark hours are defined for each Azure region, and near-zero downtime updates will occur during the dark hour period.

## The proactive update process

Deployment of proactive quality updates will follow a safe deployment process (SDP). The specifics of the SDP will evolve, but quality updates will initially be deployed to sandbox environments. The process will start with environments that opt in for early deployment. As the percentage of successfully deployed sandboxes increases, deployment to production environments will begin. Once again, the process will start with environments that opt in for early deployment. Listening systems will monitor system telemetry and Livesite incidents, and will stop the rollout of a specific version if any regression is detected. Customers will still be able to pull the quality updates ahead of proactive deployment if they want.

Current release management data shows that less than 3 percent of regressions are introduced in quality updates. With increased focus on eliminating regression and an enhanced SDP, the potential impact of regressions will be dramatically lower than the quality gains that are achieved by more quickly getting fixes deployed to customers broadly.

## Process changes

A set of process changes is being implemented ahead of the activation of proactive quality update deployment:

- **Schema** – Tooling will ensure that quality update builds include only schema changes that can be applied while the service is online. This approach will help preserve the ability to apply the update with near-zero downtime.
- **Increased change scrutiny** – Currently, there is already an extra process step to approve changes for inclusion in a quality update. The scrutiny in the extra step will be increased to help reduce the potential for regressions. Breaking changes aren't allowed in quality updates, and the increased change scrutiny will help ensure that we meet this target.
- **Visibility** – We will send notifications through email and Lifecycle Services (LCS) for upcoming proactive quality updates. In addition, support teams and incident leads will have visibility into where quality updates have been proactively deployed.
- **Fail Safe via flighting** – Flighting will be used to guard code changes wherever applicable in a quality update bug fix or use the existing feature flighting relevant to the fix. If a fallback or turning a change off change is required after a proactive deployment, it can be done through the flighting system to avoid further failures.
- **Sandbox sync designation** – Less than 20 percent of customers today have multiple sandboxes and keep one sandbox deployed where the version matches production, to help with troubleshooting. If a customer is using a sandbox to test a newer version than their production, that sandbox will receive quality updates to the newer version.

## What is the rollout roadmap for quality updates?

Distribution of proactive quality updates for sandbox environments is expected to begin in late September or October 2022 for Azure public cloud customers. Trial environments will also start to receive proactive update deployment at that time. In September, a notification will be sent to each customer to inform them about the expected schedule for their environments. Exceptions to the proactive updated distribution process will be allowed only for FDA-regulated customers. We're still working out how regulated environments and sovereign and government cloud customers will be managed.

Over the next six-month period, we will gradually increase the percentage of sandbox environments that receive proactive updates, until all designated environments are included and progress to updating production environments. Throughout the period, we will monitor to ensure that the deployment process is seamless and that we're hitting our target of non-disruptive payloads.

Because customers will regularly receive smaller payloads, we expect the process of staying current to become simpler. We will adjust the frequency of update deployment as we demonstrate the ability to run the process without disruption. This process is already working effectively for our Dataverse platform and applications, and is delivering the anticipated improvements in service quality. We're anxious to take the same step forward for finance and operations applications.

## When will quality updates start for production environments?
At this time, quality updates are only targeting sandboxes. We will update this space with a start date for production environments when we have more concrete data and metrics from proactive updates for sandboxes to gauge readiness for prod.

## What is the schedule for sandbox quality updates?
For information on the dark hours for each region, see [What is the schedule for proactive quality updates?](../../dev-itpro/deployment/plannedmaintenance-selfservice.md#what-is-the-schedule-for-proactive-quality-updates).

## How are the dark hours handled for customers that have one finance and operations apps instance but are active in multiple time zones? 
There are no special schedules outside of the dark hours where a finance and operations apps instance exists, as we plan to roll out quality updates in a minimally disruptive manner with [nZDT](../../dev-itpro/deployment/plannedmaintenance-selfservice.md#what-does-near-zero-downtime-maintenance-mean).

## How will Microsoft ensure the quality of these updates?
Microsoft strives to keep the release pipeline efficient enough to deliver small payloads to keep the validation cost low. Every fix in a quality update goes through a rigorous and safe deployment process which helps improve quality and reliability, thereby reducing customer impact. Deployment will happen in stages on sandbox environments first, followed by production. Staged deployments allow for proper monitoring to determine if further deployment is safe. We will stop the rollout if issues are detected with each group of customers deployed and ensure that each step in the rollout has enough time for issues to surface. For every upcoming quality update, we will provide visibility into the schedule through updates to public documentation and emails, so customers can plan ahead.

## Can customers delay, reschedule, or pause a quality update?
No. The main objective of quality updates is to ensure fundamentals like security, privacy, reliability, availability, and performance are continuously improving for our customers. By delaying or pausing an update, security, availability, and reliability will be at risk.

## How can one know the set of changes that went into a quality update payload?
You will be able to look at all the KB articles in a quality update build on the **Environment details** page in LCS, by navigating to the **Quality Update** section. 

## What is the process if a critical issue is found after a quality update?
A critical issue or regression is one or more events that typically cause multiple customers to have a degraded experience with one or more of our services. These issues can cause unplanned downtime including unavailability, performance degradation, and interference with service management. If there is a broad customer impact due to such regressions, we will stop the rollout of a quality update until we can communicate and fix the issue. Typically, the next quality update will have the necessary fix to resume rollout.

If a single customer environment is affected, contact Microsoft support to open a ticket. Based on the justification, we will stop the quality update rollout to all other environments in that project until the issue is mitigated.

## Can customers still manually apply hotfix updates from LCS?
Yes. To ensure ongoing parity with how hotfixes work, hotfix updates can still be applied to customer environments in LCS. However, it's important to note that hotfixes that are deployed as part of a quality update go through the standard SDP before the update is deployed. This reduces the risk of regressions due to higher quality. We recommend that you choose a quality update over manually applying hotfixes for increased reliability.

## Can customers self-install a quality update build by themselves ahead of the schedule?
Yes. You can install a quality update proactively. Microsoft will skip the update if the environment’s current build version is equal or higher than the quality update in question.

## If an environment has an upcoming scheduled monthly service update within a week, will it still receive quality updates?
- Quality updates aren't applied if there is an impending service update scheduled within a week from when the quality update is scheduled to happen.
- If a sandbox environment has the same or higher build version than the impending quality update, it will be skipped.
- If a production environment has the same or higher build version than the impending quality update, it will be skipped.
- If a sandbox has the same or higher build version because of a quality update or a manual update to the production, the production will still get the scheduled version of the monthly service update. If you don't want the scheduled production environment to be updated to the service update version, you can pause the service update from LCS. 
- We recommend you utilize the latest quality update build to test your changes for an upcoming service update for better stability and results.

## Can an environment be brought back to its previous state if there are issues after a quality update is applied?
After a quality update is applied, there is no rollback under any circumstances. There are only patch forward options available to mitigate issues.

## What about FDA regulation and GPX?
The plan for customers subject to FDA validation and regulation is still evolving. Expect more updates in this space soon. For now, all such customers are exempt from quality updates.

## What versions of service updates are supported for these quality updates?
Customers on versions lower than N-2 will not receive quality updates. 

## Finance and operations apps deployments with retail components typically require additional work in addition to having to redeploy MPOS. How will these quality updates impact the RetailSDK? 
As the nature of the hotfixes itself doesn’t change in the quality updates payload, we don’t anticipate any additional impact at this time specifically related to retail components.

## Is there any impact to Cloud Hosted Environments (CHE)? ? 
No.

## Are there any integration issues with Microsoft Dataverse? 
No.

