# rest-api

A website is just a framework to display the content but not actual content. As soon as we start navigating the website the framework starts sending and receiving the contents using REST API's. 

```Client(Mobile App, Web Browser, Smart Watch)```-----------```Rest API```-----------```Data Store```                   

(Make Plant UML Diagram)

```
"Representational State Transfer (REST) refers to a group of Software Architecture Design Constraint that brings about efficient, reliable, and Scalable systems."
```


### How webpages/website work:
    
    Each webpage compromises of:
        1. HTML Page
        2. CSS Style sheet to represent the data.
        3. Java Script manipulating the document. 

    When a visitor navigates from one page to another.
        1. They send a URL request to the server pointing at a specific HTML document.
        2. The server return the required HTML page with files to replace the current webpage. 
    
    This work is fine but it is resource intensive. Every time a new page is rendered, which should be either written by a developer or rendered by a content management system. 

### How Web Application work:

    The web app is downloaded in the browser and run in the browser, and is populated the data from the web. In a web app each page is a view of a current state.

    As soon as the user run the web app for the first time, all the components are downloaded from the web and a view is created, including a HTML framework.
        1. The application then sends the URI request for web resource to the server asking for the next state of the application to be transferred. 
        2. This representation state is transferred as a Data Object, and application can then change the data object inside with rendering the entire new page. 


### Universal Resource Identifier(URI)

    "A compact sequence of characters that identifies an abstract or physical resource that provides a simple and extensible means for identifying a resource"

    Example: 

    1. https://restful.dev/posts/5
    2. ftp://myserver.dev/files/docs/script.docs
    3. mailto:morten@example.com
    4. tel:+1-888-555-1212
    5. urn:library:names:authors:mrh
    6. library:names:authors:mrh

    In Short any combination of string which can identify an Resource is a URI.

### Universal Resource Locator(URL)

    "Subset of URI that identifies a resource and explain how to access that resource by providing and explicit method like https:// or ftp://".

    In other words all URL are URI but not all URI and URL.

### The Six constraints of REST API's.

    1. Client-server architecture.
    
    Separation of concerns. The client manages the user interface concerns while the server manages data storage concerns. This architecture efficiently manages 1 REST server with different clients. Hence we have complete separation between the content and how it is presented.

    2. Statelessness.

    No client context or information aka state can be stored on the server between requests.

    3. Cacheability.

    ALL REST response must be clearly marked as cacheable or not cacheable.

    4. Layered System.

    The client cannot know, and shouldn't know if it is connected to REST Server  or intermediary like a CDN or mirror. This ensures scalability and also helps with security.

    5. Code on demand.

    Servers are allowed to transfer executable code like JavaScript and compiled components to clients.

    6. Uniform Interface.

        6.1 Resource Identification in requests
        6.2 Resource Manipulation through representation.
        6.3 Self-descriptive messages.
        6.4 Hypermedia as the engine of application.



