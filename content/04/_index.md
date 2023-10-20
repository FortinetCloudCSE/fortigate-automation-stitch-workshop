---
title: "Chapter 4 - FortiGate Complex Automation Stitch"
chapter: true
weight: 4
---

## Fortinet FortiGate Automation Stitch Workshop

### Chapter 4 - FortiGate Complex Automation Stitch (30min)

A FortiGate Automation Stitch brings together a Trigger and one or more Actions. In the previous chapter the goal was to create a simple automation stitch that was self-contained and resulted in a notification by email of an event but took no further action related to the event.

The tasks presented in this chapter will incorporate several components of the FortiGate and Azure. The goal of the Automation Stitch created by the next set of tasks is to **manage a host route in an Azure Route table**. The host route will be managed (added/deleted) in the Azure Route table based on the existence of a VM with a specific tag and a specific value.

An Azure Route table is used to provide a more specific route to data traffic in an Azure Virtual network. Azure Virtual network data traffic, by default, can route between all VMs in all subnets in the Virtual network. The traffic can be controlled by Azure Network Security Groups (NSGs) but not inspected.

The preferred way for traffic to flow would be through a Network Virtual Appliance (NVA), like a FortiGate, where the traffic can be inspected, this can be achieved by using a Route table. By associating subnets to a Route table, all routes in the Route table will supersede the default routes that the data traffic within the Virtual network normally utilizes, for the subnets included in the Route table. A Route table route can ensure that data traffic between subnets must utilize the FortiGate (NVA) as the next hop.

Data traffic from subnet to subnet can be inspected, but what about data traffic between VMs in the same subnet? For this type of routing Azure allows host routes in a Route table. A host route is a /32 route, this means that the most specific route in an Azure Route table can be a host's IP address. Adding a host route to the Azure Route table and specifying the next hop for that route to be the FortiGate, ensures that data traffic to the host must use the FortiGate as the next hop. Even if the traffic is coming from a VM in the same subnet as the host.

Ensuring that VM to VM data traffic in the same subnet is routed via the FortiGate is a form of micro-segmentation.

## Tasks

* Create a Complex Automation Stitch - Update an Azure Route table to micro-segment VMs in the same subnet, using host routes
* Create a FortiGate Azure SDN Connector in disabled mode
* Utilize FortiGate Dynamic Address Objects in FortiGate Policy
* Utilize FortiGate Log entries as an Automation Stitch trigger
* Utilize FortiGate Automation Stitch to trigger an Azure Automation Runbook
* Enable the FortiGate Azure SDN Connector
* Check that the Automation Stitch is working

## Note

To complete these task's configurations without having to go through the manual process use these following Terraform commands, while in the `terraform/fortios` directory.

```bash
terraform init
terraform apply -auto-approve
```
