# Lab 03.2: Canvas app

In this module you will design and build a canvas app for the company employees to submit problem reports.

## What you will learn

  - Import and use a pre-built component library
  - Create a Power Apps canvas app
  - Connect to a data source
  - Filter data
  - Create data Rows
  - Use images with data Rows
  - Embed canvas Power App into Microsoft Teams

## High-level lab steps

  - Import company components
  - Create app and layout main screen (including list of my items)
  - Submit New Report
  - Test
  - Embed canvas app in Microsoft Teams

## Prerequisites

* Must have completed **Lab 02.1: Data model and model-driven app**

## Detailed steps

  ### Exercise 1: Create canvas application

In this exercise, you will import a solution with shared components, create a view for the problem report Table and create a canvas application.

#### Task 1: Import component library solution

In this task, you will import the shared components solution into your environment. This shared component library was built by another team at your company.

1.  Navigate to the [Power Apps maker portal](https://make.powerapps.com/) page and make sure you are in the correct environment.

1.  Select **Solutions** and click **Import**.

	![A Screenshot with an arrow pointing to the import button](03-2/media/image1.png)

1.  Click **Browse**.

1.  Go to the course resources folder, select the **Shared components** solution, and click **Open**.

1.  Click **Next**.

1.  Click **Import** and wait for the import to complete.

1.  Click **Publish All Customizations** and wait for the publishing to complete.

1.  You should now see the **Shared Components** solution you imported. Click to open the **Shared Components** solution.

1. The solution should have one item in it. (**Lamna Healthcare Shared Components**)

	![A screenshot of the shared components window with the Lamna Healthcare shared components item](03-2/media/image2.png)

	**IMPORTANT**: There is an issue where importing the app as part of a solution may not add it to your components library. The following steps are designed to resolve the issue.

1. Navigate to **Apps**, Select the **Lamna Healthcare Shared Components App**.

1. Click the **Edit Icon** to edit the app.

	![A Screenshot with an arrow pointing to the edit button](03-2/media/image2-1.png)

1. Select your **Region/Country** and click **Get started** if prompted.
    
    **Note**: When the app is open in Edit mode, move on to next step, as the Preloader component shows a Loading icon but it is not actually waiting for something to load.

1. After the app opens, click **File** > **Save As**.

1. Save the app as **Lamna Healthcare Share Components A**.

	![A screenshot with a border around the app name saved as Lamna Healthcare Shared Components A](03-2/media/image2-2.png)

1. Click **OK**.

1. Close the **Lamna Healthcare Shared Components** tab in your browser.

#### Task 2: Create view

In this task, you will create a view that will show the current user’s problem reports. Later you will use this view with the filter function in the canvas app.

1.  Navigate to the [Power Apps maker portal](https://make.powerapps.com/) page and make sure you are in the correct environment.

1.  Select **Solutions** and click to open the **Company 311** solution.

1.  Locate and click to open the **Problem Reports** Table.

1.  Select the **Views** tab and click to open the **Active Problem Reports** view.

	![A Screenshot with an arrow pointing to the active problem reports view button](03-2/media/image3.png)

1.  Click **Edit filters**.

	![A Screenshot with an arrow pointing to the edit filters button](03-2/media/image4.png)

1.  Change the filter to **Created By Equals current user** and click **OK**.

	![A screenshot of the edit filters window](03-2/media/image5.png)

1.  Click on the chevron button next to the Save button and select **Save As**.

	![A Screenshot with an arrow pointing to the save as button](03-2/media/image6.png)

1.  Enter **My Reports** for **Name** and click **Save**.

1.  Click **Publish** and wait for the publishing to complete.

1. Click on the **Back** button in your browser tab to go back to the Problem Report table details.

#### Task 3: Create the user application

In this task, you will create a canvas application using the phone form factor.

1.  Navigate to the [Power Apps maker portal](https://make.powerapps.com/) page and make sure you are in the correct environment.

1.  Select **Solutions** and click to open the **Company 311** solution.

1.  Click **+ New | App |Canvas app**.

	![A Screenshot with an arrow pointing to the new button with the drop down menu under app upon and a border around the canvas app button](03-2/media/image7.png)

1.  Enter **Company 311 Phone App**, select **Phone** for format, and click **Create**.

1.  Select **Skip**.

1.  Go to the Tree view and double click **Screen1**.

	![A Screenshot with an arrow pointing to the screen 1 button](03-2/media/image9.png)

1. Rename the screen **Main Screen**. It’s always a good idea to give your screens a meaningful name.

	![A screenshot with the Screen 1 name highlighted and renamed Main Screen](03-2/media/image10.png)

1. Select the **Main Screen** and click **Insert**.

	![A Screenshot with an arrow pointing to the plus icon for insert](03-2/media/image11.png)

1. Select **Get more Components**.

	![A screenshot with a border around the get more components button](03-2/media/image12-1.png)

1.  Expand the **Lamna Healthcare Shared Components A** Library, select **Header** and **Tab Control**, and then click **Import**.

	![A screenshot of the import components window with Ta control and header selected](03-2/media/image12-2.png)

1.  Expand **Library components**, select **Header Control** and **Tab Control**. These are both components from the library you imported earlier in the lab.

	![A screenshot with a border around the library components Header and Tab control](03-2/media/image12-3.png)

1. Move the **Tab Control** to the bottom of the screen and the **Header Control** to the top of the screens.

1. Select the **Header Control** and change the **Text** value to **"Company 311".**

	![A screenshot of a border around the expression tab with the text value set to company 311](03-2/media/image13.png)

1. Set the **Height** of the **Header Control** to **75**.

	![Set Height - Header](03-2/media/image37.png)

1. Right click on the Main Screen and select **Duplicate screen**.

	![A screenshot with a border around the duplicate screen button](03-2/media/image14.png)

1. Rename the new screen **New Reports Screen**.

1. Select the **Tree view**, select **App** and change the **OnStart** value to the formula below. This formula will create a new variable named My Tabs and set it to a table of tab items.

```javascript
Set('My Tabs', Table( {
	Label: "My Reports",
	Screen: 'Main Screen',
	Icon: "",
	SelectedIcon:""
},
{
	Label: "New Report",
	Screen: 'New Reports Screen',
	Icon: "",
	SelectedIcon:""
}
))
```

  **IMPORTANT:** When expressions are copied, the quotes and double quotes are sometimes replaced with their "smart" counterparts which are not valid in formulas. If you copy and paste the expression above, make sure the resulting formula does not contain any errors.     

	![A screenshot of the copied expression into the expression tab](03-2/media/image15.png)

1. Select the **Tab Control** in the **Main Screen** and change the **Items** value to **‘My Tabs’**.

	![A screenshot of the items value set to my tabs for Tab control](03-2/media/image16.png)

1. Change the **SelectedColor** value to **WhiteSmoke**.

1. Select the **Tab Control** inside the **New Report Screen** and set the Item value to **‘My Tabs’**.

1. Change the **SelectedColor** value to **WhiteSmoke**.

1. Click on the **…** button of the **App** and select **Run OnStart**.

	![A screenshot of the run on start button coming from the ellipsis icon for see more under the app button](03-2/media/image17.png)

1. Your tabs should now show the two tabs you added.

	![A screenshot of the two tabs you added](03-2/media/image18.png)

1. Click **File** and then click **Save**.

1. Click on the **<- back** button.

1. Do not navigate away from this page.

### Exercise 2: My reports

In this exercise, you will add a gallery that will show reports created by the current logged in user.

#### Task 1: Add gallery

1.  Select the **Main Screen**, go to the **Insert** tab, click **Gallery**, and select **Vertical**.

	![A Screenshot with an arrow pointing to the vertical gallery option](03-2/media/image19.png)

1.  Rename the new gallery **My Reports Gallery**.

1.  Resize and reposition **My Reports Gallery** and make sure the screen looks like the image below.

	![A screenshot of the my reports gallery selected](03-2/media/image20.png)

1.  Select **My Reports Gallery**, go to the **Properties** pane, and select **Problem Reports** for **Data Source**. If you do not see Problem Reports, click **See all tables** or **Search** for the table.

	![A screenshot of the my reports gallery window and the properties pane with problem reports selected for data source](03-2/media/image21.png)

1.  Select the **My Reports** view you created for **View**.

1.  Click **Edit fields**.

	![A Screenshot with an arrow pointing to the edit button](03-2/media/image22.png)

1.  Change Subtitle1 to **statuscode**. This is the Status Reason Column.

	![A screenshot of a border around subtitle 1 changed to the correct name](03-2/media/image23.png)

1.  Click **File** and then click **Save**.

1.  Click on the **<- Back** button.

1. Do not navigate away from this page.

### Exercise 3: Allow removing reports

In this exercise, you will allow unassigned reports to be removed. This will allow users to easily remove any reports that were accidentally created.

#### Task 1: Allow remove

1.  Expand the **My Reports Gallery**.

1.  Select the **Icon** inside the **My Reports Gallery**.

	![A screenshot of the arrow icon inside the my reports gallery](03-2/media/image24.png)

1.  Change the **Icon** value to **Icon.Trash**.

	![A screenshot of icon.trash typed into the expression tab](03-2/media/image25.png)

1.  Change the **Visible** value to the formula below. This formula will hide the icon if the status reason is not New.

`If(Text(ThisItem.'Status Reason') = "New", true, false)`

	![A screenshot of the expression tab with the relevant command pasted in](03-2/media/image26.png)

1.  Make sure you still have the icon selected. Change the **OnSelect** value to the formula below. This formula will remove item from the data source.

`Remove('Problem Reports', ThisItem)`

1.  Click **File** and then click **Save**.

1.  Click on the **<-** **Back** button.

1.  Do not navigate away from this page.

### Exercise 4: Add new report

In this exercise, you will add a form to submit new problem reports.

#### Task 1: Add new report form

1.  Select the **New Report Screen**, go to the **Insert** tab, click **Form**, and select **Edit**.

	![A screenshot of the inset tab and forms button selected](03-2/media/image27.png)

1.  Rename the form to **New Report Form**.

1.  Select **New Report Form**, go to the **Properties** pane, and select **Problem Report** for **Data source**.

1.  Click **Edit fields**.

	![A Screenshot with an arrow pointing to the edit fields button](03-2/media/image28.png)

1.  Remove the **Status Reason** Column.

	![A Screenshot with an arrow pointing to the ellipses icon for more options and a border around the remove button](03-2/media/image29.png)

1.  Remove the **Created On** Column.

1.  Remove the **Location** Column.

1.  Click **+ Add field**.

1.  Select **Details**, **Building**, **Department**, and **Photo**, and then click **Add**.

	![A screenshot of photo, details, building, and location selected in the fields window](03-2/media/image30.png)

1. Resize and reposition the form so it takes most of the page and leave enough room for a button in the bottom.

	![A screenshot of the form resized and reposition for room at the bottom for a button](03-2/media/image31.png)

1. Select the **New Report Screen**.

1. Go to the **Insert** tab and select **Button**.

1. Rename the button **Submit Report**.

1. Place the button below the form and make it stretch across the screen

1. Change the **Submit Report** button's **text** property to **Submit**.

1. Select the Submit Report button and change the **OnSelect** value to the formula below. This formula will create a new Row in the Problem Reports table.

`SubmitForm('New Report Form') `

1. Select the **New Report Form**.

1. Change the **OnSuccess** value to the formula below. This formula will show a notification after the new Row gets created and clear the form when the record creation is successful.

`Notify("Created new problem report row");NewForm('New Report Form')`

1. Select the **New Report Screen**.

1. Set the **OnVisible** value to the formula below. This formula will create a new form when the screen becomes visible.

`NewForm('New Report Form')`

1. Click **File** and then click **Save**.

1. Click **Publish**.

1. Click **Publish this version** and wait for the publishing to complete.

1. Click on the **<-** **Back** button.

1. Do not navigate away from this page.


### Exercise 5: Test the application

In this exercise, you will test the canvas application you created by submitting a problem report.

#### Task 1: Test application

1.  Select the **Main Screen** and click **Preview the app**.

	![A Screenshot with an arrow pointing to the play icon to preview the app](03-2/media/image32.png)

1.  The application should load, and the list should show all the reports you created.

	![A screen of your loaded application](03-2/media/image33.png)

1.  Select the **New Report** tab.

1.  The **New Report Form** should load. Fill out the form and click on the **Photo** Column.

1.  Select an image.

1.  Click **Submit**

1.  The Row should get created successfully and you should see the success message.

	![A screen of the success message reading "created new problem report record"](03-2/media/image38.png)

1.  Select the **My Reports** tab.

1.  You should see the new report you created. Click **Delete** to test the delete.

	![A Screenshot with an arrow pointing to the trash can icon to delete](03-2/media/image35.png)

1. The Row should be deleted and removed from the list.

	![A screenshot of the row deleted and removed from the list](03-2/media/image36.png)

1. **Close** the preview.

1. **Close** the app studio by closing the browser tab.

### Exercise 6: Embed canvas app in Microsoft Teams

In this exercise, you will add the Company 311 Phone App that you created earlier, to Microsoft Teams as a way for staff to be able to log issues directly within Teams.

#### Task 1: Setup Company 311 Team

In this task, you will setup a **Microsoft Teams** team for the Lamna Healthcare Company, if you have not done so previously.

1.  Navigate to [Microsoft Teams](https://teams.microsoft.com) and sign in with the same credentials you have been using previously.

1.  Select **Use the web app instead** on the welcome screen.

	![A screenshot of the Microsoft Teams web browser landing page with a border around the use the web app instead button](03-2/media/image-3-teams.png)

1.  When the Microsoft Teams window opens, dismiss the welcome messages.

1.  Select **Teams**.

1.  On the bottom left corner, choose **Join or create a team**.

1.  Select **Create a team**.

	![A screenshot of a border around the join or create a team button and another border around the create a team button](03-2/media/image-3-createteam.png)

1.  Press **From scratch**.

1.  Select **Public**.

1.  For the Team name enter **Company 311** and select **Create**.

1.  Select **Skip** adding members to Company 311.

1. Do not navigate away from this page.

#### Task 2: Add canvas app to Teams

1.  Select the **General** channel of the **Company 311** team.

1.  On the top of the page, press the **+** symbol to add a new tab.

	![A screenshot of a border around the plus icon to add a new tab](03-2/media/image-3-addpowerbitab.png)

1.  Search for **power** and select **PowerApps** from the results.

1.  Select **Add** to add Power Apps to Teams

	![A screenshot of the prompt to add Power Apps to Teams](03-2/media/image-3-powerappsteams.png)

1. Select the **Company 311 Phone App** that you created earlier in this lab. 

	**IMPORTANT:** If you do not see the app you need to go back to the app editor and publish the app

1. Select **Save**.

1. The **Company 311** app should now appear on a tab in Microsoft Teams.

	![A screenshot of the company 311 app appearing on a tab in Microsoft Teams](03-2/media/image-3-powerappinteams.png)


### Exercise 7: Embed canvas in model-driven app

In this exercise, you will create a canvas application and add it to the model-driven application.

#### Task 1: Add canvas app to the form

1. Navigate to [Power Apps maker portal](https://make.powerapps.com/) and make sure you are in your practice environment.

1. Select **Solutions** and click to open the **Company 311** solutions.

1. Locate and click to open the **Building** table.

1. Select the **Forms** tab and click to open the **Information** form of type **Main**.

	![A Screenshot with an arrow pointing to the word information with a border around the form type being main](03-2/media/opentableform.png)

1. Select the **form section**.

1. Go to the Properties pane and click to expand **Formatting**.

1. Change the **Columns** value to **2**.

	![A screenshot with a border around the number of columns](03-2/media/formsectioncolumns.png)

1. Make sure you still have the section selected. Select the **Table columns** tab.

1. Uncheck the **Show only unused table columns** checkbox and click on the **Name** column.

	![A Screenshot with an arrow pointing to the name button](03-2/media/addcolumntoform.png)

1. The column should now appear on right side column of the section. Select the **Name** column on the form.

1. Check the **Hide label** checkbox and click **Save**.

	![A Screenshot with an arrow pointing to the save button](03-2/media/saveform.png)

1.  Click on the **Switch to classic** button. Select **Skip** if prompted.

	![A Screenshot with an arrow pointing to the switch to class button](03-2/media/switchtoclassic.png)

1.   Double click on the **Name** column you added to the form.

1.   Select the **Controls** tab and click **Add control**.

![A Screenshot with an arrow pointing to the add control button](03-2/media/ex_7_addcontrol.png)

1.   Select **Canvas app** and click **Add**.

1.   Click **Customize**.

![A Screenshot with an arrow pointing to the customize button](03-2/media/ex_7_customizeapp.png)

1.   A new browser window or tab should open and load the app studio.

1.   Do not navigate away from this page.

#### Task 2: Customize the app

1.  Right click on **Form1** and select **Delete**.

	![A screenshot with a border around the delete button](03-2/media/ex_7_deleteform.png)

1.  Click **File**.

1.  Select **The cloud**, enter **Model embed app** for name, and click **Save**.

	![A screenshot of the Save As prompt](03-2/media/ex_7_saveapp.png)

1.  Select **Settings**.

1.  Select **Display**.

1.  Enter **400** for Width.

	![A screenshot with a border around the width changed to 400](03-2/media/ex_7_displaywidth.png)

1.   Click **Apply** on the popup.

1.   Enter **500** for Width.

1.  Click **Apply** on the popup.

1.  Close the Settings popup window.

1.  Select the **App** object from the Tree view.

1.  Select the **OnStart** of the **App** object and set it to the formula below. This formula will create two variables one to keep track of the current index of the reports table and another to keep track of the current item row.

```Set(currentIndex,1);Set(CurrentItem, Last(FirstN([@ModelDrivenFormIntegration].Item.'Problem Reports',currentIndex)))```

	![A screenshot with a border around the app object changed to onstart and set to the aforementioned formula. There is also another border around the app button selected](03-2/media/ex_7_apponstart.png)

1.  Select the **Insert** insert tab, click **Media**, and select **Image**.

	![A screenshot of a border around the image button](03-2/media/ex_7_insertimage.png)

1.  Select the image you just added and set the **Image** value to the formula below.

```CurrentItem.Photo```

1.   Click on the **...** button of the **App** object and select **Run OnStart**.

	![A Screenshot with an arrow pointing to the ellipses icon for more options and a border around the run on start button](03-2/media/ex_7_runonstart.png)

1.  You should see the photo. Select **Image control** from Tree View.

	![A screenshot of an icon of a broken door](03-2/media/ex_7_imagephoto.png)

1. Set the **X** value of the image to **0**.

1. Set the **Y** value of the image to **0**.

1. Set the **Width** value of the image to the formula below.

```Parent.Width```

1. Set the **Height** value of the image to the formula below.

```Parent.Height```

1. Go to the **Properties** pane and select **Fill** for **Image position**.

	![A Screenshot with an arrow pointing to the the file tab](03-2/media/ex_7_imageposition.png)

1. Click **File** and then click **Save** to save your progress.

1. Click on the **<-** **Back** button.

1. Do not navigate away from this page.


#### Task 3: Add controls

1.  Select the **Insert** tab and click **Label**.

1.  Select the label you just added and set the **Text** value to the formula below.

```CurrentItem.Title```

1.  Set the **Height** value of the label to **60**.

1.  Set the **X** value of the label to **0**.

1.  Set the **Y** value of the label to formula below.

```Parent.Height -Self.Height```

1.  Set the the **Width** value of the label to formula below.

```Parent.Width```

1.  Set the **Fill** value of the label to **RGBA(0, 108, 191, .5)**.

1.  Set the **Color** value of the label to **RGBA(255, 255, 255, 1)**.

1.  Set the **Align** value to the formula below.

```Align.Center```

1. The label should now look like the image below. If you don't see the title, click on the **...** button of the **App** object and **Run OnStart** again.

	![A screenshot of the broken door icon now with a label](03-2/media/ex_7_resizedlabel.png)

1.  From the **Insert** tab, click **Icons** and select **Next**.

1.  Double click on the icon you just added and rename it **Next icon**.

1.  From the **Insert** tab, click **Icons** and select **Back**.

1.  Double click on the second icon you just added and rename it **Back icon**.

1.  Drag and place the the **Next icon** above the right side of the label.

1.  Drag and place the the **Back icon** above the left side of the label.

1.  The icons should now look like the image below.

	![A screenshot of the broken door icon with the next and back icons](03-2/media/ex_7_iconlocation.png)

1.  Select the **Next icon** and set the **OnSelect** value to the formula below.

```UpdateContext({CurrentItem: Last(FirstN([@ModelDrivenFormIntegration].Item.'Problem Reports',currentIndex))});Set(currentIndex, currentIndex +1)```

1.  Set the **DisplayMode** value of the **Next icon** to the formula below.

```If(currentIndex = CountRows([@ModelDrivenFormIntegration].Item.'Problem Reports'), DisplayMode.Disabled, DisplayMode.Edit)```

1.  Select the **Back icon** and set the **OnSelect** value to the formula below.

```UpdateContext({CurrentItem: Last(FirstN([@ModelDrivenFormIntegration].Item.'Problem Reports',currentIndex))});Set(currentIndex, currentIndex -1);```

1.  Set the **DisplayMode** value of the **Back icon** to the formula below.

```If(currentIndex > 1, DisplayMode.Edit, DisplayMode.Disabled)```

1. Click **File** and then click **Save**.

1. Open a new browser tab and navigate to [Power Apps maker portal](https://make.powerapps.com/) page and make sure you are in the correct environment

1. Select the **Apps** and click to launch the **Company 311 Admin** application.

1. Click **Change Area** and Select **Settings**.

	![Change sitemap area - screenshot](03-2/media/image39.png)

1. Select **Buildings**. 

1. Sort the Buildings rows on **Created On** Column in **Oldest to Newest** order. Keep a note of the oldest record.

1. Click **Change Area** and Select **Manage Problems**.

1. Select **Problem Reports**.

1. Click **+New**. 

1. Enter **Broken Tap** for Name, select the oldest building in the **Building** column and enter **The Tap is broken and the water is continuously flowing.** in the Details column. Add any image of your choice in the **Photo** column.

1. Click **Save**.

1. Click **+New**.

1. Enter **Roof Leaks** for Name, select the oldest building in the **Building** column and enter **Water is seeping through the ceiling.** in the Details column. Add any image of your choice in the **Photo** column.

1. Click **Save** and close the browser tab of the Model Driven App.

1. Open the Canvas App Editor for the **Model embed app** application. Select **Data** icon on the left menu.

	![Select Data - screenshot](03-2/media/image40.png)

1. Locate **Problem Reports** and click on the **ellipsis** and then click on **Refresh**.

1. Click on the **...** button of the **App** object and select **Run OnStart**.

1. Select **Tree View** from the left menu and select **FormScreen** screen.

1. Click **Play**.

1. Click on the next and back icons and make sure the image changes.

1. Close the preview.

1. Click **File**.

1. Click **Save**.

1. Click **Publish**.

1. Click **Publish this version** and wait for the publishing to complete.

1. Close the app studio browser window or tab.

1. You should now be back on the **Field Properties**. Select **Web, Phone, Tablet** and click **OK**.

	![A screenshot with a border around the canvas app item under control with web, phone, and tablet selected. There is also an arrow pointing to the ok button at the bottom of the window](03-2/media/ex_7_fieldproperties.png)

1. Click **Save** on the classic form editor.

1. Close the classic form editor browser window or tab.

1. You should now be back on the modern form editor. Click on **<-** **Back** button.

	![A Screenshot with an arrow pointing to the back button](03-2/media/ex_7_backtomaker.png)

1. Select **Solutions**.

1. Click **Publish all customizations** and wait for the publishing to complete.


#### Task 4: Test app

1. Select the **Apps** and click to launch the **Company 311 Admin** application.

	![A Screenshot with an arrow pointing to the company 311 admin application](03-2/media/ex_7_launchmodelapp.png)

1. Select **Problem reports** and click to open one of the problem report rows.

1. Make sure the problem has a photo and click on the **Building** lookup.

	![A Screenshot with an arrow pointing to the building lookup](03-2/media/ex_7_lookup.png)

1. The Canvas app should load inside the Model-Driven application. Click on the Next/Back icons and make sure the application behaves as expected.

	![A screenshot of the broken door icon in the context of the canvas app inside the Model-Driven Application](03-2/media/ex_7_canvasinmodel.png)

