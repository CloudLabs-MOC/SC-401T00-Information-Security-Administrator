# Lab 3 - Exercise 1 - Implement Insider Risk Management

## Estimated Duration: 90 minutes

You are Joni Sherman, the Information Security Administrator for Contoso Ltd. Your role involves ensuring regulatory compliance and protecting sensitive information within the organization. Recently, Contoso Ltd. has noticed unusual browsing activities that could potentially expose sensitive data. To proactively address this insider risk, you will implement Microsoft Purview Insider Risk Management, focusing on identifying, analyzing, and responding to potential insider threats effectively.

## Lab Objectives

In this lab, you will perform the following:

- Task 01: Assign insider risk management permissions
- Task 02: Configure insider risk indicators
- Task 03: Create an insider risk policy
- Task 04: Customize the data leaks policy
- Task 05: Enable Microsoft Defender for Endpoint integration with Insider Risk Management
- Task 06: Enable indicators and configure priority users
- Task 07: Create a policy for security policy violations by priority users
- Task 08: Create a notice template

## Task 1 – Assign insider risk management permissions

In this task, you'll assign Joni Sherman the Insider Risk Management role so she can access and manage insider risk features in Microsoft Purview.

1. You’ll now be working within the **LabVM**, signed in as demouser.

1. In Microsoft Edge, navigate to **`https://purview.microsoft.com`** and sign into the Microsoft Purview portal as Administrator, 

    - Username: **<inject key="AzureAdUserEmail" enableCopy="false"/>** 
    - Password: **<inject key="AzureAdUserPassword" enableCopy="false"/>**.

1. Select **Settings (1)** > **Roles and Scopes (2)** > **Role groups (3)**.

    ![Screenshot showing the files matching dropdown with the internal option added.](../Media/mod3-ex1-task1-1.png)

1. On the **Role groups for Microsoft Purview solutions** page select **Insider Risk Management (1)**. On the **Insider Risk Management** flyout panel on the right, select **Edit (2)**.

    ![Screenshot showing the files matching dropdown with the internal option added.](../Media/mod3-ex1-task1-2.png)

1. On the **Edit members of the role group** page select **+ Choose users**.

    ![Screenshot showing the files matching dropdown with the internal option added.](../Media/mod3-ex1-task1-6.png)

1. On the **Choose users** flyout panel, search for **Joni (1)** then select the checkbox for **Joni Sherman (2)**.
Select the **Select (3)** button at the bottom of the panel.
On the **Edit members of the role group** page select **Next (4)**.

    ![Screenshot showing the files matching dropdown with the internal option added.](../Media/mod3-ex1-task1-3.png)

1. On the **Review the role group and finish** page select **Save**.

    ![Screenshot showing the files matching dropdown with the internal option added.](../Media/mod3-ex1-task1-04.png)

1. Once you have successfully added Joni to the role group, select **Done** on the **You successfully updated the role group** page.

    ![Screenshot showing the files matching dropdown with the internal option added.](../Media/mod3-ex1-task1-05.png)


1. Sign out of the **Administrator** account by selecting the **01 (1)** icon on the top right of the window, then selecting **Sign out (2)**.

    ![Screenshot showing the files matching dropdown with the internal option added.](../Media/mod3-ex1-task1-7.png)

You've assigned Joni the necessary permissions to work with Insider Risk Management in the Microsoft Purview portal.

## Task 2 – Configure insider risk indicators

Before you create an insider risk policy, you'll turn on the indicators needed for detection. These indicators define the types of risky activity the system will look for.

1. In **Microsoft Edge**, navigate to **`https://purview.microsoft.com`** and sign into the Microsoft Purview portal as **JoniS@<inject key="TenantDomainName"></inject>**.

1. Select **Settings (1)** > **Insider risk management (2)**. Select the tab on the left for **Policy indicators (3)**.

    ![Screenshot showing the files matching dropdown with the internal option added.](../Media/mod3-ex2-task1-2.png)

1. On the **Policy indicators** page, expand and select **Select all** to enable all indicators in these categories:

   - Office indicators
   - Cumulative exfiltration detection

      ![Screenshot showing the files matching dropdown with the internal option added.](../Media/mod3-ex2-task1-5.png)

      ![Screenshot showing the files matching dropdown with the internal option added.](../Media/mod3-ex2-task1-3.png)

1. Select **Save** at the bottom of the page.

    ![Screenshot showing the files matching dropdown with the internal option added.](../Media/mod3-ex2-task1-4.png)

You've enabled key policy indicators so the system can detect sensitive actions like file exfiltration or risky Office activity.

## Task 3 – Create an insider risk policy

