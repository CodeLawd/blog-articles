## Learn REST APIs from the beginning


![What-is-REST-API.jpg](https://cdn.hashnode.com/res/hashnode/image/upload/v1646502807329/sQX11pYCQ.jpg)

Hi, welcome once again. This article is a compilation of some REST APIs tutorials. In this article, you will learn what REST APIs are from the scratch.

To understand REST APIs, you need to understand what an API (or Application Programming Interface) is and how they work.

### What is an API?

An API or Application Programming Interface is a set of guidelines or rules that state how applications interact. An API lets one application request data from another system.

### Why are APIs important?

An API lets one application use the capabilities of another system. This means you can easily use the features of another system without building it yourself. 

### Example of an API

Imagine that you are building a trading platform. You will need to support various features like exchange of currency, fluctuation of market rates, authentication, payment processing, and much more. Building and maintaining such functionalities is difficult. To resolve these issues, you can use integrations with various other software via APIs.

### Components of an API

The three main components of an API are Request, Response, and Resource. You would make a request to a server. The server will return a response that will contain data regarding a resource.

### Anatomy of an API Request


- **Endpoint**: This contains the URL that you request for e.g. ```
https://sampleapi.com/api/v1/users
```
- **Method**: This contains the type of your request e.g. ```
POST
``` or ```
GET
```
- **Headers**: This contains additional information for either the client or the server
- **Body**: This contains information sent to the server


Now that you've understood what APIs are, let's now talk about **HTTP**

### What is HTTP?
HTTP (or Hypertext Transfer Protocol) is a protocol generally used by web services for serving HTML documents. A client requests to a server for a resource, and the server sends a response.

### What are the different methods of HTTP?
HTTP has a fixed number of methods that the client can use to indicate what type of operation it wants to perform via the request. These request methods are also known as HTTP verbs.

There are 9 HTTP methods:

1. GET
2. POST
3. DELETE
4. PATCH
5. PUT
6. HEAD
7. TRACE
8. CONNECT
9. OPTIONS

While there are 9 different methods, GET, POST, PATCH, PUT and DELETE are the most popular.

#### GET
The GET request is used to request data from a server.

For example, when you visit an e-commerce website, the browser will make a GET request to fetch all the details. Once the server responds to the GET request, the browser will show a list of items.

#### POST
The POST request is used to send some data to the server.

For example, when you want to place an order on an e-commerce website, the browser will make a POST request to save that information on the server.

#### PATCH and PUT
The PATCH AND PUT requests are used most often to update on the server.

The main difference between PATCH and PUT is that PATCH is used to partially modify a resource, whereas PUT is used to update the entire resource on the server.

#### DELETE
The DELETE request is used to delete the specified resource.


Now that we've fully understood what **HTTP** is and the different methods available, let's now dive deep into **REST APIs**

### What is a REST API
A REST API is an API that follows the design principles of the REST (or REpresentational State Transfer) architecture.

REST APIs communicate via HTTP requests to perform CRUD (or Create, Read, Update, and Delete) operations.

### Different types of HTTP headers
When a client requests to the server, the client can pass additional information as a part of the request via HTTP headers. As mentioned earlier, headers are case insensitive.

Headers can contain information about the type of data that the client is sending to the server. It can also contain information about authenticating a user agent with the server.

Headers can be grouped into four types based on their contexts:

### Request headers
In an HTTP request, the [Request headers](https://developer.mozilla.org/en-US/docs/Glossary/Request_header) pass information about the request. It contains information about the requested resource and the client making the request.

A request header can contain information about the type of the request, the URL to which the request is being made, authentication details, cache policy as well as the user agent.

Some of the popular request headers are:

#### Accept
The [Accept](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Accept) HTTP header informs the server about the type of data that the client can understand.


```
Accept: text/html
Accept: application/xhtml+xml
Accept: image/png
``` 

#### Accept-Encoding
The Accept-Encoding HTTP header informs the server about the type of encoding the client is able to understand.

```
Accept-Encoding: gzip
Accept-Encoding: gzip, compress
``` 

#### Authorization
The [Authorization](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Authorization) HTTP header is used to pass credentials which lets the server authenticate a client and provide access to protected resources.

```
Authorization: Basic YWxhZGRpbjpvcGVuc2VzYW1l
Authorization: Bearer eyYWxhZGRpbjpvcGVuc2VzYW1l
``` 

#### Cache-Control
The [Cache-Control](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Cache-Control) HTTP header holds caching instructions for the client and the server.

```
Cache-Control: stale-while-revalidate=60
Cache-Control: no-cache
``` 

### Response headers
Like the request headers contain information about the client, the response headers contain information about the server from which the resource is requested. All headers in a response message can be called response headers.

Some response headers like [Age](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Age), [Location](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Location), [Server](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Server) can give a more detailed response context.

### Representation headers
The Representation headers contain information about the resource body, which is sent in a response. Some representation headers are [Content-Type](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Type), [Content-Encoding](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Encoding), [Content-Language](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Language), [Content-Location](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Location)

### Principles of REST API
REST APIs follows six design principles which are as follows:

- **Client-server Separation**: The application which is requesting the resource is called the client, and the application which has the resource is called the server. When the client requests a request to the server, the server sends a response to the client. The server can’t initiate a request to the client. In a RESTful API, the client and server are always kept independent of each other. This ensures that both the client and the server can be scaled independently.

- **Stateless**: In a RESTful API, each request needs to contain the data that is necessary to process it. Servers aren’t allowed to store any data related to the client. No session or authentication state is stored on the server. If the client requires authentication, then the client needs to authenticate itself before sending a request to the server.

- **Cacheable**: In REST APIs, the resources should be able to cache themselves either on the client or on the server. When a client requests a resource from the server, the response from the server will contain the information of whether the resource can be cached or not and for how long. The main idea of caching is to improve the performance of the client by reducing the bandwidth required to load the resource.

- **Layered System**: In REST APIs, there can be multiple intermediaries between the client and the server. It isn’t always necessarily true that the client connects directly to the server and requests a resource. There can be multiple systems in between them that are responsible for handling security, traffic, balancing the load, redirection, etc. The client or the server doesn’t have any information about how many systems are in between them.

- **Uniform Interface**: All requests and responses in a REST API should follow a common protocol. This allows the applications to evolve independently. The client and server can interact with each other in a single language irrespective of the architecture that they are based upon.

- **Code on Demand (optional)**: When a client requests a resource, the server can return executables as a part of the response. This is an optional constraint. In certain cases, this might help reduce the amount of code that has to be written on the client.

### Versioning 
Imagine that you are working in an extensive application that releases new versions of an API every day. A lot of other applications depend on your API for their features to work as expected. When a bug gets released in your API, all the applications that rely on your API will stop working. Maintaining uptime for any application is essential, and having downtime because of the bug will cause many problems. One way to resolve this problem is by version control.

A good versioning strategy will ensure that at least one version of your API will work as expected. Because of this, the applications using the buggy version can fall back to a previous version.

Generally, version control is maintained in a changelog which the consumers of an API can refer to. Versioning can be breaking and non-breaking.

#### Different types of versioning strategies
- **URI versioning**: This is the most common versioning strategy, although it violates every URI should contain a unique resource. When a URI version is done, all the resources get updated to a new version. URI versioning can also cause issues with caching. An example of this strategy is the following:

```
https://website.com/api/v1/users
https://website.com/api/v2/users
``` 

- **Query parameters versioning:** This strategy states the version of an API by using query parameters. An example of this kind of strategy can be the following:

```
https://website.com/users?version=1
``` 

- **Custom headers versioning:** Versioning can also be done by passing custom request headers. An example will be the following:

```
curl -H "accept-version: 1"  https://website.com/users
``` 

### Security
#### Content Security Policy (CSP)
[Content Security Policy](https://developer.mozilla.org/en-US/docs/Web/HTTP/CSP) (CSP) is an added layer of security that helps to detect and mitigate certain types of attacks, including Cross-Site Scripting (XSS) and data injection attacks. These attacks are used for everything from data theft, to site defacement, to malware distribution.

The syntax looks like this:

```
Content-Security-Policy:  <policy-directive>; <policy-directive>
``` 


Alternatively, the ```<meta>``` element can be used to configure a policy, for example:

```
<meta http-equiv="Content-Security-Policy"
      content="default-src 'self'; img-src https://*; child-src 'none';">
``` 

#### Cross-Origin Resource Sharing (CORS)
[Cross-Origin Resource Sharing](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS) (CORS) is an HTTP-header-based mechanism that allows a server to indicate any origins (domain, scheme, or port) other than its own from which a browser should permit loading resources. CORS also relies on a mechanism by which browsers make a "preflight" request to the server hosting the cross-origin resource, in order to check that the server will permit the actual request. In that preflight, the browser sends headers that indicate the HTTP method and headers that will be used in the actual request.

Congrats on completing this article. Though quite a long read but I hope you've been able to understand what REST APIs are and how they work.

Huge credit goes to [RapidAPI Learn](https://rapidapi.com/learn)
You can follow me on [Twitter](https://twitter.com/CodeLawd)

