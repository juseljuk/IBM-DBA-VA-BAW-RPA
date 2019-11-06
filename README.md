
## AWiB Workshop
### Use case
Corporate customers contact details have changed. To avoid any issues on future deliveries from their key Supplier, customer initiates contact details changes via Suppliers self-service.

Supplier utilizes AI to collect changed information from Corporate customer in a chatbot dialog. After all valid information has been collected (company name, address, phone number, etc...) - chatbot initiates a business workflow that orchestrates the actual information change into Suppliers system.  

Workflow utilizes both automated and manual tasks to finalize the contact details change. Robotic Process Automation (RPA) is used to supplement and validate company details given by customer from ytj.fi service.  
All contact and validation information collected during the process (company name, address, phone number, Business ID, etc...) are provided to workflow handler in modern UI, where handler can check the information provided by the customer matches the one got from ytj.fi and then decide to accept or decline the new address information.

![](./Images/overall.png)

1. Customer has a discussion with our virtual agent (implemented with Watson Assistant service) to inform us about their new address.
2. Our virtual agent gathers the needed address information and their business id (y-tunnus) from the customer and then starts a managed workflow (running on IBM Business Automation Workflow environment) to handle this new information.
3. First, the workflow triggers a RPA bot (implemented with IBM RPA) that opens YTJ-site and makes a search using the business id (y-tunnus) given by the customer. Bot then extracts the official address infomation from YTJ for that specific business id and sends the results back to the workflow.
4. When our bot has gathered the official address information from YTJ, workflow automatically moves forward to its next step. It brings up a human task that one of our employees need to handle. Workflow shows an UI with both the information customer provided and the information that our bot gathered from YTJ. Now our handler can inspect if these match and can then decide to accept or decline the address information change for the customer.
5. The rest of the workflow is fully automated and executes based on the decision our handler made. If the change request was accepted, workflow would save new address information to our CRM system and notify the customer, but if not, just notify the customer of the situation.

#### Content
- [Assistant](#assistant)
- [Connecting Chatbot to Business Automation Workflow](#connecting-chatbot-to-ibm-business-automation-workflow)
- [Automation](#automation)
- [Summary](#summary)  

#### Prerequisites
- [IBM Cloud](https://cloud.ibm.com) Account
- Access to IBM Cloud image with [IBM RPA](https://www.ibm.com/automation/software/rpa) and [IBM BAW](https://www.ibm.com/products/business-automation-workflow) installed


## Assistant
In this part we create the **Chatbot** and edit it so that it can communicate with Cloud Functions.
 - [LAB 1: Cognitive Chatbot Basics](./1-Basics)

## Connecting Chatbot to IBM Business Automation Workflow
This connects the backends of the chatbot and a workflow so that they can communicate together. With this we are able to trigger a new workflow and send the inputs from the chatbot to it. 
  - [LAB 2: Integrating BAW with Watson Assistant](./2-Functions)    
 
## Automation
Login to your ``Virtual Machine``, using the instructions handed out to you by your instructors.
- [LAB 3: Business Automation Workflow](./3-Baw)
- [LAB 4: Robotic Process Automation](./4-RPA)
  
## Summary
- [LAB 5: Our system in action](./5-Summary)

If you manage to finish all the labs, ask your instructor to help you to run the hole solution together!
