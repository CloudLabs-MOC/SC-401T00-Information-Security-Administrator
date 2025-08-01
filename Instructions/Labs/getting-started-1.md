# SC-401: Information Security Administrator

## Overall Estimated Duration: 3 Hours

## Overview

In this hands-on lab, you will act as Joni Sherman, the Information Security Administrator at Contoso Ltd., to implement data protection and compliance using Microsoft Purview. You'll create custom sensitive information types, configure sensitivity labels with encryption options like Double Key Encryption (DKE), integrate with Microsoft Defender for Cloud Apps, and set up Microsoft Purview Message Encryption with custom branding. This lab provides practical experience in securing and managing sensitive data across Microsoft 365.

## Objectives

Use Azure services to automate document processing, including data extraction, sentiment analysis, OCR, and classification. They will integrate Azure OpenAI's ChatGPT and Cosmos DB to analyze and interact with the processed data through a web application.

- **Manage compliance and security roles:** Learn how to assign appropriate compliance and security roles within Microsoft 365 to ensure proper access control and oversight. Gain familiarity with the Microsoft Purview portal and understand how role-based access contributes to regulatory compliance and secure information governance across a growing organization.

- **Create and manage sensitive information types:** Learn how to define and customize sensitive information types in Microsoft Purview to improve the detection of confidential data such as employee IDs and personal health information. This includes configuring custom types, adjusting confidence levels, using Exact Data Match (EDM) classifiers, and building keyword dictionaries to reduce false positives and enhance data protection accuracy.

- **Create and manage sensitivity labels:** Learn how to design and implement a sensitivity labeling strategy in Microsoft Purview to classify and protect sensitive data across the organization. This includes creating and publishing labels and sublabels, configuring manual and automatic labeling, enabling advanced encryption options such as Double Key Encryption (DKE), and integrating labeling policies with Microsoft Defender for Cloud Apps to support secure file sharing and data governance.

- **Deploy Microsoft Purview Message Encryption:** Learn how to configure Microsoft Purview Message Encryption to secure email communications across departments. This includes verifying Azure Rights Management Service (RMS) functionality, customizing default branding, and creating department-specific branding templates to ensure a consistent and secure messaging experience.
  
## Prerequisites

Participants should have basic knowledge and understanding of the following:

- Microsoft 365 administration and navigation of the Microsoft 365 admin center
- Core concepts of Microsoft Purview and its compliance solutions
- Role-based access control (RBAC) in Microsoft 365
- Sensitivity labels, data classification, and information protection strategies
- Azure Active Directory (Microsoft Entra) and group management
- General understanding of secure communication practices within organizations
  
## Architecture

**Azure Document Intelligence** processes and extracts data from documents. **Azure Functions** trigger the document processing based on blob changes. **Azure Storage Account** stores the documents to be processed. **Azure AI Search** indexes and searches the extracted data. **Azure OpenAI Service** provides AI capabilities for natural language processing and generation. **Web Application** facilitates user interaction and displays the results of the AI processing. A storage mechanism stores chat history for viewing and analysis.

## Architecture Diagram

![Architecture](images/aaaarch%20diagram.png)

## Explanation of Components

The architecture for this lab involves the following key components:

- **Microsoft Purview Compliance Portal:** The central platform used to manage compliance features across Microsoft 365, including data loss prevention (DLP), information protection, insider risk management, and more.

- **Microsoft Purview Information Protection:** Enables the creation, publishing, and enforcement of sensitivity labels for classifying and protecting sensitive information within documents and emails.

- **Microsoft Purview Data Loss Prevention (DLP):** A policy engine that helps prevent the unintentional sharing of sensitive information by detecting content that matches sensitive information types and applying actions like alerts or blocking.

- **Microsoft Purview Message Encryption:** Secures email messages both inside and outside the organization by enforcing encryption and branding policies, powered by Azure Rights Management.

- **Custom Sensitive Information Types:** User-defined criteria used to detect organization-specific data, such as employee IDs or health information, based on exact data match (EDM) or keyword dictionaries.

- **Microsoft Defender for Cloud Apps:** Integrated with Purview to extend labeling and protection to third-party cloud services, enabling auto-labeling of externally shared content and real-time monitoring.

- **Azure Active Directory (Microsoft Entra ID):** Provides identity and access management, supporting role assignments and group-based access control for compliance-related roles and features.

- **Exact Data Match (EDM):** A classification technique in Microsoft Purview that allows detection of structured sensitive data from secure, pre-defined datasets like employee databases.

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