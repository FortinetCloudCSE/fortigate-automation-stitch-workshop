---
title: "Fortinet FortiGate Automation Stitch Workshop"
chapter: true
weight: 1
---

## FortiGate Automation Stitch Workshop

In this workshop you will learn how to deploy Utilize FortiGate Automation Stitches on Azure in several different use cases

## FortiGate Automation Stitch TEC Workshop

Introduction:
As enterprises adopt the Cloud as the new core for application hosting, the application environments may change dynamically related to workload needs. Policies need to be dynamic to secure these changing environments. Utilizing configuration options of the FortiGate along with Cloud automation capabilities, security can be designed to automatically respond to environment evolution.

FortiGate Automation Stitches, Dynamic Address Objects, SDN Connectors and Azure Automation combined create a unique and powerful way to enhance Cloud security postures by

* Stitching together Triggers and Actions
* Recognizing changes to the Cloud environments
* Maintaining dynamic address objects comprising the IPs of target VM groups
* Executing FortiGate security and Azure routing updates in response to VM existence

The purpose of this Workshop is to explore and utilize the concepts specific to FortiGate Automation Stitches and their incorporation with Azure Cloud environment.

## Workshop Objectives

* Deploy using Terraform
  * One FortiGate VM
  * Two Linux VMs
  * Azure Automation Account
  * Azure Automation Runbook
* Configure FortiGate Automation Stitches
  * Email on user login - Easy
  * Update Azure Route Table triggered by VM existence and Tag - Complex

### About TEC Workshops

TEC Workshops provide the learner with the opportunity to put into practice newly developed skills in an easy to launch environment that can be used for customer engagements. At a minimum a TEC Workshop will include the following:

* A use case description
* An integrated lab and demo environment

  * Informational call-outs for key points to discuss or highlight to a customer
  * Questions that could be asked while giving the TEC Workshop as a demo
  * Points of value that relate the business value to the technical feature
* A reference architecture(s)

Optional components may be included for certain use cases

The TEC Workshop may not be a completely, self-contained learning experience for a single product. A TEC Workshop will cover features and often multiple products where they relate to the use case of interest.  

Deployments will be automated for those tasks that are not salient to the learning or demonstration activity in the use case. For example, for a TEC Workshop focused on Indicators of Compromise, the system may deploy a FortiGate and FortiAnalyzer with configurations for these systems. However, the leaner will have to configure the Event Handlers for IOC setup.
***

{{< notice warning >}}
The examples and sample code provided in this workshop are intended to be consumed as instructional content. These will help you understand how various Fortinet and Azure services can be architected to build a solution while demonstrating best practices along the way. These examples are not intended for use in production environments without full understanding of how they operate.
{{< /notice >}}
