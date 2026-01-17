## Lab 6 - Implement Virtual Networking

## Lab Introduction:

- In this lab you will learn about basics of Virtual Networking and Subnetting, along with Network Security Group and Application Security Groups. You will also learn about DNS zones and records.


## Problem Statement:

Your global organization plans to implement virtual networks. The immediate goal is to accommodate all the existing resources. However, the organization is in a growth phase and wants to ensure there is additional capacity for the growth.

The CoreServicesVnet virtual network has the largest number of resources. A large amount of growth is anticipated, so a large address space is necessary for this virtual network.

The ManufacturingVnet virtual network contains systems for the operations of the manufacturing facilities. The organization is anticipating a large number of internal connected devices for their systems to retrieve data from.


## Architecture Diagram:

<img width="1313" height="668" alt="image" src="https://github.com/user-attachments/assets/50120ee9-452b-473a-b15d-ebf3adc7e2f3" />

## Tasks:

## Task 1: Create a virtual network with subnets:

<img width="584" height="203" alt="image" src="https://github.com/user-attachments/assets/1fba9952-4d43-411f-8cb8-d382808b0701" />

<img width="686" height="356" alt="image" src="https://github.com/user-attachments/assets/a03b2b6d-0029-429c-8f6e-96958192c5e8" />

- Created a VNet and subnets, per above mentioned parameters, using CLI:

<img width="1078" height="412" alt="image" src="https://github.com/user-attachments/assets/11d39e5b-63b4-4683-880a-101e0a67462f" />

** Created a new RG named az104-rg4 for this task **

<img width="736" height="699" alt="image" src="https://github.com/user-attachments/assets/a96f7a29-a7bb-4f25-a59f-30d7d8f11b1f" />

** Created a new VNet as per the ask **

<img width="616" height="412" alt="image" src="https://github.com/user-attachments/assets/cf3545b1-01c3-4942-a6b1-bb6e96ec9ff1" />

<img width="621" height="412" alt="image" src="https://github.com/user-attachments/assets/9dae56d1-5da8-4025-ad19-a73fca9083a6" />

** Created 2 subnets **

<img width="1410" height="475" alt="image" src="https://github.com/user-attachments/assets/7f315f80-de17-4fed-92b6-6be1b175648c" />

- Navigated to portal to verify and downloaded ARM template for the creation of VNet
- Exported ARM template contains both tempate.json and parameters.json


## Task 2: Create a virtual network and subnets using a template

Goal here is to use previously exported template to tweak it and create Manufactirung Vnet and its subnets

- Manufacturing VNet = 10.30.0.0/16
- Sensor Subnet1 = 10.30.20.0/24
- Sensor Subnet2 = 10.30.21.0/24

** Made necessary changes to the template and parameters file **


- Deployment can be done via portal > Deploy a custom template

- However, I uploaded both (template.json and parameters.json) files to the cloud shell and deployed using CLI (Alternatively it can also be done via PowerShell if files were stored locally on a host Windows machine!)

<img width="592" height="200" alt="image" src="https://github.com/user-attachments/assets/d94fc064-6b17-40f4-bf64-f93cad8a4789" />

** Validated first **

<img width="871" height="314" alt="image" src="https://github.com/user-attachments/assets/6def11d5-2ba8-442c-8e4b-f96a317bf1c1" />

<img width="1665" height="409" alt="image" src="https://github.com/user-attachments/assets/fde5ec96-0b48-4413-a50c-26b0347f72d0" />

** Deployed successfully **



## Task 3: Create and configure communication between an Application Security Group and a Network Security Group
## Task 4: Configure public and private Azure DNS zones


