---
lab:
    title: 'Lab 00: Validate lab environment'
    module: 'Module 01: Course introduction'
---


> **NOTE**
> Effective November 2020:
>
> - Common Data Service has been renamed to Microsoft Dataverse. [Learn more](https://aka.ms/PAuAppBlog)
> - Some terminology in Microsoft Dataverse has been updated. For example, *entity* is now *table* and *field* is now *column*. [Learn more](https://go.microsoft.com/fwlink/?linkid=2147247)
>


Module 0: Course introduction
=============================

## Practice Lab – Validate lab environment

Scenario
--------

In this Module 0 lab, you will acquire a Power Platform trial tenant and access the Power Platform admin center. In the admin center, we will create an individual environment for configuration during the course.

Exercise 1 – Acquire your Power Platform trial tenant 
-----------------------------------------------------

1.  Copy your **Microsoft 365 credentials** from the Authorized Lab Hoster.

2.  Navigate to [Power Apps](https://powerapps.microsoft.com/) and select **Start free**.

3.  Enter the email address from the provided Microsoft 365 credentials. Select the checkbox to agree to the terms & conditions then select **Start your free trial**.

4.  You will see a prompt that you have an existing account with Microsoft. Select **Sign in**.

5.  Enter the password provided by the Authorized Lab Hoster. 

6.  Select **Yes** to stay signed in.

7.  In the **Phone number** field, enter `0123456789` and select **Submit**.

8.  Read through the prompts by selecting **Next**, then select **Let's Go**.

    > **NOTE**
    >
    > If you encounter an error: "Sorry, there's been a disconnect", you can follow the steps below. If not, you can continue to **Exercise 2**.
    >
    > 1. Navigate to [Power Apps Maker Portal](https://make.powerapps.com).
    > 2. Select the **Gear Icon** (Settings) from top-right corner on the header of the page.
    > 3. Select **Plan(s)** and verify if you have **Power Apps Per User Plan Trial**. 
    > 4. If you have the above mentioned license, please proceed to **Exercise 2** otherwise repeat **Exercise 1**.


Exercise 2 - Create your environment 
------------------------------------

In this exercise, you will create a **Practice** environment that you will use to do the majority of the lab work in this training. 

### Task 1 – Create environment

1.  Open a new browser tab and navigate to the [Power Platform admin center](https://admin.powerplatform.microsoft.com). 
    
    Log in with your Microsoft 365 credentials if prompted again. 

2.  Select **Get Started** to begin the tour and select **Next** through each prompt. Select **Done** to finish the tour. 

3.  Select **Environments** from the site navigation and select **+ New** from the toolbar. 

    - For **Name**, enter **[my initials] Practice**. (Example: AJ Practice.) 
    
    - For **Type**, select **Trial**. 
    
    - Change the toggle on **Add a Dataverse data store?** to **Yes**. 
    
    - Leave all other selections as default and select **Next**. 

    - On the next tab, under **Security group**, select the **Select** button.

    - Under **Open access**, select **None (All users from thi...)**

    - Select **Done**.
    
    - Leave all other selections as default and select **Save**. 

    - Select **Done** and select **Save**.  

5.  Your **Practice** environment should now show in the list of Environments. 

6.  Your environment may take a few minutes to provision. Refresh the page if needed. When your environment is prepared, select your **Practice** environment by clicking on the ellipses next to its name to expand the drop down menu and select **Settings**.  

7.  Explore the different areas in **Settings** that you are interested in but do not make any changes. 

