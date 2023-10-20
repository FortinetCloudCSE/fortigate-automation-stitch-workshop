---
title: "Task 1 - SDN Connector & Dynamic Addresses"
chapter: true
weight: 2
---

### Task 1 - Create FortiGate Azure SDN Connector and Dynamic Address Objects

The completed Automation Stitch trigger will be when a log is recorded for the following events:

* Dynamic address added
* Dynamic address removed

These log events are recorded when a FortiGate Dynamic Address is updated by adding or removing an address. FortiGate Dynamic Addresses are updated when the conditions of the Dynamic Address filter are met.

The Dynamic address filters can utilize the data returned from the FortiGate Azure SDN Connector. The filters can match on several aspects of the Azure environment. The Dynamic address filters in this task will match on Azure Tags and Values.

The configurations are presented as a combination of FortiGate CLI commands and screenshots of the configured object.  All of the command blocks can be copied and pasted into the FortiGate CLI console.

1. **Login** to the FortiGate using the IP address and credentials from the Terraform output.
1. **Click** through any opening screens for FortiGate setup actions, no changes are required.
1. **Click** the CLI Console
1. **Enter** the following CLI commands to create an Azure SDN Connector named "AzureSDN"

    ```bash
    config system sdn-connector
        edit "AzureSDN"
            set type azure
            set status disable 
        next
    end
    ```

    ![sdnconnector1](../images/sdnconnector-01.jpg)
    ![sdnconnector2](../images/sdnconnector-02.jpg)

The Azure SDN Connector is set to **disable** for now, it will be set to **enable** in Task 5. The SDN Connector needs to exist for the Dynamic Addresses to refer to it, but at this point in the exercise it needs to remain disabled.

#### Create Dynamic Addresses

1. Use the FortiGate CLI Console to enter the following commands
1. Create **AppServers** Address

    ```bash
    config firewall address
        edit "AppServers"
            set type dynamic
            set sdn "AzureSDN"
            set filter "Tag.ComputeType=AppServer"
        next
    end
    ```

1. Create **DbServers** Address

    ```bash
    config firewall address
        edit "DbServers"
            set type dynamic
            set sdn "AzureSDN"
            set filter "Tag.ComputeType=DbServer"
        next
    end
    ```

1. Create **WebServers** Address

    ```bash
    config firewall address
        edit "WebServers"
            set type dynamic
            set sdn "AzureSDN"
            set filter "Tag.ComputeType=WebServer"
        next
    end
    ```

1. View the configured Addresses in the FortiGate UI
    * **Minimize** "CLI Console"
    * **Click** "Policy & Objects"
    * **Click** "Addresses"

      ![dynamicaddress1](../images/dynamicaddress-01.jpg)
      ![dynamicaddress2](../images/dynamicaddress-02.jpg)

As part of the environment deployment by Terraform:

* A linux VM with the name **vm-linux-2** was deployed
* A tag **ComputeType** with the value **WebServer** was added to the VM
* The VM data retrieved by the Azure SDN connecter matched the **WebServers** address filter
* The address object was populated with the IP address of the VM **vm-linux-2**

The red exclamation point near an address name indicates that the filter(s) for the address did not match anything.

1. View the Matched addresses in the FortiGate UI
    * **Hover** over the address name **WebServers**
    * **Click** the "View Matched Addresses" button

1. View an Address configuration in the FortiGate UI
    * **Double-Click** the **WebServers** Address

      ![dynamicaddress3](../images/dynamicaddress-03.jpg)
