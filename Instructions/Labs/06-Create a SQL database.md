# Lab 06 - Create a SQL Database

### Estimated Timing: 20 Minutes

## Lab Overview

A SQL database is a collection of tables that stores a specific set of structured data using a relational model. It is designed to efficiently organize and retrieve data using a language called Structured Query Language (SQL).

In this walkthrough, we will create an SQL database in Azure and then query the data in that database.

## Lab Objectives

In this lab, you will be able to complete the following tasks:

+ **Task 1:** Create the Database
+ **Task 2:** Test the Database

## Architecture Diagram

![](../images/az900lab06.PNG) 

### Task 1: Create the Database

In this task, we will create an SQL database based on the AdventureWorksLT sample database. 

1. On the **Azure Portal** page, within the **Search Resources, Services, and Docs** search bar, search for **SQL databases (1)** and select **SQL databases (2)**. 

   ![](./images/az-900-63.png)

1. Click **+ Create**. 

   ![](./images/az-900-64.png)
   
1. On the **Basics** tab, fill in all the information provided and then click on **Next: Networking> (7)**.  

    | Settings | Values | 
    | --- | --- |
    | Subscription | **Choose your subscription (1)** |
    | Resource group | **AZ-900-<inject key="DeploymentID" enableCopy="false"/> (2)** |
    | Database name| **db1 (3)** |
    | Workload Environment| **Development (5)** |
    | Compute + storage| **General Purpose - Serverless Gen 5 (6)** |

    ![](./images/az-900-66.png)
    
1. Next to the **Server** drop-down list, click on **Create new**. Select **OK (7)** when finished.       

    | Settings | Values | 
    | --- | --- |
    | Server name | **sqlserver<inject key="DeploymentID" enableCopy="false"/> (1)** (must be unique) |
    | Location | **(US) East US (2)** |
    | Authentication method | **Use SQL authentication (3)** | 
    | Server admin login | **sqluser (4)** |
    | Password | **Pa$$w0rd1234 (5)** |
    | Confirm Password | **Pa$$w0rd1234 (6)** |

    ![](./images/az-900-65.png)    

1. On the **Networking** tab, configure the following settings (leave others with their defaults) and then click on **Next: Security> (4)**

    | Settings | Values | 
    | --- | --- |
    | Connectivity method | **Public endpoint (1)** |    
    | Allow Azure services and resources to access this server | **Yes (2)** |
    | Add current client IP address | **No (3)** |

    ![](./images/az-900-67.png)        

1. On the **Security** tab, verify the below **Settings** and then click on **Next: Additional settings >**
 
    | Settings | Values | 
    | --- | --- |
    | Enable Microsoft Defender for SQL| **Not now** |

1. On the **Additional settings** tab, insert the information available below. We will be using the **AdventureWorksLT** **sample (1)** database. If a pop-up comes up, click on **OK (2)** and then click on **Review + create (3)**.

    | Settings | Values | 
    | --- | --- |
    | Use existing data | **Sample (1)** |

    ![](./images/az-900-68.png)        

1. Review the configurations and then click on **Create** to deploy and provision the resource group, server, and database. Deployment may take approximately 2 to 5 minutes.

   ![](./images/az-900-69.png)

1. Wait for the deployment to succeed.

### Task 2: Test the Database

In this task, we will configure the SQL server and run a SQL query. 

1. From the **Search Resources, Services, and Docs** box, search and select **SQL databases** and ensure your new database was created. You may need to **refresh** the page.

    ![Screenshot of the SQL database and server that have just been deployed.](./images/az-900-70.png)

1. Click on the **db1** entry representing the SQL database you had created, and then click on **Query editor (preview)** from the left navigation pane.

   ![](./images/az-900-71.png)

1. Log in as **sqluser (1)** with the **Password** `Pa$$w0rd1234` **(2)** and then click on **OK (3)**.

   ![](./images/az-900-72.png)

1. If you are able to log in, proceed with **Step 7**.

1. If you are not able to log in, follow the steps below: 

    ![Screenshot of the Query Editor login page with IP address error.](../images/0503.png)
    
    - Within the **db1** blade, click on **Overview (1)** and then select **Set server firewall (2)** from the top menu bar.

      ![](./images/az-900-73.png)    

    - Scroll down to the **Firewall rules** section and click on **+ Add your client IPv4 address (1)**. Be sure to **Save (2)** your changes. 

      ![Screenshot of the SQL server firewall settings page with the new IP rule highlighted.](./images/az-900-74.png)

1. Return to your SQL database and the **Query Editor (Preview)** login page. Try to log in again as an `sqluser` with the **Password** `Pa$$w0rd1234`. Click on **OK**. This time, you should succeed. Note that it may take a couple of minutes for the new firewall rule to be deployed. 

1. Once you log in successfully, the query pane appears. Enter the following query into the editor pane **(1)** and then click on **Run (2)**.

    ```
    SELECT TOP 20 pc.Name as CategoryName, p.name as ProductName
    FROM SalesLT.ProductCategory pc
    JOIN SalesLT.Product p
    ON pc.productcategoryid = p.productcategoryid;
    ```

   ![](./images/az-900-75.png)    

    >**Note**: This SQL query selects the top 20 records from the SalesLT.ProductCategory table and SalesLT.Product table, displaying the CategoryName from the ProductCategory table as "CategoryName" and the ProductName from the Product table as "ProductName." The query performs an inner join between the two tables based on the productcategoryid column

1. Review the query results in the **Results** pane. The query should run successfully.

    ![Screenshot of the database Query Editor pane with the SQL code having been run successfully and the output visible in the results pane.](./images/az-900-76.png)

1. Close the query editor and select **OK** on the **portal.azure.com**.

> **Congratulations** on completing the task! Now, it is time to validate it. Here are the steps:
> - Click on the **Validate** button for the corresponding task. If you receive a success message, you can proceed to the next task. 
> - If not, carefully read the error message and retry the step, following the instructions in the lab guide.
> - If you need any assistance, please contact us at **labs-support@spektrasystems.com**. We are available 24/7 to help.

<validation step="3f6d725f-f26f-461d-a922-9f871108d2f1" />

## Summary
In this exercise, we have created a database and tested its functionality to ensure it was set up correctly. We explored the process of database creation, followed by verifying its performance and accessibility. Throughout the exercise, we gained hands-on experience in setting up and testing databases in the cloud environment.

## Review
In this lab, you have:
- Created the database.
- Tested the database.

## Reference Link

- https://learn.microsoft.com/en-us/sql/relational-databases/databases/create-a-database?view=sql-server-ver16
  
## You have successfully completed this lab. Proceed with the next lab.
