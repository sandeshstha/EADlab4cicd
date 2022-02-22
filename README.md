## Web Architecture styles:
1) Service Oriented Architecture (SOA)
2) Object Oriented Architecture (OOA) 
3) Resource Oriented Architecture (ROA)


### SOA
* SOA is architecture oriented at service.

#### What is Service?
* Software or piece of code, that performs specific task or response to particular event as per request and produce specific output.
* It is logical representation of repeatable business activities that have specified output.
* Eg: Weather Predictor, accessing stock price


* SOA is a web architectural style of web service, but is not any programming language or technology.
* It defines best approaches to design and develop a web service.
* It is a set of principles, procedures and methodologies.
* System is made up of services and those services performs some operations and, they can communicate with each other.
* Internally, service can consist of many parts such as getting data from database, calling external system, applying some algorithms but consumer of SOA doesn't know internally how it produces output (i.e Black Box).
* Server doesn't store any information related to client state and client is responsible to pass information necessary for communication (i.e. Stateless)
* Additionally, each service in SOA have interface description such as WSDL file, which defines the messages and payload formats.
* EG: SOAP over HTTP, SOAP over JMS (Java Message Service)



### Resource Oriented Architecture (ROA)
* A foundation of the semantic web or Web 3.0
* ROA is an architecture oriented to resource.

#### What is Resource?
* Resource is anything that can be stored in computer, any document or data.
* A record in database, file or document or result of algorithm as a resource.
* EG: Retrieving HTML page with GET request or Database table
* The idea of ROA is to use web technologies (HTTP, URI and XML/JSON) with the core design principles and providing guidelines to support and implement interaction of resources.

#### Concepts and Properties of ROA

* Resource providers:
	- Server that provides resource is resource providers.
	- EG: AWS and Microsoft Azure
* Resource:
	- EG: Servers, devices, web pages, Javascript, document, data.
	- Resources will have name and unique address or path to it.

* Resource representation:
	- It is the useful information about the current state of a resource, specified with a specific format, in a specific language.
	- EG: Transcript of some speech in multiple languages

* Resource link and connectedness:
	- Resource link means another resource or the resource itself. Connectedness is all about how reliable and relevant the resource's links are.
	- EG: One resource connected with other resource of same kind ( Watching videos on youtube).

* Statelessness:
	- Server won't store any client state related information, every request should be self-contained

* The uniform interface:
	- Uniform interface means all services should happen same way.
	- EG: GET, POST, PUT, DELETE


#### Benefits of ROA

* Scalability and performance:
	- Because of statelessness and no session stickiness- it is possible to achieve good performance and scalability

* Explicit state:
	- Client and Server will have explicit state
	- Every request will be independent.

* No Contract:
	- ROA follows HTTP Protocols,
	- No need to establish any new contracts and connections, between client and server.


> SOA can use SOAP or REST, AND ROA uses REST.


#### SOAP
- Simple Object Access Protocol
- Microsoft developed SOAP to replace older technologies
- It is specification that describes how to format messages for communications between application.
- Before SOAP there are following technologies like
	- DCOM - Distributed Component Object Model
	- CORBA - Common Object Request Broker Architecture
	-- These technologies use binary messaging system, which was not efficient
- SOAP is protocol and it provides details on how to prepare message in XML and it defines goal of request and action.
- After initial release, IETF (Internet Engineering Task Force) standardized it.
- IETF is an international community of Network Engineers, Network Designer, Operators, Researchers and Vendors, and these people are concerned about future of internet.
- Standardization of SOAP was done with expansion and scalability in mind. EG: WS-addressing, WS-security, WS-Policy etc.


#### Why Standardization? 
- Actual content of message which is in headers and body is not specified by SOAP.
- SOAP is kind of envelop, header and body is letter inside that envelop.
- SOAP doesn't specify actual content.
- Application can put anything inside envelop (header and body) based on requirement.
- Common requirement for implementation, 
	- Routing and addressing,
	- Deal with large payloads
	- Security
