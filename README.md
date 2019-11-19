
# IBM Digital Business Automation Workshop Exercise - How to combine different automation capabilities
## Virtual Agent with IBM DBA (Business Automation Workflow and Robotic Process Automation)
### Use case
Banks corporate customers address details have changed. Since the bank is providing a _Virtual Assistant_ service, customer initiates a discussion with the virtual assistant in order to notify bank of the address change.

Bank uses AI (**IBM Watson Assistant service**) to collect the changed address information from the customer in a humanlike chatbot dialog. After all valid information has been collected (business id, company name and address information) - virtual assistant initiates **a managed business workflow** that orchestrates the actual information change into banks CRM system.  

Workflow consists of both automated and manual tasks. _Robotic Process Automation (RPA)_ is used to supplement and validate the company details given by the customer from **ytj.fi** (a public corporate information service) web site.

All information collected during the process are provided to a handler in modern UI, where handler can check that the information provided by the customer matches the one got from ytj.fi and then decide to accept or decline the new address information.

![](./Images/overall.png)

1. Customer has a discussion with our virtual agent (implemented with Watson Assistant service) to inform us about their new address.
2. Our virtual agent gathers the needed address information and their business id from the customer and then starts a managed workflow (running on IBM Business Automation Workflow environment) to handle this new information.
3. First, the workflow triggers a RPA bot (implemented with IBM RPA) that opens the YTJ-site and makes a search using the business id given by the customer. Bot then extracts the official address information from YTJ for that specific business id and sends the results back to the workflow.
4. When our bot has gathered the official address information from YTJ, workflow automatically moves forward to its next step. It brings up a human task that one of our employees need to handle. Workflow shows an UI with both the information customer provided and the information that our bot gathered from YTJ. Now our handler can inspect if these match and can then decide to accept or decline the address information change for the customer.
5. The rest of the workflow is fully automated and executes based on the decision our handler made. If the change request was accepted, workflow would save new address information to our CRM system and notify the customer, but if not, just notify the customer of the situation.

#### Content
- [Assistant](#assistant)
- [Connecting Chatbot to Business Automation Workflow](#connecting-chatbot-to-ibm-business-automation-workflow)
- [Automation](#automation)
- [Putting it all together!](#putting-it-all-together)  

#### Prerequisites
- [IBM Cloud](https://cloud.ibm.com) Account
- Access to IBM Cloud image with [IBM RPA](https://www.ibm.com/automation/software/rpa) and [IBM BAW](https://www.ibm.com/products/business-automation-workflow) installed


## Assistant
In this part we create our **Virtual Assistant / Chatbot** by importing a B2B Banking _skill_ to our Watson Assistant service. We also take a look at how our chatbot has been constructed and we can also test it out.
 - [LAB 1: Cognitive Chatbot Basics](./1-Basics)

## Connecting Chatbot to IBM Business Automation Workflow
Here we connect our chatbot to our managed workflow, so that our chatbot can trigger a new managed workflow instance when done collecting information from the banks corporate customer. We will use **IBM Cloud Functions** (serverless computing services) _actions_ to achieve this.
  - [LAB 2: Integrating Watson Assistant with IBM Business Automation Workflow (BAW)](./2-Functions)

## Automation
For this part of the exercise you will be using a ``Virtual Machine``running on cloud that you access via your web browser. Your instructor will tell you how to access your environment.
- [LAB 3: Business Automation Workflow](./3-BAW)
- [LAB 4: Robotic Process Automation](./4-RPA)

## Putting it all together!
- [LAB 5: Our system in action](./5-Final)

If you manage to finish the labs 1 to 4, ask your instructor to help you to run the hole solution together!
