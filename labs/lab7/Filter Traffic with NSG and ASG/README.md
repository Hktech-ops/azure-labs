## Lab 7 : Filter traffic with a Network Security Group and Application Securoity Group

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

<img width="609" height="483" alt="image" src="https://github.com/user-attachments/assets/c294e88d-8ca6-443d-b025-c7b1c7173a8e" />
** Rule 1: Allow inbound traffic on port 80(HTTP) from asg-web

<img width="572" height="459" alt="image" src="https://github.com/user-attachments/assets/576f4661-3fb9-41ef-b014-c3645794134b" />
** Rule 2: Deny inbound traffic on port 3389(RDP) from asg-web





** Rule 3: Allow inbound traffic on port 3389(RDP) from asg-mgmt


** Rule 4: Deny inbound traffic on port 80(HTTP) from asg-mgmt


