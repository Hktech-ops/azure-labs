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




## Steps
1. Create a resource group
2. Create a user and group
3. Assign RBAC role
4. Test access
5. Remove access

## Scripts
- deploy.ps1: Creates RG and assigns role
- cleanup.ps1: Removes RG and role assignment

## Diagram
See /diagrams/rbac-diagram.png

## What I Learned
- Role scopes (RG, subscription)
- Least privilege principle
