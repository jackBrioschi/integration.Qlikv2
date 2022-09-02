# integration.Qlikv2
This is a repo to share the work Giacomo and Baptiste are doing in relation to create a SaaS version of integration.Qlik.com


## What's the value of Embedded Analytics?
As data-driven decision making is becoming more and more a key part of organizations, having embedded analytics in the core applications that business people use on a regular basis becomes critical to being able to take full advantage from the data assets.

*Embedded analytics* seamlessly integrate analytic capabilities and content into business applications, products, websites or portals. It lets users quickly access relevant data and insights in their daily workflows without slowing down and switching to use a separate analytics application. This makes it easier for organizations to empower employees, customers, suppliers and partners with the information they need right where they work to answer questions, make better decisions and take actions faster. Please visit [Qlik Embedded Analytics](https://www.qlik.com/us/bi/embedded-analytics)

### Introduction to Web Integration
Unlike other Business Intelligence and Analytics Platforms on the market that start out as BI platforms and become endpoints within a data pipeline, Qlik wants to ensure that what
is created inside the *Qlik Active Intelligence Platform*, does not remain bounded and accessible only within it but can be embedded
in a single entry-point solution where corporate decision-making processes take place.

Hence, if we create a data model together with data visualization layer in Qlik, this by default will be accessible on the dedicated Qlik Sense SaaS tenant but can also be embedded within portals, business solutions or services that an ISV delivers to its end customers.

This can be easily accomplished because Qlik embedded strategy is not based on proprietary languages, but on standard web technologies. This is enriched by what we call at  Qlik *"API first approach"* which allows us to expose almost all the features of the standard product to be integrated and used within a third party applications.

### What is a mashup and what are common use cases?
The way to integrate Qlik Data Analytics into a third-party solution is to create a mashup.
What is a mashup? A mashup is a web page or web application that reuses content from one or more sources to create a service made available to the end user via a single graphical interface/tool. Hence think about your web solution on-premise or on SaaS that may retrieve content from your Qlik Sense SaaS tenant. Analytics are embedded inside the solution itself and allow the end users to have all the information and advanced analytics tools they need within a single platform where business decision-making processes take place, without having to use two different instruments that do not communicate between each other.

## How to do it?
How to make embedded analytics with Qlik? 
As for the analytics part, we offer different methods and levels of integration, each with a different complexity. Which one is right for your needs depends on the design requirements you have. 

<img width="949" alt="embedding_strategies" src="https://user-images.githubusercontent.com/61158347/188099708-30b24b77-90a4-4be4-86b2-66a477114d31.PNG">

In any case, as you will be able to see in the following sections, everything can be done by calling the Qlik native APIs included within the standard product in SaaS.

Despite in this section we will focus on the Analytics part only, it is important to consider that **Augmented Intelligence** capabilities are increasingly available to improve and enhance the user's analytical skills within the platform. These concern for example the *creation of intelligent alerts* or a virtual assistant that talks with the user in natural language. Qlik's API first approach permits to even integrate these additional functionalities into your solutions. [More detail in the section ...].

## Embedding strategies
As for the Embedded Analytics part, we basically offer two different types of embedding strategies, the embedding via Iframe and the embedding using one of the available JS libraries.
Let's see them in details in the next sections.

  ### Iframe integration
  The simplest and by far the most common method of embedding into your solutions analytics built in Qlik Sense SaaS is certainly through the use of an Iframe. An Iframe is generally used to show the content of a web resource, in our case Qlik Sense, within a frame of a web page/main portal.
  

   #### How does it work?
     To start using this capability, simply head over to a sheet, right click a visualization, and choose "Embed chart" from the context menu.
   <p align="center">
    <img src="src/gif/Single%20Object%20Integration.gif" width="2800" title="Single Object Integration" align="center"/>
   </p>

  ###### Entire Sheet
  If you want to embed the entire sheet, click on the top-left context menu and choose "Embed sheet" like in the example below.
   <p align="center">
    <img src="src/gif/Single%20Sheet%20Integration.gif" width="800" title="Single Sheet Integration" align="center"/>
   </p>
   
   
   #### When to use it/when not to use it?
   PRO: when you need a quick fix. When Qlik Sense's look & feel meets your needs. Because? because there are still themes
that can be applied to Qlik dashboards to completely customize their appearance and make them completely in line with what are the
corporate color palette and corporate standards (white labeling of the platform) but obviously we cannot go to use style and JS to go to
customize the style and native behavior of graphic objects by making them interact with our page.
If you want to embed the self-service part, that is to give the user the possibility to create new sheets, or to embed an entire sheet of a
application or the insight advisor to allow you to use the Qlik Cognitive Engine for guided data analysis through the use of insights, this
It is the only way.
   
  ### Javascript Integration
  As you already know from the Introduction section, Qlik Solutions are based on standard web-technologies such as HTML, CSS and Javascript and that makes life easier when dealing with integration scenarios. If we add to this the fact that Qlik provides developers with a complete set of Javascript APIs to connect to the Qlik engine, retrieve a previously created app, retrieve its objects (Charts, Filters, etc...) and render them within a web-based solution, we can say that the integration experience that you have using the Javascript libraries is 360 degrees integration which allows a bi-directional communication between the information and objects contained in your web portal with the information and graphic objects contained in the Qlik apps.
  
In fact, in addition to the use of Qlik integrated analytics, I can use APIs to extract information from the app data model to represent them within native objects of your solution or, viceversa by interacting with the native components of your solution I can trigger actions on the Qlik associative engine like for example applying a filter on the data that recalculates the Qlik charts in real time once I click on a dropdown menu, rather than a reset of the filters applied so far to the app.

To obtain the results described above, for a web-integration project with Qlik we offer different methods and libraries that you will find more in details in the section below.
  
   #### Enigma.js and Nebula.js 
   Modern Embedded Analytics solutions using Qlik offers a stack of open-source libraries to build customized analytical platforms backed up with the robustness of Qlik’s Associative Engine. Historically, Capability APIs have been extensively used to build mashups and perform application related operations. A more modern alternative offering to Capability API-based operations is [Nebula.js](https://qlik.dev/libraries-and-tools/nebulajs) and [Enigma.js](https://qlik.dev/libraries-and-tools/enigmajs).

![image](https://user-images.githubusercontent.com/61158347/188104671-b70edb87-cb5c-44db-8ed2-96955af63139.png)

##### How does it work?

**Enigma.js** is an open source library, developed on GitHub that helps you to communicate with the Qlik associative engine. You can use it as a wrapper to connect to Qlik Associative Engine and by using [QIX api](https://qlik.dev/apis/json-rpc/qix#docs) methods. The enigma.js library can be used as an SDK or to do CRUD (that is create, read, update and delete) operations on apps and on app entities, in our case we can retrieve an app, the objects of an app and the hypercubes that will be rendered using Nebula.js
To use enigma.js, you should be familiar with JavaScript, promises, websockets, and open source libraries. You will need Node.js. Since enigma.js implements the methods of the Qlik Engine JSON API so you should be familiar with referencing the [Qlik Engine JSON API](https://qlik.dev/apis/json-rpc/qix#docs). 

 On the other hand, **Nebula.js** is an open source library, developed on GitHub. Nebula.js is a collection of product and framework agnostic JavaScript libraries and APIs that helps developers integrate visualizations and mashups on top of the Qlik associative engine in Qlik Sense Desktop, Qlik Sense Enterprise on Windows, and Qlik Sense SaaS. It offers developers an alternative to the capability APIs that have historically been used to create mashups.
To use nebula.js, you should be familiar with JavaScript, promises, websockets, and open source libraries. You will need Node.js and access to the Qlik associative engine through Enigma.js. Knowledge of Qlik concepts such as generic objects and hypercubes would also be helpful.

To understand how the integration works we have several tutorials online. Here you can find some useful link:
* [Build a simple mashup using Nebula.js](https://qlik.dev/tutorials/build-a-simple-mashup-using-nebulajs)

   ##### When to use it/when not to use it?
   
   #### Capability APIs
   description
   ##### How does it work?
   tbd
   ##### When to use it/when not to use it? 
   
   
  
 





