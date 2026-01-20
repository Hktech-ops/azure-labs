## Lab 7 : Filter traffic with a Network Security Group and Application Decurity Group

## Lab Scenario:
This lab illustrates Filtering of Network traffic via NSG

## Architecture Diagram:

<img width="876" height="738" alt="image" src="https://github.com/user-attachments/assets/6f91ba17-a8d4-427a-b84c-c2c9f43c32a4" />

Following NSG rules will be implemented:

1. Allow HTTP traffic(port 80) on vm-1 via asg-web & block RDP traffic
2. Allow RDP traffic(port 3389) on vm-2 via asg-mgmt & block HTTP traffic
3. Diable outbound Internet traffic from both VMs

## Tasks

## Task 1: Creation of Resources - VNet, Subnet, ASG

<img width="830" height="420" alt="image" src="https://github.com/user-attachments/assets/52d284a2-0480-4b33-b84b-4aa09ee6bc9c" />

** Created a RG named lab7 **

<img width="590" height="501" alt="image" src="https://github.com/user-attachments/assets/501147de-5cb7-4199-ac02-056dc67607f4" />

** Created VNet and Subnet **

<img width="678" height="632" alt="image" src="https://github.com/user-attachments/assets/24b275f5-d3f7-4e45-b289-3587d79b76ea" />

** Created ASGs ** 

## Task 2: Creation of NSG and it's rules

<img width="721" height="454" alt="image" src="https://github.com/user-attachments/assets/493cc9ca-1b83-4bc0-b15d-e80cc98aa2c6" />

** Created NSG **

<img width="660" height="459" alt="image" src="https://github.com/user-attachments/assets/652bb0a3-c6ba-4c86-8f99-2885a83d811b" />

** Rule 1: Allow inbound traffic on port 80(HTTP) to asg-web

<img width="720" height="464" alt="image" src="https://github.com/user-attachments/assets/5e4c955b-97b5-4569-b0a1-58e99da8d13b" />

** Rule 2: Deny inbound traffic on port 3389(RDP) to asg-web



<img width="597" height="485" alt="image" src="https://github.com/user-attachments/assets/1cdd0a0f-b789-4152-9e8c-b9f0fa47f847" />

** Rule 3: Deny inbound traffic on port 80(HTTP) to asg-mgmt


<img width="661" height="457" alt="image" src="https://github.com/user-attachments/assets/a3b1f077-8d23-4f94-b710-430815960a93" />

** Rule 4: Allow inbound traffic on port 3389(RDP) to asg-mgmt


## Task 3: Associate nsg-1 with subnet-1

<img width="602" height="501" alt="image" src="https://github.com/user-attachments/assets/ccd956d5-2f80-428f-8638-b9163697a791" />


## Task 4: Deploy VMs and associate their NICs to ASGs

<img width="1631" height="667" alt="image" src="https://github.com/user-attachments/assets/dd63868e-a56b-4cae-b1e0-588adddb91b3" />

<img width="1687" height="642" alt="image" src="https://github.com/user-attachments/assets/7c26dbfa-0b74-4f38-b403-d964640de8c8" />

** Deployed 2 Windows VMs **

- Recall, we had created 2 ASGs earlier

<img width="1388" height="132" alt="image" src="https://github.com/user-attachments/assets/55f9089f-c7d0-44c0-a6f9-6ab1debe0812" />

** Queried ids of both ASGs - to be used in the next command **

<img width="978" height="444" alt="image" src="https://github.com/user-attachments/assets/1aa70fef-dfcb-4e82-9c9c-e4de7e05df05" />

<img width="1060" height="468" alt="image" src="https://github.com/user-attachments/assets/d20b4d85-f153-4ede-b1ce-833e6e365f31" />

** Associate NICs to their respective ASGs **

## Task 5: Put your architecture to test!




