# Lab 05 - Create Blob Storage

### Estimated Timing: 15 Minutes

## Lab Overview

A storage account is a resource that acts as a container that groups all the data services from Azure storage (Azure Blobs, Azure Files, Azure Queues, and Azure Tables). This helps us manage all of them as a group.

In this walkthrough, we will create a storage account and then work with blob storage files.

## Lab Objectives

In this lab, you will be able to complete the following tasks:

+ **Task 1:** Create a Storage Account
+ **Task 2:** Work with Blob Storage
+ **Task 3:** Monitor the Storage Account

## Architecture Diagram

![](../images/az900lab05.PNG) 

### Prerequisites

1. In the **Lab-VM**, search for **Notepad (1)** in the **Start menu**, then launch **Notepad (2)**. Finally, input a random text within the **Notepad application**.

   ![](../images/az-900-54.png) 

1. Next, access the menu bar at the top and select **File (1)> Save as (2)**.

   ![](../images/az-900-55.png) 

1. Navigate to the **Desktop (1)** directory, name the file **Test (2)**, and **Save (3)** the file to the desktop.

   ![](./images/az-900-59.png) 

### Task 1: Create a Storage Account

In this task, we will create a new storage account. 

1. On the **Azure Portal** page, from the **Azure services** blade, search for **Storage accounts (1)** and select **Storage accounts (2)**.

   ![](./images/az-900-44.png) 

1. Click on **+ Create**. 

   ![](./images/az-900-45.png) 

1. On the **Basics** tab of the **Create a storage account** blade, fill in the following information. Leave the rest as default, then click on **Next (7)**.

    | Settings | Values | 
    | --- | --- |
    | Subscription | **Choose the default subscription (1)** |
    | Resource group | **AZ-900-<inject key="DeploymentID" enableCopy="false"/> (2)** |
    | Storage account name | **storageaccount<inject key="DeploymentID" enableCopy="false" /> (3)** |
    | Region | **<inject key="Region" enableCopy="false"/> (4)**  |
    | Performance | **Standard (5)** |
    | Redundancy | **Locally redundant storage (LRS) (6)** |
    
      ![Screenshot of the newly created storage account in the Azure portal .](../images/5-1.png)

1. On the **Advanced** tab of **Create a storage account**, choose **Hot (1)** for the **Access tier** setting under **Blob storage**, then click on **Review + create (2)**.

   ![](./images/az-900-46.png) 

1. Once validated, click on **Create**. Wait for the **Deployment Succeeded** notification.

   ![Screenshot of the newly created storage account in the Azure portal .](../images/5-2.png)

1. From the **Home** page, search for and select **storageaccount** and ensure your new storage account is listed.

    ![Screenshot of the newly created storage account in the Azure portal .](./images/az-900-60.png)

### Task 2: Work with Blob Storage

In this task, we will create a blob container and upload a blob file. 

1. Click on the **storageaccount<inject key="DeploymentID" enableCopy="false" />** (newly created storage account).

   ![](./images/az-900-60.png) 

1. From the left navigation pane under the **Data storage** section, click on **Containers (1)**. Click on **+ Container (2)** and complete entering all the required information. Use the information icons to learn more. When done, click on **Create (5)**.

   | Settings | Values |
   | ---- | ---- |
   | Name | **container1 (3)**|
   | Anonymous access level| **Private (no anonymous access) (4)** |

   ![](./images/az-900-47.png)    
  
1. Click on the **container1** option.

   ![](./images/az-900-48.png) 

1. Click on **Upload**.

   ![](./images/az-900-49.png) 

1. Click on **Browse to a file (1)**, then select **Test.txt (3)** that you had created in a previous task, located on the **Desktop (2)**. Then select the file and click on **Open (4)**.

   ![](./images/az-900-50.png) 
  
1. Click on the **Advanced** arrow, leave the default values but review the available options, and then click on **Upload**.

   ![](./images/az-900-51.png) 

    >**Note:** You can upload as many blobs as you like in this way. New blobs will be listed within the container.

1. Once the file is uploaded, right-click on the file and notice the options, including **View/edit, Download, Properties, and Delete**. 

   ![](./images/az-900-62.png) 

   >**Note:** In the event that the access level for the storage account is configured as public, accessing the contents of the storage account can be done through a URL. To gain a deeper understanding of Storage Account access levels, please go through the following link: [Access Levels](https://learn.microsoft.com/en-us/azure/storage/blobs/anonymous-read-access-configure?tabs=portal)

1. As you have time, from the storage accounts blade, review the options for **File shares, Tables, and Queues**.

   ![](./images/az-900-53.png) 

### Task 3: Monitor the Storage Account

1. If needed, return to the **storageaccount<inject key="DeploymentID" enableCopy="false" />** blade, and from the left navigation menu, click on **Diagnose and solve problems**. 

   ![](./images/az-900-57.png) 

1. Explore some of the most common storage problems. Notice there are multiple troubleshooters.

1. On the **storageaccount** blade, from the left navigation menu, scroll down to the **Monitoring (1)** section and click on **Insights (2)**. Notice there is information on *Failures, Performance, Availability, and Capacity*.

    ![Screenshot of the storage account Insights page.](./images/az-900-58.png)

    >**Note:** In your Lab-Vm information will be different.

> **Congratulations** on completing the task! Now, it is time to validate it. Here are the steps:
> - Click on the **Validate** button for the corresponding task. If you receive a success message, you can proceed to the next task. 
> - If not, carefully read the error message and retry the step, following the instructions in the lab guide.
> - If you need any assistance, please contact us at labs-support@spektrasystems.com. We are available 24/7 to help.

<validation step="8f85ae2c-c70e-4d55-9443-7e1b7e19a6cf" />

## Summary
In this exercise, we created a storage account and worked with blob storage to manage data efficiently. We also monitored the storage account to ensure optimal performance and health. Throughout the exercise, we gained practical experience in setting up and managing cloud storage, utilizing blob storage for data storage, and monitoring the account for any issues or performance metrics.

## Review
In this lab, you have:
- Created a storage account.
- Worked with blob storage.
- Monitored the storage account.

## Reference Link

- https://learn.microsoft.com/en-us/azure/storage/blobs/quickstart-storage-explorer

## You have successfully completed this lab.
