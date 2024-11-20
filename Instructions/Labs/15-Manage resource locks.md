# Lab 15 - Manage Resource Locks

### Estimated Timing: 15 Minutes

## Lab Overview

To protect your Azure resources from accidental deletions or modifications, you can use management locks. These locks allow you to enforce restrictions at different levels: subscription, resource group, or individual resource.

**Read-Only Locks:** A read-only lock allows read access but prevents any modification to a resource and deletion. Although still allowing authorized users to examine the resource, this kind of lock is important for preventing unintentional modifications to crucial resources.

**Delete Locks:** You cannot delete the resource, but the authorized user can read and modify the resource. This kind of lock is helpful for preventing unintentional or unauthorized deletion of crucial resources.

In this walkthrough,  we will verify the existing resource group, add a lock to the resource group and test deletion, test deleting a resource in the resource group, and remove the resource lock.

## Lab Objectives

In this lab, you will be able to complete the following tasks:

+ **Task 1:** Verify the Existing Resource Group
+ **Task 2:** Add a Lock to the Resource Group and Test Deletion
+ **Task 3:** Test Deleting a Member of the Resource Group
+ **Task 4:** Remove the Resource Lock

## Architecture Diagram

![](../images/az900lab15.png)

### Task 1: Verify the Existing Resource Group

In this task, we will verify the existing resource group for this exercise. 

1. On the **Azure Portal** page, in the **Search Resources, Services, and Docs** (G+/) box at the top, enter **Resource groups (1)**, and then select **Resource groups (2)** under **Services**.

   ![image](../images/lab14-image1.png)

1. View the existing resource group **AZ-900-<inject key="DeploymentID" enableCopy="false"/>**

### Task 2:  Add a Lock to the Resource Group and Test Deletion

In this task, we will add a resource lock to the resource group and test deleting the resource group. 

1. In the **Azure Portal** page, navigate to the existing resource group **AZ-900-<inject key="DeploymentID" enableCopy="false"/>**.

1. You can apply a lock to a subscription, resource group, or individual resource to prevent accidental deletion or modification of critical resources. 

1. Expand the **Settings** section, click on **Locks (1)**, and then click on **+ Add (2)**. 

    ![](../images/lab15-image2.png)

1. Configure the new lock. When you are done, click on **OK (3)**. 

    | Settings | Values | 
    | --- | --- |
    | Lock name | **RGLock (1)** |
    | Lock Type | **Delete (2)** |
    |||

    ![](../images/lab15-image3.png)

1. On the **AZ-900-<inject key="DeploymentID" enableCopy="false"/> | Locks** blade, from the left navigation, select **Overview**.

1. On the **AZ-900-<inject key="DeploymentID" enableCopy="false"/>** blade, click on **Delete resource group (1)**. Copy the **Resource Group** name **(2)** and paste it into the **Enter resource group name to confirm deletion (3)** and click on **Delete** **(4).** Confirm the deletion by selecting **Delete** on the **Delete Confirmation** window.

   ![](../images/lab15-image4.png)

1. You will receive an error message stating the resource group is locked and cannot be deleted.

    ![](../images/lab15-image5.png)

### Task 3: Test Deleting a Member of the Resource Group

In this task, we will test if the resource lock protects a storage account in the resource group. 

1. On the **Azure Portal** page, in the **Search Resources, Services, and Docs** (G+/) box at the top, enter **Storage accounts (1)**, and then select **Storage accounts (2)** under **Services**.

    ![](../images/lab15-image6.png)
  
1. On the **storageaccounts** blade, click on **+ Create**. 

1. On the **Basics** tab of the **Create a storage account** blade, fill in the following information. Leave the rest as default and click on **Review + create (7)**.

    | Settings | Values |
    | --- | --- |
    | Subscription | **accept the default (1)** |
    | Resource group | **AZ-900-<inject key="DeploymentID" enableCopy="false"/> (2)** |
    | Storage account name | **strgaccount<inject key="DeploymentID" enableCopy="false" /> (3)** |
    | Region | **<inject key="Region" enableCopy="false"/> (4)**   |
    | Performance | **Standard (5)** |
    | Replication | **Locally redundant storage (LRS) (6)** |
    |||

     ![](../images/lab15-image(7).png)

1. Once validated, click on **Create**. Wait for the notification that the account was successfully created. 

1.  Wait for the notification that the storage account was successfully created and click on **Go to resource**.

     ![](../images/lab15-image8.png)

1. From the **Overview** pane of the newly created storage account, click on **Delete (1)** and notice an **error message** **(2)** stating the resource or its parent has a delete lock. 

    ![](../images/lab15-image9.png)

    **Note**: Although we did not create a lock specifically for the storage account, we did create a lock at the resource group level, which contains the storage account. As such, this *parent-level* lock prevents us from deleting the resource, and the storage account inherits the lock from the parent.

### Task 4: Remove the Resource Lock

In this task, we will remove the resource lock and test. 

1. Return to the **AZ-900-<inject key="DeploymentID" enableCopy="false"/>** resource group blade and, in the **Settings** section, click on **Locks (1)**. Click on the **Delete (2)** option to the right of the **RGLock** entry.

    ![](../images/lab15-image10.png)

1. On the **AZ-900-<inject key="DeploymentID" enableCopy="false"/>** | locks blade, from the left navigation pane, click on **Overview** and select the **storgeaccount<inject key="DeploymentID" enableCopy="false" />**.
  
1. On the **storageaccount** blade, select **Delete (1),** copy the storage account's **(2)** name, and paste it into the **Enter storage account name to confirm deletion (3)** field, then click on **Delete (4)** and select **Delete** on the **Delete Confirmation** window.

    ![](../images/lab15-image11.png)
  
1. Monitor the notification and confirm you can now delete the resource.

     ![](../images/lab15-image12.png)

   **Note**: **Wait for 10 minutes before heading to the validation step.**

> **Congratulations** on completing the task! Now, it is time to validate it. Here are the steps:
> - Click on the **Validate** button for the corresponding task. If you receive a success message, you can proceed to the next task. 
> - If not, carefully read the error message and retry the step, following the instructions in the lab guide.
> - If you need any assistance, please contact us at **labs-support@spektrasystems.com**. We are available 24/7 to help.

<validation step="ad4f80cc-e446-4cec-abb6-071609ac684c" />

## Summary
In this exercise, we verified the existing resource group and added a lock to prevent its accidental deletion. We tested the deletion of the resource group and a member within it, ensuring that the lock functioned as intended. Finally, we removed the resource lock to restore full management capabilities. Throughout the exercise, we gained experience in using resource locks to protect critical resources in a cloud environment.

## Review
In this lab, you have:
- Verified the existing resource group.
- Added a lock to the resource group and tested deletion.
- Tested deleting a member of the resource group.
- Removed the resource lock.

## Reference Link

- https://learn.microsoft.com/en-us/azure/storage/common/lock-account-resource?tabs=portal
  
## You have successfully completed this lab. Proceed with the next lab.
