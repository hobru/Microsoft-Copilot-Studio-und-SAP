# Quest 1: Getting started with RFC
[🏠Home](../../README.md) - **[🔌 Quest 2 >](Quest2.md)**

## SAP ERP Connector
As before the first step is to go to Tools and **+Add a tool**
![Add a tool to the agent](../images/C2-AddTool.png)

Unlike before we will not call the connector directly, but wrap it in an Agent Flow. For this select **Agent Flow**

![Select Agent Flow](../images/C3-AgentFlow.png)

In the Agent Flow designer we first have to tell the Agent that is calling this flow, that we need an input parameter: the Sales Order number for which we want to fetch the status. 

Expand the **When an agent calls the flow** step and click on **+ Add an input**

![Add an input parameter](../images/C4-AddInput.png)

Select **Text**

![Select Text input type](../images/C5-Text.png)

enter the text ````Sales Order ID```` and click on the **+**

![Enter Sales Order ID as input name](../images/C6-SalesOrderID.png)


In the *Add an action* screen search for ````SAP ERP```` and select the **Call SAP function (V3)** action

![Search for SAP ERP connector](../images/C7-SearchForERP.png)

Since this is your first connection to the SAP system, you have to create a new connection. Enter the following values:
Connection name: Connection to PM4
Data Gateway: Select opdg-pm4
SAP Username: SYNTAX01
SAP Password: <as shared>

![Create new SAP connection](../images/C8-CreateNewConnection.png)


Now you are ready to connect to the SAP system. Enter the SAP System name and RFC name as follows:
SAP System: 
````json
{"AppServerHost": "10.15.0.6", "Client": 400, "SystemNumber":"01", "LogonType":"ApplicationServer"}
````
RFC name: BAPI_SALESORDER_GETSTATUS

![Enter SAP system details and RFC name](../images/C9-SAPSystem+RFC.png)


If everything is correct, you should see a new field *RfcInputs/SALESDOCUMENT* being displayed. Click on the field and on the Flash that is appearing. Now you can select the **Sales Order ID** which we defined as a required input parameter in the first step

![Map Sales Order ID input using Flash icon](../images/C10-Flash.png)


As a final step we need to tell the Agent flow what to return to the agent. For this go to the last step **Respond to the agent** and click on **+ Add an output**

![Add an output to the flow response](../images/C11-AddOutput.png)

As before select Text and then provide a name **Sales Order Status** for the variable and via the flash icon select Body

> [!NOTE]
> You will have to click on **See more (52)** first to get the full list

![Click See more to expand the list](../images/C12-SeeMore.png)

so that you can select **Body**

![Select Body as output value](../images/C13-Body.png)

Now the response should look like this. Click on **Publish** to publish the agent

![Publish the agent flow](../images/C14-Resposne.png)

Once published don't go back to the agent just yet, but **Stay in the flow**

![Stay in the flow after publishing](../images/C15-StayInFlow.png)

In the Overview Tab, click on the **Untitled** name and change it to ````SAP Sales Order Status Lookup````

![Rename the flow](../images/C16-ChangeName.png)

Then on the right under *Connection references* click on **Manage** and change and select the Connection that you had previously created. You will be prompted if you are sure to change the connection. Click on **OK** and then **Save**

> [!NOTE]
> This simplifies the interaction from the agent later on. For Single Sign-On we would keep this as is.

![Change the connection reference](../images/C17-ChangeConnection.png)

Now it is time to integrate this new flow in the agent. 


# Where to next?

[🏠Home](../../README.md) - **[🔌 Quest 2 >](Quest2.md)**

[🔝](#)
