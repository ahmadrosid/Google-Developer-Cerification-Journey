# Google Compute Engine

## Playing with Google Cloud Platform (Web) Console
- Use the pin icon to create a shortcut to a menu that you use frequently.
![GCP Pin menu](/assets/gcp_pin_menu.png)

## Virtual Machine - Best Practices
- Choose **Zone and Region** based on :
    - Cost, Regulations, Availability Needs, Latency and Specific Hardware needs
    - Distribute instances in multiple zones and regions for hight availability
- Choose **right machine type** for you needs:
    - Play with them to find out the right machine type
    - Use **GPUs** for Match Graphic intensive applications
- Use preemtible instance for fault-tolerant, NON time critical workloads
- Use **labels** to indicate environment, team, business unit etc.

## Scenarios - Virtual Machines in Google Cloud Platform
|Scenario   |Solution   |
|-----------|-----------|
|What are the pre-requisites to able to create a VM Instance?|1. Project <br />2. Billing Account <br />3. Compute engines APIs should be enabled|
|You want dedicated hardware for your compliance, licensing, and management|Sole tenant nodes|
|I have 1000s of VM and I want to automate OS patch management,<br />OS Inventory management and OS configuration management (manage software installed)|Use "VM Manager"|
|You want to login to your VM instance to install software|You can SSH into it|
|You do not want to expose a VM to internet|Do NOT assing an external IP Address|
|You want to allow HTTP traffic to you VM|Setup "Firewall" Rules|

How to request custom dedicated hardware.
```bash
Compute Engine -> Sole-tenant nodes -> Create -> Create Node Group
```

On `Create a node group` :
These properties are permanent and cannot be edited after creation.

1. Node group properties
2. Node template properties
    * Select node template
    * Or create new node template
3. Configure autoscaling
   Use autoscaling to allow automatic resizing of this node group for periods of high and low load.
4. Configure maintenance settings (optional)

![Create sole tenant nodes](/assets/create_sole_tenant_nodes.png)

How to use it when create new VM instance.
```bash
Compute Engine -> Create VM ->  Management, security, disks, networking, sole tenancy -> Sole Tenancy
```
And config the VM instance :
![Config VM Insance Sole tenancy](/assets/config_sole_tenancy.png)
