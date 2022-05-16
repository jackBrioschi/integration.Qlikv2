# Embedded Analytics Modernization : Moving fast to Qlik Cloud

Embedded analytics seamlessly integrate analytic capabilities and content into business applications, products, websites or portals.
It lets users quickly access relevant data and insights in their daily workflows without slowing down and switching to use a separate analytics application.
Embedded analytics from *Qlik Sense Client Managed* site can easily be modernized by moving to *Qlik Cloud Platform.*

## What's the value to move your mashup on Qlik Cloud?

There are many advantages we can offer for moving your embedded analytics solution to Qlik Cloud architecture:
  * A high-performance and secure cloud architecture, scalable and elastic
  * Seamless, continuous release of upgrades and enhancements
  * Reduced burden on internal IT resources
  * Improve your embedded analytics by
    * Add value embedding new capabilities features : Alerting, Notes, Automation,...
    * Oppurtunity to upgrade your web integration with the lastest released libraries as Nebula.js wihtout limitations
    * An easy and secure cloud solution integration with for example handling CORS requests in Qlik Sense SaaS

Qlik Cloud allows you to surf the wave of modern analytics, always giving you immediate access to new features and improvements. It allows you to discover new use cases, deploying to a larger population and create new business value with Active Intelligence platform.

## How to move your mashup from Qlik Sense Client-Managed to Qlik Cloud?

### Assess your current web integration
Typically the three main pillars for completing an integration project concern understanding and choosing *where to host the solution*,  *how I can authenticate and authorize users* who already use the services inside my platform to be able to access the embedded analytics and which is the *web integration method* most in line with the needs I have.
There are many different ways and possibility to deploy mashup with Qlik. Start by asking you the right questions:

 * *Where my mashup or web application is hosted?*

 * *How do I manage the authentication?*

 * *Which embedding strategy do I currently use?*
 <br></br>
 <p align="center">
  <img src="src/img/analytics_modernization_flow.png" width="1000" title="hover text" align="center"/>
 </p>

### Hosting (Baptiste)
tbd

