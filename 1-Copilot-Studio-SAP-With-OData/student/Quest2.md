# Quest 2: Connect to SAP OData Services from Copilot Studio
[< 🤖 Quest 1](Quest1.md) - [🏠Home](../../README.md)

## Connecting Copilot Studio to OData
Now that we have a basic understanding of OData Service, the next step is to connect Copilot Studio to an OData service. 
We will do a simple integration to show the concept and outline how easily it can be to connect. 

In [Copilot Studio](https://copilotstudio.microsoft.com/) go to **Agents** and click on **+ Create blank agent**
![Create a new blank agent](../images/A-CreateAgent.png)

Enter the name ````GWSAMPLE - Basic```` and click on **Create**
![Enter agent name GWSAMPLE Basic](../images/B-AgentName.png)

Once the Agent is setup, go to **Tools** and click on **"+ Add a tool"**
![Add a tool to the agent](../images/D-AddATool.png)

Search for **OData** and select the **Query OData Entities** tool
![Search for Query OData Entities tool](../images/E-QueryODataEnttity.png)

In the first step we need to create a connection to the SAP system. Click on **Connection** and select **Create new connection**
![Create new OData connection](../images/F-CreateNewConnection.png)

The SAP OData Connector in Copilot Studio allows you to browse available Entity Sets. So enter the OData Base URI for the GWSAMPLE Service:
* OData Base URI: https://microsoftintegrationdemo.com:44301/sap/opu/odata/IWBEP/GWSAMPLE_BASIC/
* Username: SYNTAX01
* Password: <as provided>

![Enter OData connection details](../images/G-EnterConnectionDetails.png)


Once entered, click on **Add and configure**

![Click Add and configure](../images/H-AddAndConfigure.png)


To simplify the interaction, expand the **Details** section and under **Additional details** change the **Credentials to use** to **Maker-provided credentials**. Then click on **Save**

![Set Maker-provided credentials](../images/I-MakerProvidedCredentials.png)


Now when you click on **+ New Test session** you can already interact with your SAP system. Start by asking a question ````Show me 5 sales orders````


![Copilot returns 5 Sales Orders from SAP](../images/J-5SalesOrders.png)

You can see that Copilot Studio was able to identify the right tool (e.g. Query OData entities), that it selected the correct Entity name (e.g. SalesOrderSet) and it returned a list of Sales Orders. 

You can do similar query with:
* ````Show me 3 products````
* ````Show me 3 business partners````


> Note:
If the lookup does not work and the agent is not able to connect to the SAP OData service, then give it some help. Go to **Tools**, **Query OData entties**, **Inputs**, **Additional details** and change the **description** to 
````text
Typically the following entities are available: SalesOrderSet, ProductSet and BusinessPartnerSet
````

![Change the description](../images/AA-AdditionalDescription.png)


## Summary
This section showed how to easily access OData services. More complex OData integration scenarios can be developed using Flows, see also https://www.youtube.com/watch?v=zt62mhPr_k0



# Where to next?

[< 🤖 Quest 1](Quest1.md) - [🏠Home](../../README.md)

[🔝](#)
