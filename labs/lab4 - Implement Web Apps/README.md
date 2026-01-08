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


** Created a web app

<img width="1724" height="536" alt="image" src="https://github.com/user-attachments/assets/c8740967-0cda-4c55-8e54-4234eecf89ea" />


# Task 2: Create and configure a deployment slot

-Added a stagig deployment slot 

<img width="1269" height="400" alt="image" src="https://github.com/user-attachments/assets/5e62ffdc-2fcf-4cf4-b567-73f72b653ab5" />


# Task 3: Configure web app deployment settings

- Linked staging slot with external Git code repo via CLI script

<img width="1373" height="665" alt="image" src="https://github.com/user-attachments/assets/7923ff2c-c6b7-4d7d-871d-f9ea3d7f8fd2" />

- Staging slot output

<img width="602" height="234" alt="image" src="https://github.com/user-attachments/assets/7b556d55-9192-4464-9550-9fda5d68da99" />


# Task 4: Swap deployment slots

Now that we have successfully tested staging slot, time to make it live on the production slot by swapping slots!

- Swap Staging ---> Production slot via CLI

<img width="585" height="154" alt="image" src="https://github.com/user-attachments/assets/2236a55f-a6ec-4371-9851-3ddf2436e496" />

- Output of the production slot after swapping

<img width="495" height="173" alt="image" src="https://github.com/user-attachments/assets/3d95e602-e908-40f6-bff0-1097e4c7b851" />


# Task 5: Configure and test autoscaling of the Azure web app

- Goal here is to scale out (horizontal scaling) with a maximum of 2 instances to cater to increased traffic!

- Navigate to App service plan to add a custom autoscale rule
   - Scale out by 1 instacne if average CPU usage >= 80%
   - Scale in by 1 instacne if average CPU usange < 30% 

<img width="1240" height="820" alt="image" src="https://github.com/user-attachments/assets/793bd925-2ede-4edc-83c7-cd583882eaff" />


- Created a Load Test of Web App

<img width="1539" height="436" alt="image" src="https://github.com/user-attachments/assets/e94638b1-818e-4be4-9eac-db1ff0efcb56" />

- Load test by adding HTTP requests (URL based test)

<img width="1852" height="823" alt="image" src="https://github.com/user-attachments/assets/0b354e30-d2bd-4191-9002-637bb51e6e3b" />

** Test results


***THIS MARKS THE END OF THIS LAB******


