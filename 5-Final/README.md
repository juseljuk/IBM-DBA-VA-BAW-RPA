## ALL DONE?

Not quite! Now it's time to test all the components together! Btw, **CONGRATS** making this far!

Now it's time to pull all the things together and test our solution end-to-end. Before running the solution, we need to test that the connection from your IBM Cloud Functions to BAW virtual environment is working and you your Virtual Assistant configurations are correct.

## Test your IBM Cloud Functions connection to BAW

**1.** Open your IBM Cloud Functions view from your IBM Cloud account. Navigate to **_actions_**, open **Get Workflow Token** and in the code view, click the **Invoke** button from the right upper corner.

![](./images/invoke_get_token.png)

**2.** If everything is working as expected, you should see a successful activation. **Note!** When you run your action for the first time, it might take serveral seconds (even over 10 secs) to complete. So, be patient.

![](./images/invoke_get_token_result.png)

If you do not see a message about successful activation, something is wrong and you need to troubleshoot. Otherwise you can move forward to next step (3).

> Troubleshooting

Check these first:

- Your virtual BAW environment is running (you can access the environment as you did in lab 3 and 4).
- The **port number** you are using in your IBM Cloud Functions _action_ is correct (matches with the one you got from your instructor).

When you have made the checks and found nothing to correct or after corrections you are still not able to run a successful invocation, please ask help from your instructor.

**3.** xxx
