# REST-API's

A website is just a framework to display the content but not actual content. As soon as we start navigating the website the framework starts sending and receiving the contents using REST API's.

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
If and only if a web based api's meets these constraints then only it can be called as REST API. 

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


### HTTP and REST:

    When a rest service runs on the web over HTTP to give us access to a resources we call it a ```RESTful API```.
    
### Anatomy for REST Request.

    In the most basic form REST have two parts:
        1. Method (POST,GET,UPDATE,PATCH,DELETE,PUT,OPTIONS,HEAD)
        2. URI (http://www.restful.com/post/5)
    Working of all the REST methods on the URI at the end depends on the configuration of REST API and the authorization from client.

When sending rest request to the Server, we can also include MetaData with the requests. With the POST/PUT request we should send the Message Body. 

### Discovery of REST API.

Discovering what resources and methods are available and what we can do with them? Even if no documentation is present the rest api will describe itself. 

    Using GET and OPTIONS methods we can walk our way to any resp api resources and methods. 

### Resource and Representation. 

    "Any information that can be name is resource." Resource is conceptual mapping of information.
    
    "Rest components performs actions on resource by using a representation to capture the current or intended state of the resource and transfer that representation between states."

Rest server creates a unique representation of that requested resources and even modify the representation to fit the specification.

### REST Methods/Verbs.

1. **POST**
    Create a new resource and often add it in the collection.
    | Response        | Description      |
    | ------------- |:-------------:|
    | 201 | Resource **Created**, and return the resource URI with the Response Header. |
    | 401 | Client is **not authorized** to create a resource. |
    | 409 | **Conflict**, if the resource already exits. |
    | 404 | Resource Not found, if the resource is not found. |
2. **PUT**
    Update a existing singleton resource based on ID. Unlikely as the POST, PUT resource have the ID of the resource along with the New Data. PUT will replace the current content with the content send along with the PUT request.
    
    If the Resource already exits the Content is replaced, else the a new resource is made with the ID specified.(Only Singleton Resource.)
    | Response        | Description      |
    | ------------- |:-------------:|
    | 200 OK | Resource Updated or **Created**. |
    | 204 | **No content**, when no content is present. |
    | 404 | **Resource Not found**, if the resource is not found. |
    | 401 | Client is **not authorized** to create a resource. |
    | 405 | **Method Not Allowed**. If PUT is trying to update a collection. |

3. **PATCH**
    Patch is used to modify a existing resource with replacing the Content.
    | Response        | Description      |
    | ------------- |:-------------:|
    | 200 OK | Resource Updated or **Created**. |
    | 204 | **No content**, when no content is present. |
    | 404 | **Resource Not found**, if the resource is not found. |
    | 401 | Client is **not authorized** to create a resource. |
    | 405 | **Method Not Allowed**. If PUT is trying to update a collection. |
4. **OPTIONS**
    Get the options available for the Resource.
    | Response        | Description      |
    | ------------- |:-------------:|
    | 200 OK | **Returned** the description. |
5. **HEAD**
    Return just the header from the resource.
    | Response        | Description      |
    | ------------- |:-------------:|
    | 200 OK | **Returned** the description. |
    | 404 | **Resource Not found**, if the resource is not found. |
6. **DELETE**
    Delete Single Resource. If try to delete a collection will get 405 :** Method Not Allowed** exception.
7. **GET**
    Get the resource at the end of the address and send it to the client. Every time we refresh, move forward or backward in the browser, we use GET request.
    | Response        | Description      |
    | ------------- |:-------------:|
    | 200 OK | Resource Received Successfully. |
    | 404 | **Resource Not found**, if the resource is not found. |

### Response

Any time a client sends a REST request, it gets back the HEAD section from the Server. Every response from the Head Section will have a Head section. 

#### Http Status Code

The HTTP response status code let the client know about the success and the failure of the Request.

| Response | Description |
| ------------- |:-------------:|
| 1XX | Information |
| 2XX | Success |
| 3XX | Redirection |
| 4XX | Client Error |
| 5XX | Server Error |

1. Information Codes. 
These codes are informational and rarely encountered. Server send these error to client for FYI e.g. I got your request, I got an open connection now.

2. Success Codes.

| Response | Description |
| ------------- |:-------------:|
| 200 | **OK**: The request was successful |
| 201 | **Created**: The request was successful and a new resource was created. |
| 204 | **No Content**: The request was successful, and no content was send back by server. |

3. Redirection Codes.
The client was is being provided with a new URI to access the resource. The 300 response set are quite confusing.

| Response | Description |
| ------------- |:-------------:|
| 301 | **Moved permanently** |
| 302/303 | **Found at this other URL** |
| 307 | **Temporary redirect** |
| 308 | **Resume incomplete** |

4. Client Error.

| Response | Description |
| ------------- |:-------------:|
| 400 | **Bad Request**: Request is malformed, too large or similar |
| 401 | **Unauthorized**: The Client lack Authorization |
| 403 | **Forbidden**: Client is not logged in or do not have right permissions |
| 404 | **Not Found**: If the resource is not found |
| 405 | **Method Not Allowed**: If the resource does not know the method it is being applied.  |

5. Server Error.

| Response | Description |
| ------------- |:-------------:|
| 500 | **Internal Server Error** |
| 502 | **Bad Gateway** |
| 503 | **Service Unavailable** |