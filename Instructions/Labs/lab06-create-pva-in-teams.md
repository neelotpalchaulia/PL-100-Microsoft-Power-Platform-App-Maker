---
lab:
    title: 'Lab 06: Create Power Virtual Agents in Teams'
    module: 'Module 06: AI builder and Power Virtual Agents'
---

> **NOTE**
>
> Effective November 2020:
> - Common Data Service has been renamed to Microsoft Dataverse. [Learn more](https://aka.ms/PAuAppBlog)
> - Some terminology in Microsoft Dataverse has been updated. For example, *entity* is now *table* and *field* is now *column*. [Learn more](https://go.microsoft.com/fwlink/?linkid=2147247)
>

# Lab 06: Power Virtual Agents in Teams

## Scenario

Your organization is trying to recycle E-waste and decided to schedule a quarterly E-waste pickup service. Facilities department created an Excel file in OneDrive for business and want employees to be able to add their name and information about the item they want to get picked up to the list.

In this exercise, you will create a Power Virtual Agents bot that will get the information from users and add them to the pickup list.

## Requirement

 1. Bot should be able to get information about the item.
 2. Bot should be able to get information about the user.
 3. Bot should be able to add the new item to the list.

## What you will learn

 1.	How to create a Power Virtual Agents in Teams.
 2. How to publish Power Virtual Agents.
 3. How to use Power Virtual Agents flow template.

## Detailed steps

### Exercise 1 – Create PVA bot

#### Task 1 - Add Excel file to OneDrive

In this task, you will add an Excel file to your OneDrive for business and add new rows to this file using PVA and Power Automate.

1.  Navigate to [Microsoft Teams](https://teams.microsoft.com).

2.  Select the **App launcher** and select **OneDrive**.

    ![A Screenshot with an arrow pointing to the app launcher icon and a box around the Onedrive option in the app launcher](06/media/ex1-t1-image1.png)

3.  Select **Upload** and select **Files**.

    ![A screenshot with a box around the files option in the dropdown from the upload button](06/media/ex1-t1-image2.png)

4.  Browse to the Lab Resources folder, select the **Recycle.xlsx** file, and select Open.

    > **TIP**
	>
	> The lab resources folder can be found here: `F:\Instructions\Labs\06\Resources\`

5.  Open the file you just added.

    ![A Screenshot with an arrow pointing to the recycle.xlsx file](06/media/ex1-t1-image3.png)

6.  The file should just have headers. **Close** the file and OneDrive browser tabs.

    ![A screenshot of an excel spreadsheet with four headers in the first row: name, email, location, and description](06/media/ex1-t1-image4.png)


#### Task 2 - Install PVA

In this task, you will install PVA.

1.  Navigate to [Microsoft Teams](https://teams.microsoft.com).

2.  Select **...More added apps**, enter **power virtual**, and select **Power Virtual Agents**.

    ![A Screenshot with an arrow pointing to the ellipsis icon on the left side of the window and a box around the power virtual agents option](06/media/ex1-t2-image1.png)

3.  Select **Add**. 

4.  Right-click on the **Power Virtual Agents** and select **Pin**. (If the **Power Virtual Agents** menu is not coming on the left menu, then select **... More added apps** and pin it from the recents.)

    ![A Screenshot with an arrow pointing to the power virtual agents icon and a box around the pin button](06/media/ex1-t2-image2.png)

5.  Do not navigate away from this page.


#### Task 3 - Create bot

In this task, you will create the bot.

1.  Select **Power Virtual Agents** and select **Start now**.

    ![A Screenshot with an arrow pointing to the start now button](06/media/ex1-t3-image1.png)

2.  Select the **Green** team you created and select **Continue**.

3.  Enter **Green Bot** for name, select **English (US)** for language, and then select **Create**.

4.  **Wait** for the bot to be created.

5.  Select **Test your bot** in the bottom left.

6.  Enter **Hello** in the text box and select **Send**. 

7.  The bot should respond with the default greeting. You will edit this greeting in the next task.

    ![A screenshot with a box around the bot's default greeting reading: "Hi! I'm a virtual agent. I can help with account questions, orders, store information and more. If you'd like to speak to a human agent, let me know at any time. So what can I help you with today?"](06/media/ex1-t3-image2.png)

8.  You can show/hide the bot by clicking on the bot icon located in the bottom left. This will give more room for the authoring canvas.

    ![A Screenshot with an arrow pointing to the hide bot button](06/media/ex1-t3-image3.png)

9.  Do not navigate away from this page.


#### Task 4 - Edit greeting

In this task, you will edit the default greeting.

1.  Select **Topics** and open the **Greeting** topic.

    ![A Screenshot with an arrow pointing to the greeting topic in the topics menu](06/media/ex1-t4-image1.png)

2.  Take a look and see the trigger phrases for this topic.

3.  On the authoring canvas go to the first **Message** and replace the message with the text below.

    ```Hi! I'm a virtual agent. I can help you recycle e-waste by posting items to the Upcycle application or add them to the quarterly e-waste pickup list.```

    ![A screenshot of the greeting message replaced with the aforementioned text](06/media/ex1-t4-image3.png)

4.  Select **Save**.

5.  Select **Test your bot** to show the bot.

6.  Enter **Hey** and select **Send**.

7.  The bot should now use your updated message. 

    ![A screenshot of the updated bot greeting message](06/media/ex1-t4-image4.png)

8.  Hide the bot.

9.  Do not navigate away from this page.


#### Task 5 - Create topic

In this task, you will create a new topic for the bot so it can respond to inquiries.

1.  Select **Topics** and select **+ New topic**.

    ![A Screenshot with an arrow pointing to the new topic button](06/media/ex1-t5-image1.png)

2.  Select **Details** to open the Details pane.

3.  Enter **Recycle Reuse Reduce** for Name.

4.  Select **Trigger phrases**.

5.  Copy the multi-line text below and paste it into **Add phrases** input box.

    ```
    Recycle
    E-waste
    Green
    Add me
    Upcycle
    Reuse
    Reduce
    Recycle list
    ```

    ![A screenshot of multiple trigger phrases entered in Add phrases textbox](06/media/ex1-t5-image2.png)

6.  Select **+** to add entries for trigger phrases in bulk.

7.  Select the first message, enter **I can help you with that.** And then select the **+ Add node** button.

    ![A Screenshot with an arrow pointing to the plus icon to add a node](06/media/ex1-t5-image4.png)

8.  Select **Ask a question**.

    ![A Screenshot with an arrow pointing to the ask a question button](06/media/ex1-t5-image5.png)

9.  Enter the text below in the Ask a question textbox.

    ```I can add your item to the Upcycle application or to the e-waste pick-up list. What would you like me to do?```

10. Make sure you have **Multiple choice options** selected for Identity, enter **Add to the Upcycle app** for first option and select **+ New option**.

    ![A Screenshot with an arrow pointing to the new option button](06/media/ex1-t5-image6.png)

11. Enter **Add to the pick-up list** as another option.

12. You should now have two conditions. Select the **...** Options button of one of the conditions and select **Delete**. We are deleting the conditions because adding item to the pick-up list and adding item to the Upcycle application required similar information.

    ![A Screenshot with an arrow pointing to the three dots icon and a red box around the delete button](06/media/ex1-t5-image7.png)

13. Change the second input value in Condition menu to **has value**.

    ![has value - screenshot](06/media/image1.png)

14. Select the edit variable icon.

    ![A Screenshot with an arrow pointing to the pencil icon in the box under the text save response as](06/media/ex1-t5-image8.png)

15. Change the variable name to **UserOption** and close the variable properties pane.

    ![A Screenshot with an arrow pointing to the cross icon in the top right corner of the pane](06/media/ex1-t5-image9.png)

16. Select **+ Add node** and select **Ask a question**.

17. Enter the text below in the Ask a question textbox.

    ```What is the name of the item?```

18. Select the **Identify** dropdown and select **User's entire response**.

    ![A Screenshot with an arrow pointing to the drop down icon in the identify field and a box around the user's entire response button](06/media/ex1-t5-image10.png)

19. Select the **Edit variable** icon.

    ![A Screenshot with an arrow pointing to the pencil icon in the box under the text save response as](06/media/ex1-t5-image11.png)

20. Change the variable Name to **ItemName** and close the variable properties pane.

21. Select **+ Add node** after the question.

22. Select **Ask a question** again.

23. Enter the text below in the Ask a question textbox.

    ```What is the description of this item?```

24. Select the **Identify** dropdown and select **User's entire response** again.

25. Select the **Edit variable** icon again. 

26. Change the variable Name to **Description** and close the variable properties pane.

27. Select **+ Add node** after the question.

28. Select **Ask a question** one more time.

29. Enter the text below in the Ask a question textbox.

    ```What is the location of this item?```

30. Select the **Identify** dropdown and select **User's entire response** again.

31. Select the **Edit variable** icon again.

32. Change the variable Name to **Location** and close the variable properties pane.

33. The three questions should now look like the image below. Select **Save**.

    ![A Screenshot with an arrow pointing to the save button in the top right corner](06/media/ex1-t5-image12.png)

34. Do not navigate away from this page.


#### Task 6 - Create flow

In this task, you will create a flow that will add the item to the recycle list or to the Upcycle application depending on the user option.

1.  Go to the last question, select **+ Add node** and select **Call an action**.

    ![A screenshot of a box around the call an action button](06/media/ex1-t6-image1.png)

2.  Select **Create a flow**.

3.  Select **Power Virtual Agents Flow Template**

    ![A screenshot of a box around the power virtual agents flow template option](06/media/ex1-t6-image2.png)

4.  Rename the flow **Add item to app or list** and select **+ Add an input**.

    ![A screenshot of a box around the add item to app or list button and an arrow pointing to the add an input button under power virtual agents](06/media/ex1-t6-image3.png)

5.  Select **Text**.

6.  Enter **User ID** and select **+ Add an input** again.

    ![A Screenshot with an arrow pointing to the add an input button](06/media/ex1-t6-image4.png)

7.  Select **Text**.

8.  Enter **UserOption** and select **+ Add an input** one more time.

9.  Select **Text**.

10. Enter **ItemName** and select **+ Add an input** one more time.

11. Select **Text**.

12. Enter **Description** and select **+ Add an input** one more time.

13. Select **Text**.

14. Enter **Location**.

15. You should now have five inputs.

16. Select **+ Insert a new step** and select **Add an action**.

    ![A Screenshot with an arrow pointing to the plus icon at the bottom of the power virtual agents pane and a box around the add an action button](06/media/ex1-t6-image5.png)

17. Search for initialize and select **Initialize variable**.

    ![A screenshot with a box around the initialize variable button](06/media/ex1-t6-image6.png)

18. Enter **Response to bot** for Name, select **String** for Type.

19. Select **+ Insert a new step** and select **Add an action**.

    ![A Screenshot with an arrow pointing to the plus icon at the bottom of the initialize variable pane and a box around the add an action button](06/media/ex1-t6-image7.png)

20. Select **+ Insert a new step** again and select **Add an action**.

21. Search for get user profile and select **Get user profile (V2)**.

    ![A screenshot with a box around the get user profile V2 button](06/media/ex1-t6-image8.png)

22. Select the **User (UPN)** field and select **User ID** from the dynamic content pane.

    ![A screenshot with a box around the user ID box in the user UPN field. There is also an arrow pointing to the user ID option in the dynamic content pane](06/media/ex1-t6-image9.png)

23. Select **+ Insert a new step** again and select **Add an action**.

24. Search for condition and select **Condition**.

25. Select the first **Choose a value** field and select **UserOption** from the dynamic content pane.

    ![A Screenshot with an arrow pointing to the UserOption in the dynamic content pane. There is also a box around the user option box in the condition pane](06/media/ex1-t6-image10.png)

26. Select **is equal to** and enter **Add to the Upcycle app**.

27. Go to the **if no** branch and select **Add an action**.

    ![A Screenshot with an arrow pointing to the add an action button in the if no window](06/media/ex1-t6-image11.png)

28. Search for add a row and select **Add a row into a table** from Excel Online (Business).

    ![A screenshot with a box around the add a row into a table button](06/media/ex1-t6-image12.png)

29. Select **OneDrive for Business** for Location, **OneDrive** for Document Library, **Recycle.xlsx** for File and **PickupTable** for table.

30. Select the **Name** field and select **Display Name** from the dynamic content pane.

    ![A screenshot of a box around the display name box in the name field. There is also an arrow pointing to the dynamic content pane and the display name button](06/media/ex1-t6-image13.png)

31. Select the **Email** field and select **Mail** from the dynamic content pane.

32. Select the **Location** field and select the **Location** dynamic content from the Power Virtual Agents step in the dynamic content pane.

    ![A screenshot with a box around the power virtual agents part of the dynamic content pane and an arrow pointing to the location button. There is also a box around the location box in the location field](06/media/ex1-t6-image14.png)

33. Select the **Description** field and select **Description**  from the dynamic content pane.

34. The flow step should now look like the image below. Select **Add an action**

    ![A Screenshot with an arrow pointing to the add an action button](06/media/ex1-t6-image15.png)

35. Search for set variable and select **Set variable**.

36. Select **Response to bot** for name, select the Value field and select **ItemName** from the dynamic content pane.

    ![A Screenshot with an arrow pointing to the item name option in the dynamic content pane](06/media/ex1-t6-image16.png)

37. Add the text below after the ItemName.

    ``` was added to the e-waste pick-up list.```

38. Go to the **If yes** branch and select **Add an action**.

    ![A Screenshot with an arrow pointing to the add an action button](06/media/ex1-t6-image17.png)

39. Search for add new row and select **Add a new row** from Microsoft Dataverse.

    ![A screenshot with a box around the add a new row microsoft dataverse button](06/media/ex1-t6-image18.png)

40. Select **Gadgets** for the table name.

41. Select the Location field and select **Location** from the dynamic content pane.

42. Select the Name field and select **ItemName** from the dynamic content pane.

43. Select **Show advanced options**.

    ![A Screenshot with an arrow pointing to the show advanced options button](06/media/ex1-t6-image19.png)

44. Select **Available** for Availability, select the Description field and select **Description** from the dynamic content pane.

45. Select **Add an action** after the add a new row step.

46. Search for set variable and select **Set variable**.

47. Select **Response to bot** for Name, select the Value field and select **ItemName** from the dynamic content pane.

48. Add the text below after the ItemName.

    ``` was added to the Upcycle application.```

48. The two branches of the condition should now look like the image below. Expand the **Return value(s) to Power Virtual Agents** step.

    ![A Screenshot with an arrow pointing to the return values to power virtual agents box beneath the if yes and if no conditions boxed](06/media/ex1-t6-image20.png)

49. Select **+ Add an output**.

50. Select **Text**.

51. Enter **Response**, select the value field, and select **Response to bot** from the dynamic content pane.

    ![A Screenshot with an arrow pointing to the response to bot option in the dynamic content pane under variables](06/media/ex1-t6-image21.png)

52. Select **Save** to save the flow.

53. Select the **<-** back button next to the flow name.

    ![Back to PVA button - screenshot](06/media/ex1-t6-image22.png)

54. You should now be back to the bot authoring canvas.

55. Do not navigate away from this page.


#### Task 7 - Call flow 

In this task, you will call the flow as an action from the Power Virtual Agents bot.

1.  Go to the last question, select **+ Add node** and select **Call an action**.

2.  Select the **Add item to app or list** flow you created.

    ![A Screenshot with an arrow pointing to the add item to app or list button](06/media/ex1-t7-image1.png)

3.  Select the **User ID** field and select **bot.UserId**.

    ![A Screenshot with an arrow pointing to the drop down icon in the field asking the user to enter or select a value. There is also a box around the variable option bot.UserId](06/media/ex1-t7-image2.png)

4.  Select the **UserOption** field and select **UserOption**.

5.  Select the **ItemName** field and select **ItemName**.

6.  Select the **Description** field and select **Description**.

7.  Select the **Location** field and select **Location**.

8.  Select **+ Add node** and select **Show a message**.

    ![A Screenshot with an arrow pointing to the show a message button](06/media/ex1-t7-image3.png)

9.  Select the **Insert variable** icon and select **Response**.

    ![A Screenshot with an arrow pointing to the insert variable icon and a box around the response button in the drop down](06/media/ex1-t7-image4.png)

10. Select **+ Add node** and select **End with survey**.

11. The end of the bot conversation should look like the image below.

    ![A screenshot of the end of the bot conversation which shows a message command with {x} response in the box and then an end of conversation command connected below](06/media/ex1-t7-image5.png)

12. Select **save** to save your changes and wait for the bot to be saved.

13. Do not navigate away from this page.


### Exercise 2 – Test and publish the bot

#### Task 1 - Test bot

In this task, you will test the bot.

1.  **Show** the bot if it is hidden by selecting Show Bot option on the bottom left side of the screen.

2.  Enter **Recycle** and select **Send**.

3.  The bot should ask you if you want to add the item to the e-waste list or the upcycle application. Select **Add to the Upcycle app**.

    ![A screenshot with a box around the add to the upcycle app](06/media/ex2-t1-image1.png)

4.  The bot should ask you to provide name. Enter **Bot charger** and select **Send**.

5.  The bot should ask you the description of the item. Enter **Universal bot charger** and select **Send**.

6.  The bot should ask you the location of the item. Enter **Building 4 Room A-754** and select **Send**.

7.  The bot should tell you the item was added to the Upcycle application and ask you if your question was answered. Select **Yes**.

    ![A Screenshot with an arrow pointing to the yes button](06/media/ex2-t1-image2.png)

8.  The bot should ask you to rate your experience, give it a rating.

9.  The bot should thank you and ask you if it can help you with anything else. Select **Yes**.

10. Enter **Reuse** and select **Send**.

11. Select **Add to the pick-up list** this time.

12. The bot should ask you to provide name. Enter **Bad bot charger** and select **Send**.

13. The bot should ask you the description of the item. Enter **Bad universal bot charger** and select **Send**.

14. The bot should ask you the location of the item. Enter **Building 4 Room A-754** and select **Send**.

15. The bot should tell you the item was added to the e-waste pick-up list and ask you if your question was answered. Select **Yes**.

    ![A Screenshot with an arrow pointing to the yes button](06/media/ex2-t1-image3.png)

16. Rate the bot.

17. Select **No, thanks**.

18. The bot should end the conversation.

19. Select **Teams**.

    ![A Screenshot with an arrow pointing to the teams icon](06/media/ex2-t1-image4.png)

20. Select **Green** team chat. Select the **Upcycle** tab.

21. Search for bot. You should see the **Bot charger** the bot added to the application.

    ![A screenshot with the word bot in the search bar in the upcycle tab](06/media/ex2-t1-image5.png)

22. Select the App launcher and select **OneDrive**.

    ![A Screenshot with an arrow pointing to the app launcher icon and a box around the onedrive option](06/media/ex2-t1-image6.png)

23. Open the **Recycle.xlsx** file. 

24. You should see the **Bad universal bot charger** added by the bot.

    ![Excel table- screenshot](06/media/ex2-t1-image7.png)

25. Close the **Excel file**.

26. Close **OneDrive**

27. You should now be back on the Upcycle application.

28. Do not navigate away from this page.


#### Task 2 - Publish and add bot

In this task, you will publish the bot you created.

1.  Select **Power Virtual Agents**. 

    ![A Screenshot with an arrow pointing to the power virtual agents icon on the left hand side of the window](06/media/ex2-t2-image1.png)

2.  Select the **Chatbots** tab and open the **Green Bot**.

    ![A Screenshot with an arrow pointing to the green bot button](06/media/ex2-t2-image2.png)

3.  Select **Publish**.

    ![A Screenshot with an arrow pointing to the publish button](06/media/ex2-t2-image3.png)

4.  Select **Publish** again.

5.  Select **Publish** on the Publish latest content pop-up and wait for the publishing to complete.

6.  Expand **Manage** and select **Channels**.

    ![A screenshot with a box around the channels button](06/media/ex2-t2-image4.png)

7.  Select **Microsoft Teams**.

8.  Select **Availability options**.

9.  Select **Show to my teammates and shared users**.

    ![A screenshot of a publish pane with a cursor over shaow to my teammates and shared users.](06/media/ex2-t2-image5.png)

10. Select **Share**.

11. Select **Apps**.

    ![A Screenshot with an arrow pointing to the apps icon](06/media/ex2-t2-image6.png)

12. Select **Built with Power Platform** and select the **Green Bot** you created.

    ![A screenshot with a cursor pointing to Green Bot button](06/media/ex2-t2-image7.png)

13. Select **Add**. 

14. The bot should greet you. You may test the bot again.