- WS is Web Standards is a set of standards based on SOAP specification.
- Purpose of these standards is to address these common requirements of communications.
- Standards can be used individually, EG: for only security, use WS-Security only.
- Standards help in development, deployment, management, governance, and composition of services.
- Envelope (request) reached at provider, body and header needs to be understood by provides for operations and inputs.
- Every operation is defined with structure of request and response, each input parameters and types are defined.
- WSDL - Web Service Description Language
 	- Describes supported actions, message formats and things required for operation.
 	- Contract between two parties, helps both parties to understand communication messages.
 	- Descriptor file also solved other problems that cannot be addressed with plain old XML.

- SOAP has built in error handling
	- If there is a problem with request, response contains error information.
	- Helpful in solving error, with standardized error codes, can be used in automatic error handling.
- SOAP is stateful, useful in conversational state management.
- Conversational State- services that goes bak and forth to perform operation.



### SOAP v/s REST
						SOAP										REST
What is it?   	- Complete Protocol 					    - Architectural styles
															- It is not protocol, needs HTTP as protocol for communication

Architecture	- SOA 									    - ROA
				  - Exposes application logic as service		- Access resource & expose data.
				  - Function driven								- Data driven.



Transfer Protocol 
				
				- Any transport protocols 					- Only HTTP.
				 EG: SOAP over HTTP, SOAP over JMS			

				- Standard protocols make communication 	- Easy to understand (EG: GET, POST, PUT...)
				easy over different levels.
				EG: Firewalls and proxies

Communication
			  - Distributed communication 					- Client Server Communication

			  - Process involves multiple sub				- 1 central server host entire systems
			  processing over different servers.


Data Format
Support 	
			- Depends only on XML							- Support multiple formats
			- Not browser compatible (XML)					(Eg: plain text, HTML, XML, JSON)
			- Complex in use because of complexity          - Browser compatible
			of XML											- Easy to use
															- Modern UI framework work with JS which makes consumption of payloads easy
															Eg: Cloud, Mobile, IOT

Payloads
			- It uses XML, which is very heavy				- It uses HTTP and JSON
			that uses more resource

			- Creating XML can be very complex 				- JS is compatible with JSON so no need of 
																extra processing of payload

Security
		   - Supports WS-security which is great			- Supports secure version of HTTP (HTTPS)
		   at transport level security,
		   - More ideal for enterprise level security
		   tools


Bandwidth
			- More bandwidth 								- Light weight in terms of design
			  - Due to envelop style and WSDL					- because uses light weight JSON
			   files

Caching
			- Envelop style requires multiple steps 		- It is possible to cache data
			for caching


State
			- Stateful - server keeps track of clients      - Stateful- server doesn't know about 															client's state


			Incase of disconnection							Incase of disconnection
				- Retry action requires lot of 				- Reconnection is very easy because each
				initialization configuration because of 	request is independent of each other
				this state and state code

				- Concerns in scalability 					- Makes it more scalable.


Dependency
			- Tightly coupled with server 					- Not much depended on server
			- Strict contract for communication 			- Easy to understand, easy to update
			- Complex to understand, difficult to update


Ease of Use
			- Client need information about everything 	 	- Client needs almost no knowledge about 
			before beginning of interaction  					API to communicate

			- Testing is difficult because of multiple      - Testing is very easy
			layers of dependency and architecture

			- Less coding required especially because of    - Simple architecture, Easy to understand
			already availble standards 						  makes faster development.


When to use?
		 
		  - Application that requires high security         - Application that required faster response
		  	 - E-Commerce										, light weight payloads
		  	 - Financial Applications								- Social Network applications
		  	 														- Online Photo editor


		- SOAP is preferred for financial application        - REST is preferred for developing public
		because of its security and built in ACID compliance      APIS.




#### How to design URI/URL

* Internet is changing rapidly with huge traffic and load on it.
* In this situation, API is the method that is capable to provide service with desired output and can sustain huge load.


