# Embedded Analytics Modernization : Moving fast to Qlik Cloud

Embedded analytics seamlessly integrate analytic capabilities and content into business applications, products, websites or portals.
It lets users quickly access relevant data and insights in their daily workflows without slowing down and switching to use a separate analytics application.
Embedded analytics from Qlik Sense Client Manage site can easily be modernized by moving to Qlik Cloud Platform.

## What's the value to move your mashup on Qlik Cloud?

Take profit from Qlik Cloud architecture for your embbeded analytics
- A high-performance and secure cloud architecture, scalable and elastic
- Seamless, continuous release of upgrades and enhancements
- Reduced burden on internal IT resources

Improve your embedded analytics :
- Add value embedding new capabilities features : Alerting, Notes, Automation,...
- Oppurtunity to upgrade your web integration with the lastest released libraries as Nebula.js wihtout limitations
- An easy and secure cloud solution integration with for example handling CORS requests in Qlik Sense SaaS

It allows you to discover new use cases, deploying to a larger population and create new business value with Active Intelligence platform

## How to move?

### Assess your current web integration

1. Start by asking you the right questions

- *Where my mashup or web application is hosted?*

You must host your mashup in a cloud accessible location.
In Qlik Sense Client manage your mashup or web app can be hosted in your Qlik Sense Client Managed site.
Qlik Cloud don't allow the hosting.

- *How do I manage the authentication?*

Authentication is done by triggering a login process on the Qlik Cloud deployment, which is turn relies on the configured IdP.
Authentication source and flow is changing.

- *What is embbed?*

Assess what you use for embedded analytics and how.
  - IFrame
  - Div
  - On the fly visualization
  - Data Only
  
