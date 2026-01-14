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

* Verified - both VMs are running

<img width="988" height="221" alt="image" src="https://github.com/user-attachments/assets/ddcb808b-d12c-4d23-b032-5febc49492d5" />

- Now that both the VMs are setup on two different VNets - we will test connection using a Network Watcher

<img width="897" height="563" alt="image" src="https://github.com/user-attachments/assets/3d536078-ff2f-4c65-9537-8953bb68f0e2" />

***Results of Connectivity test*****

<img width="1245" height="528" alt="image" src="https://github.com/user-attachments/assets/10b571de-aabc-48dd-8a16-0b2d3e9fe987" />

- Why connectivity test shows unreachable ?
   - Resources deployed in different VNets won't communicate unless there is an established relationship between them!

- To solve this and make them connect, we will configure VNet peering b/w the two Networks!


# Task 4 : Configure virtual network peerings between virtual networks

<img width="1231" height="407" alt="image" src="https://github.com/user-attachments/assets/86f41008-3d49-4f85-813e-896ea5b4306e" />

*** Configured Bi-directional peering b/w 2 Vnets via CLI ****

<img width="1393" height="246" alt="image" src="https://github.com/user-attachments/assets/26807e5e-43e5-4028-b7d4-ecffc8500736" />

* Extracted both VM's ids to be used in the script

<img width="1438" height="372" alt="image" src="https://github.com/user-attachments/assets/8b2f9421-2042-406c-9604-638754e17957" />

<img width="1549" height="319" alt="image" src="https://github.com/user-attachments/assets/f02eb43d-081a-43af-b486-2656865eadac" />

<img width="1148" height="149" alt="image" src="https://github.com/user-attachments/assets/8baf896b-dcf2-4914-a8cd-fc0989579e52" />

<img width="1144" height="159" alt="image" src="https://github.com/user-attachments/assets/45795c2d-8752-492c-9fb5-4ecb5a150721" />


# Task 5: Use Azure PowerShell to test the connection between virtual machines

* Private IP of CoreServicesVM = 10.0.0.4
* Pricate IP of Manufacturing VM = 172.16.0.4

- Alright so now that we have peered both VNets and set NSG rules allowing network traffic to flow either way - time to test connection from ManufacturingVM to CoreServicesVM

- I could have launched ManufacturingVM via RDP to Test-NetConnection command, however, I'm using the ability of Azure portal to run commands 

** Test RDP traffic on CoreServicesVM via internal IP address ***
Test-NetConnection 10.0.0.4 -port 3389

<img width="1387" height="842" alt="image" src="https://github.com/user-attachments/assets/f2fadb4a-bbcc-483e-a6fa-267733170c07" />


# Task 6: Create a custom route (User defined route) to route traffic to perimeter subnet before reaching to core subnets

- Goal here is to divert routing traffic coming to CoreServices to a perimeter subnet first and then to core subnet to have better control

- Why? By default, Azure's behaviour is to allow all subnets inside a VNet (or a peered VNet) talk to each other freely..... We are limiting this very behaviour to force internal traffic to pass through perimeter subnet first

<img width="363" height="156" alt="image" src="https://github.com/user-attachments/assets/92764e45-9c17-4930-a416-51d7a3f75646" />

- Created a new perimeter subnet

<img width="1008" height="403" alt="image" src="https://github.com/user-attachments/assets/39d10193-e739-4d91-add2-ad8474150109" />

- Next, created a new route table, per these specifications

<img width="500" height="306" alt="image" src="https://github.com/user-attachments/assets/4f53907c-04a9-49c2-bd10-a890f53bf27a" />

<img width="1597" height="557" alt="image" src="https://github.com/user-attachments/assets/d30968b3-54b2-47e7-9c14-07538c40c8fe" />

- Finally, associated core subnet with the rout (perimieter subnet)

<img width="1265" height="607" alt="image" src="https://github.com/user-attachments/assets/07755eb5-81bb-4fa1-810f-5bd850375f94" />


* Benefits of creating a perimeter subnet :

   * Without perimeter, internal traffic (from manufacturing) flows directly to core subnets without inspection or control
   * With perimter, traffic flows from core subnet --> perimter (any virtual appliance VM/Firewall, Router etc.) and out to the other Vnet  

****** THIS MARKS THE COMPLETION OF THE LAB *********
