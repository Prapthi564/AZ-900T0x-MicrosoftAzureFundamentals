# Lab 09 - Create a VM with a Template

## Lab overview

In this walkthrough, we will deploy a virtual machine with a QuickStart template and examine monitoring capabilities.

## Lab objectives

In this lab, you will complete the following tasks:

+ Task 1: Explore the gallery and locate a template
+ Task 2: Verify and monitor your virtual machine deployment

## Estimated timing: 15 minutes

## Architecture diagram

![](../images/az900lab09.PNG) 

### Task 1: Explore the gallery and locate a template

In this task, we will browse the Azure QuickStart gallery and deploy a template that creates a virtual machine.

1. In a new tab of the **Microsoft Edge**, access the [Azure Quickstart Templates gallery](https://azure.microsoft.com/resources/templates?azure-portal=true). In the gallery, you will find many popular and recently updated templates. These templates automate the deployment of Azure resources, including the installation of popular software packages.

1. Browse through the many different types of templates that are available. Are there any templates that are of interest to you?.

1. Search and Select the **Deploy a simple Windows VM with tags**.

    >**Note**: The **Deploy to Azure** button enables you to deploy the template via the Azure portal. During such deployment, you will be prompted only for a small set of configuration parameters. 

1. Click the **Deploy to Azure** button. Your browser session will be automatically redirected to the [Azure portal](http://portal.azure.com/).

    ![](../images/l9.5.png)

1. If prompted, sign in to the Azure with the **Username:** <inject key="AzureAdUserEmail"></inject> and **Password:** <inject key="AzureAdUserPassword"></inject>.

1. Click **Edit template**. The Resource Manager template format uses the JSON format. In the template go to line number **35** and change the default value of the OS version to **2019-datacenter-gensecond**

   ![](../images/l9os.png)
   
1. Next, go to line number **110** change the VM name to **myVMTemplate**, and save the changes made to the template file by clicking on **Save**.

   ![](../images/l9vm.png)

3. To review the parameters and variables click on **Edit parameters file**, review the contents and  click on **Save**.
  
1. Now configure the parameters required by the template. Leave the defaults for everything else. 

    | Setting| Value|
    |----|----|
    | Subscription | **Accept default subscription** (1)|
    | Resource group | **myRGTemplate-<inject key="DeploymentID" enableCopy="false"/>** (2) |
    | Region | **<inject key="Region" enableCopy="false"/>** (3) |
    | Admin username | **azureuser** (4) |
    | Admin password | **Pa$$w0rd1234** (5) |
    | DNS label prefix | **myvm-<inject key="DeploymentID" enableCopy="false"/>** (6) |
    | Windows OS version | **2019-datacenter-gensecond** (7)|
    | VM Size | **Standard_D2s_v5** (8)|
    |||
   
    ![](../images/lab9-image1.png)

1. Click **Review + Create**.
 
1. Click the **Create**.

1. Monitor your deployment, wait until your deployment is completed.

### Task 2: Verify and monitor your virtual machine deployment

In this task, we will verify the virtual machine is deployed correctly. 

1. From the **Search resources, services, and docs** blade, search for and select **Virtual machines**.

1. Ensure your new virtual machine was created. 

    ![Screenshot of the virtual machines page. The new VM is shown and running.](../images/(VM1).png)

1. Select your virtual machine and on the **Overview** pane scroll down to view monitoring data.

    ![Screenshot of the virtual machines page. The new VM is shown and running.](../images/(VM3).png)

    >**Note**: The monitoring timeframe can be adjusted from one hour to 30 days.

1. Review different charts that are provided including **CPU (average)** and **Disk bytes (total)**. 

    ![Screenshot of the virtual machine monitoring charts.](../images/(VM2).png)

1. Click on any chart. Note that you can **Add metrics** and change the chart type.

1. Return to the **Overview** blade.

1. Click on the **Activity log** (left pane). Activity logs record such events as the creation or modification of resources. 

1. Click **Add filter**, and experiment with searching for different event types and operations. 

   ![Screenshot of the Add filters page with Event type selected.](../images/l9.4.png)

<validation step="96efa9b4-389e-4cc9-9b9f-060cc6726976" />

> **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:
> - If you receive a success message, you can proceed to the next task.
> - If not, carefully read the error message and retry the step, following the instructions in the lab guide. 
> - If you need any assistance, please contact us at labs-support@spektrasystems.com. We are available 24/7 to help you out.
    
### Review
In this lab, you have completed:
- Explored the gallery and locate a template
- Verified and monitor your virtual machine deployment

## Reference link

- https://learn.microsoft.com/en-us/azure/virtual-machines/windows/ps-template  

## You have successfully completed this lab.