### Authentication
Within this part, therefore, we must deal with the concept of security within the Sense platform and show you also in this case the different possibilities we have to authenticate a user to our platform. Authentication in Qlik Sense allows you to establish a user session within the platform and typically answers the question *"Who is the user"*? The authentication process requires that based on something that the user has, this allows him or her to access the platform or not. 
In Qlik Sense Cloud, as well as in Qlik Sense Client-Managed, you can use an already existing identity provider (IdP) when setting up your deployment. For more information regarding this part, please visit [Authentication for Qlik Cloud Mashup](https://github.com/apamo/QlikSenseCM2SaaS/blob/main/introduction%20to%20Qlik%20Sense%20SaaS%20security.md)

### Embedding Strategy 
How to modernize your embedded analytics with Qlik? 
As you are probably already aware, we offer different methods and levels of integration, each with a different complexity.
Which one is right for your needs depends on the design requirements you have. 
In relation to Embedded Analytics with Qlik, we basically offer four different types of embedding strategies:
 * **Iframe Integration**
 * **Div-Tag Integration**
 * **On the fly**
 * **Data Only**
 
Can I maintain the same embedding strategies I adopted on Qlik Sense Client Manage on my new Qlik Cloud platform? **Yes, of course you can!**.
You just need to be aware about some small differences there are between the two different platform in terms of embedding. 
Let's see them in details in the next sections where we assume you are already aware and you already know the embedding strategies you are currently using.
If this is not the case, we invite you to see the section [Web Integration With Qlik](link to giacomo) where you can start from scratch and choose the best integration method that fits with your needs.
In any case, as you will be able to see in the following sections, everything can be done by calling the Qlik native APIs included within the standard product in SaaS.

### Iframe Integration

#### Introduction
Converting your Integration via Iframe from Qlik Sense Enterprise on Windows to Qlik Cloud Services is fairly straightforward. 
To convert your existing Iframe Integration to Qlik SaaS, please follow the steps below.

#### Prerequisites
Before performing any kind of integration via Iframe, **Content Security Policy (CSP)** needs to be properly configured.
Every Qlik Sense SaaS tenant explicitly states in its CSP header that an iframe can only be displayed by “self” which is the Qlik Sense SaaS tenant itself. Unlike in some cases on Qlik Sense Client-Managed, the Qlik Sense SaaS tenant and your web app server are two separate entities, meaning Qlik's CSP policy blocks the access of objects in other domains for a security precaution. If content security policy is not configured ,the browser throws an error because it's unable to display the iframe. Please for more details regarding *Content Security Policy(CSP)* and how to properly configure it to correctly load an iframe from Qlik Sense Saas, visit [this page on qlik.dev](https://qlik.dev/tutorials/csp---what-is-it-and-how-to-use-it)

#### How to do it
 Once pre-requisites are met, there are two different possibilities to embed Qlik Cloud content using Iframe: Embed an entire sheet or embed an existing visualization object. 
 The APIs to be used are the same you've already used on the client-managed platform, i.e. [Single Integration APIs](https://qlik.dev/apis/javascript/single-integrations).
 
You can then easily migrate from a Qlik Sense on Windows Iframe integration to Qlik Cloud by only changing the *hostName* and the *appId* inside the iFrame URL. 
*Do I need to change also sheetId and objects Id?* Well, if you migrated correctly the app into Qlik Sense SaaS, the ids of these objects should remain the same.
If otherwise you need to embed new content (new visualizations or new sheets) via iFrame that didn't exist before inside the former Qlik app, please go to [this section](https://github.com/jackBrioschi/integration.Qlikv2/tree/Jack) to see how to generate the correct Iframe URL to perform the integration.

  ##### Single Sheet
  * Just replace your old *hostName* (old Qlik Sense Enterprise on Windows server name) with the new Qlik Cloud tenant name and region (e.g. *your-tenant.eu.qlikcloud.com*). 
  * Replace your former *appId* on Qlik Sense on Windows environment with the new appId your tenant assigned to the app you've imported previously.*sheetId* should remain the same as before.
   ```HTML
  <iframe src="https://{hostName}/single/?appid={appId}&sheet=0fb8a6b4-341d-4999-af96-2130849f0f85&opt=ctxmenu,currsel" style="border:none;width:100%;height:100%;">
</iframe>
   ```
  ##### Single Object
  * Replace your old *hostName* (old Qlik Sense Enterprise on Windows server name) with the new Qlik Cloud tenant name and region (e.g. *your-tenant.eu.qlikcloud.com*).
  * Replace your former *appId* on Qlik Sense on Windows environment with the new appId your tenant assigned to the app you've imported previously. *objectId* should remain the same as before.
   ```HTML
  <iframe src="https://{hostName}/single/?appid={appId}&obj=BbKPXm&opt=ctxmenu,currsel" style="border:none;width:100%;height:100%;">
  </iframe>
   ```
#### Known Limitation
* Embedding the Hub in Qlik Cloud is not possible at the moment.


### Div-Tag Integration

#### Introduction
In this section we are going to describe how to adapt your existing mashup based on [Capability APIs](https://qlik.dev/apis/javascript/capabilities) to be moved to Qlik Cloud. Please note that we have also another Javascript library available for Embedded Analytics use case that is **Nebula.js**. This is a collection of product and framework agnostic JavaScript libraries and APIs that helps developers integrate visualizations and mashups on top of the Qlik associative engine. It offers developers a modern alternative to the capability APIs. If you are interested to convert your existing mashup to Nebula.js please go to [this section](https://github.com/jackBrioschi/integration.Qlikv2/tree/Jack). Otherwise, if you are just interested to adapt your Capability APIs mashup to Qlik Cloud, continue in the below sections.

#### Prerequisites
In order to correctly perform an integration using Javascript APIs, a new **web integration id** has to be created from the Qlik Cloud management console.
You can create web integrations to add origins that are allowlisted to access the tenant. The web integration containing the allow list is connected to an ID used in for example a mashup that is connecting to your tenant. When a request arrives, Qlik Sense confirms that the request derives from an allowlisted domain and then approves the request, else not.
Make sure you add the source that hosts the mashup to your whitelist while creating a new web Integration ID.

#### How to do it
In order to move your existing Div Tag integration from Qlik Sense Enterprise on Windows to Qlik Sense Enterprise SaaS, we need to make a set of small changes to the config settings and the source of Qlik libraries we are loaded to perform the integration. 
**The core part of the integration using the apis capabilities remains unchanged** as the same library is available on Qlik Cloud.

The adaptation we need to make can be summarized in the following steps:

* **Change Config settings**, in particular:
  * **Change the references of the actual Qlik associative engine connection**, which is used when you open an app or get a list of apps. This is covered by the config JavaScript object, used as a parameter in the openApp call.
  * To define where the **Qlik Sense client-side software and files should be loaded from**. This is achieved by configuring RequireJS with the require.config call and setting the baseUrl.
  * **To define the web integration ID**, which is necessary to enable cross-domain resource sharing.

  ```javascript
    const config = {
      host: 'your-tenant.eu.qlikcloud.com',        //for example, 'abc.eu.qlikcloud.com'
      prefix: '/',
      port: 443,
      isSecure: true,
      webIntegrationId: 'web-integration-id-here',  //paste here the web integration id you've created in the pre-reqs section
    };
    require.config({
      baseUrl: `https://${config.host}/resources`,
      webIntegrationId: config.webIntegrationId,
    });
  ```
* **Connect to the right Qlik Sense Cloud app** containing the objects you want to display on your web page.
   ```javascript
     const app = qlik.openApp('AppId', config); // Replace the former 'AppId' with the new appId of the app imported in the cloud tenant
   ```
   If you properly performed the app migration to Qlik Cloud, the objects id in the subsequents getObject calls *app.getObject('divID','objectId');*, should remain the same as the former Qlik Sense on Windows app.

* **Change the location to load both qlik-styles.css and require.js**. Replace the relationship between the current html document and the linked Qlik Sense defined style sheet in <link/> rel tag inside the <head/> of the HTML file, together with the link to require.js module loader loaded through the <script> tag.
 Replace both qlik-styles.css and require.js location inside the main .html file where these resources are loaded.
    ```HTML
       <link rel="stylesheet" href="https://your-tenant.eu.qlikcloud.com/resources/autogenerated/qlik-styles.css" />
       <script src="https://your-tenant.eu.qlikcloud.com/resources/assets/external/requirejs/require.js"></script>

    ```

 
#### Known Limitation
tbd


### On the fly

#### Introduction
tbd

#### Prerequisites
tbd

#### How to do it
tbd

#### Known Limitation
tbd


### Data Only

#### Introduction
tbd

#### Prerequisites
tbd

#### How to do it
tbd

#### Known Limitation
tbd
