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
Typically the three main pillars for completing an integration project concern understanding and choosing *where to host the solution*,  *how I can authenticate and authorize users* who already use the services inside my platform to be able to access the embedded analytics and which is the *web integration method* most in line with the needs you have.
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

#### Iframe Integration

##### Introduction
Converting your Integration via Iframe from Qlik Sense Enterprise on Windows to Qlik Cloud Services is fairly straightforward. 
To start using this capability, simply head over to a sheet, right click a visualization, and choose "Embed chart" from the context menu.

##### Prerequisites

##### How to do it
 ###### Single Object
 To start using this capability, simply head over to a sheet, right click a visualization, and choose "Embed chart" from the context menu.
  <p align="center">
   <img src="src/gif/Single%20Object%20Integration.gif" width="2800" title="Single Object Integration" align="center"/>
  </p>

 ###### Entire Sheet
 If you want to embed the entire sheet, click on the top-left context menu and choose "Embed sheet" like in the example below.
  <p align="center">
   <img src="src/gif/Single%20Object%20Integration.gif" width="800" title="Single Sheet Integration" align="center"/>
  </p>

