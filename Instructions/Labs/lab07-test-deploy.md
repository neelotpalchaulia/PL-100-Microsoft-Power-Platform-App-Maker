---
lab:
    title: 'Lab 07: Test & Deploy'
    module: 'Module 07: Testing & deployment'
---

> **NOTE**
>
> Effective November 2020:
> - Common Data Service has been renamed to Microsoft Dataverse. [Learn more](https://aka.ms/PAuAppBlog)
> - Some terminology in Microsoft Dataverse has been updated. For example, *entity* is now *table* and *field* is now *column*. [Learn more](https://go.microsoft.com/fwlink/?linkid=2147247)
>

# Lab 07: Test & Deploy

In this lab you will complete solution configuration by adding security roles for the users. Then you will verify, test, and deploy the solution in the production environment.

## What you will learn

  - How to deploy a solution to another environment

## High-level lab steps

  - Exercise 1 – Create security roles for users 
    
      - Company 311 User – read all on Building, user owned on Problem Reports 
      
      - Company 311 Admin – All access for Buildings, Departments, Problem Reports 
      
      - Associate Company 311 Admin role with model-driven app 

  - Exercise 2 – Run solution checker

  - Exercise 3 – Use Test Studio to create test case for submitting problem (ok to not include image)

  - Exercise 4 – Export and import solution
  
  - Exercise 5: Add existing flow to solution

## Prerequisites

* Must have completed **Lab 02.1: Data model and model-driven app**

## Detailed steps

### Exercise 1: Create security roles

In this exercise, you will create security roles for users.

#### Task 1: Create security roles

1.  Navigate to the [Power Apps maker portal](https://make.powerapps.com/) and make sure you are in the correct environment.
2.  Select **Solutions** and click to open the **Company 311** solution.
3.  Click **+ New >> Security** and select **Security Role**.
4.  Enter **Company 311 User** for **Role Name** and select the **Custom Entities** tab.
5.  Set the read privilege of the **Building** table to **Organization**.
6.  Set the read privilege of the **Problem Report** Table to **User**.
7. The read privileges for the **Building** and **Problem Report** Tables should now look like the image below. Click **Save Create New**.

   ![A Screenshot with an arrow pointing to the save create new icon in the topmost part of the window and borders around the building and problem report on the list of custom entities](07/media/image2.png)

8. Enter **Company 311 Admin** for **Role Name** and select the **Custom Entities** tab

9. Set all privileges of the **Building**, **Department**, and **Problem Reports** Tables to **Organization**.

   ![A screenshot of building, department, and problem report having all privileges selected in the custom entities tab](07/media/image3.png)

10. Select the **Customizations** tab.
11. Set all privileges for **Model-driven app**.

![A screenshot of the security role edit dialog with all privileges selected for Model Driven app table](07/media/image25.png)

12. Click **Save and Close**.
13. Click **Done** on the popup.
14. Select **Solutions**.
15. Click **Publish all customizations** and wait for the publishing to complete.

### Exercise 2: Solution checker

In this exercise, you will run the solution checker on the Company 311 solution.

#### Task 1: Run solutions checker

1. Make sure you are still on the [Power Apps maker portal](https://make.powerapps.com/) site and you are in the correct environment.

2. Select **Solutions**, select **Company 311** solution, click **Solution checker** and select **Run**.

   ![A screenshot of the drop down from the solution checked button](07/media/image4.png)

3. The solution checker should start checking your solution, wait for it to complete. The solution check column value will change to Results with a timestamp.

4. **Refresh** the page and select the solution again, click **Solution checker**, and select **View results**.

![A Screenshot with an arrow pointing to the solution checked drop down icon and a border around the view results button](07/media/image5.png)

5. Review the solution check results and make sure there are no issues.

> **NOTE**
>
> If you are seeing errors in the Solution Check Result, open the component showing errors one by one and resolve the issues.
>
> At this point you will see errors for Canvas Apps. Open both the apps one by one and fix the assessible label and Tab Index error. For assistance, you can refer to [Microsoft Documentation](https://docs.microsoft.com/en-us/powerapps/maker/canvas-apps/accessibility-checker). After resolving the issues, save and publish your app. Go back to the solution and re-run the solution checker.
>
> Users who have vision, hearing, or other impairments can use your canvas app more easily and successfully if you consider accessibility as you design how the app looks and behaves.

### Exercise 3: Use test studio

In this exercise, you use test studio to create test case for submitting a problem report.

#### Task 1: Create test case

1.  Navigate to the [Power Apps maker portal](https://make.powerapps.com/) and make sure you are in the correct environment.

2.  Select **Apps**, select the **Company 311 Phone** application, and click **Edit**. Select **Skip** if prompted.

    ![A Screenshot with an arrow pointing to the edit button](07/media/image6.png)

3.  Click **File** and select **Settings**.

4.  Select **Upcoming features**.

5.  Select the **Experimental** tab and enable **Formula level error management**.
6.  Close the settings pane.
    
    Note: Currently test studio cannot record steps inside components like the tab control we are using, you edit the App OnStart formula, so the app navigates directly to the new report screen.

7.  Select the **Tree view** menu.

8.  Select **App** and select **OnStart**.
9.  Add the formula below to the existing formula.

    ```; Navigate('New Reports Screen')```

    ![A screenshot with a border around the relevant formula added to the existing formula](07/media/image7.png)
    

**Note:** Navigate in App Onstart has been retired, to enable it perform the following steps:
    1. Select **File**
    2. Select **Settings**
    3. Select **Upcoming Features**
    4. Select **Retired**
    5. Turn on the **Enable the Navigate function in App.onstart** feature
    6. Close the **Settings** pane.

9. Click **File** and select **Save**.

10. Click **Publish**.

11. Select **Publish this version** and wait for the publishing to complete.

12. Click on the **back** button to go back to the app designer.

13. Select the **Advanced tools** tab and select **Open tests**.

    ![A screenshot of the left navigation pane with an arrow pointing to the Advanced tools icon. Advanced tools pane is expanded with Open tests link highlighted with a rectangular border.](07/media/image26.png)

14. Click on the **ellipsis** of the **Case** and select **Rename**.

15. Rename the Case to **Submit problem report**.

16. Click **Record**.

17. You should see the **New Report** tab.

18. Fill out the form and click **Submit**.

19. Click **Done** button on the bottom-left side of the screen.

21. You should see list of the recorded steps. Click **Play**.

    ![A Screenshot with an arrow pointing to the play button](07/media/recordedSteps.png)

22. Click **Publish** and wait for the publishing to complete.

23. The steps should replay correctly. Click **Done**.

24. Close the test studio browser window or tab.

25. Close the app designer browser window or tab.


### Exercise 4: Import export

In this exercise, you will export the company 311 solution and import it into a new environment.

#### Task 1: Export solution

1.  Navigate to the [Power Apps maker portal](https://make.powerapps.com/) and make sure you are in the correct environment.

2.  Select **Solutions**, and click to open the **Company 311** solution.
3.  Click **+ Add existing** and select **Connection Reference**.

![A Screenshot with an arrow pointing to the add existing drop down icon](07/media/add_connection_ref.png)

4.  Select all of the connection references and click **Add**.
5.  Click **Publish all customizations** and wait for the publishing to complete.
7.  Click **Export**.

![A Screenshot with an arrow pointing to the export button](07/media/image8.png)

8.  Click **Next**.
9.  Select **Managed** and click **Export**.

10. Save the solution on your computer.

11. Click **Export** again.

12. Click **Next**.

13. Select **Unmanaged**, change the **version** to match the managed solution version and click **Export**.

14. You should have the managed and unmanaged versions of the solution exported.

#### Task 2: Create new environment and import solution

1.  Navigate to [Power Apps Community Plan page](https://powerapps.microsoft.com/en-us/communityplan/)
2.  Click on **Existing User? Add a dev environment**.
3.  Enter your credentials when prompt to sign in
4.  Select your country from the dropdown menu and click **Accept**
5.  Navigate to [Power Platform Admin Center](https://admin.powerplatform.microsoft.com/environments) to see a new environment had been created by the system. We will refer to it as "Prod" environment for the rest of this course (the environment name will be <your account name>'s Environment).
6.  Navigate to the [Power Apps maker portal](https://make.powerapps.com/) and select the environment you just created.
7.  Select **Solutions** and click **Import**.
8.  Click **Browse**.
9.  Select the managed solution you exported and click **Open**.
    ![A screenshot of a border around a zip file of the managed solution you exported](07/media/image10.png)
10.  Click **Next**.
11.  Click **Next** again.
12.  Click **Select connection** for outlook and then click **+ New connection**.

![A Screenshot with an arrow pointing to the drop down icon and a border around the plus new connection button](07/media/new_connection.png)

13. It will open a new window. Click **Create**.
14. Provide your **credentials**.
15. Close the connections browser window or tab.
16. Click **Refresh**.
17. Repeat steps 12 - 16 for the rest of the of the connections.
18. Click **Import** and wait for the import to complete.
19. Click **Publish all customizations** and wait for the publishing to complete.
20. Click to open the **Company 311** solution you just imported.
21. Review the components in solution.
22. Select **Apps** and make sure you have both the Canvas and Model-driven applications.
23. Click to open the **Company 311 Admin** application.
24. The application should load without issues.
25. Close the Company 311 Admin application browser window or tab.
26. Click To open the **Company 311 Phone App**.
27. The application should load without issues.
28. Close the **Company 311 Phone App** browser window or tab.


### Exercise 5: Add existing flow to solution

An employee has created a simple personal productivity flow. The flow looks like a very useful addition to everyone at the company so the decision was made to make this flow available to everyone by including it into the existing solution.
In this exercise, you will create the flow outside of the solution and then add it to the Company 311 solution.


#### Task 1: Create the team
In this task, you will create the Lunchtime Sports team.

1.  Navigate to [Microsoft Teams](https://teams.microsoft.com/).
2.  Select **Teams** and click **Join or create a team**.

![A Screenshot with an arrow pointing to the join or create a team button](07/media/join_create_team.png)

3.  Click **Create team**.
4.  Select **From scratch**.
5.  Select **Public**.
6.  Enter **Lunchtime Sports** for Team name and click **Create**.
7.  Click **Skip**.

#### Task 2: Create the flow
In this task, you create a flow that will get triggered when someone is added to the group "Lunchtime Sports", the flow will send a notification to you and tell you to find out what sport the new member will be playing.

1.  Navigate to the [Power Apps maker portal](https://make.powerapps.com/) and make sure you are in the correct environment (your practice environment).
2.  Select **Flows**.
3.  Click **+ New flow** and select **Automated cloud flow**.

![A Screenshot with an arrow pointing to the new flow button](07/media/image11.png)

4.  Click **Skip**.
5.  Search for groups and select **When a group member is added or removed** Office 365.

![A screenshot with a border around the when a group member is added is added or removed button](07/media/image12.png)

6.  Click **Sign in**.
7.  Provide your credentials.
8.  Select **Lunchtime Sports** for Group Id and click **+ New step**.
9.  Select **Condition**.
10. Click on the left value field and select **@removed** from the dynamic content pane.
11. Select **is equal to** on the second value field, for third value field select the **Expression** tab, type **null** and click **OK**.

    ![A screenshot of a border around the choose value field, then another border around the text null typed into the expression tab and an arrow pointing to the ok button](07/media/image13.png)

12. Go to the **If yes** branch and click **Add an action**.
13. Search for **get user profile** and select **Get user profile (V2)**.
14. Click on the User (UPN) field and select **User Id** from the dynamic content pane.

    ![A screenshot of a border around user UPN field and user Id in the field. There is also an arrow pointing to the user Id option in the dynamic content pane](07/media/image14.png)

15. Click **Add an action** again.
16. Search for **send** and select **Send me an email notification**.
17. Type **New Lunchtime Sports Member** for Subject.
18. Click on the Body field and select **Display Name** from the dynamic content pane.
19. Type **was added to the Lunchtime Sports team, find out what sports this member is interested in.** after the Display Name.

![A screenshot of the send me an email notification command in the flow with the relevant text in the subject and body field](07/media/image15.png)

20. Rename the flow **Notify me when a member is added to the Lunchtime Sports group** and click **Save**.

    ![A screenshot with a box around new name of the flow and an arrow pointing to the save button](07/media/image16.png)



#### Task 3: Test the flow
In this task, you will test the flow.

1.  Navigate to the [Teams](https://teams.microsoft.com/).
2. Click on the **... More options** button of the Lunchtime Sports team and select **Manage team**.

   ![A Screenshot with an arrow pointing to the ellipsis icon for more options and a border around the manage team button](07/media/image17.png)

3. Click **Add member**.
4. Search and select a user you want to use for testing.
5. click **Add**.
6. Click **Close**.
7. Navigate to [Outlook online](https://outlook.office.com/).
8. You should receive the email notification. Open the notification email.
9. The email should look like the image below.

   ![A screenshot of how the email should look](07/media/image18.png)




#### Task 4: Add flow to solution
In this task, you will add the flow to the Company 311 solution.

1.  Navigate to the [Power Apps maker portal](https://make.powerapps.com/) and make sure you are in the correct environment.
2.  Select **Solutions** and click to open the **Company 311** solutions.
3.  Click **+ Add existing** and select **Automation >> Cloud flow**.
4. Select the **Outside Dataverse** tab, select the flow you created, and click **Add**.

   ![A screenshot of the flow you created selected and an add button below](07/media/image19.png)

5. Click **Publish all customizations** and wait for the publishing to complete.
6. Click **Export**.
7. Click **Next**.
8. Select **Managed** and click **Export**.
9. Wait for the export to complete and save the exported solution on your machine.
10. Click **Export** again.
11. Click **Next**.
12. Select **Unmanaged**, change the **version** to match the managed solution you just exported and click **Export**.
13. Wait for the export to complete and save the exported solution on your machine.

#### Task 5: Import solution
In this task, you will import the solution into another environment.

1.  Navigate to the [Power Apps maker portal](https://make.powerapps.com/) and select the **Prod** environment that you created in **Exercise 4 Task 2**.
2.  Select **Solutions** and click **Import**.
3.  Click **Browse**.
4.  Select the **managed** version you just exported and click **Open**.
5.  Click **Next**.
6.  You should get a message **This solution package contains an update for a solution that is already installed** click **Import**.

![A screenshot of the import a solution pane with the message mentioned in step six having appeared.](07/media/image27.png)

7.  Wait for the solution import to complete.
15. Click to open the **Company 311** solution.
16. Locate the flow you added to the solution and click to open it.

![A Screenshot with an arrow pointing to the name of the flow you added to the solution](07/media/image21.png)

10. Click **Edit**.

    ![A Screenshot with an arrow pointing to the edit button](07/media/image22.png)

11. Click to expand the trigger.
12. Click **+ Add new connection**.

![A Screenshot with an arrow pointing to the add new connection button](07/media/image23.png)

13. Click to expand the condition..
14. Click to expand the first step in the **If yes** branch.
15. Click **+ Add new connection** again.
16. Click to expand the last step.
17. Click **+ Add new connection** one more time.
18. Click **Save** and wait for the flow to be saved.
19. Click on the **<-** back button.
20. Click **Turn on**.
21. The flow should show the status as **On**. You can verify the Status value in the Details sections.

