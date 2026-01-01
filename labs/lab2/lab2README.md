## Lab 2: Manage Azure Storage

--------------------------

## Objectives:

1. Create storage accounts for Azure blobs and files
2. Configure and secure blob containers
3. Configure and secure Azure files shares using Storage Browser

---------------------------

## Lab scenario:

Your organization is currently storing data in on-premises data stores. Most of these files are not accessed frequently. You would like to minimize the cost of storage by placing infrequently accessed files in lower-priced storage tiers. You also plan to explore different protection mechanisms that Azure Storage offers, including network access, authentication, authorization, and replication. Finally, you want to determine to what extent Azure Files is suitable for hosting your on-premises file shares.

----------------------------

## Architecture Diagram:

<img width="865" height="714" alt="image" src="https://github.com/user-attachments/assets/0bb418a3-7ff7-433b-a37c-f8a14eb8c78a" />

----------------------------

## Tasks:

TASK 1. Create and configure a storage account with the following parapeters

<img width="1201" height="423" alt="image" src="https://github.com/user-attachments/assets/0e6e5458-ec6f-45e0-87d3-9892ea35b621" />



**Created a RG and storage account

<img width="1344" height="363" alt="image" src="https://github.com/user-attachments/assets/cff3d484-cfab-4636-9aa2-6912fd37def6" />

<img width="1497" height="717" alt="image" src="https://github.com/user-attachments/assets/aa2a5136-f351-4231-b799-0cb0712ab24e" />

For increased security and scope of this lab, enabled public network access from my IP address (selected IP address)

** For reducing costs, created Life Cycle Management rule comprising 3 parameters:

      - Base blobs : Move to cool access tier, if haven't modified in 30 days
      - Snapshots : Delete snapshots create more than 30 days ago
      - Delete blob version created more than 7 days ago

<img width="1153" height="580" alt="image" src="https://github.com/user-attachments/assets/1a959117-dc0e-4f40-af44-89192b2fb10d" />



TASK 2. Create and configure secure blob storage:

**Created a blob container with time based retention policy

<img width="1601" height="647" alt="image" src="https://github.com/user-attachments/assets/7f1adb16-34c8-42b0-8d69-1428b0234449" />

time based retention of immutable blob storage at container level for 180 days

** In order to upload files, I needed ton grant myself appropriate permission

** Granted 'Storage Blob Data Contributor' and 'Storage File Data Privileged Contributor' for scope = storage account

<img width="1471" height="392" alt="image" src="https://github.com/user-attachments/assets/98dd9d93-4cee-4afc-af6f-590a42443522" />

<img width="1593" height="723" alt="image" src="https://github.com/user-attachments/assets/b523156a-b183-41a0-92cd-126f5e17fbe4" />



** Copied a file from on-premises computer to the newly created containe using AzCopy

Now that i have sufficient permission, I can go ahead to copy file to container!

<img width="1461" height="305" alt="image" src="https://github.com/user-attachments/assets/b4cf77c8-8ff6-4bde-963b-871b36d78bfa" />

** To grant secure access - created a time bound Access policy

<img width="655" height="320" alt="image" src="https://github.com/user-attachments/assets/3339413c-f357-4b68-8420-806551553e70" />


** Verified the file access by generating SAS token

<img width="757" height="491" alt="image" src="https://github.com/user-attachments/assets/1dd4f499-1ef6-4abb-aa90-32ef68d2a852" />



and again verified after the speficied time lapsed - authentication failed error!

<img width="1423" height="302" alt="image" src="https://github.com/user-attachments/assets/1b2d2612-3802-4518-b0b6-5b7436811cc3" />


Task 3: Create and configure an Azure File storage

** Created a File Share named lab2fileshare1 via portal

Uploaded a file via AzCopy

<img width="1472" height="413" alt="image" src="https://github.com/user-attachments/assets/1c644206-9c18-4fac-9fc4-3d7666b3597b" />

** Restrict Network access to storage account:

- Created a VNet

<img width="558" height="442" alt="image" src="https://github.com/user-attachments/assets/1ee98e13-ce65-4033-ae15-4f6ad29820d8" />

- Added a new service end point for this VNet

<img width="1505" height="444" alt="image" src="https://github.com/user-attachments/assets/8e62f1e7-6044-4790-ab44-90e1be0d9ef6" />

- In order to restrict anyone on the poublic to view files, Added VNet to the storage account - allowting only devices connected to VNet to access this storage account!

<img width="1252" height="772" alt="image" src="https://github.com/user-attachments/assets/22ab9afd-7289-42f7-af0b-f329a47b8f07" />


** Now uploaded blobs and file share are NOT accessible, unless it is accessed from VNet!

** You can view the storage account but can't access it's containers

** Verified by attempting to access both blob containers and file share

<img width="1593" height="718" alt="image" src="https://github.com/user-attachments/assets/6429f6f2-8514-4843-b53f-971bcac7c21f" />

<img width="1342" height="671" alt="image" src="https://github.com/user-attachments/assets/2e57daa3-41a7-4d01-8f11-b64d2efd0e99" />


**** THIS MARKS THE END OF LAB








