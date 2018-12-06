## HTTP Essential
		Morten Rand Hendriksen Lynda COurse
		50 min

Web Content Interaction Request and Responses between client and server are guided by the HTTP protocol.

---
### HTTP: Hypertext Transfer Protocol
#### What is HTTP?
Hypertext Transfer Protocol 
Protocol - sys of rules allowing comm of info betn dif entities
Hypertext - outdated word - text display containing hyperlink to other texts. 

Set of rules server browsers used to send hypertext front and back. 

Plain Language and Human readable 
- GET 
- POST 
- PUT 
- DELETE 
- CONNECT 
- HEAD 

Stateless protocol - no req is connected to another req. No previous req memory. 

Sesions - Stored state shared betn browser and server. Stateles but sessionless.

HTTP Headers 
- What type of client sent the req. 
- Server config 
- Time and Date of the res.
- Duration of data storage 
- Data format 
- Cookies used to track sessions. 

HTTP works based on request/response pairs. 

#### HTTP, HTTP/2 and HTTPS
[HTTP/2](https://kinsta.com/learn/what-is-http2/)
HTTP Protocol is constatnly evolving 
HTTP/1.1 - 
HTTP/2   - 70-80%, faster and more secure, compression algorithm, encrypted connection through HTTPS 

Ideal 
every HTTP > HTTPS using HTTP/2 protocol 

Real
most HTTP > HTTPS over HTTP/2 > Unecrypted HTTP/1.1 

#### HTTP Terminology 
Browser - app used to navigate HTML doc 
User Agent - typically browser (midlleware / google services).
TCP - transmission COntrol Protocol used by www, email, ftp
IP - Internet Protocol used to actually transfer data between computers over network. Every device connected to interne has an IP address. 
URL -Universal Resource Locator - address pointing to 
resource on web. 
DNS - Domain Name Services - catalogs all domain name URLs and points them to the IP addresses of servers. 
Resource - The file or files available on server when following a URL. 
Server- Computer on internet running some form of data storage and sharing application. most commonly a web server application. 
Proxy - Spftware or hardware service acting as a middle person between clients and servers. Often used when IP address of server needs to be hidden
Request-Response Pair
header - Req and res use HTTP headers to pass info back and forth
HTTP Request Methods/Verb - explaining what action the sender want to perform on the resource. 
Status Response Code - 100-500 range error code, what type of response the server sent back to client. 
Cache - Method for sharing data on the client or the server to speed up performance. 
Stateless - no link between to requests
Cookie - String of data passed back and forth between the client and server to crete a stateful session.
Session - Client and Servers can share info about states by passing information bak and forth, creating a session. 

#### The HTTP Flow 
Browser opens a TCP connection to the server ensuring data sent back and forh oover the network and the data uniformity. 
With HTTPS TLS certificates exchanged to ensure only the server and computer and encrypt and decrypt the transmitted data preventing data hacking. 
Browser can sent HTTP Requests. 
Server performs req action and sent required action. 
After transaction TCP connection is finished. 
HTTP/2 Multipleing + Server Push - Multiple transaction over same TCP onnection, and push data to browser. 

#### Tools to see HTTP in action 
https://goo.gl/yeZFsL
Browser Tools 
POSTMAN
insomnia
VS CODE REST client 
Load the site and boot up the developer tools 
goto network 
Reload 
Explore 

---
### Request and Responses
#### The request/response pair 
User Agent Req Res pair for the server 

#### Anatomy of a URL 
URL: Universal Resouce locator 
HUman readable address describing where on the web a particular resource located. 
https://linkedin.com/learning/blahblah
Protocol Declaration - [https://]
URN Uniform Resource name - [linkedin.com/learning/blahblah] 
Host - [linkedin.com] domain
Connection Port(usually hidden) - :443 
for HTTP default port is 80 and forHTTPS its 443. 
Resource Path - learning/blahblah
the server and bowser automatically looks for the file with index.html or default.htm, index.php or similar if not provided a certain file name. 
Optional URL query - eg_ ?u=1234567 

#### HTTP Methods
GET 
POST 
DELETE 
PUT 
PATCH 
HEAD 
OPTIONS 
TRACE 

GET 
Get the specified resource if available. 
	success -> 200 OK 
	failure -> 404 Not found 
			   405 Not allowed 
			   403 Forbidden 

POST 
Create a new resouce and add it to a collection 
success ->	201 Created
failure ->  401 Unaauthorized 
			409 Conflict 
			404 Not found 

PUT 
Update an existing singleton resource based on ID.
success	->	200 OK 
failure	->	204 No content 
			404 Not found 
			405 Method not allowed 

PATCH 
Modify an existing singleton resource based on ID.
success	->	200 OK 
failure ->  204 no content 
			404 Not found 
			405 Method not allowed 

DELETE 
Delete a singleton resource based on ID. 
success	->	200 OK 
failure	->	401 Unauthorised
			404 Not found 
			405 Method not allowed 

HEAD 
Get just the response headers from he resource 
success 	-> 200 OK 
failure 	-> 404 not found 

OPTIONS 
Get the options available from this resource 
success 	->	200 OK 

TRACE 
Create aloopback of req message 
success 	-> 200 OK

#### HTTP Status messages 
HTTP Status Code 
1xx Infomation ( rarely encounered, server status, 102- processing wait )

2xx Success ( 200-OK, 201-Created, 204-No content )

3xx Redirection ( client is provided with new URL, 301-moved permanently, 302/303 Found at this other URI, 307-Temporay redirect, 308-Permanent redirect )

4xx Client Error (400-Bad request, 401-Unauthorized, 403-Forbidden, 404-Not found, 405-Method not allowed )

5xx Server Error ( 500-Internal server error, 502-Bad gateway, 503-Service Unavailable )

---
### HTTP Headers
#### What are HTTP headers
Host: mor10.com 
User-Agent: mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:57.0)
Gecko/20100101 Firefox/57.0 
Accept: text/html, application/xhtml+xml,application/xml;q=0.9*/*;q=0.8
Accept-Language: en-US,en,q=0.5
Accept-Encoding: gzip, deflate, br 
Connection: keep-alive 
Upgrade-Insecure-Requests: 1
Cache-control:max-age=0

Base64 encoded - Username and password 
Caching files will save alot of bandwidth

#### How to see HTTP Headers 
REST client 
Representational State Transfer - set of rules how data is transferred and managed between client and server. 
POSTMAN 
VS code Rest Client extension

POSTMAN HEAD 
website url 
check headers 

#### Anatomy of a request header 
Browser communoication with metadata for cystal clear conveying. 
GET
https://mor10.com/gutenberg-and-the-future-of-wordpress/

Host: mor10.com
User-Agent: Mozilla/5.0 (Windows NT 10.0 ...)
Accept: text/html, application/xhtml+xml, application/xml 
Acept-Language: n-US,en;q=0.5 
Accept-Encoding: gzip, deflate, br 
Referer: http://mor10.com/ 
Connection: keep-alive
Upgrade-Insecure-Requests:1
Cache-Control: max-age=0

#### Anatomy of a response header 
HTTP/2.0 200 OK 

server: ngix
date: Thu, 25 Jan 2018 23:43:39 GMT 
content-type: text/html; charset=UTF-8
link: <https://mor10.com/wp-json>; rel="https://api...."
host-reader: 192fdg2df21d1d1dgf2d8cd
x-proxy-cache: MISS 
x-Firefox-Spdy: h2

#### Cookies
Cookies are used to pass states between clients and server over the stateless HTTP Protocol affectively setting sessionss between client and server. 
Authentication and other purposes. 
Keeping people logged in to land off where they screenLeft
mostly used by advertisers. 
European Union have laws to intimate users about the use of the cookies.

#### Caching
Both servers and client can tell the other party to store Rarely updated content and this can dramatically increase the performance. clearMarksCached files can't be overwritten from the server. 
So time limit is required. 

Cache Request Directives
Cache-Control:
	max-age=<seconds>
	max-state[=<seconds>]
	min-fresh=<seonds>
	no-cache 
	no-store 
	no-transform 
	only-if-cached 

Cache Response Directives
Cache-Control 
	must-revalidate
	no-cache 
	no-store 
	no-transform 
	public 
	private 
	proxy-revalidate 
	max-age=<seconds>
	s-maxage=<seconds>

max-age: 31536000
Store this file for one year and use it instead of requesting to downlpoad a fresh copy during that time. 

no-cache, max-age: 31536000
Store this file for one year, but before you use it, check if a new version is available. 

no-store 
Do not cache this file 

Cache Busting 
Each file with uniquename thus anytime uploading new version of the file, actually uploading a new file. 


#### Footnote
[MDN cache-control](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Cache-Control)
[Google Developers web](https://developers.google.com/web/)
