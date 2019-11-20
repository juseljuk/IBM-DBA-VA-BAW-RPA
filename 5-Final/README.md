## ALL DONE?

Not quite! Now it's time to test all the components together! Btw, **CONGRATS** making this far!

Now it's time to pull all the things together and test our solution end-to-end. Before running the solution, we need to test that the connection from your IBM Cloud Functions to BAW virtual environment is working and you your Virtual Assistant configurations are correct.

## Test your IBM Cloud Functions connection to BAW

**1.** Open your IBM Cloud Functions view from your IBM Cloud account. Navigate to **_actions_**, open **Get Workflow Token** and in the code view, click the **Invoke** button from the right upper corner.

![](./images/invoke_get_token.png)

**2.** If everything is working as expected, you should see a successful activation. **Note!** When you run your action for the first time, it might take serveral seconds (even over 10 secs) to complete. So, be patient.

![](./images/invoke_get_token_result.png)

If you do not see a message about successful activation, something is wrong and you need to troubleshoot. Otherwise you can move forward to next step.

> Troubleshooting

Check these first:

- Your virtual BAW environment is running (you can access the environment as you did in lab 3 and 4).
- The **port number** you are using in your IBM Cloud Functions _action_ is correct (matches with the one you got from your instructor).

When you have made the checks and found nothing to correct or after corrections you are still not able to run a successful invocation, please ask help from your instructor.

## Open your BAW web designer INSPECTOR view and make sure you do not have any previous workflow instances running

In oder to verify that your Watson Assistant can indeed start a new _**Handle data change**_ workflow instance, you need to open your BAW web designer and its **INSPECTOR** view.

**1.** Open _Handle data change_ process as you did in lab 3, if not already open.

- Open Chrome browser within your virtual desktop and navigate to **Workflow Center - Solutions**.
- Open **Process Apps** and then **AWiB-workflow**.
- Finally open **Handle data change** from the left-hand side navigation bar under _Processes_.

**2.** Switch to _**INSPECTOR**_ view by clicking the "INSPECTOR" text on the top bar.

![](./images/open_inspector.png)

**3.** Next open the instance search view by clicking the "magnifying glass" icon on the top bar.

![](./images/mf.png)

**You should NOT have any instances in your environment as the case is with the picture shown above**. If you have accidentally started the workflow during the earlier labs, you might have have similar situation as shown in the picture. If so, follow the below instructions to remove the instances, otherwise you can move to the next section of this lab. **Leave the INSPECTOR / Search View open**.

> How to remove the instances

1. Click the instance to select it and you see the instance information appearing to right-hand side.

![](./images/delete_instance1.png)

2. Click "the Terminate" (if the instance is active) or/and "the Delete" control (if/when the instance is terminated or completed) to clear out the instance from the list. Accept the termination / deletion when asked.
3. Repeat for all the instances in the search result list.
4. Finally click "the Refesh" button to verify that all the instances are deleted and your search result list is clear. **Leave the INSPECTOR / Search View open**.

![](./images/delete_instance2.png)


## Use your Watson Assistant to trigger the workflow

We can run through our Watson Assistant **dialog** and test, if we can trigger a new workflow instance.

**1.** Open your Watson Assistant service and your B2B Bank Bot _**skill**_ - that we imported in Lab 1 and extended in Lab 2 - from IBM Cloud (if not already open).

**2.** Click "**Try it**" button on the top right-hand side to test your skill and its dialog.

**3.** When "the Try it out" section opens to the right of your browser window, run through the dialog with the following selections / input:

- Select **Address change**
- Type in something (does not really matter what) for the _**company name**_.
- Type in something (does not really matter what) for the _**business id**_.
- Type in something (does not really matter what) for the _**street address**_.
- Type in something (does not really matter what) for the _**postcode**_.
- Type in something (does not really matter what) for the _**city**_.
- Click **Yes** when the dialog shows the collected information and asks if it's correct.
- Click **No thanks** when the dialog asks if you want an email confirmation.

**4.** Move back to your **INSPECTOR view** in your virtual environment and hit the **Refresh** button.

``If you have configured everything correctly, you should now see a new active instance in your search results list!``

**Click the instance** to select it and bring up the instance information panel to the right-hand side of the view. You can then expand the **Data** section and the **data(Customerdata)** object to see the data that your Watson Assistant collected via its dialog and sent to your BAW workflow. Nice!

![](./images/new_instance.png)
