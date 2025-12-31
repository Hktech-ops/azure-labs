# Lab 1: Manage Governance via Azure Policy

## Objective
- Implement organizations's governance plans
- Enforce operational decisions using Azure policy
- Use resource tagging to improve reporting


## Lab Scenario
Your organization's cloud footprint has grown considerably in the last year. During a recent audit, you discovered a substantial number of resources that do not have a defined owner, project, or cost center. In order to improve management of Azure resources in your organization, you decide to implement the following functionality:

1. apply resource tags to attach important metadata to Azure resources
2. enforce the use of resource tags for new resources by using Azure policy
3. update existing resources with resource tags
4. use resource locks to protect configured resources

## Architecture Diagram

<img width="1006" height="514" alt="image" src="https://github.com/user-attachments/assets/e3cbf194-c44a-4d1a-93b9-8004da5745f7" />

***************
## TASKS

Task 1. Create a RG and assign tags

<img width="955" height="434" alt="image" src="https://github.com/user-attachments/assets/64bacc00-2146-475b-a8df-60b4cc932773" />

-------------------------------


Task 2. Enforce tagging via an Azure Policy

Assingn built in policy named 'Require a tag and its value on resources' policy to the newly created RG, az104-rg2

grabbed policy definition id from portal = /providers/Microsoft.Authorization/policyDefinitions/1e30110a-5ceb-460c-a204-c1c3969c6d62

<img width="1083" height="382" alt="image" src="https://github.com/user-attachments/assets/514a4382-fb7a-4287-9b02-f35bdac15112" />

Now, assigning this policy to RG via portal

***Remember that you can't assign policy to Resource. It can be assigned to Resource Groups, Subscriptions or Management Groups

<img width="1618" height="576" alt="image" src="https://github.com/user-attachments/assets/a4630171-5cec-41d6-95ba-f543eb6faf03" />

- Policy implementation verified by creating a resource

-----------------------------------------

Task 3: Apply tagging via an Azure policy

----------------------------------------

Task 4: Configure and test resource locks

Apply a delete lock on Resource level

<img width="1203" height="174" alt="image" src="https://github.com/user-attachments/assets/a5b7535e-4da7-4db8-9d51-8b9dd4e4d1f5" />

<img width="1837" height="355" alt="image" src="https://github.com/user-attachments/assets/fe222452-71aa-4531-8670-44df16890e34" />


----------------------------------------

***Marks the end of this lab!
