# Introduction to Google Cloud Platform

## 1. What is Google Cloud Platform?
Google Cloud Platform, offered by Google, is a suite of cloud computing services that runs on the same infrastructure that Google uses internally for its end-user products, such as Google Search, Gmail, file storage, and YouTube.

The Google Cloud Platform allows us not only to rent servers, but to use services in order to handle different scenarios as well, such as delivering content via cdn, dealing with big traffic, etc.

## 2. Regions and Zones
Region: Spesific geographical location to host your resources.
Advantages: 
    - High Availability
    - Low latency
    - Global Footprint
    - Adhere to goverment regulations

Zones: Each region has three or more zones.
Advantages
    - Increase availability and fault tolerance within same region
    - Each zone has one or more discrete clusters ( Cluster: Distict physical infrastructure that housed in a data center )
    - Zone in region are connected through low-latency links

## 3. Google Compute Engine (GCE)
Google Compute Engine is the Infrastructure as a Service component of Google Cloud Platform which is built on the global infrastructure that runs Google's search engine, Gmail, YouTube and other services. Google Compute Engine enables users to launch virtual machines on demand. 
- Wikipedia

Feature of GCE :
- Create and manage lifecycle of Virtual Machine (VM) instances
- Load balancing and auto scaling for multiple VM Instances
- Attach storange (& Network Storage) to your VM Instances
- Manage network connectivity and configuration for your VM Instances

Pratice : 
- [Create VM Instance](https://www.loom.com/share/0aaab2855b084874aaf14096dc2df6a4)
- [Connect to VM Instace using SSH](https://www.loom.com/share/cd7d645c75bd4b42a036b0c46fc6a789)
- Command to practice setup http server
```bash
sudo su
apt update 
apt install apache2
ls /var/www/html
echo "Hello World!"
echo "Hello World!" > /var/www/html/index.html
echo $(hostname)
echo $(hostname -i)
echo "Hello World from $(hostname)"
echo "Hello World from $(hostname) $(hostname -i)"
echo "Hello world from $(hostname) $(hostname -i)" > /var/www/html/index.html
sudo service apache2 start
```
- [Setup HTTP Server in VM](https://www.loom.com/share/f0de9bc046a24140a69943abcbdc394e)

## 4. Internal & External IP Address
External IP: Used to talk with the internet.
Internal IP: Used to talk within VM Network.

Notes:
- When we stop the VM the public or external ip address will be changed.
- If you want to have VM with the same ip address use static ip address and attach it to the VM make sure to use the same region.
- Static IP Address is Billed even i you are not using it.
- Static IP Address remain attached even if the VM is stopped.
- Static IP Address can be switched to other VM address.

Practice :
- [Attach Static IP Address to VM Instance](https://www.loom.com/share/7835f5e1008d4bf3aea58787b9a02a28)

## 5. Compute Engine with Startup Script
It is useful to build startup scripts when you want to install and configure software for your VM instance.

Example startup script :
```bash
#!/bin/bash
apt update 
apt -y install apache2
echo "Hello world from $(hostname) $(hostname -I)" > /var/www/html/index.html
```

Practice :
- [Setup Startup Script](https://www.loom.com/share/e4073e5b989b41139e13b63053016ade)

## 6. Instance Template

Notes :
- Instance template can not be updated, you can do it but you need make a copy from it and then modify.
- With instance template we can deploy a group vm instance.

Practice :
- [Create VM instance Using Template](https://www.loom.com/share/75e6727e48b4419bb58aeed95e789a8b)
