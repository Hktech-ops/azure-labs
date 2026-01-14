## Lab 4 - Implement Intersite Connectivity

## Lab introduction

 * Goals:
   
   *  Implement Virtual Network (VNet) peering and test connections
   *  Create a custom route


## Problem Statement:

Your organization segments core IT apps and services (such as DNS and security services) from other parts of the business, including your manufacturing department. However, in some scenarios, apps and services in the core area need to communicate with apps and services in the manufacturing area. In this lab, you configure connectivity between the segmented areas. This is a common scenario for separating production from development or separating one subsidiary from another.

## Architecture Diagram:

<img width="1314" height="550" alt="image" src="https://github.com/user-attachments/assets/da9c6c75-41f7-49ea-a3a9-11f50a89ba38" />

## Tasks

# Task 1 : Create a core services virtual machine and virtual network

<img width="997" height="598" alt="image" src="https://github.com/user-attachments/assets/3c80f1cb-6863-4400-8c7e-a1a0eadf99ac" />



* Created VM as per the availability

<img width="1670" height="638" alt="image" src="https://github.com/user-attachments/assets/5063a106-de99-4a13-9f6c-7965c2ec6037" />



# Task 2: Create a virtual machine in a different virtual network

<img width="736" height="613" alt="image" src="https://github.com/user-attachments/assets/12f98597-d40c-4682-8509-78fc75ff30ff" />


* Created a separate Vnet and subnet for Manufacturing VM

<img width="411" height="152" alt="image" src="https://github.com/user-attachments/assets/64de918b-0638-4ecf-88fa-24b456a76d5f" />


* Created second VM for Manufacturing

<img width="1653" height="620" alt="image" src="https://github.com/user-attachments/assets/938e858e-e9ec-4b59-86a5-33735946f64f" />


# Task 3: Use Network Watcher to test the connection between virtual machines


# Task 1 : Create and configure an Azure web app
