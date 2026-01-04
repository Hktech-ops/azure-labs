## Lab 8 - Manage Virtual Machines


## Lab Introduction:

In this lab, you create and compare virtual machines to virtual machine scale sets. You learn how to create, configure and resize a single virtual machine. You learn how to create a virtual machine scale set and configure autoscaling.

This lab requires an Azure subscription. Your subscription type may affect the availability of features in this lab. You may change the region, but the steps are written using East US.


## Lab Scenario:

Your organization wants to explore deploying and configuring Azure virtual machines. First, you implement an Azure virtual machine with manual scaling. Next, you implement a Virtual Machine Scale Set and explore autoscaling.


## Showcased Skills:

- Deploy zone-resilient Azure virtual machines by using the Azure portal.
- Manage compute and storage scaling for virtual machines.
- Create and configure Azure Virtual Machine Scale Sets.
- Scale Azure Virtual Machine Scale Sets.
- Create a virtual machine using Azure PowerShell (optional 1).
- Create a virtual machine using the CLI (optional 2).


## Architecture Diagram:

<img width="622" height="654" alt="image" src="https://github.com/user-attachments/assets/8ff7f616-84aa-44a0-8d19-8ab295c233f2" />

---------------------------

## TASK 1 - Deploy zone-resilient Azure virtual machines

a. Created a new Resource Group with appropriate tag

<img width="831" height="388" alt="image" src="https://github.com/user-attachments/assets/c4d24b2f-6aa4-443b-868f-25459bf0c1ac" />


b. Created two VMs, per the required parameters

<img width="968" height="594" alt="image" src="https://github.com/user-attachments/assets/557c1f93-17ea-4271-8b7c-88081af87c8b" />

2 VMs for zone redundancy - Zones 1 and 2. As per SLA, when you deploy 2 VMs in 2 or more zones - you get 99.99% availability!

<img width="1627" height="455" alt="image" src="https://github.com/user-attachments/assets/52fa809a-19f0-4b66-8473-c8260a6811b7" />


## Task 2 - Manage compute and storage scaling for virtual machines

Goal here is to alter the size of the previously created VM by changing it's size to a different SKU

SKU here represents a combination of vCPUs, RAM and Storage capacity (Data disks). This concept is known as Vertical Scaling (up or down), which results in a bit of downtime as the VM needs to be shut and re-started.

a. Navigate to the first VM > Size to Vertically downgrade the VM to a lower specs machine!

Earlier VM size - 2 vCPUs, 16 Gigs of RAM and 4 Data Disks (L2Oas_V4)

New (downgraded) size - 2 vCPUs, 4 Gigs of RAM and 8 Data Disks (D2s_V6)

downgrading is done based on the options available in the selected region - Central Europe

<img width="1472" height="491" alt="image" src="https://github.com/user-attachments/assets/51efba86-da3a-4b93-928a-f0c0d2c03202" />

** Next, attached a new Data Disk with the following specifications

<img width="248" height="154" alt="image" src="https://github.com/user-attachments/assets/f2975d70-c9da-45b0-ad70-dc4404450bc9" />

<img width="1882" height="357" alt="image" src="https://github.com/user-attachments/assets/7c6a9146-71df-41a0-87e6-91d4ff033c0c" />

** So by now, we have created Zone redundant VM, and done horizontal scaling (scaled SKU and data disk size)

------------------------------------

VM Scale Set (VMSS) Architecture diagram:

<img width="584" height="620" alt="image" src="https://github.com/user-attachments/assets/64f8ca52-7940-4f9c-ad94-1e8b32c8cb8f" />

-------------------------------------

## Task 3: Create and configure Azure Virtual Machine Scale Sets

Goal here is to deploy VM Scale Set across availability zones. VMSS reduce the administrative workload by using metrics (or conditions) to horizontally scale in or scale out.

** Created VMSS per these parameters:

<img width="798" height="554" alt="image" src="https://github.com/user-attachments/assets/e2152ffe-6ac7-48f0-906b-474a18db74ba" />

- Uniform orchestraton implies all VM instances would be identical

- VMSS with disk and networking + Created NSG to allow HTTP traffic. Additionally, added a Load balancer with public IP addess


## Task 4 - Scale Azure Virtual Machine Scale Sets:

Goal is to scale previously deployed VMSS using custom scale rule

--------------------------------------

- A word or two about scaling:
  - There are two types of scaling - Manual and Custom autoscale
  - Manual scaling may be a better option if there are small # of instances
  - Custom autoscale may be appropriate with larger # of VM instances

- An Azure Administrator needs to take a best call based on the organization requirements and choose the best option

---------------------------------------

For 'vmss1' created a custom autoscale rule which increases # of instances (scales out) by 50% when average CPU load is 70% or above for a 10 minute period

<img width="875" height="548" alt="image" src="https://github.com/user-attachments/assets/b9ee144c-fcac-4247-9662-eed1e3c96cd8" />


** Added custom auto scale out rule

<img width="767" height="790" alt="image" src="https://github.com/user-attachments/assets/a3def616-f624-4342-9c1a-383ab8789722" />

** For best optimization of resources, added a scale in rule to address low usage on weekends

Conditoons for scale in rule : decrease VM instances by 20% when average CPU load drops below 30%, over a 10 min period

<img width="1100" height="347" alt="image" src="https://github.com/user-attachments/assets/ec4f81f7-a974-4246-b9c2-871200e073d7" />


------------------------------------------

** As an additional task - I created a VM using powershell

<img width="1050" height="689" alt="image" src="https://github.com/user-attachments/assets/34c0adc5-85a7-4d95-a81a-4bea122a7586" />

<img width="1797" height="401" alt="image" src="https://github.com/user-attachments/assets/3861a754-0edc-4dd8-9683-d948780da084" />



** THIS MARKS END OF THIS LAB**



