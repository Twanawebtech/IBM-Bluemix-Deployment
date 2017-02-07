# IBM Bluemix Cloud Platform

1. Create a Bluemix Account

    [Sign up](https://console.ng.bluemix.net/registration/?target=%2Fdashboard%2Fapps) for Bluemix, or use an existing account.  

1. Download and install the [Cloud Foundry CLI](https://github.com/cloudfoundry/cli) to push your applications to Bluemix.

1. Create a `manifest.yml` file in the root of your application.
  ```
  applications:
  - name:      <your-app-name>
    host:      <your-app-host>
    memory:    128M
    services:
    - myMongo-db-name
  ```

  The host you use will determinate your application url initially, e.g. `<host>.mybluemix.net`.  
  The service name 'myMongo-db-name' is a declaration of your MongoDB service.  If you are using other services like Watson for example, then you would declare them the same way.

1. Connect and login to Bluemix via the Cloud-foundry CLI
  ```
  $ cf login -a https://api.ng.bluemix.net
  ```

1. Create a [MongoDB service](https://www.ng.bluemix.net/docs/#services/MongoDB/index.html#MongoDB)
  ```
  $ cf create-service mongodb 100 [your-service-name]
  ```
  **Note:** this is a free and experiment verion of MongoDB instance.  
  Use the MongoDB by Compose instance for production applications:
  ```
  $ cf create-service compose-for-mongodb Standard [your-service-name]'
  ```


1. Push the application

    ```
    $ cf push
    ```
    ```
    $ cf env <your-app-name >
    (To view the *environment variables* created for your application)

    ```

**Done**, now go to the staging domain(`<host>.mybluemix.net`.) and see your app running.  

[Cloud Foundry Commands](https://console.ng.bluemix.net/docs/cli/reference/bluemix_cli/index.html)  
[More Bluemix samples](https://ibm-bluemix.github.io/)  
[Simple ToDo app in a programming language of your choice](https://github.com/IBM-Bluemix/todo-apps)  



## IBM Watson
Be sure to check out the full list of Watson services to forwarder enhance your application functionality with a little effort. Watson services are easy to use, it is as simple as a RESTful API call.  

Here is an example of a [Watson Toner Analyzer](https://tone-analyzer-demo.mybluemix.net/) to understand the emotional context of a piece of text that you send to Watson.



### Watson catalog of services     

**<img src="https://ace-resources-production-20170203-200557.cdn.us-south.s-bluemix.net/resources/cache/286-4147526951/build/08fb1a72-e228-4e83-a37d-b90a4fa709d3-featured.png" width="25"> AlchemyAPI** - An AlchemyAPI service that analyzes your unstructured text and image content.      

**<img src="http://csbmixbroker.mybluemix.net/commerce_24.png" width="25"> Cognitive Commerce** - Cognitive Commerce is a service provided by Cognitive Scale.  

**<img src="http://csbmixbroker.mybluemix.net/graph_24.png" width="25"> Cognitive Graph** - Cognitive Graph is a service provided by Cognitive Scale.  

**<img src="http://csbmixbroker.mybluemix.net/insights_24.png" width="25"> Cognitive Insights** - Cognitive Insights™ is a service provided by Cognitive Scale.  

**<img src="https://ace-catalog-production-20170203-200557.cdn.us-south.s-bluemix.net/catalog/cache/3d6-3652049723/imgs/logos/servicedefault50.png" width="25"> Conversation** - 	Add a natural language interface to your application to automate interactions with your end users. Common applications include virtual agents and chat bots that can integrate and communicate on any channel or device.  

**<img src="https://ace-catalog-production-20170203-200557.cdn.us-south.s-bluemix.net/catalog/cache/3d6-3652049723/imgs/logos/servicedefault50.png" width="25"> Discovery** - Add a cognitive search and content analytics engine to applications.  

**<img src="https://wbi.mybluemix.net/icons/document-conversion.svg?version=2" width="25"> Document Conversion** - Converts a HTML, PDF, or Microsoft Word™ document into a normalized HTML, plain text, or a set of JSON-formatted Answer units.  

**<img src="https://ace-catalog-production-20170203-200557.cdn.us-south.s-bluemix.net/catalog/cache/3d6-3652049723/imgs/logos/servicedefault50.png" width="20" width="25"> Language Translator** - Translate text from one language to another for specific domains. 

**<img src="https://wbi.mybluemix.net/icons/natural-language-classifier.svg?version=2" width="25"> Natural Language Classifier** - Natural Language Classifier performs natural language classification on question texts. A user would be able to train their data and the predict the appropriate class for a input question.  

**<img src="https://wbi.mybluemix.net/icons/personality-insights.svg?version=2" width="25"> Personality Insights** - The Watson Personality Insights derives insights from transactional and social media data to identify psychological traits.  

**<img src="https://wbi.mybluemix.net/icons/retrieve-and-rank.svg?version=2" width="25"> Retrieve and Rank** - Add machine learning enhanced search capabilities to your application.   

**<img src="https://wbi.mybluemix.net/icons/speech-to-text.svg?version=2" width="25"> Speech to Text** - Low-latency, streaming transcription.  

**<img src="https://wbi.mybluemix.net/icons/text-to-speech.svg?version=2" width="25"> Text to Speech** - Synthesizes natural-sounding speech from text.  

**<img src="https://wbi.mybluemix.net/icons/tone-analyzer.svg?version=2" width="25"> Tone Analyzer** - Tone Analyzer uses linguistic analysis to detect three types of tones from communications: emotion, social, and language. This insight can then be used to drive high impact communications.  

**<img src="https://ace-catalog-production-20170203-200557.cdn.us-south.s-bluemix.net/catalog/cache/3d6-3652049723/imgs/logos/servicedefault50.png" width="25" > Tradeoff Analytics** - Helps make better choices under multiple conflicting goals. Combines smart visualization and recommendations for tradeoff exploration.    

**<img src="https://kpprod1.alchemyapi.com/images/vis_rec.svg" width="25"> Visual Recognition** - Find meaning in visual content! Analyze images for scenes, objects, faces, and other content. Choose a default model off the shelf, or create your own custom classifier. Find similar images within a collection. Develop smart applications that analyze the visual content of images or video frames to understand what is happening in a scene.  



[Click here](https://www.ibm.com/watson/developercloud/services-catalog.html) for live demos of each Watson service.

---
