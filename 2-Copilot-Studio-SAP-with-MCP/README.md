# Copilot Studio & SAP: Copilot Studio and MCP Servers

**[🤖 Quest 1 >](student/Quest1.md)**

## What are MCP Servers

The **Model Context Protocol (MCP)** is an open standard that defines how AI clients (like Copilot Studio or Claude) communicate with external data sources and tools. An MCP Server exposes capabilities — such as reading data, calling functions, or accessing resources — in a standardized way that any MCP-compatible client can consume without custom integration code.

Key benefits of MCP:
* **Standardized interface** — One protocol to connect AI agents to many different backends
* **Dynamic tool discovery** — Clients can discover available tools at runtime
* **Simplified integration** — No need to build custom connectors for each AI platform
* **Security built-in** — Supports authentication flows including OAuth and SSO

In the context of SAP, an MCP Server can expose OData services, BAPIs, or any API so that AI agents can query SAP data using natural language — without the agent needing to understand OData query syntax.

### 0.2 MCP Servers and where to get them
So the main question is: where can I get an MCP Server from? The [MCP Registry](https://registry.modelcontextprotocol.io/) already lists hundreds of MCP Servers, but if you want to connect to your own (SAP) systems, you can use open source solutions (like the [OData MCP Bridge](https://github.com/oisee/odata_mcp_go)) or use tools like Azure API Management which provide a simple way to expose existing APIs as an MCP Server.

In our tutorial we will use Azure API Management to create such an MCP Server from the GWSAMPLE OData Service and expose the information in a Copilot Studio agent.

### 0.3. Labs and More
For this hackathon we have prepared everything for you. However, you can also reproduce this very same scenario at home. All that you need is
* [Copilot Studio](https://copilotstudio.microsoft.com/)
* Azure API Management (start with the free trial [Azure Free Trial](https://azure.com/free))
* SAP Backend System (you can use a Service from the [SAP API Business Hub](https://api.sap.com))


> Note:
In this lab we are going not only to consume an MCP Server in Copilot Studio, but also to create an MCP Server in Azure API Management. If you don't want to create your own MCP Server, you can also jump directly to the [Copilot Studio Conifugration](student/Quest4.md) and use the MCP Server that was already created for you, e.g. https://syntax2026apim.azure-api.net/student030-sap-products-business-partner-and-sales-orders/mcp


## 📢Feedback

This repos encourages contributions and feedback via the [GitHub Issues](https://github.com/hobru/Microsoft-Copilot-Studio-und-SAP/issues/new/choose).

## Where to next?

**[🤖 Quest 1 >](student/Quest1.md)**

[🔝](#)
