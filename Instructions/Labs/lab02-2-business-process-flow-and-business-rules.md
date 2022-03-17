# Lab 02.2: Business Process Flows and Business Rules

In this lab you will enhance the data model and improve the app behavior by adding a business process flow and a business rule.

## What you will learn

  - How to identify stages in a Business Process Flow (BPF)

  - How to create and use a BPF

  - How to use a business rule to implement logic

## High-level lab steps

  - Exercise 1 – Create BPF lifecycle of problem report
    
      - Route 
      
      - Fix 
      
      - Resolved 

  - Exercise 2 – Business rule to not allow close without resolution

## Prerequisites

* Must have completed **Lab 02.1: Data model and model-driven app**

## Detailed steps

### Exercise 1: Create business process flow

In this exercise, you will create a business process flow for the problem report table.

#### Task 1: Customize Table

In this task, you will add a lookup Column to the problem report table.

1.  Navigate to the [Power Apps maker portal](https://make.powerapps.com/) page and make sure you are in the correct environment.

1.  Select **Solutions** and click to open the **Company 311** solution.

1.  Locate and click to open the **Problem Report** Table.

1.  Make sure you have the **Columns** tab and click **+ Add Column**.

1.  Enter **Assign to** for **Display name**, select **Lookup** for **Data type**, select **User** for **Related table**, and click **Done**.

    ![A screenshot of the assign to panel with all relevant values in each field](02-2/media/image1.png)

1.  Click **Save Table**.

1.  Go back to the solution by clicking on the Back arrow.

1.  Click **Publish all customizations** and wait for the publishing to complete.

#### Task 2: Create business process flow

In this task, you will create a business process flow for the problem report Table.

1.  Navigate to the [Power Apps maker portal](https://make.powerapps.com/) page and make sure you are in the correct environment.

1.  Select **Flows**.

1.  Select the **Business process flows** tab and click **+ New**.

    ![A Screenshot with an arrow pointing to the new button](02-2/media/image3.png)

1.  Enter **Problem resolution process** for **Flow Name**, select **Problem Report** for **Table**, and click **Create**.

1.  Select the **New stage**, go to the **Properties** pane, change the **Display Name** to **Route**, and click **Apply**.

    ![A screenshot of the new stage and properties pane](02-2/media/image4.png)

1.  Expand **Details** of the **Route** stage.

    ![A Screenshot with an arrow pointing to the details button](02-2/media/image5.png)

1.  Select **Data Step \#1**, go to the **Properties** pane, select **Building** for **Data Field**, and click **Apply**.

    ![A screenshot of the new stage with data step one selected and the properties pane open](02-2/media/image6.png)

1.  Click **+ Add** and select **Add Data Step**.

    ![A Screenshot with an arrow pointing to the add button and a border around add data step button](02-2/media/image7.png)

1. Select the **+** option to add the data step below the **Building** data step.

   ![A screenshot of a data step being about to be added to the process stage](02-2/media/image27.png)

1. Select the new data step, go to the **Properties** pane, select **Location** for **Data Field**, and click **Apply**.

1. Click **+ Add** again and select **Add Data Step**.

1. Select the new data step, go to the **Properties** pane, select **Department** for **Data Field**, and click **Apply**.

1. The **Route** stage should now look like the image below.

    ![A screenshot of the completed route stage with three data steps: building, location, and department](02-2/media/image8.png)

1. Click **+ Add** and select **Add Stage**.

1. Add the new stage after the **Route** stage.

1. Select the stage, go to the **Properties** pane, enter **Fix** for **Display Name**, and click **Apply**.

1. Expand **Details** of the **Fix** stage.

1. Select **Data Step \#1** of the **Fix** stage.

1. Go to the **Properties** pane, select **Assign to** for **Data Field** and click **Apply**.

1. Click **+ Add** and select **Add Stage**.

1. Add the new stage after the **Fix** stage.

1. Select the new stage, go to the **Properties** pane, enter **Resolve** for **Display Name** and click **Apply**.

1. Expand **Details** of the **Resolve** stage.

1. Select **Data Step \#1** of the **Resolve** stage.

1. Go to the **Properties** pane, select **Resolution** for **Data Field** and click **Apply**.

1. Click **+ Add** and select **Add Data Step**.

1. Add the new data step below the **Resolution** data step.

1. Select the new data step, go to the **Properties** pane, select **Resolved on** for **Date Field** and click **Apply**.

1. The Business process flow should now look like the image below. Click **Save**.

    ![A Screenshot of a Business Process Designer with an arrow pointing to the save button](02-2/media/image9.png)

1. Click **Activate Bussiness Process Flow**.

1. Click **Activate** again on the pop-up.

1. Confirm that **Status: Active** on the bottom-left side of the screen.

    ![A screeshot of a high-level overview of a business process with the words "Status: Active" highlighted in the left bottom corner](02-2/media/image28.png)

1. Close the process editor browser window or tab.

#### Task 3: Add business process flow to solution

In this task, you will add the business process flow you created to the Company 311 solution.

1.  Navigate to the [Power Apps maker portal](https://make.powerapps.com/) page and make sure you are in the correct environment.

1.  Select **Solutions** and click to open the **Company 311** solution.

1.  Click **+ Add existing**, Keep your Mouse pointer on **Automation** and then select **Process**.

    ![A Screenshot with an arrow pointing to the drop down icon next to the add existing button and a border around the process button](02-2/media/image10.png)

1.  Search for problem, select **Problem resolution process**, and click **Add**.

    ![A screenshot of the add existing processes window with problem resolution process selected](02-2/media/image11.png)

1.  Click **Publish all customizations** and wait for the publishing to complete.

### Exercise 2: Create business rule

In this exercise, you will create a business rule that will block completion of problems without resolution.

#### Task 1: Create business rule

1.  Navigate to the [Power Apps maker portal](https://make.powerapps.com/) page and make sure you are in the correct environment.

1.  Select **Solutions** and click to open the **Company 311** solution.

1.  Locate and click to open the **Problem Report** Table.

1.  Select the **Business rules** tab and click **Add business rule**.

    ![A screenshot of the business rules tab](02-2/media/image12.png)

1.  Make sure the **Scope** is set to **Entity** and click **Show details** **Chevron**.

    ![A Screenshot with an arrow pointing to the drop down icon next to the text problem report: new business rule and a border around the scope set to entity on the right hand side of the page](02-2/media/image13.png)

1. Change **Business rule name** to **Completion rule** and click **Hide details** chev

    ![A screenshot of a business rules property pane with an arrow pointing to the shevron that collapses the entire property pane](02-2/media/image29.png)

1. Select the **Condition**.

1. Go to the **Properties** pane and change the **Display name** to **Resolution required**.

1. Scroll down to **Rule 1**, select **Status Reason** for **Field**, select **Equals** for **Operator**, select **Value** for **Type**, select **Completed** for **Value**, and click **Apply**.

    ![A screenshot of the rules panel](02-2/media/image14.png)

1. Click **+ New**.

    ![A Screenshot with an arrow pointing to the new button](02-2/media/image15.png)

1. Scroll down to **Rule 2**, select **Resolution** for **Field**, select **Does not contain data** for **Operator**, make sure **And** is selected for **Rule Logic**, and click **Apply**.

    ![A screenshot of the rules panel if you scroll further down with the relevant text in each field](02-2/media/image16.png)

1. Click **+ Add**.

    ![A Screenshot with an arrow pointing to the add button](02-2/media/image17.png)

1. Select **Add show error message**.

1. Add the action on the **true** path of the condition.

    ![A Screenshot with an arrow pointing to the add button on the true path of the condition](02-2/media/image18.png)

1. Select the new action, go to the **Properties** pane, enter **Show message** for **Display Name**, select **Status Reason** for **Field**, enter **The Problem must have a resolution before it can be closed** for **Message**, and click **Apply**.

    ![A screenshot of the properties panel with the relevant text in the fields](02-2/media/image19.png)

1. The business rule should now look like the image below. Click **Save**.

    ![A Screenshot with an arrow pointing to the save button](02-2/media/image20.png)

1. Click **Activate the rule**.

1. Click **Activate** again on the pop-up.

1. Confirm activation.

1. Close the process editor browser window or tab.

1. Click **Done**.

### Exercise 3: Test processes

In this exercise, you will test the business process flow and the business rule you created.

#### Task 1: Test processes

1.  Navigate to the [Power Apps maker portal](https://make.powerapps.com/) page and make sure you are in the correct environment.

1.  Select **Apps** and click to open the **Company 311 Admin** application.

    ![A Screenshot with an arrow pointing to the company 311 admin option in apps](02-2/media/image21.png)

1.  Select **Problem Reports** and click **+ New**.

1.  You should see the business process flow stages. Enter **Dark parking lot** for **Title**, select **London Paddington** for **Building**, enter **There are no lights at the north end of the parking lot** for **Details**, and click **Save**.

    ![A screenshot of the new problem report](02-2/media/image22.png)

1.  Click on the **Route** stage.

    ![A Screenshot with an arrow pointing to the route stage at the top of the page](02-2/media/image23.png)

1. Enter **North-end** for **Location**, select **Facility Maintenance** for **Department** and select the **Next stage** stage.

    **NOTE:** If the Next Stage option is not visible, then refresh the page.
  
   ![A screenshot of the drop down from the route stage with the relevant options selected and typed in](02-2/media/image24.png)

1. Select a user for **Assign to** and click **Next stage**.

1. Select date and time for the **Resolved on** and leave the **Resolution** value empty.

1. Scroll down to the resolution details section and select **Completed** for **Status Reason**. You should see the business rule error message.

    ![A screenshot of the error message under status reason](02-2/media/image25.png)

1. Provide **Resolution**. The error message should go away.

    ![A screenshot of the form without the error message after resolution](02-2/media/image26.png)

1. **Save** the Row.

Click **Next** to advance to the next lab.

