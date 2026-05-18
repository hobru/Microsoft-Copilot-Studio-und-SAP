# Quest 2: Manage APIs in Azure API Management
[< 🤖 Quest 1](Quest1.md) - **[🔧 Quest 3 >](Quest3.md)**

## Azure API Management
Azure API Management (APIM) is a fully managed service that helps organizations securely publish, expose, and manage APIs at scale. It acts as a façade between API consumers and backend services, providing a consistent entry point where developers can discover APIs, learn how to use them, and access them in a controlled way.

At the same time, Azure API Management gives API owners powerful control and observability. It enables policies for authentication, throttling, transformation, and caching, while offering built‑in monitoring, analytics, and versioning. This makes it easier to protect backend services, ensure reliability, and evolve APIs without breaking consumers.


### Open Azure API Management in the Azure Portal:
Open a new browser tab and open the link:

https://portal.azure.com/#@tws22.onmicrosoft.com/resource/subscriptions/0973cd86-8527-4a13-a1c8-b3431c0e1fde/resourceGroups/syntax2026-apim/providers/Microsoft.ApiManagement/service/syntax2026apim/apim-apis


### Accept Permissions
Click on **Accept**

![Accept permissions dialog](../images/quest4/step01.png) 

### Add to Authenticator App
Since this is an external user in this Azure subscription you need to add also this user to the Authenticator

![Add user to Authenticator](../images/quest4/step02.png) 
 
### Run through enrollment process
As before run through the process to add the user to your Authenticator app
![Authenticator enrollment process](../images/quest4/step03.png)
 
 
 
 
## Import your API

### In Azure API Management
Now you are in Azure API Management. This is one instance that is used by  all participants. Please don’t delete any existing APIs and only work with your own

![Azure API Management overview](../images/quest4/step04.png) 
 
### Managing APIs
Expand **API** and click on **APIs**

![Expand APIs menu](../images/quest4/step05.png) 
 
### Define API from OpenAPI specification
Scroll down and click on OpenAPI

![Select OpenAPI option](../images/quest4/step06.png)
 
### Upload OpenAPI Specification
Click on **Select a File** and select the **$metadata-openapi.json** file that we converted and downloaded before in Step 3.1.5

> [!NOTE]
> If you had issues converting the file, you can find another file [here](../files/$metadata-openapi.json)


![Select OpenAPI specification file](../images/quest4/step07.png) 
 
 ### Configure the Displayname & more
For the **API URL Suffix** enter your ID, e.g. 
```text
student0XX
``` 
with your student number, 

Make also sure to adjust the **display name** and add 

```text
student0XX GWSAMPLE_BASIC
```  

(the Name should be automatically be adjusted)

then click on **Create**

![Enter API URL suffix and display name](../images/quest4/step08.png) 
 
From now on, please only use your API, e.g. **student0XX GWSAMPLE_BASIC**
![API overview page](../images/quest4/step09.png)
 
## Configure authentication

### Configure authentication
Next we will configure the authentication. Here you would now setup principal propagation / SSO. In our scenario we are going to do basic authentication with a username and password that is already configured as “Named values” pair. In order to use that configuration, click on the *Policies Code editor*

![Open Policies Code editor](../images/quest4/step10.png) 
 
### Enhance the policy
 Under     
 ```xml
 <inbound> 
    <base /> 
 ```
 add the following line. This will fetch the username and password from the Named Value store and add it to an authorization header for each call to the backend system
````xml
<authentication-basic username="{{sap-user}}" password="{{sap-password}}" />
````

And click on **Save**

![Save the policy](../images/quest4/step11.png) 

> [!NOTE]
> The full policy should now look like
> 
```xml
<!--
    - Policies are applied in the order they appear.
    - Position <base/> inside a section to inherit policies from the outer scope.
    - Comments within policies are not preserved.
-->
<!-- Add policies as children to the <inbound>, <outbound>, <backend>, and <on-error> elements -->
<policies>
    <!-- Throttle, authorize, validate, cache, or transform the requests -->
    <inbound>
        <base />
        <authentication-basic username="{{sap-user}}" password="{{sap-password}}" />
    </inbound>
    <!-- Control if and how the requests are forwarded to services  -->
    <backend>
        <base />
    </backend>
    <!-- Customize the responses -->
    <outbound>
        <base />
    </outbound>
    <!-- Handle exceptions and customize error responses  -->
    <on-error>
        <base />
    </on-error>
</policies>
```

 
## Adjust the settings

### Adjust the settings
Now click on **Settings**

![Open Settings tab](../images/quest4/step12.png) 
 

### Change the target URL
And change the **Web Service URL** to 

```text
https://microsoftintegrationdemo.com:44301/sap/opu/odata/IWBEP/GWSAMPLE_BASIC
```

and click on **Save**

![Update URL](../images/quest4/step13.png) 
 
### Uncheck Subscription Required
On the same screen, scroll down and uncheck “**Subscription required**” and click on **Save**
![Uncheck Subscription required](../images/quest4/step14.png) 
 
## Test the API

### Test the API
Now click on **Test**, select the *Entity Type* ```Get entities from BusinessPartnerSet``` 
![Select Test and choose BusinessPartnerSet](../images/quest4/step15.png) 

### Submit the request
And click on **Send**

![Click Send to submit the request](../images/quest4/step16.png) 

 
If you scroll down you should see **HTTP/1.1 200 OK** and lots of Business partners
![HTTP 200 OK response with Business Partners](../images/quest4/step17.png)




# Where to next?

[< 🤖 Quest 1](Quest1.md) - **[🔧 Quest 3 >](Quest3.md)**

[🔝](#)
