---
lab:
    title: 'Lab 00: Validate lab environment'
    module: 'Module 01: Course introduction'
---


> [!NOTE]
> Effective November 2020:
> - Common Data Service has been renamed to Microsoft Dataverse. [Learn more](https://aka.ms/PAuAppBlog)
> - Some terminology in Microsoft Dataverse has been updated. For example, *entity* is now *table* and *field* is now *column*. [Learn more](https://go.microsoft.com/fwlink/?linkid=2147247)
>


Module 0: Course introduction
=================================

## Practice Lab – Validate lab environment

Scenario
--------

In this Module 0 lab, you will acquire a Power Platform trial tenant and access the Power Platform admin center. In the admin center, we will create an individual environment for configuration during the course.

Exercise 1 – Acquire your Power Platform trial tenant 
------------------------------------------

1. Copy your **Microsoft 365 credentials** from the Authorized Lab Hoster.
2. Navigate to [Power Apps](https://powerapps.microsoft.com/) and click **Start free**.
3. Under **Work email**, enter the email address from your Microsoft 365 credentials and click **Next**.
4. You will see a prompt that you have an existing account with Microsoft. Select **Sign in**.
5. Enter the password provided by the Authorized Lab Hoster. 
6. Select **Yes** to stay signed in.
7. Enter your country or region and Phone Number. Select **Get Started**.
8. Click **Get Started** again.

> [!NOTE]
> If you encounter an error: "Sorry, there's been a disconnect", you can follow the steps below. If not, you can continue to **Exercise 2**.
>
> 1. Navigate to [Power Apps Maker Portal](https://make.powerapps.com).
> 2. Select the **Gear Icon** (Settings) from top-right corner on the header of the page.
>3. Select **Plan(s)** and verify if you have **Power Apps Per User Plan Trial**. 
> 4. If you have the above mentioned license, please proceed to **Exercise 2** otherwise repeat **Exercise 1**.

Exercise 2 - Create your environment 
------------------------------------------

In this exercise, you will create a **Practice** environment that you will use to do the majority of the lab work in this training.

### Task 1 – Create environment

1.  Navigate to [Power Platform admin center](<https://admin.Powerplatform.microsoft.com) and log in with your Microsoft 365 credentials if prompted again.

2. Select **Environments** and click **+ New**.

    - For **Name**, enter **[my initials] Practice**. (Example: AJ Practice.)
    
    - For **Type**, select **Trial**.
    
    - Change the toggle on **Create a database for this environment?** to **Yes**.
    
    - Leave all other selections as default and click **Next**.

    - On the next tab, leave all selections to default and click **Save**.

3. Your **Practice** environment should now show in the list of Environments. 

4. Your environment may take a few minutes to provision. Refresh the page if needed. When your environment is prepared, select your **Practice** environment by clicking on the ellipses next to its name to expand the drop down menu and select **Settings.** 

5.  Explore the different areas in **Settings** that you are interested in but do not make any changes. 
