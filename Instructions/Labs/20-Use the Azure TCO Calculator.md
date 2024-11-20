# Lab 20 - Use the Azure TCO Calculator

### Estimated Timing: 10 Minutes

### Lab Overview

The Azure Total Cost of Ownership (TCO) Calculator is a tool provided by Microsoft Azure that helps organizations assess the cost savings and benefits of migrating their workloads to the Azure cloud platform compared to on-premises infrastructure.

In this walkthrough, you will use the Total Cost of Ownership (TCO) Calculator to generate a cost comparison report for an on-premises environment.

## Lab Objectives

In this lab, you will be able to complete the following tasks:

+ **Task 1:** Configure the TCO Calculator
+ **Task 2:** Review the Results and Save a Copy

## Architecture Diagram

![](../images/az900lab20.png)

**Note**: This walkthrough provides example definitions of on-premises infrastructure and workloads for a typical data center. To create a TCO Calculator report, use the example definitions or provide details of your *actual* on-premises infrastructure and workloads.

### Task 1: Configure the TCO Calculator

In this task, we will add infrastructure information to the calculator. 

1. In your Edge browser, navigate to the [Total Cost of Ownership (TCO) Calculator](https://azure.microsoft.com/en-us/pricing/tco/calculator/) page.

1. To add details of your on-premises server infrastructure, click on the **+ Add server workload** option in the **Define your workloads** pane.

    | Settings | Values |
    | -- | -- |
    | Name | **Servers: Windows VMs (1)** |
    | Workload | **Windows/Linux server (2)** |
    | Environment | **Virtual Machines (3)** |
    | Operating system | **Windows (4)** |
    | Operating system license | **Datacenter (5)** |
    | VMs | **50 (6)** |
    | Virtualization | **Hyper-V (7)** |
    | Core(s) | **8 (8)**|
    | RAM (GB) | **16 (9)** |
    | Optimize by | **CPU (10)** |
    | Windows Server 2008/2008 R2 | **Off (11)** |

    ![](../images/lab20-image1.png)
    ![](../images/lab20-image2.png)
   
1. Select **+ Add server workload** to make a row for a new server workload definition. 

    | Settings | Values |
    | -- | -- |
    | Name | **Servers: Linux VMs (1)** |
    | Workload | **Windows/Linux server (2)** |
    | Environment | **Virtual Machines (3)** |
    | Operating system | **Linux (4)** |
    | VMs | **50 (5)** |
    | Virtualization | **VMware (6)** |
    | Core(s) | **8 (7)**|
    | RAM (GB) | **16 (8)** |
    | Optimize by | **CPU(9)** |

    ![](../images/lab20-image3.png)
   
1. In the **Storage** pane, click on **Add storage**.

    | Settings | Values |
    | -- | -- |
    | Name | **Server Storage (1)** |
    | Storage type | **Local Disk/SAN (2)** |
    | Disk type | **HDD (3)** |
    | Capacity | **60 TB (4)** |  
    | Backup | **120 TB (5)** |
    | Archive | **0 TB (6)** |

     ![](../images/lab20-image4.png)
      ![](../images/lab20-image5.png)

1. In the **Networking** pane, add bandwidth and click **Next (2)**.

    | Setting | Value |
    | -- | -- |
    | Outbound bandwidth | 15 TB (1)|

    ![](../images/lab20-image6.png)

1. Explore the options and make any adjustments that you require. 

    | Setting | Value |
    | -- | -- |
    | Currency | **Euro zone** |
    
    ![](../images/lab20-image7.png)

   >**Note**: You have the freedom to choose the **Currency** option that best suits your needs and proceed with the lab.

1. Click on **Next**.

### Task 2: Review the Results and Save a Copy

In this task, we will review cost-saving recommendations and download a report. 

1. Review the Azure cost-saving recommendations and visualizations.

    | Settings | Values |
    | -- | -- |
    | Timeframe| **3 years (1)** |
    | Region | **North Europe (2)** |

    ![](../images/lab20-image8.png)

1. To save or print a PDF copy of the report, click on **Download** and then on **Print**. Provide a relevant name to save the file. 

   ![](../images/lab20-image9.png)

1. To modify the information you provided, go to the bottom of the page and click on **Back**. 

    >**Congratulations!** You have used the TCO Calculator to generate a cost comparison report for an on-premises environment.

## Summary

In this lab, you used the Azure TCO Calculator to compare the costs of on-premises infrastructure versus Azure cloud services. You configured workload details, reviewed cost savings, and generated a downloadable report for cloud migration planning.

## Review
In this lab, you have:
- Configured the TCO Calculator.
- Reviewed the results and saved a copy.

## Reference Link

- https://bluexp.netapp.com/blog/azure-cvo-blg-how-to-reduce-your-cloud-bill-with-the-azure-tco-calculator

## You have successfully completed this lab. Proceed with the next lab.
