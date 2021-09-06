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