In this task, you'll create a data leaks quick policy to automatically detect and respond to risky user behavior related to data exfiltration. Quick policies use built-in templates and default thresholds to simplify setup.

1. In Microsoft Purview, select **Solutions (1)** > **Insider Risk Management (2)** > 

    ![Screenshot showing the files matching dropdown with the internal option added.](../Media/mod3-ex1-task3-2.png)

1. Select **Policies (1)** from the options. On the **Policies** page, select **+ Create policy (2)**, then select **Quick policy (3)**.

    ![Screenshot showing the files matching dropdown with the internal option added.](../Media/mod3-ex1-task3-1.png)

1. On the **Create quick policies** flyout, select to **Get started** under **Data leaks**.

    ![Screenshot showing the files matching dropdown with the internal option added.](../Media/mod3-ex1-task3-3.png)

1. Review the settings for creating a quick data leak policy, update **Policy name** as **Data leaks quick (1) policy** then select **Create policy (2)**.

    ![Screenshot showing the files matching dropdown with the internal option added.](../Media/mod3-ex1-task3-4.png)

1. On the **Your data leak policy is being created** page, select the checkboxes for:

   - **Email me when policies have unresolved warnings (1)**
   - **Email me when new high severity alerts are generated (2)**
   - Then select **Update notification settings (3)**
   - On the bottom of the **Your data leak policy is being created** page, select **Done (4)**.

      ![Screenshot showing the files matching dropdown with the internal option added.](../Media/mod3-ex1-task3-5.png)

You've created a quick policy for detecting potential data leaks using the default settings. Next, you'll customize it to resolve the configuration warning.

## Task 4 – Customize the data leaks policy

Some insider risk policies require additional indicators to function correctly. In this task, you'll modify your policy to enable sequence indicators and bring the policy into a healthy state.

On the **Policies** page for **Insider Risk Management**, you'll notice your data leaks policy has a recommendation.

1. Select the **Data leaks quick policy (1)** you just created.

1. Review the recommendation in the flyout page for the policy. You have a warning stating **Sequence trigger required indicators are not selected (2)**. To resolve this warning, select **Edit policy (3)**.

    ![Screenshot showing the files matching dropdown with the internal option added.](../Media/mod3-ex1-task4-1.png)

1. On the **Choose a policy template** page, let the page load completely then select **Next**.

    ![Screenshot showing the files matching dropdown with the internal option added.](../Media/mod3-ex1-task4-2.png)

1. On the **Name your policy** page, select **Next**.

    ![Screenshot showing the files matching dropdown with the internal option added.](../Media/mod3-ex1-task4-3.png)

1. On the **Choose users, groups, & adaptive scopes** page, select **Next**.

    ![Screenshot showing the files matching dropdown with the internal option added.](../Media/mod3-ex1-task4-4.png)

1. On the **Exclude users and groups (optional)** page, select **Next**.

    ![Screenshot showing the files matching dropdown with the internal option added.](../Media/mod3-ex1-task4-5.png)

1. On the **Decide whether to prioritize content** page, select **Next**

    ![Screenshot showing the files matching dropdown with the internal option added.](../Media/mod3-ex1-task4-6.png)

1. On the **Choose triggering event for this policy** page, review the **Select which sequences will trigger this policy** and view the information stating **Some sequences require specific indicators to be turned on in 'Settings' before they can be selected below.**

1. Select the option to **Turn on indicators** to enable the necessary sequence indicators for this policy.

    ![Screenshot showing the files matching dropdown with the internal option added.](../Media/mod3-ex1-task4-9.png)

1. Data leaks is primarily a data exfiltration insider risk policy. In the dialogue to enable sequence indicators, select **Select all** to turn on all required **Exfiltrate indicators**, then select **Save**.

    ![Screenshot showing the files matching dropdown with the internal option added.](../Media/mod3-ex1-task4-8.png)

1. Select **Next** on the **Choose triggering event for this policy** page.

    ![Screenshot showing the files matching dropdown with the internal option added.](../Media/mod3-ex1-task4-11.png)

1. On the **Choose thresholds for triggering events** page, select **Next**.

    ![Screenshot showing the files matching dropdown with the internal option added.](../Media/mod3-ex1-task4-10.png)

1. On the **Indicators** page, select **Next**.

    ![Screenshot showing the files matching dropdown with the internal option added.](../Media/mod3-ex1-task4-12.png)

1. On the **Detection options**, select **Next**.

    ![Screenshot showing the files matching dropdown with the internal option added.](../Media/mod3-ex1-task4-13.png)

1. On the **Choose threshold type for indicators** page, select **Next**. This policy uses a built-in triggering event and indicators. It starts evaluating user activity only when Microsoft Defender for Endpoint detects threats like defense evasion or unwanted software.

    ![Screenshot showing the files matching dropdown with the internal option added.](../Media/mod3-ex1-task4-14.png)

