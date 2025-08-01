# SC-401: Information Security Administrator

## Lab 02- Implementing Data Protection and Compliance Monitoring in Microsoft Purview

## Overall Estimated Duration: 4 Hours

## Overview

In this hands-on lab, you will take on the role of Joni Sherman, the Information Security Administrator at Contoso Ltd., to strengthen the organization’s auditing and investigation capabilities using Microsoft Purview. You will search the Microsoft 365 audit log to review activities such as DLP policy changes and ensure critical audit records are retained for extended periods. Additionally, you'll perform targeted content searches across Microsoft 365 workloads to locate and analyze potentially exposed sensitive financial data. This lab provides practical experience in using Microsoft Purview for audit, compliance monitoring, and incident investigation.

## Objectives

Use Azure services to automate document processing, including data extraction, sentiment analysis, OCR, and classification. They will integrate Azure OpenAI's ChatGPT and Cosmos DB to analyze and interact with the processed data through a web application.

- **Implement and manage endpoint DLP:** Learn how to configure and manage Data Loss Prevention (DLP) policies in Microsoft Purview to safeguard sensitive information such as credit card numbers and employee IDs. Gain hands-on experience creating custom DLP policies, defining conditions and actions, and monitoring policy matches to prevent accidental or unauthorized sharing of sensitive data across Microsoft 365 services.

- **Implement Insider Risk Management:** Learn how to identify, assess, and respond to insider threats using Microsoft Purview Insider Risk Management. Gain hands-on experience creating policies that detect risky user behaviors and applying risk indicators. Then, enhance data protection with Microsoft Purview Adaptive Protection by dynamically adjusting Data Loss Prevention (DLP) controls based on user risk levels ensuring sensitive data is safeguarded without disrupting productivity.

- **Audit and search activity in Microsoft Purview:** Learn how to strengthen compliance and investigation capabilities by leveraging Microsoft Purview's auditing and content search features. Gain experience in reviewing audit logs to track sensitive activity and policy changes, configuring audit log retention policies, and conducting targeted content searches to identify potential data exposure involving sensitive financial information across Microsoft 365 services.
  
## Prerequisites

Participants should have basic knowledge and understanding of the following:

- Microsoft 365 administration and navigation within the Microsoft Purview portal
- Audit logging and compliance monitoring practices in Microsoft 365
- Familiarity with Data Loss Prevention (DLP) policies and configuration
- Understanding of Microsoft 365 workloads such as Exchange Online, SharePoint Online, and OneDrive for Business
- Basic experience with content search and eDiscovery tools
- Role-based access control (RBAC) and permissions in Microsoft Entra ID (Azure AD)
  
## Architecture

**Azure Document Intelligence** processes and extracts data from documents. **Azure Functions** trigger the document processing based on blob changes. **Azure Storage Account** stores the documents to be processed. **Azure AI Search** indexes and searches the extracted data. **Azure OpenAI Service** provides AI capabilities for natural language processing and generation. **Web Application** facilitates user interaction and displays the results of the AI processing. A storage mechanism stores chat history for viewing and analysis.

## Architecture Diagram

![Architecture](images/aaaarch%20diagram.png)

## Explanation of Components

The architecture for this lab involves the following key components:

- **Microsoft Purview Compliance Portal:** A unified platform for managing compliance and risk across Microsoft 365. It provides access to tools such as Audit, eDiscovery, DLP, and Content Search.

- **Microsoft Purview Audit (Standard and Premium):** Allows administrators to track and review user and admin activity across Microsoft 365 services. Supports searching audit logs, exporting results, and configuring audit log retention policies.

- **Microsoft Purview Content Search:** Enables targeted searches across Microsoft 365 services (such as Exchange, SharePoint, and OneDrive) to identify emails, documents, or content matching specific criteria, such as sensitive keywords or user actions.

- **Audit Log Retention Policies:** Defines how long audit records are retained for different Microsoft 365 workloads, helping organizations meet compliance and investigation requirements.

- **Microsoft Exchange Online, SharePoint Online, and OneDrive for Business:** Core Microsoft 365 workloads where user and admin activities are monitored and searched during the audit and investigation process.

## Getting Started with the Lab

Welcome to your SC-401: Information Security Administrator Workshop! We've prepared a seamless environment for you to explore and learn about Information Security. Let's begin by making the most of this experience.
 
## Accessing Your Lab Environment
 
Once you're ready to dive in, your virtual machine and lab guide will be right at your fingertips within your web browser.

  ![OpenAI](images/new-get-start-25-9upd.png)
 
## Exploring Your Lab Resources
 
To get a better understanding of your lab resources and credentials, navigate to the **Environment** tab.
 
  ![OpenAI](images/envtab(1).png)
 
## Utilizing the Split Window Feature
 
For convenience, you can open the lab guide in a separate window by selecting the **Split Window** button from the Top right corner.
 
  ![OpenAI](images/splitwin(1).png)

## Managing Your Virtual Machine
 
Feel free to **Start, Restart,** or **Stop** your virtual machine as needed from the **Resources** tab. Your experience is in your hands!

  ![OpenAI](images/new-get-start-25-4upd.png)

## Lab Validation

1. After completing the task, hit the **Validate** button under the Validation tab integrated within your lab guide. If you receive a success message, you can proceed to the next task; if not, carefully read the error message and retry the step, following the instructions in the lab guide.

   ![Inline Validation](images/new-get-start-25-5upd.png)

## Lab Guide Zoom In/Zoom Out
 
1. To adjust the zoom level for the environment page, click the **A↕: 100%** icon located next to the timer in the lab environment.

     ![OpenAI](images/zoominwin(1).png)

## Let's Get Started with Azure Portal
 
1. On your virtual machine, click on the **Azure Portal** icon as shown below:
 
    ![OpenAI](images/sc900-image(1).png)

1. On the **Sign in to Microsoft Azure** tab, you will see the login screen. Enter the following email/username, and click on **Next**. 

   * **Email/Username:** <inject key="AzureAdUserEmail"></inject>
   
      ![OpenAI](images/sc900-image-1.png)
     
1. Now enter the following password and click on **Sign in**.
   
   * **Password:** <inject key="AzureAdUserPassword"></inject>
   
      ![OpenAI](images/sc900-image-2.png)

1. If you see the pop-up **Action Required**, keep default and then click on **Ask later**. If you see the pop-up Help us protect your account, click on **Skip for now** (14 days until this is required), and then click on **Next**.

   ![Asklater](images/asklater.png)

   >**NOTE:** Do not enable MFA, select **Ask Later**.
     
1. If prompted to **Stay signed in?**, click **"No"**.
 
1. If a **Welcome to Microsoft Azure** pop-up window appears, simply click **Cancel** to skip the tour.

## Support Contact
The CloudLabs support team is available 24/7, 365 days a year, via email and live chat to ensure seamless assistance at any time. We offer dedicated support channels tailored specifically for both learners and instructors, ensuring that all your needs are promptly and efficiently addressed.

Learner Support Contacts:

   - Email Support: cloudlabs-support@spektrasystems.com
   - Live Chat Support: https://cloudlabs.ai/labs-support

Now you're all set to explore the powerful world of technology. Feel free to reach out if you have any questions along the way. Enjoy your workshop!

Now, click on **Next** from the lower right corner to move on to the next page.

  ![Asklater](images/num.png)

## Happy Learning!!