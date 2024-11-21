# Lab 14 - Manage Access with RBAC

### Estimated Timing: 15 Minutes

### Lab Overview

Azure role-based access control (Azure RBAC) helps you manage who has access to Azure resources, what they can do with those resources, and what areas they have access to. Azure RBAC is an authorization system built on Azure Resource Manager that provides fine-grained access management to Azure resources.

In this walkthrough, we will assign roles and view activity logs.

## Lab Objectives

In this lab, you will be able to complete the following tasks:

+ **Task 1:** View and Assign Roles
+ **Task 2:** Monitor Role Assignments and Remove a Role

## Architecture Diagram

![](../images/az900lab14.png)

### Task 1: View and Assign Roles

In this task, we will assign the virtual machine contributor role. 

1. On the **Azure portal** page, in the **Search Resources, Services, and Docs** (G+/) box at the top, enter **Resource groups (1)**, and then select **Resource groups (2)** under **Services**.

   ![image](../images/lab14-image1.png)

1. Then, view and select the existing resource group **AZ-900-<inject key="DeploymentID" enableCopy="false"/>**.

1. You will be directed to the overview page of the resource group.

1. Click on the **Access control (IAM) (1)** blade, and then switch to the **Roles (2)** tab. Scroll down and notice the role definitions that are available. Use the view link under details to get an idea of each role's permissions. Notice there is also information on the number of users and groups that are assigned to each role.

   ![image](../images/lab14-image3.png)

1. On the **AZ-900-<inject key="DeploymentID" enableCopy="false"/> | Access control (IAM)** blade, select **+ Add (1),** then from the drop-down, select **Add role assignment (2)**. 

   ![image](../images/lab14-image4.png)
   
1. In  the **Add role assignment** blade on the **Role** tab, search for the **Virtual Machine Contributor (1)** role and select **Virtual Machine Contributor (2),** then click on **Next (3).**

    ![image](../images/lab14-image5.png)
   

1. On the **Members** tab, make sure to select **Assign access to: the user, group, or service principal (1)**. Next, click on **+ Select members (2)** to open a pop-up window. In the search bar within the pop-up, enter your Azure account name (Username:**<inject key="AzureAdUserEmail"></inject>) (3)**, and then click on **select (4)**.

    ![image](../images/lab14-image6.png)

1. Click on **Review + Assign**.

   ![image](../images/lab14-image7.png)
   
     **Note:** The virtual machine contributor role lets you manage virtual machines but not access their operating system or manage the virtual network and storage account they are connected to. The username can be obtained from the Lab Environment output page.

1. Back on the **AZ-900-<inject key="DeploymentID" enableCopy="false"/> | Access control (IAM)** blade, select the **Role assignments** tab.

    ![image](../images/lab14-image8.png)

1. **Refresh** the Role assignments page and ensure you are now listed as a virtual machine contributor (you need to scroll down).

     ![image](../images/lab14-image9.png)

    **Note**: This assignment does not grant you any additional privileges since your account already has the owner role, which includes all privileges associated with the contributor role.

### Task 2: Monitor Role Assignments and Remove a Role

In this task, we will view the activity log to verify the role assignment and then remove the role. 

1. On the **AZ-900-<inject key="DeploymentID" enableCopy="false"/>** resource group blade, click on the **Activity log**.

1. In the search bar, search for **Create role assignment**.

1. Verify the activity log shows your role assignment with your User ID. 

     ![image](../images/lab14-image13.png)
   
    **Note**: Can you figure out how to remove your role assignment?

> **Congratulations** on completing the task! Now, it is time to validate it. Here are the steps:
> - Click on the **Validate** button for the corresponding task. If you receive a success message, you can proceed to the next task. 
> - If not, carefully read the error message and retry the step, following the instructions in the lab guide.
> - If you need any assistance, please contact us at **labs-support@spektrasystems.com**. We are available 24/7 to help.

<validation step="d5b66b53-22d2-4a55-bff0-7415cf18338d" />

## Summary
In this exercise, we viewed and assigned roles to manage access and permissions. We also monitored role assignments and learned how to remove a role when necessary. Throughout the exercise, we gained practical experience in managing role-based access control (RBAC) and ensuring appropriate access levels within a cloud environment.

## Review

In this lab, you have completed:
- View and assign roles
- Monitor role assignments and remove a role

## Reference Link

- https://learn.microsoft.com/en-us/azure/role-based-access-control/overview
  
## You have successfully completed this lab. Proceed with the next lab.
