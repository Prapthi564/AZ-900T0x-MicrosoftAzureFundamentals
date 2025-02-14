# Lab 05 - Create blob storage

## Lab Overview

Storage account is a resource that acts as a container that groups all the data services from Azure storage (Azure blobs, Azure files, Azure Queues, and Azure Tables). This helps us manage all of them as a group.

In this walkthrough, we will create a storage account, then work with blob storage files.

## Lab Objectives

In this lab, you will complete the following tasks:

+ Task 1: Create a storage account
+ Task 2: Work with blob storage
+ Task 3: Monitor the storage account

## Estimated timing: 15 minutes

## Architecture diagram

![](../images/az900lab05.PNG) 

### Prerequisites

1. In the **Lab-VM**, launch **Notepad** by searching for it in the Start menu, then input a random text within the **Notepad** application.

    ![](../images/L5-preq1.png)

1. Next, access the menu bar at the top and select **File > Save as**. Navigate to the Desktop directory, name the file as **Test**, and save the file to the desktop.

    ![](../images/L5-preq2.1.png)
    ![](../images/save-test-file.png)

### Task 1: Create a storage account

In this task, we will create a new storage account. 

1. 1. On Azure Portal page, in **Search resources, services, and docs (G+/) box** at the top of the portal, enter **Storage accounts**, and then select **Storage accounts** under services, and then click **+ Create**. 

    ![](../images/T1S1-1402.png)

1. On the **Basics** tab of the **Create storage account** blade, fill in the following information.Leave the defaults for everything else, then click on **Next**.

    | Setting | Value | 
    | --- | --- |
    | Subscription | **Choose the default subscription** |
    | Resource group | **myRGStorage-<inject key="DeploymentID" enableCopy="false" />** |
    | Storage account name | **storageaccount<inject key="DeploymentID" enableCopy="false" />** |
    | Region | **<inject key="Region" enableCopy="false"/>**  |
    | Performance | **Standard** |
    | Redundancy | **Locally redundant storage (LRS)** |

    ![](../images/T1S2-1402.png)

1. On the **Advanced** tab of the **Create a storage account**, choose **Hot** for **Access tier** setting under **Blob storage**.

    ![](../images/T1S3-1402.png)

1. Click **Review + create** to review your storage account settings and allow Azure to validate the configuration. 

1. Once validated, click **Create**. Wait for the **Deployment Succeeded** notification. 

1. From the Home page, search for and select **Storage accounts** and ensure your new storage account is listed.

    ![Screenshot of the newly created storage account in the Azure portal .](../images/AZ-9000501.png)

### Task 2: Work with blob storage

In this task, we will create a Blob container and upload a blob file. 

1. Click on the **storageaccount<inject key="DeploymentID" enableCopy="false" />** (newly created storage account), from the left navigation pane under **Data storage** section, and then click **Containers (1)** under Data storage.

    ![](../images/T2S1-1402.png)

1. Click **+ Container (2)** and complete the information. Use the Information icons to learn more. When done click **Create**.

   | Setting | Value |
   | ---- | ---- |
   | Name | **container1**|
   | Anonymous access level| **Private (no anonymous access)** |

    ![](../images/T2S2-1402.png)
    
    ![Screenshot of the newly created blob container in the storage account in the Azure portal.](../images/AZ-9000502.png)

1. Click the **container1** container, and then click **Upload**.

1. Browse to a file **Test.txt** that you created in a previous task, located on the desktop, then select the file and select **Open**.
  
1. Click the **Advanced** arrow, leave the default values but review the available options, and then click **Upload**.

    >**Note:** You can upload as many blobs as you like in this way. New blobs will be listed within the container.

1. Once the file is uploaded, right-click on the file and notice the options including View/edit, Download, Properties, and Delete. 

   >**Note:** In the event that the access level for the storage account is configured as public, accessing the contents of the storage account can be done through a URL. To gain a deeper understanding of Storage Account access levels, please go through the following link:[Access Levels](https://learn.microsoft.com/en-us/azure/storage/blobs/anonymous-read-access-configure?tabs=portal).

1. As you have time, from the storage account blade, review the options for Files, Tables, and Queues.

### Task 3: Monitor the storage account

In this task, familiarize yourself with the monitoring tools and insights provided for managing and troubleshooting your storage account's health and performance.

1. If needed, return to the storage account blade and click **Diagnose and solve problems**. 

1. Explore some of the most common storage problems. Notice there are multiple troubleshooter.

1. On the storage account blade, scroll down to the **Monitoring** section and click **Insights**. Notice there is information on Failures, Performance, Availability, and Capacity. Your information will be different.

    ![Screenshot of the storage account Insights page.](../images/AZ-9000503.png)

   <validation step="920a6ecb-b2ae-40e8-92c8-10039a6017e0" />

   > **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:
   > - Hit the Validate button for the corresponding task. If you receive a success message, you have successfully completed the task. 
   > - If not, carefully read the error message and retry the step, following the instructions in the lab guide.
   > - If you need any assistance, please contact us at labs-support@spektrasystems.com. We are available 24/7 to help
   
### Review
In this lab, you have completed:
- Create a storage account
- Work with blob storage
- Monitor the storage account

## Reference link

- https://learn.microsoft.com/en-us/azure/storage/blobs/quickstart-storage-explorer

## You have successfully completed this lab.
