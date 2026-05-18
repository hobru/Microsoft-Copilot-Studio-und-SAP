# Quest 5: Test the Agent
[< 🔌 Quest 4](Quest4.md)  - **[Quest 6 >](Quest6.md)**

## Test the new Agent
Now we are ready to test the new agent and access data from the SAP system


In the **Test your agent** screen, enter a question, e.g. ```Show me 5 sales orders```

 ![Enter ask the first question](../images/quest7/step01.png) 


The call to the MCP Server should be executed. You can see that the *getEntitiesFromSalesOrderSet* has been executed. 

 ![Get answer](../images/quest7/step07.png) 
 
Ask additional question to explore what is possible retrieving Sales Order, Business Partner and Product related information, e.g.
* show me 5 open sales orders
* Show me all sales orders with a net amount over 10,000
* Show me sales orders created in the last 30 days
* What is the total net amount of all open sales orders?
* Which business partner has the most sales orders?
* Find the latest sales order for customer SAP
* show me 5 business partners
* Find business partners whose name contains "Tech"
* show me more details about BP 0100000000
* How many business partners are there in total?
* What is the average order value per business partner?
* show me 5 products
* Show me products with a price above 500
* Show me products in category Tablets
* Show me the details of product HT-1000
* Which customers generated the highest revenue last quarter, and which products contributed most to that revenue?




# Where to next?

[< 🔌 Quest 4](Quest4.md) - **[Quest 6 >](Quest6.md)**

[🔝](#)