![image](https://user-images.githubusercontent.com/24877503/166873460-7a988057-87d6-44c0-b3e3-810ab303c30d.png)


> Do the hub is embedded? This is a current limitation on Qlik Cloud.

- *What is the source of my resource?*

Identify the resources used in your mashup or web application : 
What is the new app in Qlik Cloud and its AppId?
What is the links to my resources : Qlik JS, CSS, Images, etc. Links requires to change to resources located in the Qlik Sense SaaS resources folder or accessible from your mashup.  

### Update your mashups or web application

#### Hosting

##### Understand the context
First thing is to assess what will move to Qlik Cloud : 
- Where the analytics is embedded?
- Which can of resources is using?
- Where the sources are hosted?

In Qlik, we have 2 kind of applications :
- Web Apps : All the web applications in which I'm using the Qlik Backend API. No Qlik front-end files are used (JS or CSS).
- Mashups : The integration of Qlik resources in web applications using Qlik Sense Capabilities API and other front-end Qlik resources as JS files and CSS.

Moreover, the mashup or web application can be embedded in another product.
The potentential specific dependencies have to be identified.

##### Where can I host my mashups?
The mashup or web-app must be hosted in a cloud accessible location. Qlik Cloud and the user must have access to the resources. 
In Qlik Sense Client-Managed the mashup or web app can be hosted in your Qlik Sense Client-Managed site. This is not possible in Qlik Cloud.
One possibility is to host it in a cloud provider.
For simple use case with a static web-site mashup, a common storage provider can be used.

Here some example on different cloud provider
> **Warning : These tutorials make content available to the public internet. Please adapt the security regarding your use cases.**
- [Hosting a static website on AWS](https://docs.aws.amazon.com/AmazonS3/latest/userguide/WebsiteHosting.html)
- [Hosting a static website on Azure](https://azure.microsoft.com/fr-fr/blog/static-websites-on-azure-storage-now-generally-available/)
- [Hosting a static website on Google Cloud Platform](https://cloud.google.com/storage/docs/hosting-static-website)


##### Settings

Moving the mashup or the web app to Qlik Cloud will have impacts in term of security and resources location.

Browsers and web servers implement security policies to mitigate risks inherent with being connected to the internet. 
Cross-Origin Resource Sharing (CORS) allows to a server to indicate the origin (other than its own) from which a browser should permit loading resources.
When a web server shares a resource such as an image on its own server, it is following the same-origin policy. In this case, the resource is accessed by the same protocol, domain, and port as the server. On the other hand, a secure request for a resource from a different origin (known as a cross-origin request) requires a cross-origin resource sharing (CORS) policy. CORS allows servers to specify who (the origin) can access the assets on the server. To enable cross-origin resource sharing, the site URL that is hosting the mashup or web app must be added to a whitelist on the Qlik Sense SaaSserver. This process of setting up the whitelist is known as web integration. Qlik Sense allows you to configure CORS policies on a per web integration basis. For example, if you have two web integrations "A" and "B", and you want both to be accessible from foo.com, you need to add foo.com to the domain whitelist of both web integrations. Web integration entities are created by the tenant admin through the management console. *From [Qlik Help Page](https://help.qlik.com/en-US/sense-developer/May2022/Subsystems/Mashups/Content/Sense_Mashups/Howtos/external-mashups-integrate-cloud.htm)*

[Need help?](https://help.qlik.com/en-US/cloud-services/Subsystems/Hub/Content/Sense_Hub/Admin/mc-administer-content-security-policy.htm)

The resources location will also be updated

 ``` HTML     
<link rel="stylesheet" href="https://www.yourtenant.eu.qlikcloud.com/resources/autogenerated/qlik-styles.css">
<script src="https://www.yourtenant.eu.qlikcloud.com/resources/assets/external/requirejs/require.js"></script>
<script src="helpdesk.js"></script>
```

Of course, as your Qlik applications are now hosting in a new Qlik Sense site, the Application should also be changed...

All these kind of change will be details below!



[How To](https://help.qlik.com/en-US/sense-developer/February2022/Subsystems/Mashups/Content/Sense_Mashups/Howtos/external-mashups-integrate-cloud.htm)

1. Update the authentication method
2. Deploying web apps and mashups
  - Potentially change the hosting
  - Update links and resources location
  - Cross-domain resource sharing
  - Update AppId to the new application created on Qlik Cloud

Need help? take a look on a [simple Qlik Mashup integration on Qlik Cloud](https://help.qlik.com/en-US/sense-developer/February2022/Subsystems/Mashups/Content/Sense_Mashups/mashups-build_cloud.htm)

#### Others change with Qlik Cloud?

- *Where my application must be store?*

Check app life cycle management

- *Ouch! I was used to developping with the Dev-Hub!?*

There is currently no Dev-Hub in Qlik Cloud. However, here are some tips and tools to facilitate the move : 
  - Developper mode
    1. Open a sheet in a Qlik Sense app in your browser
    2. Add /options/developer to the url
    3. Right click on an object and choose "Developer"
    
    ![image](https://user-images.githubusercontent.com/24877503/168016445-65fbb1fa-e096-40aa-9c8a-6a17b16dc1ee.png)
    
    You can get the object id, properties, and layout of any object this way. There's also a link to open the object in single configurator, and test   exporting. The object id's are useful for embedding visualizations. The properties are useful if you are creating your own objects and want to check the properties of an object in a Qlik Sense app for reference.

  - Other tooling, as Glitch (add links...)
  - qix explorer (add tool beta)

### Going further : Improve your embedded analytics

#### Embedded Active Intelligence 

- Embedded Notes : Giacomo? (Not public API)
- Embedded Insight Advisor : 
[How To](https://help.qlik.com/en-US/sense-developer/February2022/Subsystems/Mashups/Content/Sense_Mashups/Howtos/mashups-integrate-IA-chat.htm)
- Embededd Alert : To dig ???

#### Nebula.js and Enigma.js

adding example
Enigma.js and Nebula.js allows an advanced capabilities of integration
- Enigma.js is a wrapper library that makes communicating with the engine easier with JavaScript rather than using the straight websockets.
- Qlik nebula.js is an open source collection of JavaScript libraries, visualizations, and CLIs that help developers build and integrate visualizations into their own web app or build their own client extension.

More info on [Qlik.Dev](https://qlik.dev/basics/integrating-qlik-objects-into-web-apps)