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
