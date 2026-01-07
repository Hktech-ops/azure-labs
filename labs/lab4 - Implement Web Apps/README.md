## Lab 4 - Implement Web Apps

## Lab introduction

 * Goals:
   
   *  Configure a Web App to display an application in external GitHub repo
   *  Create a staging slot
   *  Swap with the production slot
   *  Autoscale to accomodate demand chnages


## Problem Statement:

Your organization is interested in Azure Web apps for hosting your company websites. The websites are currently hosted in an on-premises data center. The websites are running on Windows servers using the PHP runtime stack. The hardware is nearing end-of-life and will soon need to be replaced. Your organization wants to avoid new hardware costs by using Azure to host the websites.

## Architecture Diagram:

<img width="1315" height="716" alt="image" src="https://github.com/user-attachments/assets/4b47e843-8c84-4040-8476-9bcd498ee637" />


## Tasks

# Task 1 : Create and configure an Azure web app

- Set subscription and created a new ResourceGroup

<img width="651" height="508" alt="image" src="https://github.com/user-attachments/assets/7dc8a0f8-0654-496b-b55b-4a45545954f6" />

<img width="1164" height="520" alt="image" src="https://github.com/user-attachments/assets/f4281c1d-8876-4722-b7fd-d483664c4e4b" />



<img width="1633" height="486" alt="image" src="https://github.com/user-attachments/assets/8fae18ee-9ede-421f-b9c5-fffac5e6dd0d" />


# Task 2: Create and configure a deployment slot

-Added a stagig slot

<img width="1269" height="400" alt="image" src="https://github.com/user-attachments/assets/5e62ffdc-2fcf-4cf4-b567-73f72b653ab5" />


# Task 3: Configure web app deployment settings

- Linked staging slot with external Git code repo

<img width="1062" height="751" alt="image" src="https://github.com/user-attachments/assets/c2a2b48b-38b1-47c7-801e-889fa7408ca0" />

Staging slot outout




# Task 4: Swap deployment slots

Now that we have successfully tested staging slot, time to make it live on the production slot by swapping slots!




# Task 5: Configure and test autoscaling of the Azure web app

- Goal here is to scale out (horizontal scaling) with a mazimum of 2 instances to cater to increased traffic!

- Added autoscale rule
   - Scale out by 1 instacne if average CPU usage >= 80%
   - Scale in by 1 instacne if average CPU usange < 30% 

<img width="1240" height="820" alt="image" src="https://github.com/user-attachments/assets/793bd925-2ede-4edc-83c7-cd583882eaff" />




