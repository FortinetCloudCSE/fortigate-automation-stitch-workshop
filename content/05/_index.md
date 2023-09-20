---
title: "Chapter 5 - FortiGate Policy & Route"
chapter: true
weight: 5
---

## Fortinet FortiGate Automation Stitch Workshop

### Chapter 5 - FortiGate Policy & Route (5min)

The previous task was created a complex FortiGate Automation Stitch that when triggered caused a route table update in Azure utilizing and Azure Automation Runbook.

Why do this? To force traffic that would have otherwise flowed between VMs in the same subnet to go through the FortiGate. This enables the traffic to be inspected. In order for the FortiGate to inspect the traffic and then send it on to the desired destination a policy and a route are required to be configured in the FortiGate.

The **Policy** will allow all traffic between WebServers. By using Dynamic Addresses, as WebServers are deployed and deallocated in Azure, the Address object will be updated by the Azure SDN Connector.

The **Route** will indicate to the FortiGate which port to send the traffic out to reach the destination.

## Tasks

* Create a FortiGate Policy to allow WebServer to WebServer Communication
* Create a FortiGate Static Route to the WebServer Subnet

## Note

To complete these tasks configuration without having to go through the manual process use these following Terraform commands, while in the `terraform/fortios` directory.

```bash
terraform init
terraform apply -auto-approve
```
