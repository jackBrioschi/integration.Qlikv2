# integration.Qlikv2
This is a repo to share the work Giacomo and Baptiste are doing in relation to create a SaaS version of integration.Qlik.com


## What's the value of Embedded Analytics?
As data-driven decision making is becoming more and more a key part of organizations, having embedded analytics in the core applications that business people use on a regular basis becomes critical to being able to take full advantage from the data assets.

*Embedded analytics* seamlessly integrate analytic capabilities and content into business applications, products, websites or portals. It lets users quickly access relevant data and insights in their daily workflows without slowing down and switching to use a separate analytics application. This makes it easier for organizations to empower employees, customers, suppliers and partners with the information they need right where they work to answer questions, make better decisions and take action faster. Please visit [Qlik Embedded Analytics](https://www.qlik.com/us/bi/embedded-analytics)

### Introduction to Web Integration
Unlike other Business Intelligence and Analytics Platforms on the market that start out as BI platforms and become endpoints within a data project, Qlik wants to ensure that what
is created inside the *Qlik Active Intelligence Platform*, does not remain bounded and accessible only within it but can be embedded
in a single platform entry-point which corporate decision-making processes take place.

Hence, if we create a data model together with data visualization layer in Qlik, this by default will be accessible on the dedicated Qlik Sense SaaS tenant but can also be embedded within portals, business solutions or services that an ISV delivers to its end customers.

This can be easily accomplished because Qlik embedded strategy is not based on proprietary languages, but on standard web technologies. This is enriched by what we call at  Qlik *"API first approach"* which allows us to expose almost all the features of the standard product to be integrated and used within A third party applications.

### What is a mashup and what are common use cases?
The way to integrate Qlik into a third-party system is to create a mashup.
What is a mashup? A mashup is a web page or web application that reuses content from one or more sources to create a service made available to the end user via a single graphic interface/tool. Hence imagine you have your web solution on-premise or on SaaS that may retrieve content from your Qlik Sense SaaS tenant. Analytics are embedded inside the solution itself and allow the end users to have all the information and advanced analytics tools they need within a single platform where business decision-making processes take place, without having to use two different instruments that do not communicate between each other.

## How to do it?
How to make embedded analytics with Qlik? 
As for the analytics part, we offer different methods and levels of integration, each with a different complexity. Which one is right for your needs depends on the design requirements you have. In any case, as you will be able to see in the following sections, everything can be done by calling the Qlik native APIs included within the standard product in SaaS.

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
  description
   #### Nebula.js and Enigma.js libraries
   description
   ##### How does it work?
   tbd
   ##### When to use it/when not to use it?
   
   #### Capability APIs
   description
   ##### How does it work?
   tbd
   ##### When to use it/when not to use it? 
   
   
  
 