1. On the **Review settings and finish** page, select **Submit**.

    ![Screenshot showing the files matching dropdown with the internal option added.](../Media/mod3-ex1-task4-15.png)

1. Select **Done** on the **Your policy was created** page.

    ![Screenshot showing the files matching dropdown with the internal option added.](../Media/mod3-ex1-task4-16.png)

1. Back on the **Policies** page, your policy should now have a **Healthy** status.

    ![Screenshot showing the files matching dropdown with the internal option added.](../Media/mod3-ex1-task4-17.png)

Your insider risk policy is now healthy and ready to detect risky activities based on sequence triggers and enabled indicators.

## Task 5 – Enable Microsoft Defender for Endpoint integration with Insider Risk Management

In this task, you'll enable integration between Microsoft Defender for Endpoint and Microsoft Purview so security alerts can be used in insider risk policies.

1. In Microsoft Edge, navigate to Microsoft Defender by going to `https://security.microsoft.com`.

1. In the left navigation pane, select **System (1)** > **Settings (2)** > **Endpoints (3)**.

    ![Screenshot showing the files matching dropdown with the internal option added.](../Media/mod3-ex1-task5-1.png)

1. Under **Advanced features (1)**, scroll down and select the toggle to **On (2)** to **Share endpoint alerts with Microsoft Compliance Center**.

1. Select **Save preferences (3)** at the bottom of the screen.

    ![Screenshot showing the files matching dropdown with the internal option added.](../Media/mod3-ex1-task5-2.png)

You've successfully enabled Defender for Endpoint to share alerts with Microsoft Purview.

## Task 6 – Enable indicators and configure priority users

In this task, you'll configure the policy indicators and create a priority user group that can be used in insider risk policies.

  >**Note:**  Microsoft Defender for Endpoint indicators might appear greyed out and unselectable if the integration from the previous task hasn't finished processing. If that happens, wait a few minutes and refresh the page before continuing.

1. In **Microsoft Edge**, navigate to `https://purview.microsoft.com`.

1. Select **Settings (1)** > **Insider risk management (2)**. Select the tab on the left for **Policy indicators (3)**.

    ![Screenshot showing the files matching dropdown with the internal option added.](../Media/mod3-ex1-task6-1.png)

1. On the **Policy indicators** page, expand and select **Select all** to enable all indicators in these categories:

   - Microsoft Defender for Endpoint indicators
   - Risky browsing indicators (preview)

        ![Screenshot showing the files matching dropdown with the internal option added.](../Media/mod3-ex1-task6-2.png)

        ![Screenshot showing the files matching dropdown with the internal option added.](../Media/mod3-ex1-task6-3.png)

1. Select **Save** at the bottom of the page.

    ![Screenshot showing the files matching dropdown with the internal option added.](../Media/mod3-ex1-task6-4.png)

1. Select the **Priority user groups (1)** tab, then select **+ Create priority user group (2)**.

    ![Screenshot showing the files matching dropdown with the internal option added.](../Media/mod3-ex1-task6-5.png)

1. On the **Name and describe the priority user group** page, enter:

   - **Name**: `Finance team (1)`
   - **Description**: `Team members who manage financial operations, budgeting, and payroll systems. (2)`
   - Select **Next (3)**.

        ![Screenshot showing the files matching dropdown with the internal option added.](../Media/mod3-ex1-task6-6.png)

1. On the **Members** page, select **+ Members (1)**. In the **Members** flyout, search for and select. Then choose **Add (5)** to add the three members to the Finance team priority group. Then select **Next (6)**.

   - `Lynne Robbins (2)`
   - `Debra Berger (3)`
   - `Megan Bowen (4)`

     ![Screenshot showing the files matching dropdown with the internal option added.](../Media/mod3-ex1-task6-7.png)

1. On the **Choose who can view data involving users in this priority group**, select **+ Choose users and role groups (1)**. In the flyout, select the checkbox for **Insider Risk Management (2)**, then select **Add (3)**. Then choose **Next (4)**.

    ![Screenshot showing the files matching dropdown with the internal option added.](../Media/mod3-ex1-task6-8.png)

1. From the **Review** page, choose **Submit** , then select **Done** once your priority user group has been created.

You've configured policy indicators and created a priority group for monitoring high-risk users.

## Task 7 – Create a policy for security policy violations by priority users

In this task, you'll create an insider risk policy that detects Defender for Endpoint alerts for risky activity by priority users.

1. In Microsoft Purview, select **Solutions** > **Insider Risk Management** > **Policies**.