As a developer, It is our duty:
	- API is capable to provide service to anything, anywhere, anytime
	- APIs should be easy to understand
	- Authentication and Authorization to handle security concerns
	- Should be consistency by making a standard methodology which will save time for design so that we can focus on business logic.
	- Standardization and Reusability


* For example below:
	- www.data.com/country/np/state/gandaki/city/pkr

	- www.data.com/12345/city/13344

	- Here both apis do the same thing
	- but 1st one is the better choice as it gives more information.


#### REST communication Flow:

* REST uses:
	- HTTP
	- ROA
	- Client Server
	- Stateless


* 2 things in REST communication flow

	- Request
		- URI
		- HTTP Method
		- Header
		- Request Body

	- Response
		- Response body
		- HTTP Response code


* What is RFC Document?
	- RFC stands for Request For Comment
	- A document published by technology community, sometime individual too.

* According to RFC-3986,
	- Generic URI sequence: 
		- scheme: [//authority]path[?query][#fragment]

	- It is sequence of five elements in order
	- Some elements are mandatory, some are optional

1. scheme:
	- It is mandatory
	- case insensitive
	- It always starts with letter and followed by combination of letters, digits and special character such as (+), (.), (-).
	- Schemes should be registered with IANA (Internet Assigned Numbers Authority)
	- Eg: http, https, ftp, mailto, file, data
	- REST uses http and https


> After scheme we use (:), two forward slash (//)

2. authority
	- Optional element
	- It is combination of 3 tings
	 	- User info: username & password
	 	- Host
	 	- port
	 	- eg: username:password@host:port

 	- In our case, ipaddress:port
 	- eg: 127.0.0.1:8080

3. path
	- path of resources/ address of resource
	- It should be hierarchical sequence and resemble our file system
	- we use (/) to represents hierarchical relationship

4. query
	- Optional element
	- It helps to fine tune our result
	- It adds additional value to our URI, that can be used for many various purpose.
	- It contains list of parameters
	- parameters could be mandatory or optional, starts with ? and joins with &
	- We use query parameters for:
		1. To filter collection or stores
		2. pagination purpose

5. fragment
	- It starts with hash sign (#)
	- It is very useful in modern web mostly for UI where single page applications is in vague
	- For REST there is no use of this

> We cannot use following special characters (:, ?, #, [], @) in URI


* Some rules to design URI
1. Use of "/" separator is to represent hierarchical relationship
2. Trailing forward slash shouldn't be used. (i.e. on the last of url => https://abc.com/123/) 	

3. Use hyphen(-) to increase readability and use underscore (_) as least as possible.

4. Use lowercase instead of upper case as dual behavior causes confusion and doesn't add any value to URI.

5. Don't include file extension in URI as representation can change based on consumer and using file extension becomes tightly coupled with URI. Instead we can use content-type and accept in the header.

### Resources Modeling

* In REST there are 4 distinct resource archetypes
	1. Document
	2. Collection
	3. Store
	4. Controller

	- It helps us to understand behavior and structure of resources
	- For simplicity and clean design, every resource aligns with only 1 archetype
	- If resources are closely related to each other, we create separate API for that instead of merging and creating hybrid design


1. Document
	- It is a singular entity
	- Resource's representation includes fields and values. Values can be any object, links or anything
	- Consider we want to retrieve  information about particular user, then the url become:
	- https://data.com/users/1

	- and the response can be:
	`{
		"firstname": "Nishal"
		"lastname": "Gurung"
		"address": "Pokhara"
	}`

	- Similarly if we want to retrieve only address from the individual resource, url become:
	- https://data.com/users/1/address


2. Collection
	- It is directory, or collection of object
	- client can add, delete or modify existing resource, decisions for creation, deletion will be from server.
	- Eg: http://data.com/users , here users is a resource of collection type

3. Store
	- It is also a directory - client managed directory
	- Client can put anything or take it back or delete it
	- Client doesn't create new resource.
		- Eg: All user have videos resource, client can't delete videos folder
		- https://data.com/users/1/videos

	- URI will be chosen by client when first time they add resource
	- Eg: Add a video, system generated unique id of video 1.
	- https://www.data.con/users/1/videos/1

> Collection is server managed whereas store is client managed.

4. Controller
	- It is executable function, takes some input and returns output.
	- Eg: we need to calculate something or want send some message.

	- Actions can not be mapped with our standard CRUD methods: POST, PUT, DELETE, GET
	- URI to these kinds of resource is very simple - no child, controller name appears at very last like:
		- https://www.data.com/users/1/calculate-age


- We must align our resource with only one of these, before designing our URI

* To make communication clearer, client or consumer should know about our resources, it's structure and behavior by just looking at URI

- Two things can help to achieve this goal:
	1. Forward slash that represents relationship between resources.
	2. Follow some naming convention as :

	Resource Types 					Naming convention 									Example
	Document							Singular Noun								/users/**user-1**
	Collection							Plural noun or plural phrase				/**users**
	store 								Plural noun or plural phrase				/users/user-1/**videos**
	Controller 							verb or verb phrase							/users.users-1/**calculateage**


Other rules are:

* Variable segments should be using identity-based values
	- There are 2 types of segments
		1. static
			- Static segments means segments that don't change and it is selected by API designers.
		2. dynamic
			- which change based on resource we are addressing to

		- For example: http://www.data.com/users/u-12/videos/v-13
		- Static segments: scheme, host, port details, users and videos
		- dynamic segments: user id and video id
		- every dynamic segment should be replaced with identity based values and should use alphanumeric values.

	- Do not use CRUD function name as in URI
		- **wrong** eg: /users/deleteuser?id=123
		- it is good on the basis of readability but the correct way is to use HTTP method to indicate crud function.


### HTTP Methods

 - We use HTTP methods to understand client's intention behind calling the API.
 - HTTP methods are : GET, POST, PUT, DELETE, HEAD, OPTIONS, PATCH
 - also can be referred as HTTP verbs.
 - these methods are basically category of operations on resources, so not all resource have to support all methods

 - Categorizing HTTP methods as:
 	1. SAFE Methods:
 		- consider safe if request doesn't alter the state of the server.
 		- Read only operations consider to be safe.
 		- Client doesn't request any change, but just ask for information so, request shouldn't introduce any side effect or load on server, also it should not trigger any external calls.
 		- There is no any restriction imposed by server for get method for creation of load.
 		- Developers shouldn't allow to do any operation that is not safe with SAFE methods.
 		- Eg: GET and HEAD method is considered as SAFE.
 		- Developers need to make sure GET and HEAD methods
 			- Don't alter a state of server
 			- Introduced any side effect
 			- Don't call external systems.

	2. Idempotent methods
		- idempotent http methods are the methods, that doesn't matter how many times you call with identical request, it will generate same results.
		- Use of these methods will leave server in same state except keeping logging and other statistics.
		- PUT and DELETE we can consider idempotent
		- All SAFE methods are idempotent, but all idempotent methods are not Safe.
		- Idempotent means an operation in mathematics or in programming, that no matter how many times you execute on same resource, you will get same result. (Eg: adding 0 to a number, multiplication by 1)

	3. Cacheable methods
		- Response of the request can be cacheable
		- Some methods such as GET and HEAD are cacheable, and some response codes are cacheable.
		- Ideally, a request that has both cacheable request and cacheable response code is eligible for caching


#### GET Method
	- It request a representation of resource
	- Client can request with GET HTTP method to get data and response will contain data of resource.
	- Data could be of resource or it could be preprocessed data
	- Request body is not part of GET request
	- To make request more efficient, these methods works with other features of HTTP.
	- GET request retrieves data but we can attach header properties as below to make GET request conditional
		- If-Modified-since
		- If-Unmodified-Since
		- If-Match
		- If-None-Match
		- If-Range
	- GET method is SAFE, IDEMPOTENT, CACHEABLE


#### POST Method
	- To submit an entity, that can cause change in resource state or it can affect server.
	- POST is a request to server for accepting entity in the request body as resource or sub-resource.
	- use to create new resource
	- Eg: Adding a new user via signup
	- Response returns 201 CREATED, or 200 OK
	- Response of this method is not cacheable, but we can make it by using appropriate Cache-Control or Expires header fields, or redirect.
	- POST method is sometime CACHEABLE, Not Idempotent, Not SAFE


#### PUT Method
	- PUT request is for server to replace resource if exist or create a new one if not found with request body.
	- If request URI refers to existing resource than replace it and if URI doesn't point to any resource than create new one.
	- In case of updating user information, we can use PUT
	- For Eg:
		- PUT -> http://www.data.com/users/1
		`{
			"firstname": "Nishal",
			"lastname": "Gurung"
		}`

		- It will update specific user.

		- PUT -> http://www.data.com/users
		`{
			"firstname": "Nishal",
			"lastname": "Gurung"
		}`
		- It will create new user with above detail

	- If new resource has been created then we must inform client with 201 http response code.
	- PUT is Idempotent, not Cacheable, not SAFE
	- PUT tries to identified resource with request but POST doesn't
	- Multiple request with PUT doesn't affect server but does POST.
	- Same request multiple time with PUT will update data and updated data is also same so it won't make any difference but with POST it will create new resrouce every time we fire it.


#### DELETE Method
	- Request to server for deleting resource identified by URI.
	- Possible success response codes
		- 200 - OK, in case of successful deletion of request and response have response body
		- 202 - Accepted, if request accepted but not executed yet.
		- 204 - No Content, if request is successful but nothing in respond body

	- DELETE is not CACHEABLE, not SAFE, is IDEMPOTENT
	- Making DELETE idempotent is very important.

#### HEAD
	- Requests a header without body, it is same as GET but without response body
	- It will return only header same as GET request.
	- It is use for the performance as the return header can give you information about the response for eg: size
	- HEAD is CACHEABLE, IDEMPOTENT, SAFE


#### OPTION
	- A method to request communication options for the resource identified by URI.
	- OPTIONS doesn't invoke any action or an operation on resource, but it provides necessary information for communication with that resource.
	- Response of this method doesn't content response body, but we can add body to make it more informative.
	- Some server doesn't allow body with OPTION method and discard it.
	- Eg: http://www.data.com/* will return information about server whereas http://www.data.com/users/1 return information about resource
	- OPTION is not cacheable, is idempotent and is safe

#### PATCH
	- A method for partial modification to a resource and it represents modification of existing resource.
	- It is same as update in our CRUD operation
	- PATCH is not idempotent because it won't generate same outcome everytime.
		- For eg: For auto increment fields,
			- PUT will overridden the filed whereas PATCH will change something everytime and cause side effect.
	- PUT replaces entire representation whereas PATCH updates specific part of resource.
	- PATCH is not cacheable, not idempotent, not SAFE


* Guidelines for usage HTTP method:
- REST API shouldn't compromise design by misusing methods
	- Limited method vocabulary for REST communication
	- Wrong usage of methods can lead to client- side confusion.
	- It can compromise protocol transparency
	- Select correct method as :
		- GET - to retrieve representation of resource
		- PUT - to update existing gresource or insert new resource
		- POST - to create new resoruce and to execute controllers
		- DELETE - to delete resource


### HTTP Headers
	- A segment in request that provides an extra space to client and server
	- This extra space can be used to put additional information with request
	- Information could be important for client and server as well as proxies and gateways.
	- Header is basically a key value pair. (key => name of property , value => value of property)


* Categories of header property:
1. Authentication property
2. Content property
3. Conditional property
4. Caching related property

1. Authentication property
	- Security in communication is fundamental requirement.
	- 4 fields:
		1. Authorization
			- This field contains user credential for authorization
				` Authorization : <type> <credential> `
			- <type> : type(scheme) of authentication eg: Basic, Bearer
			- Different type varies in strength of encoding
			- In case of wrong credential, server will throw 401 Unauthorized Response

		2. WWW-Authenticate
			- Come with response from server.
			- It defines authentication methods or schemes required or  should be used in order to gain access to the resource.
			- It provides information to client about which authentication scheme to use.
				` WWW-Authenticated: <type> realm = <realm> `
			- WWW-Authenticate: Basic
			- WWW-Authenticate: Basic realm="Dev site", charset="UTF-8"
			- Realm is optional
			- Realm as a space or area or group of web resource having same credentials
			- If no realm specified them host name can be used here.
			- Need configuration of server for this header property to get in response.

		3. Proxy-Authorization
			- Proxy servers must be used proxy servers for various purpose such as activity logging, caching, security, saving bandwidth etc.
			- Same as Authorization
		
		4. Proxy-Authenticate
			- same as WWW-Authenticate

2. Content Properties
	- In content body, specified data is solely related to our business logic.
	- For ease of communication, there is a need for extra information about data such as media type of resource.

	* Content-Type
		- Represents media type of resource - can be used for both request and resource
		- It is possible that server could accept and provide multiple content format.
		- Client should specify resource content type in header while request and server also should specify content type of coming data as a response.

			`Content-Type: <mime-type> ; < encoding-type>`

			- MIME - Multipurpose Internet Mail Extensions
			- It is not one type of extension but is a group of extensions
			- It is a combination of two values type and sub type which represents media type : eg Application/json, Application/xml, Text/Html, Text/Plain, Application/pdf, Audio/mpeg
			- MIME type can also include encoding type as 
			`Content-Type: text/html; charset=UTF-8
			 Content-Type: multipart/form-data; boundary=something `

			 - multipart means a file will be transferred in multiple data chunks over HTTP

	 * Content-Length
	 	- Represents size of content body in Bytes.
	 	- With it client gets information about size of response body.
	 	- Before client starts download, if file is too big client can make decisions based on that.
	 	` Content-Length: <length> `

 	* Content-Encoding
 		- To make communication faster, data compression is one of the best ways to reduce size of payloads.
 		- Eg: retreiving image as JPEG - huge in size, But instead of sending image as it is, compressed version can be sent, and client can decode to get it in desired format.
 		- But server needs to tell client, how to decode or which decode mechanism to use for that
 		- This field can hold information about compress algorithm.
 		- When client get this field in response, that means response body needs decoding to get desired form of media type:
 		- ` Content-Encoding: gzip
 			Content-Encoding: compress
 			Content-Encoding: gzip, compress
 		`

	* Accept-Encoding
		- Sometimes, client doesn't have ability to apply specific algorithm specified in content-encoding
		- To resolve this issue, we have another property called Accept-Encoding
		- In request, client can put desired algorithm in Accept-Encoding, server will respond in that encoding mechanism, if possible.
		- `Accept-Encoding: gzip `

	* Content-Location
		- Represents an alternate location for the returned data.
		- Value of this property is URL that returns data.
			`Content-Location: /my-first-blog`

	* Accept
		- This property is used for the content negotiation
		- Content negotiation is a concept that helps cleint to ask server a specific format of content in repsonse
		- Accept property defines MIME type, which is type and subtype combination
		- It is same as Content-Type properties 
		- Content-Type can be used in request as well as response whereas Accept can be used in Request only.

	* Accept-Charset
		- To display content properly, proper charset is required.
		- Client also can ask for specific charset to srever
		`Accept-Charset: utf-8`


3. Conditional Properties
	- To make our request conditional

	* Combination of ETag and If-match, If-None-Match

	* Etag:
		- Response header property - Client gets it from server in the response.
		- Represents version of a resource.
			`ETag: W/"<etag_value>"
			 ETag: <etag_value>"
			`
		- Client gets it from server while retrieving resource, client can store it.
		- ETag is unique value, if resource changes server needs to generate new ETag value for that version of resource.
		- Next time, when Client request same resource for latest data, with that request we can pass this value in other properties such as If-Match, or If-None-Match.
		- Based on comparision between value provided by client and current ETag value of resource at server side, server responds or take actions.
		* If-Match :
		- Eg: Let's say we put that value in If-Match field, then server will act if ETag matches with current value
			- GET & HEAD - server will respond if ETag matches.
			- PUT - server will update data if ETag value matches.
			- ETag with PUT is also very useful, toi prevent simultaneous update
			- Eg: Two clients are trying to edit user information.
				- If-match with PUT and if ETag doesn't matched then server will return 412 precondition failed response.
				- That means resource has been modified by some other client after client retrieve it, so we need to fetch latest copy again and then try to update
		* If-None-Match:
			- If no other resource matches this ETag then server will take action or respond.
			- GET & HEAD - server will respond with 304 NOT Modified, if condition fails.
			- That means that resource hasn't been changed after last retrieval, so client already have latest resource.
			- No need to send data again, so response will only have header not body.
			- By not sending body we are saving network bandwidth
			- Flaw in this approact - It save bandwidth, but it also increase load at server side.
				- Every time client sends ETag with request, server needs to compare ETag with latest value.
				- Server needs calculate latest ETag for resource.
				- To create ETag, server needs to retrieve resource and check for last modification, which is extra work at server side.

			- Solution for above flaw - server creates ETag when someone updates resource and server stores that ETag for future use, so server don't need to create it every time request comes.
			- Value of ETag is version number or combination of hases of different values
			- Comma separated values for multiple ETags:
				`If-None-Match: W/16736acd343223232334a, 134343434acb2343434c3434dac`
			- To address all resouces then we can use * 
				`If-None-Match: *`

		* Last-Modified:
			- This is a response property - client gets it from server as a response.
			- It is same as ETag but instead of giving hash code value, it returns time stamp
			- Logically time stamp is less accurate then hash code.
			 `Last-Modified: <day-name>, <day> <month> <year> <hour>:<minute>:<second>GMT` 
		    - Value here represents time and date at which the resource was modified.
		    - Can be used in combination with If-Modified-Since and If-Unmodified-Since

	    * If-Modified-Since
	    	- Makes request conditional with condition that server will send value with 200 response code only if resource is modified after last-modified time.
	    	- Otherwise it will return 304 Not Modified with no response body, we use this only when cache is out of date

    	* If-Unmodified-Since
    		- Makes server to send resource only if it is not modified after last date.
    		- Can be used with POST and PUT, and in that case if condition fials then it will return 412 Pre-Conditions failed.

    	> Etag combination take precedence over Last-Modified, because of accuracy. Server will condition Etag only when both combination are there.


4. Caching properties
	- Caching is important for efficient communication

	* Age
		- Defines time for how long object or data has been in a proxy cache
		- Value of this property is in Seconds
		- Calculated based on current time and time of fetching
		- If age is 0, that means resource has just been fetched from main server.
		- Client can ask for latest data if data is seating there in Cache for too long
		- Now here, question is who can decide time for getting old means after what time, we should ask for fresh data

	* Cache-Control
		- Defines instructions for caching
		- Those instuctions can be used to control caching mechanism and both client and server can use this
		- Possible values are:

		* Cache-Control: max-age=30
			- Resource data is not fresh if age is more than 30 sec.
			- If age is more than 30 then cache will again request for fresh data

		* Cache-Control: min-fresh=15
			- Client needs a resource which is at least fresh for 15 seconds

		* Cache-Control: public
			- It will make sure response will be stored by any caching, event if resource is non-cacheable

		* Cache-Control: private
			- It will make sure response will be cached by browser cache only

		* Cache-Control: only-if-cached
			- To save network bandwidth
			- Server will respond if and only if resource is stored at cachedm it won't use network at all

		* Cache-Control: no-cache
			- If caching not required at all

		Also there are many others


* Guidelines
	- Should always use Content-Type, Content-Length because client and intermediaries use this data a lot.
	- Last-Modified or ETag mus be used to prevent conflict at server side
	- Stores resource type must use PUT with conditionals to save simultaneous update.
	- Store archetype uses put method for insert as well as update. There is no way to know client's intention behind calling api so must use Conditionals
	- Content-Location must be used to show location of the created resource. 


### Status Code
