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