1. On the **Policies** page, select **+ Create policy (1)**, then select **Custom policy (2)**.

    ![Screenshot showing the files matching dropdown with the internal option added.](../Media/mod3-ex1-task7-1.png)

1. On the **Choose a policy template** page, select **Security policy violations by priority users (1)**, then select **Next (2)**.

    ![Screenshot showing the files matching dropdown with the internal option added.](../Media/mod3-ex1-task7-2.png)


1. On the **Name your policy** page, enter:

   - **Name**: `Security policy violations - Priority users (1)`
   - **Description**: `Detects Defender for Endpoint alerts for risky activity by priority users, such as malware or disabled protections. (2)`
   - Select **Next (3)**.

        ![Screenshot showing the files matching dropdown with the internal option added.](../Media/mod3-ex1-task7-3.png)

1. On the **Choose users, groups, & adaptive scopes** page, select **+ Add or edit priority user groups (1)**.

1. On the **Choose priority user groups** flyout, select the checkbox for the **Finance team (2)** group, then select **Add (3)**. Select **Next (4)**.

    ![Screenshot showing the files matching dropdown with the internal option added.](../Media/mod3-ex1-task7-4.png)

1. On the **Decide whether to prioritize content** page, select **Next**.

    ![Screenshot showing the files matching dropdown with the internal option added.](../Media/mod3-ex1-task7-5.png)

1. On the **Choose triggering event for this policy** page, select **Next**.

    ![Screenshot showing the files matching dropdown with the internal option added.](../Media/mod3-ex1-task7-6.png)

1. On the **Indicators** page, select **Next**.

    ![Screenshot showing the files matching dropdown with the internal option added.](../Media/mod3-ex1-task7-7.png)

1. On the **Choose threshold type for indicators** page, leave the default **Apply thresholds provided by Microsoft** option selected, then select **Next**.

    ![Screenshot showing the files matching dropdown with the internal option added.](../Media/mod3-ex1-task7-8.png)

1. On the **Review settings and finish** page, select **Submit**.

    ![Screenshot showing the files matching dropdown with the internal option added.](../Media/mod3-ex1-task7-9.png)

1. On the **Your policy was created** page, select **Done**.

    ![Screenshot showing the files matching dropdown with the internal option added.](../Media/mod3-ex1-task7-10.png)

You've created a custom insider risk policy that uses Defender for Endpoint signals to detect risky activity from priority users.

## Task 8 – Create a notice template

In this task, you'll create a notice template in Microsoft Purview to notify users when an insider risk alert is triggered.

1. In Microsoft Purview, select **Solutions (1)** > **Insider Risk Management (2)**.

    ![Screenshot showing the files matching dropdown with the internal option added.](../Media/mod3-ex1-task8-1.png)

1. Click on **Notice templates (1)** from the options available in the **Insider Risk Management** toolbar. On the **Notice templates** page, select **+ Create notice template (2)**.

    ![Screenshot showing the files matching dropdown with the internal option added.](../Media/mod3-ex1-task8-2.png)

1. Fill out the necessary information in **Create a new notice template** flyout panel on the right then Select **Create (5)**.

    - **Template name**: `Security Violation Alert (1)`
    - **Send from**: Search and select `Joni Sherman (2)`
    - **Subject**: `Unusual activity detected - please review (3)`
    - **Message body (4)**:

        ````html
        <!DOCTYPE html>
        <html>
        <body>
        <h2>Security Alert</h2>
        <p>We've detected activity from your account that might violate our organization's security policies. This could be due to malware, disabled protections, or other risky behavior.</p>
        <p>Please review your recent actions and ensure your device security settings are up to date. If you believe this alert was generated in error, contact the IT Security team for assistance.</p>
        <p>To avoid future issues, refer to the <a href="https://contoso.com/security-guidelines">Contoso Security Guidelines</a>.</p>
        <p>Thank you,</p>
        <p><em>Compliance and Security Team</em></p>
        </body>
        </html>
        ````

        ![Screenshot showing the files matching dropdown with the internal option added.](../Media/mod3-ex1-task8-3.png)

1. Wait for sometime for template to get created. Back on the **Notice templates** page you'll see the **Security Violation Alert** template you just created.

    ![Screenshot showing the files matching dropdown with the internal option added.](../Media/mod3-ex1-task8-4.png)

You've created a notice template that Insider Risk Management can use to notify users of security policy violations.

## Review

In this lab, you have completed the following tasks:

- Assigned insider risk management permissions
- Configured insider risk indicators
- Created an insider risk policy
- Customized the data leaks policy
- Enabled Microsoft Defender for Endpoint integration with Insider Risk Management
- Enabled indicators and configure priority users
- Created a policy for security policy violations by priority users
- Created a notice template