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

## Quick review of Compute Engine

### Image
- What **operating system** and what **software** do you want on the VM instance?
- Reduce boot time and improve security by createing custom **hardened image**.
- You can share an Image with other projects.

### Machine Types
- Optimized combination of compute(CPU, GPU), memory, dist (storage) and networking for specific workloads.
- You can **create your own Custom Machine Types** when existing ones don't fit your needs.
- **Static IP Addresses**: Get a constant IP addresses for VM instances.
- **Instance Templates**: Pre-configured template simplifying the creation of VM instances.
- **Sustained use discount**: Automatic discounts for running VM instances for significant portion of the billing month.
- **Committed use discount**: 1 year or 3 year reservations for workloads with **predictable resource** needs.
- **Preemtible VM**: Short-lived cheaper (upto 80%) compute instaces for non-time critical fault-tolerant workloads.

## Questions
<details>
    <summary>1. What does 2 in the Machine Type e2-standard-2 represent?</summary>

    2 vCPUs
</details>

<details>
    <summary>2. How can you avoid specifying all the VM instance details every time you create a VM?</summary>

    Create an Instance Template
</details>

<details>
    <summary>3. Which of these is the preferred option to reduce the launch time of a VM instance? (startup script/ custom image)</summary>

    Custom image
</details>

<details>
    <summary>4. You want to keep your costs to a minimum. Which of these would you use for a non-time-critical fault-tolerant batch program?</summary>

    Preemtible VM
</details>

<details>
    <summary>5. Which of these is recommended for a web application that is expected to run continuously for years serving hundreds of thousands of users?
    </summary>

    Committed use discount
</details>
