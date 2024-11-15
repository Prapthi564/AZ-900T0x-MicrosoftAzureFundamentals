# Lab 12 - Implement Azure Key Vault

### Estimated timing: 10 minutes

## Lab overview

Azure Key Vault is a cloud service for securely storing and accessing secrets. A secret is anything that you want to tightly control access to, such as API keys, passwords, certificates, or cryptographic keys. 

Secrets: Provides secure storage of secrets, such as passwords and database connection strings.

Certificates: Supports certificates, which are built on top of keys and secrets and add an automated renewal feature. Keep in mind when a certificate is created, an addressable key and secret are also created with the same name.

In this walkthrough, we will create an Azure Key vault and then create a password secret within that key vault, providing a securely stored, centrally managed password for use with applications.

## Lab objectives

In this lab, You will be able to complete the following tasks:

+ Task 1: Create an Azure Key Vault
+ Task 2: Add a secret to the Key Vault

## Architecture diagram

![](../images/az900lab12.png)

### Task 1: Create an Azure Key Vault

1. On Azure Portal page, in **Search resources, services and docs (G+/)** box at the top of the portal, enter **Key vaults (1)** and then select **Key vaults (2)** under services.

   ![](./images/az-900-115.png)
  
1. On **Key vaults** blade, select **+ Create**.

   ![](./images/az-900-116.png)

1. On the **Basics tab** specify the following to configure the key vault and click on **Review + create (6)**.

    | Setting | Value | 
    | --- | --- |
    | Subscription | **Accept default subscription (1)** |
    | Resource group | **AZ-900-<inject key="DeploymentID" enableCopy="false"/> (2)**  |
    | Key vault name | **keyvault<inject key="DeploymentID" enableCopy="false" /> (3)** |
    | Location | **<inject key="Region" enableCopy="false"/> (4)** |
    | Pricing tier | **Standard (5)** |
    | | |

    ![](./images/az-900-117.png)
   
1. Click **Create**. 

1. Once the new key vault is provisioned, click **Go to resource**.

   ![](../images/lab12-image3.png)

1. Click on the key vault **Overview (1)** tab and take note of the **Vault URI (2)**. Applications that use your vault through the REST API will need this URI.

   ![](./images/az-900-122.png)

1. Take a moment to browse through some of the other key vault options. Under **Objects** review **Keys**, **Secrets** and **Certificates**.

   ![](./images/az-900-119.png)
   
   >**Note**: Your Azure account is the only one authorized to perform operations on this new vault.
   
### Task 2: Add a secret to the Key Vault
        
In this task, we will add a password to the key vault. 

1. Under **Objects**, click on **Secrets (1)** and then click **+ Generate/Import (2)**.

   ![](../images/lab12-image5.png)
   
1. Configure the secret. Leave the other values at their defaults. Notice you can set an activation and expiration date. Notice you can also disable the secret and click **Create (4)**.

    | Setting | Value | 
    | --- | --- |
    | Upload options | **Manual (1)** |
    | Name | **ExamplePassword (2)** |
    | Secret value | **hVFkk96 (3)** |
    | | |

    ![](../images/lab12-image6.png)
   
1. Wait until you see the secret has been successfully created, refresh the page once if your not able to see the secret.

1. Once **ExamplePassword** secret is listed notice it has a status of **Enabled**.

   ![](./images/az-900-120.png)

1. Select the **ExamplePassword** secret and click the current version.

   ![](../images/lab12-image9.png)

1. Under **properties**, note the **Secret Identifier**. This is the URL value that you can now use with applications. It provides a centrally managed and securely stored password. 

   ![](../images/lab12-image10.png)
   
1. Click the button **Show Secret Value** under **Settings** to display the password you specified earlier.

   ![](./images/az-900-121.png)

   ![](../images/lab12-image11.png)
   
> **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:
> - If you receive a success message, you can proceed to the next task.
> - If not, carefully read the error message and retry the step, following the instructions in the lab guide. 
> - If you need any assistance, please contact us at labs-support@spektrasystems.com. We are available 24/7 to help you out.

<validation step="b7285084-2658-4a78-a80b-cc7c97f8fa45" />

## Summary
In this exercise, we created an Azure Key Vault and added a secret to it. We explored the process of securely storing sensitive information in the Key Vault and managing access to the secret. Throughout the exercise, we gained hands-on experience with Azure Key Vault for secret management and security best practices.

## Review
In this lab, you have completed:
- Created an Azure Key Vault
- Added a secret to the Key Vault

## Reference link

- https://learn.microsoft.com/en-us/azure/key-vault/general/basic-concepts
  
## You have successfully completed this lab. Proceed with the next lab.
