# Google Compute Engine

## 7. Reducing Launch Time with Custom Image
We can speed up the creation of vm instance using custom image.

Practice :
- [Create VM with Custom Image](https://www.loom.com/share/be976217a4a04ab9b27991beaf9f9093)


## 8. Troubleshooting Launch of Apache on GCP Virtual Machine 
When you got a problem with the apache server, check this.
- Make sure the external IP Adress is accassable.
- Makse sure index.html file is available at `/var/www/html` folder.
- If the server not working, try to start apache using this command `sudo apache2 start`
- If the url is not working, check detail vm instance and then check on the `Firewalls` section and then check `Allow HTTP Traffic`

![Commited use discount](/assets/commited_use_discount.png)

## 9. Reducing Costs - Compute Engine Virtual Machines
| **Feature**   | **GCE**       |
| ------------- |:-------------:|
| Sustained use discounts | Automatic discounts for using resources for long periods of time. Example: If you use N1, N2 machine types fir nire than 25% of a mounth, you get a 20% to 50% discount on every incremental minute.|
| Comitted use discounts | Reserve compute instance ahead of time, Commit for 1 year or 3 years up to 70% discount based on machine type and GPUs |
| Preemtible VMs | Cheaper, temporary instances for non critical workloads (Fixed pricing, Max 24 hours, CHEAPEST ) |

How to create Preemptible VMs :
```bash
Create instance -> "Management, security, disks, networking, sole tenancy" -> Availability policy -> Preemptibility
```

## 10. Achieving High Availability with Live Migration and Automatic Restart
- How do you keep your VM instances running when a host system needs to be updated (a software or a hardware update needs to be performed)?
- **Live Migration**
    - Your running instance is migrated to another host in the same zone.
    - Does NOT change any attributes or properties of the VM
    - SUPPORTED for instaces with local SSDs
    - NOT SUPPORTED for GPUs and preemtible instances
- Important Configuration - **Availability Policy**
    - **On host maintenance**: What should happen during periodic infrastructure maintenance?
        - a. Migrate(default): Migrate VM instace to toher hardware
        - Terminate: Stop the VM Instance
    - **Automatic restart**: Restart VM instacen if they are terminated due to non-user-initiated reasons (maintenance event, hardware failure etc.)


How to configure Availability Policy: On host maintenance
```bash
Create instance -> "Management, security, disks, networking, sole tenancy" -> Availability policy -> On host maintenance
```

How to configure Availability Policy: Automatic restart
```bash
Create instance -> "Management, security, disks, networking, sole tenancy" -> Availability policy -> Automatic restart
```

![Availability Policy](/assets/availability_olicy.png)

