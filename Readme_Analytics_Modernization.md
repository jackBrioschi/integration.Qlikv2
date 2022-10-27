## What's the value of Embedded Analytics?
As data-driven decision making is becoming more and more a key part of organizations, having embedded analytics in the core applications that business people use on a regular basis becomes critical to being able to take full advantage from the data assets.

*Embedded analytics* seamlessly integrate analytic capabilities and content into business applications, products, websites or portals. It lets users quickly access relevant data and insights in their daily workflows without slowing down and switching to use a separate analytics application. This makes easier for organizations to empower employees, customers, suppliers and partners with the information they need right where they work to answer questions, make better decisions and take actions faster. Please visit [Qlik Embedded Analytics](https://www.qlik.com/us/bi/embedded-analytics)

### Introduction to Web Integration
Unlike some Business Intelligence and Analytics Platforms on the market that have been designed with the only scope of being BI platforms and that hence become endpoints within a data pipeline, Qlik wants to ensure that what is created inside the *Qlik Active Intelligence Platform*, does not remain bounded and accessible only within it but can be embedded in a single entry-point solution where corporate decision-making processes take place.

Hence, if we create a data model together with data visualization layer in Qlik, this by default will be accessible on the dedicated Qlik Sense SaaS tenant but can also be embedded within third-party portals, business solutions or services that an ISV delivers to its end customers.

This can be easily accomplished because Qlik embedded strategy is not based on proprietary languages, but on standard web technologies. This is enriched by what we call at  Qlik *"API first approach"* which allows us to expose almost all the features of the standard product to be integrated and used within a third party applications.

### What is a mashup and what are common use cases?
The way to integrate Qlik Data Analytics into a third-party solution is to create a mashup.
What is a mashup? A mashup is a web page or web application that reuses content from one or more sources to create a service made available to the end-users via a single portal. Hence think about your web solution on-premise or on SaaS that may retrieve content from your Qlik Sense SaaS tenant. Analytics are embedded inside the solution itself and allow the end users to have all the information and advanced analytics features they need within a single platform where business decision-making processes take place, without having to use two different instruments that do not communicate between each other.

## How to do it?
How to make embedded analytics with Qlik? 
As for the analytics part, we offer different methods and levels of integration, each with a different complexity. Which one is right for your needs depends on the design requirements you have. 

<img width="949" alt="embedding_strategies" src="https://user-images.githubusercontent.com/61158347/188099708-30b24b77-90a4-4be4-86b2-66a477114d31.PNG">

In any case, as you will be able to see in the following sections, everything can be done by calling the Qlik native APIs included within the standard product in SaaS.

Despite in this section we will focus on the Analytics part only, it is important to consider that **Augmented Intelligence** capabilities are increasingly available to improve and enhance the user's analytical skills within the platform. These concern for example exploiting machine-learning algorithms for predicting outcomes, the *creation of intelligent alerts* or a virtual assistant that talks with the user in natural language. Qlik's API first approach permits to even integrate these additional functionalities into your solutions. More detail in the section *"Qlik Cloud APIs first approach offers more than just embedded analytics"*.

## Embedding strategies
As for the Embedded Analytics part, we basically offer two different types of embedding strategies, the embedding via Iframe and the embedding using one of the available JS libraries.
Let's see them in details in the next sections.

### Iframe integration
The simplest and by far the most common method of embedding into your solutions analytics built in Qlik Sense SaaS is certainly through the use of an Iframe. An Iframe is generally used to show the content of a web resource, in our case Qlik Sense, within a frame of a web page/main portal.

#### How does it work?
To start using this capability, simply head over to a sheet, right click a visualization, and choose "Embed chart" from the context menu.

###### Entire Sheet
If you want to embed the entire sheet, click on the top-left context menu and choose "Embed sheet" like in the example below.

 ![image](https://user-images.githubusercontent.com/24877503/191058102-a40176eb-e8f3-419e-9ffe-18ae29f4a955.png)

###### Single Object
If you want to embed a specific object, right click on the object, then "Share" --> "Embed".

![image](https://user-images.githubusercontent.com/24877503/191058471-297d01d7-eb8d-4386-9b01-27009e342df5.png)

In the both case, you can set how the object will be embedded : allowing interation, enable context menu, selection bar, modify the theme, ...

![image](https://user-images.githubusercontent.com/24877503/191058065-5abf4533-56eb-48b7-a5f9-266c41f69dc1.png)


For more information, please refer to [help page](https://qlik.dev/tutorials/embedding-charts-and-sheets-into-web-apps)
   
#### When to use it/when not to use it?
When to use it : 
- To move fast in your integration. Easy implementation
- To leverage  Qlik capabilities by embedding a whole page or a component : Self-Service, Insight advisor, ...
- To start quickly and upgrade : Going further by combining Iframe and Enigma.js

[Here](https://qlik.dev/tutorials#embed) find some examples of advanced use cases with Iframe : Set the theme, manage anonymous access, manage content session state,...


### Javascript Integration
As you already know from the Introduction section, Qlik Solutions are based on standard web-technologies such as HTML, CSS and Javascript and that makes life easier when dealing with integration scenarios. If we add to this the fact that Qlik provides developers with a complete set of Javascript APIs to connect to the Qlik engine, retrieve a previously created app, retrieve its objects (Charts, Filters, etc...) and render them within a web-based solution, we can say that the integration experience that you have using the Javascript libraries is 360 degrees integration which allows a bi-directional communication between the information and objects contained in your web portal with the information and visualization objects contained in the Qlik apps.
You can use it when you typically have an existing portal/web-page and you want to embed Qlik into it. Not only that, with the JS APIs is possible to interact with the Qlik engine by applying selections rather than actions coming from the web components of the html page external to the Qlik Sense server itself. Let's think for example about a button rather than a dropdown menu natively present within your portal. When the user makes a selection of an item from the dropdown menu, you could trigger a call to the Qlik engine that applies a data selection in the application based on the value selected by the user.
  
In fact, Qlik APIs first approach allows many different level of integration. You can use APIs to extract information from the app data model to represent them within native objects of your solution or, viceversa by interacting with the native components of your solution you can trigger actions on the Qlik associative engine like for example applying a filter on the data that recalculates the Qlik charts in real time once you click on a dropdown menu, rather than a reset of the filters applied so far to the app.

To obtain the results described above, for a web-integration project with Qlik we offer different methods and libraries that you will find more in details in the section below.

#### Capability API

Need to go further than Iframe integration?

The Capability API are a collection of JavaScript APIs that allows you to easily embed Qlik Sense content into a web page, and interact with data.
With this approach, you can create dynamically the layout in the client without using an iframe.

Capability API are used in Qlik Sense Client Managed. It is a robust integration method.

***Make sure you have considered the prerequisites before to use Capabilities API!***
Capabilities API use AngularJS and RequireJS, which are both global libraries with the potential to interact with the rest of your web app.
jQuery is also loaded with the Capability APIs. It means if your website are using another versions of these librairies you could have to manage some conflicts.

Need some help :

- How to use Capability API : [tutorial](https://qlik.dev/tutorials/build-a-simple-mashup-using-capability-apis)
- Capabilities API : [help page](https://qlik.dev/apis/javascript/capabilities)

If you plan on using Capability APIs consider using the nebula.js open-source library available on NPM instead. nebula.js is a collection of JavaScript libraries, visualizations, and CLIs that helps developers build and integrate visualizations on top of Qlik's Associative Engine. Nebula.js is Framework-agnostic

You already have a mashup based on Capability API? No worries, it is always fully compatible.
Take a look to our Embedded Analytics migration page between Qlik Sense Client Managed and Qlik Cloud.

##### When to use it/when not to use it?
When to use it : 
- For a Qlik Sense Client Managed to Qlik Cloud move
- If your web application is fully compatible and if you are already used to implement this API

When not use it :
- For a new integration project that required a more modern framework. Nebula.js is recommended.
  
#### Enigma.js and Nebula.js 
Modern Embedded Analytics solutions using Qlik offers a stack of open-source libraries to build customized analytical platforms backed up with the robustness of Qlik’s Associative Engine. Historically, Capability APIs have been extensively used to build mashups and perform application related operations. A more modern alternative offering to Capability API-based operations is [Nebula.js](https://qlik.dev/libraries-and-tools/nebulajs) and [Enigma.js](https://qlik.dev/libraries-and-tools/enigmajs).

![image](https://user-images.githubusercontent.com/61158347/188104671-b70edb87-cb5c-44db-8ed2-96955af63139.png) 
*(Image Author: Dipankar Mazumdar. source: [qlik-community-article](https://community.qlik.com/t5/Design/Dealing-with-variables-in-a-Mashup-using-Nebula-js-amp-Enigma-js/ba-p/1801289) )*

#### How does it work?

**Enigma.js** is an open source library, developed on GitHub that helps you to communicate with the Qlik associative engine. You can use it as a wrapper to connect to Qlik Associative Engine and by using [QIX api](https://qlik.dev/apis/json-rpc/qix#docs) methods. The enigma.js library can be used as an SDK or to do CRUD (that is create, read, update and delete) operations on apps and on app entities, in our case we can retrieve an app, the objects of an app and the hypercubes that will be rendered using Nebula.js
To use enigma.js, you should be familiar with JavaScript, promises, websockets, and open source libraries. You will need Node.js. Since enigma.js implements the methods of the Qlik Engine JSON API so you should be familiar with referencing the [Qlik Engine JSON API](https://qlik.dev/apis/json-rpc/qix#docs). 

 On the other hand, **Nebula.js** is an open source library, developed on GitHub. Nebula.js is a collection of product and framework agnostic JavaScript libraries and APIs that helps developers integrate visualizations and mashups on top of the Qlik associative engine in Qlik Sense Desktop, Qlik Sense Enterprise on Windows, and Qlik Sense SaaS. It offers developers an alternative to the capability APIs that have historically been used to create mashups.
To use nebula.js, you should be familiar with JavaScript, promises, websockets, and open source libraries. You will need Node.js and access to the Qlik associative engine through Enigma.js. Knowledge of Qlik concepts such as generic objects and hypercubes would also be helpful.

To understand how the integration works we have several tutorials online. Here you can find some useful link:
* [Official Documentation on Qlik.dev](https://qlik.dev/apis/javascript/nebulajs-stardust)
* [Build a simple mashup using Nebula.js](https://qlik.dev/tutorials/build-a-simple-mashup-using-nebulajs)
* [Live examples of Nebula.js charts](https://glitch.com/@Qlik-Nebulajs) that can be re-used and modified

#### When to use it/when not to use it?
* With this type of integration we can satisfy any level of integration complexity from the *Div-Tag* level, to *On-the fly* to *Data Only*.
* Unlike Capability Apis, with Nebula.js, being framework agnostic, we are free from any dependence with external frameworks that makes life easier when dealing with integration projects.
* Since Nebula is an ever-developing library and new visualizations, features and objects are continuously released, I always recommend checking component availability based on your integration needs, as well as contacting your local Qlik presales for information on the roadmap. Please you can find the documentation of what is available at this [inventory section](https://qlik.dev/libraries-and-tools/visualizations/inventory) on the Online Help.

### Qlik Cloud APIs first approach offers more than just embedded analytics
Prior to the advent of Qlik Cloud, Qlik's Web Integration was totally focused on providing users with the ability to embed analytics developed within Qlik Sense dashboards. Now the music has changed as a series of Advanced Analytics features have been developed within Qlik Cloud that enrich the user's decision-making capacity, which can easily be integrated within your solutions.

* **Data Alerts**: Just think of data-based alerts where following a statistical condition that occurs on the data, notifications are sent via popup messages or emails to users to inform them of what has happened. 
    * [Online Doc](https://qlik.dev/apis/rest/data-alerts)
* **Natural Language Processing**: Qlik Cloud, among the value-added products, provides *Insight Advisor Chat*, a chatbot that can be interrogated in natural language that has the task of making the user communicate with the Qlik cognitive engine that always returns insights as well as the information he needs that increases its ability to interpret the data. A set of APIs to communicate with Qlik Cognitive Engine via NLP is now available and can be used to build your custom solutions that embed Qlik Natural Language capabilities.
    * [Online Doc](https://qlik.dev/apis/rest/natural-language)
    * [Build your own ChatBot](https://qlik.dev/tutorials/build-a-chatbot-using-the-qlik-sense-natural-language-api)
* **Qlik Application Automation**: Qlik Application Automation provides a no-code visual interface that helps you easily build automated analytics and data workflows. An automation is a sequence of actions and triggers that runs like a program. It can be a simple workflow that collects information from one application and passes it to another, or it can be an end-to-end pipeline that takes you from raw data to active intelligence. Automations let you automate your analytics environment, create data-driven workflows, and embed data and analytics into your business processes thanks to the APIs that are now available to integrate it into your decision-making processes.
    * [Online Doc](https://qlik.dev/apis/rest/automations)

* **Qlik AutoML**:Qlik AutoML is a built-in Auto Machine Learning platform within Qlik Cloud Analytics Services for generating automated machine learning models and delivering them as predictive endpoints. This solution allows you to send data to specific predictive endpoints and returns forecasts which are loaded inside your Web Application or in the Qlik Sense apps embedded in your portal.
    * [Online Doc](https://help.qlik.com/en-US/cloud-services/Subsystems/Hub/Content/Sense_Hub/AutoML/deploying-models.htm)
