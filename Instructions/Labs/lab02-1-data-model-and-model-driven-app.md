---
lab:
    title: 'Lab 02.1: Data model and model-driven app'
    module: 'Module 02: Create a model-driven app'
---

> [!NOTE]
> Effective November 2020:
> - Common Data Service has been renamed to Microsoft Dataverse. [Learn more](https://aka.ms/PAuAppBlog)
> - Some terminology in Microsoft Dataverse has been updated. For example, *entity* is now *table* and *field* is now *column*. [Learn more](https://go.microsoft.com/fwlink/?linkid=2147247)
>


# Lab 02.1: Data model and model-driven app

In this lab you will be implementing the data model for the solution and building a model-driven app that will be used for fixing problems or managing the overall effort.

## What you will learn

  - Create Tables, Columns, and relationships

  - Create a model-driven app

  - Create a site map

  - Create and configure Table forms

  - Create and configure Table views

## High-level lab steps

  - Exercise 1 – Create publisher and solution  

  - Exercise 2 – Implement the data model 
    
      - Data Model 
        
          - Building 
          
          - Department 
          
          - Problem Report 

  - Exercise 3 – Configure forms and views 

  - Exercise 4 – Compose a basic model-driven app 

  - Exercise 5 – Input data and refine some views, import some problem reports 

## Detailed steps

### Exercise 1: Create publisher and solution

In this exercise, you will create a custom solution publisher and a solution. This solution will be used in all the labs for this course to keep all the components together.

#### Task 1: Create publisher and solution

1.  Navigate to the [Power Apps maker portal](https://make.powerapps.com/) and make sure you are in the practice environment you created.

2.  Select **Solutions** and click **+ New solution**.

3.  Enter **Company 311** for **Display name** and click.

4.  Click on the **+ New Publisher**, under the **Publisher** option.

![A Screenshot with an arrow pointing to the new publisher button](02-1/media/image1.png)

5.  Enter **Lamna Healthcare** for **Display name**, **lamnahealthcare** for **Name**, **lh** for **Prefix**, **88186** for Choice value prefix, and click **Save**.

![A screenshot of the new publisher properties pane](02-1/media/image105.png)

6.  Click on the **Publisher** dropdown and select the **Lamna Healthcare** publisher you created.

8.  Click **Create**.

![A screenshot of the new solution pane](02-1/media/image3.png)

9.  You should now see the solution you created in the solution list.

![A screenshot with a border around your solution](02-1/media/image4.png)

### Exercise 2: Implement data model

In this exercise, you will create Tables, Columns, and the Relationships you identified when you designed the data model for the Company 311 app.

#### Task 1: Create Tables

1.  In the [Power Apps maker portal](https://make.powerapps.com/) select **Solutions** and click to open the **Company 311** solution you created in Exercise 1.

2.  Click **+ New** and select **Table**.

3.  Enter **Building** for **Display name** and click **Save**.

![A screenshot of the new table window with the relevant value in each field](02-1/media/image5.png)

4.  Make sure you are on the **Company 311** solution page.

5.  Click **+ New** and select **Table** again.

6.  Enter **Department** for **Display name** and click **Save**.

![A screenshot of the new table window with the relevant value in each field](02-1/media/image7.png)

7.  Make sure you are on the **Company 311** solution page.

![Building Table properties - screenshot](02-1/media/image99.png)

8.  Click **+ New** and select **Table** one more time.

9.  Enter **Problem Report** for **Display name**, on the **Primary Column** tab, enter **Title** for **Display name**.

![A screenshot with a border around the primary name column settings: display name and name. There is also an arrow pointing to the more settings button below](02-1/media/image8.png)

10. Click to expand the **Advanced Options** under the **Properties** tab.

![A Screenshot with an arrow pointing to the collaboration button](02-1/media/image9.png)

11. Check the **Can be added to a queue** checkbox under the **Rows in this table** and click **Save**. Enabling queues allows Problem Report Rows to be associated with one or more queues to help facilitate routing to the different departments.

![A screenshot of the enable queues checkbox highlighted](02-1/media/image10.png)

12. Click **Okay** on the **Confirm changes** popup(if it appears).

![A screenshot of the confirm changes popup](02-1/media/image11.png)

#### Task 2: Add Columns

In this task, you will add Columns to the Problem Report Table.

1.  Navigate to the [Power Apps maker portal](https://make.powerapps.com/) page and make sure you are in the correct environment.

2.  Select **Solutions** and click to open the **Company 311** solution you created in exercise 1.

3.  Locate and click to open the **Problem Report** Table.

![A screenshot of a border around the problem report button](02-1/media/image12.png)

4.  Select the **Columns** tab and click **+ Add Column**.

![A Screenshot with an arrow pointing to the add column button](02-1/media/image13.png)

5.  Enter **Location** for **Display name**, select **Text** for **Data type**, and click **Advanced options**.

![A Screenshot with an arrow pointing to the advanced options at the bottom of the location window](02-1/media/image14.png)

6.  Change **Max length** to **150** and click **Done**.

![A screenshot showing the max length at a value of 150](02-1/media/image15.png)

7.  Click **+ Add Column** again.

8.  Enter **Details** for **Display name**, select **Multiline text** for **Data type**, make the Column **Required**, and click **Done**.

![A screenshot of the details window with the relevant values in each field](02-1/media/image16.png)

9.  Click **+ Add Column** again.

10. Enter **Photo** for **Display name**, select **Image** for **Data type**, and click **Done**.

11. Click **+ Add Column**.

12. Enter **Resolution** for **Display name**, select **Multiline text** for **Data type**, and click **Done**.

13. Click **+ Add Column**.

14. Enter **Resolved On** for **Display name**, select **Date and time** for **Data type**, and click **Done**.

15. Click **Default** Filter and select **Custom**. (For small screen devices, default dropdown goes into the **ellipsis**).
![A Screenshot with an arrow pointing to the default dropdown menu and a border around the custom button](02-1/media/image17.png)

16. You should now see the 5 new Columns you created. Click **Save Table**.

![A screenshot showing the 5 new columns you have created: details, location, photo, resolution, and resolved on](02-1/media/image18.png)

17. Go back to the **Solutions**, click on the solution name **Company 311**.

18. Click **Publish all customizations** and wait for the publishing to complete.

19. Do not navigate away from this page until all customizations have been published successfully.

#### Task 3: Edit status reason Choice

In this task, you will edit the status reason Column of the problem report Table.

1.  Make sure you are in the **Company 311** solution.

2.  Click to open the **Problem Report** Table.

3.  Click on the **… More commands** button and select **Switch to classic**.

> [!NOTE]  
> You are switching to classic because the modern solution explorer does not support editing status reason yet but will in the future.

![A Screenshot with an arrow pointing to the ellipses icon for more options next to AI builder and a border around the switch to classic button](02-1/media/image19.png)

4.  Select **Fields** and look for **Status Reason** in the Display Name column, double click to open the **Status Reason** Column.

> [!NOTE]  
> If the pop-ups are not enabled on the browser, the pop-up window for updating the column will not open. Make sure that you have enabled open popups and redirects on the browser tab. 

![A screenshot with a border around the fields button and an arrow pointing to the display name of status code](02-1/media/image20.png)

5.  Make sure **Active** is selected for **Status** and double click to open the **Active** option.

![A Screenshot with an arrow pointing to the status with a border emphasizing it is active](02-1/media/image21.png)

6.  Change the **Label** value to **New** and click **OK**.

![A screenshot of the modify list value window](02-1/media/image22.png)

7.  Click **Add**.

![A screenshot of the type window and a border around the add button](02-1/media/image23.png)

8.  Enter **Assigned** for **Label** and click **OK**.

![A screenshot of the add list value window](02-1/media/image24.png)

9.  Click **Add** again.

10. Enter **In Progress** for **Label** and click **OK**.

11. Click **Add** again.

12. Enter **Completed** for **Label** and click **OK**.

13. Click **Add** one more time.

14. Enter **Won’t Fix** for **Label** and click **OK**.

15. You should now have 5 options. Select **New** for **Default Value** and click **Save and Close**.

![A Screenshot with an arrow pointing to the save and close button](02-1/media/image25.png)

16. Click **Publish** and wait for the publishing to complete.

17. Click **Save and Close** to close the classic editor.

18. You should now be back on the **Power Apps Maker** portal.

![A screenshot of the Power Apps Maker portal](02-1/media/image26.png)

#### Task 4: Relationships

In this task, you will create many to one relationships between the problem report Table and the building and department Tables.

1.  Make sure you are in the **Problem Report** Table.

2.  Select the **Relationships** tab and click **+ Add relationship**.

![A Screenshot with an arrow pointing to the add relationship button](02-1/media/image27.png)

3.  Select **+ Many-to-one**.

![A screenshot of a border around the many to one button](02-1/media/image28.png)

4.  Select **Building** for **Related (One) Table** and click **Done**.

![A screenshot of the many-to-one relationship settings](02-1/media/image29.png)

5.  Click **+ Add relationship** again.

6.  Select **+ Many-to-one**.

7.  Select **Department** for **Related (One) Table** and click **Done**.

8.  Click **Save Table**.

9.  Go back to the **Solutions**, click on the solution name **Company 311**.

10. Click **Publish all customizations** and wait for the publishing to complete.

### Exercise 3: Configure form and views

In this exercise, you will configure form and views for the problem report Table.

#### Task 1: Configure form

1.  Navigate to the [Power Apps maker portal](https://make.powerapps.com/) and make sure you are in the correct environment.

2.  Select Solutions and click to open the **Company 311** solution.

3.  Locate and click to open the **Problem Report** Table.

4.  Select the **Forms** tab and click to open the **Information** form of type **Main**.

![A screen shot of a border around the main form under the forms tab](02-1/media/image30.png)

5.  Use the Zoom control at the bottom of the form to make the form large enough for you to work easily. Select the **form section**.

![A Screenshot with an arrow pointing to the selection of the form section](02-1/media/image31.png)

6.  Go to the **Properties** pane, change the **Label** to **Problem details**, and enter **section\_problem\_report** for **Name**.

![A screenshot of the properties pain with the relevant text in each field](02-1/media/image32.png)

7.  While you still have the section selected, go to the **Table Columns** pane, and click on the **Building** Column. The Building Column will be added to the form.

![A screenshot with a border around the table columns icon and an arrow pointing to the building column](02-1/media/image33.png)

8.  Add the **Details**, and **Photo** Columns to the form.

9.  Your form should now look like the image below. Select the **Details** Column.

![A screenshot with the details column selected](02-1/media/image34.png)

10. Go to the **Properties** pane and click to expand the **Formatting** section.

![A Screenshot with an arrow pointing to the formatting button](02-1/media/image35.png)

11. Change the **Form field height** to **4**.

![A screenshot of the form field height set to 4](02-1/media/image36.png)

12. Select the **Components** from the toolbar.

![A Screenshot with an arrow pointing to the components icon](02-1/media/image37.png)

13. Select **1-Column section.**

![A Screenshot with an arrow pointing to the 1-column section button](02-1/media/image38.png)

14. A new section should be added to the form. Select the **new section**.

![A Screenshot with an arrow pointing to the new section selected](02-1/media/image39.png)

15. Go to the **Properties** pane, change the **Section label** to **Resolution details**, and enter **section\_resolution\_details** for **Name**.

![A screenshot of the properties pane with the relevant text in each field](02-1/media/image40.png)

16. Select **Table columns** from the toolbar.

17. Add **Department**, **Status Reason**, **Resolved on**, and **Resolution** Columns to the **Resolution details** section.

![A screenshot of the Resolution details section with the Resolution column highlighted](02-1/media/image100.png)

18. Select the **Resolution** Column.

19. Go to the **Properties** pane and click to expand the **Formatting** section.

20. Change the **Form field height** to **4**.

21. You form should now look like the image below. Click **Save**.

![A Screenshot of the Problem Report form with an arrow pointing to the Save button](02-1/media/image101.png)

22. Click **Publish** and wait for the publishing to complete.

23. Click on the **<- Back** button.

![A Screenshot with an arrow pointing to the back button arrow icon](02-1/media/image43.png)

24. You should now be back to the Table.

#### Task 2: Edit view

1.  Select the **Views** tab and click to open the **Active Problem Reports** view.

![A Screenshot with an arrow pointing to the active problem reports button](02-1/media/image44.png)

2.  Click **+ View column** and select **Building** to add the **Building** column to the view.

![A Screenshot with an arrow pointing to the view column button and a border around the building button](02-1/media/image45.png)

3.  Add **Location**, **Status Reason**, and **Owner** columns to the view.
    You will have to change the column filter to **All** when adding status reason and owner columns.

![A screenshot of a border around the column filter set to all](02-1/media/image46.png)

4.  Go to the view properties pane and click **Edit filters**.

![A Screenshot with an arrow pointing to the edit filters button](02-1/media/image47.png)

5.  Update the existing filter and set it to **Status Reason Equals New**.

6.  Click on the Column where **New** is selected.

![A Screenshot with an arrow pointing to a column with new written in it](02-1/media/image48.png)

7.  Select **Assigned**.

![A Screenshot with an arrow pointing to the assigned option in the column where new is written](02-1/media/image49.png)

8.  Click on the column again and select **In progress**.

9.  The filter should now look like the image below. Click **OK**.

![A screenshot of the edit filters window with status reason equals, new, assigned, and in progress](02-1/media/image50.png)

10. Click **Save**.

#### Task 3: Create view from existing

In this task, you will create a new view from the Active Problem Reports view.

1.  Click **Edit filters**.

![A Screenshot with an arrow pointing to the edit filters buttton](02-1/media/image51.png)

2.  Remove **In Progress** from the filter.

![A Screenshot with an arrow pointing to the in progress box in the 3rd column in the edit filters window](02-1/media/image52.png)

3.  Remove **Assigned** and **New** values form the filter.

4.  Select **Completed**.

![A Screenshot with an arrow pointing to the completed button from the drop down in the 3rd column](02-1/media/image53.png)

5.  Add **Won’t Fix** and **Inactive** values to filter.

6.  The filter should now look like the image below. Click **OK**.

![A screenshot of the edit filters window with the following; status reason equals, completed, won't fix, inactive](02-1/media/image54.png)

7.  Click on the chevron button next to the save button and select **Save As**.

![A Screenshot with an arrow pointing to the save drop down chevron icon and a border around the save as button](02-1/media/image55.png)

8.  Enter **Resolved Problems** for **Name** and click **Save**.

![A screenshot of the save as window](02-1/media/image56.png)

9.  Click on the **Back Button** of your browser to go back to the **Solutions**.

![A Screenshot with an arrow pointing to the back button](02-1/media/image57.png)

10. On the **Solutions**, click the solution name **Company 311**.

![A Screenshot with an arrow pointing to the solution name company 311](02-1/media/image58.png)

11. Click **Publish all customizations** and wait for the publishing to complete.

![A screenshot of a border around the publish all customizations button](02-1/media/image59.png)

### Exercise 4: Compose model-driven application

In this exercise, you will create model-driven application.

#### Task 1: Create new model-driven application

1.  Navigate to the [Power Apps maker portal](https://make.powerapps.com/) and make sure you are in the correct environment.

2.  Select Solutions and click to open the **Company 311** solution.

3.  Click **+ New | App | Model-driven app**.

![A screenshot of a border around the Model-driven app button](02-1/media/image60.png)

4.  Select **Modern app designer** and click **Create**.

5.  Enter **Company 311 Admin** for name and click **Create**.

![A screenshot of the New model-driven app window](02-1/media/image61.png)

6. Select **Navigation** from left menu.

   ![A screenshot of the Pages selection pane with a red arrow pointing to the tree icon in the navigation pane](02-1/media/image102.png)

7. Select the **Area1**.

![A Screenshot with an arrow pointing to area 1 selected](02-1/media/image63.png)

**Hint:** Make sure **Enable Areas** option has been been checked under the **Navigation bar** to view the **Area1**.
8. Go to the **Properties** pane, enter **Manage Problems** for **Title**, and enter **area\_manage\_problems** for **ID**.

![A screenshot of the properties pane with the title and ID changed](02-1/media/image64.png)

9. Select the **Group1**.

![A screenshot of group 1 selected](02-1/media/image65.png)

10. Go to the **Properties**, enter **Problems** for **Title**, and enter **group\_problems** for **ID**.
11. Select the **Subarea1**.
12. Go to the **Properties** pane, select **Table** for **Content Type**, and select **Problem Report** for **Table**, and enter **Problem reports** for **Title**.

![A screenshot of the properties pane and the content type, table, and title changed](02-1/media/image68.png)

> [!NOTE]
> The new app designer doesn't provide a way to add new sitemap area yet.

13. Click **Save**.
14. Click **Switch to classic**

![A Screenshot with an arrow pointing to the Switch to classic link](02-1/media/image69.png)

15. Select **Save and Continue**.

> [!NOTE] 
> If the pop-ups are not enabled on the browser, the classic view will not open. Make sure that you have enabled open popups and redirects on the browser tab. 

![Select Save and continue - screenshot](02-1/media/image103.png)

16. Click **Edit** on the Site Map.

![A Screenshot with an arrow pointing to the pencil icon to edit the site map](02-1/media/image70.png)

17.   Click **+ Add** and select **Area**.

![A Screenshot with an arrow pointing to the add button and a border around the area button](02-1/media/image96.png)

18.   Select the **New Area** you just added.

19. Go to the **Properties** pane, enter **Settings** for **Title**, and enter **area\_settings** for **ID**.

![A screenshot of the properties pane with the title and ID changed](02-1/media/image97.png)

20.  Click **Save and close** to close the sitemap editor.

21.  Click **Save and close** again to close the classic app designer.

22. You should now be back to the new app designer. **Refresh** the browser. Switch to **Navigation** menu.

23.  The new **Settings** area should now be visible in the new app designer. Select the **Setting** area.

24. Click **+ Add** and select **Group**.

![A Screenshot with an arrow pointing to the add drop down menu and a border around the group button](02-1/media/image98.png)

25.  Select the **New Group** you just added.

26.  Go to the **Properties** pane, enter **Taxonomy** for **Title**, and enter **group\_taxonomy** for **ID**.

![A screenshot of the properties pane with the title and ID changed](02-1/media/image72.png)

27.  Select the **Taxonomy** group you just added, click **+ Add** and select **Subarea**

![A Screenshot with an arrow pointing to the subarea button](02-1/media/image73.png)

28.   Select **Table** for **Content type**, **Building** for **Table** and click **Add**.

![A screenshot of the New Subarea window and the content type changed](02-1/media/image74.png)

29.  Select the **Taxonomy** group, click **+ Add** and select **Subarea** again.

30.  Select **Table** for **Content type**, select **Department** for **Table**, and click **Add**.

31. The sitemap should now look like the image below. Click **Save** to save the sitemap.

![A Screenshot with an arrow pointing to the save button on your site map which should have active departments with a name column below](02-1/media/image76.png)

32. Click **Publish** to publish the sitemap and wait for the publishing to complete.
33. **Close** the browser tab. 
34. Open a new tab and navigate to the [Power Apps maker portal](https://make.powerapps.com/) and make sure you are in the correct environment.
35. Select Solutions and click to open the **Company 311** solution.
36. Click **Publish all customizations** and wait for the publishing to complete.

![A Screenshot with an arrow pointing to the publish all customizations button](02-1/media/image77.png)

### Exercise 5: Input data

In this exercise, you will input data to the Dataverse tables.

#### Task 1: Input data

1.  Navigate to the [Power Apps maker portal](https://make.powerapps.com/) and make sure you are in the correct environment.

2.  Select **Apps** and click to open the **Company 311 Admin** application you created.

![A Screenshot with an arrow pointing to the company 311 admin app](02-1/media/image80.png)

3.  Click **Change area**.

![A Screenshot with an arrow pointing to chevron icon next to manage problems](02-1/media/image81.png)

4.  Select **Settings** area.

5.  Select **Departments** and click **+ New**.

![A Screenshot with an arrow pointing to the new button at the top of the window](02-1/media/image82.png)

6.  Enter **Facility Maintenance** for **Name** and click **Save**.

![A screenshot showing the change in name to facility maintenance](02-1/media/image83.png)

7.  Click **+ New** again.

8.  Enter **Human Resources** for **Name** and click **Save**.

9.  Click **+ New** one more time.

10. Enter **Marketing** for **Name** and click **Save**.

11. Select **Departments**.

12. You should now have three department Rows. Select **Buildings**.

![A Screenshot with an arrow pointing to the buildings button under taxonomy](02-1/media/image84.png)

13. Click **+ New**.

14. Enter **San Francisco Main Campus** for **Name** and click **Save & Close**.

15. Click **+ New** again.

16. Enter **London Paddington** for **Name** and click **Save & Close**.

17. You should now have two building Rows. Click **Change area**.

![A Screenshot with an arrow pointing to the chevron icon next to settings in the bottom left corner of the window](02-1/media/image85.png)

18. Select **Manage Problems**.

19. Click **+ New**.

![A screenshot of the active problem reports page](02-1/media/image86.png)

20. Enter **Broken door** for **Title**, select **San Francisco Main Campus** for **Building**, enter **The main entrance door will not open all the way** for **Details**, and click **Save**

![A screenshot of the new problem report window with all relevant text in each field](02-1/media/image87.png)

21. Click on the **Photo** Column.

![A Screenshot with an arrow pointing to the upload an image button](02-1/media/image88.png)

22. Select an image from your device. The sample image displayed below can be found [here](02-1/media/image89.png).

23. The image should now show on the form.

![A screenshot of a vector image of a door which should appear](02-1/media/image89.png)

24. Click **Save & Close**.

25. Close the browser tab.

### Exercise 6: Import data

In this exercise, you will import sample data into the environment. Rows are imported by a Power Automate cloud flow that you will first import using a solution.

#### Task 1: Import solution

1.  Navigate to the [Power Apps maker portal](https://make.powerapps.com/) and make sure you are in the correct environment.
2.  Select **Solutions** and click **Import**.
3.  Click **Browse**.
4.  Select the **DataImport.zip** solution file located in the lab resources folder and click **Open**.
5.  Click **Next**.
6.  Click **Next** again.
7.  Expand **Select a connection** dropdown and click **+ New connection**.
8.  New tab will open with a prompt to create **Microsoft Dataverse** connection. 
9.  Click **Create**, authenticate if required, wait until new connection is created. Close the browser tab.
10.  Click **Refresh**. Make sure new connection is selected in the dropdown. 
11.  Click **Import** and wait for the message **Solution "Data Import" imported successfully** to appear.
12.  Click **Publish all customizations** and wait for the publishing to complete. 

#### Task 2: Review and run flow

1. Navigate to the [Power Apps maker portal](https://make.powerapps.com/) and make sure you are in the correct environment.

2. Select **Solutions** and click to open the **Data Import** solution you imported.

3.  Click to open the **Import Data** flow. Click the **Get Started** button on the **Welcome to Power Automate** window.

> [!NOTE]
> If the flow is not opened after clicking on Get Started, then close the current tab, go back to your previous window, click Done and reopen the flow.

![A Screenshot with an arrow pointing to the import data button](02-1/media/image90.png)

4.  Click **Edit**.

5.  Click **Continue**.

6.  Click to expand the **Input** **Data** step.

7.  Review the JSON text in the value Column. This is the data that will be imported into your environment. Note the image data encoded as a text.

8.  Expand the **Each Department** for each control

9.  Expand and review the **Upsert Department** step.

10. Expand and review the rest of the steps.

11. Click **Save** to save the flow.

12. Click on the button and go back to the flow details page.

![A Screenshot with an arrow pointing to the arrow icon to go back](02-1/media/image92.png)

13. Click **Run**.

14. Click **Run flow**.

15. Click **Done**.

16. Wait for the flow run to complete. Click on the **Refresh** button to check if the flow run completed successfully.

![A Screenshot with an arrow pointing to the refresh button in the top right corner and a border around the status showing it has succeeded](02-1/media/image93.png)

17. Close the flow editor browser window or tab.

18. Click **Done** on the popup

#### Task 3: Review imported data

1.  Navigate to the [Power Apps maker portal](https://make.powerapps.com/) and make sure you are in the correct environment.

2.  Select **Apps** and click to open the **Company 311 Admin** application.

3.  Select Problem Reports. You should see at least three new Rows.

![A screenshot with a border around your reports, there are three new rows at the bottom](02-1/media/image104.png)

4.  Click to open one of the **Problem Report** Rows.

5.  Click on the **Search** icon of the **Building** lookup and make sure building Rows were imported.

![A screenshot of a border around the building lookup with the building rows imported](02-1/media/image95.png)

6.  Scroll down and click on the **Department** lookup.

7.  Make sure the department Rows got imported.

### **Bonus exercise**

  - Deal with problem report assignment within a department.
