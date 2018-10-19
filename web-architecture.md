# Web Architecture Notes

### REST
 REST stands for Representational State Transfer

 Set of design principles for making network communication more scalable and flexible.

 - What are the three primary Fielding constraints? (Bonus if you can say who Fielding is!)
   1. **Client-server**, where the server has resources that the client wants interact with (Browsing internet)
   2. **Stateless**: client/servers do not keep track of each other's state. Server does not keep record of past requests.
   3. **Uniform interface**: ensures that there is a common language between servers and clients. 4 sub- constraints.


 - What sub-constraints make up a Uniform Interface
   - identification of resources
   - manipulation of resources through representations
   - self-descriptive messages: contains all the information that the recipient needs to understand it
   - hypermedia: data send from the server to the client that contains information about what requests the client can make next.


 - Walk through an arbitrary example of a RESTful request/response cycle, and describe what makes it RESTful
  - When a user types a URL in the browser and presses enter, the browser sends a HTTP GET request to the server. The server would send back a response with information on how to interpret the message body, so that the client has everything it needs in the single message. This is RESTful because the uniform interface constraint ensure that there is a common language between servers and clients.


 -  What happens when you type in www.google.com and hit enter?
  - Browser checks the 4 caches for a Domain Name System (DNS) record to find corresponding IP address of URL:   
      - **browser cache** for a repository of DNS records for websites previously visited.
      - **OS cache**, browser checks the computer OS
      - **router cache** if not found in computer
      - **ISP cache**, checks the ISP's own DNS server
  - If the requested URL is not in the cache, a DNS query is initiated to find the IP address of the server that hosts the URL.
  - The browser initiates a TCP (type of internet protocol) connection with the server.
  - The browser sends an HTTP request (GET, POST, etc) to the web server.
  - The server handles the request and sends back a response (JSON, XML, HTML)
  - The browser displays the HTML content


- How does DNS work?
  Refer to "Why do we need a DNS".

- Why do we need a DNS?
    - A DNS is like a phonebook of website addresses that matches domain names to the IP address (made up of numbers) of the website. When a user searches for a URL, the website domain name is sent to the DNS to ultimately retrieve the IP address of the website. The browser then sends a request to the website using the IP address.

- Explain TCP, and why it is a necessary protocol
  - (Transmission Control Protocol) It manages the sending and receiving of all your data as packets. When packets arrive, TCP checks and sends back acknowledgement of each packet received. If all packets required have been received, TCP sends signal for receipt of all packets in order to proceed with the loading of a webpage.


-  What is a datagram?
  - A datagram is a short message sent by UDP. It consists of a header and a data payload. The header contains the routing information from the origin to the destination. The payload is the data to be transported.

- What are the benefits of UDP (User Datagram Protocol) over TCP (Transmission Control Protocol)? What are the shortcomings?

  - Benefits: UDP contains smaller packet sizes (header: 8 bytes compared to 20 bytes), does not need to create a connection to send out data, and has more control over when data is sent out. So data can be sent faster.
  - Shortcomings: UDP has primitive error detection. It will not try to recover from a data corruption. It also does not compensate for lost packets. It does not guarantee packets arrive in order. It does not have congestion control, so a busy network will not stop UDP from sending packets still.


-  What are the common HTTP methods? When are they used, and what do they accomplish? (This is a big one)
  - GET: retrieves data from a web server by specifying parameters in the URL.
  - POST: sends data to the server, such as form data, which results in a response from the server.
  - PUT: requests the server to store the included entity-body at a location specified by the given URL.
  - DELETE: requests the server to delete a file at a location specified by the given URL.
  - CONNECT: establishes a network connection to a web server over HTTP.
  - OPTIONS: used to identify the HTTP methods and other options supported by a web server.
  - TRACE: used to echo the contents of an HTTP request back to the requester, for used in debugging at the development phase.


- **Top 10 HTTP Status Codes:**
  - 2xx = Success
    - 200 = OK
    - 201 = Created
    - 204 = No Content
  - 3xx = Redirection (additional action needed to complete the request)
    - 304 = Not Modified
  - 4xx = Client Error
    - 400 = Bad Request
    - 401 = Unauthorized
    - 403 = Forbidden
    - 404 = Not Found
    - 409 = Conflict
  - 5xx = Server Error
    - 500 = Internal Server Error (Generic server-side error)


- **Man in the Middle Attack**
  - When a middle party (Mallory) intercepts a message (with encryption key) sent from Alice to Bob. This allows the middle party to read or change the message before and after the message is encrypted.


- What is the difference between HTTP and HTTPS?
  - HTTP works by sending data that is not encrypted, which means that a third party can intercept and modify the data. HTTPS sends data through Certification Authorities by encrypting messages using symmetric cryptography (Caesar Cipher). The key used to encrypt the message is chosen by asymmetric cryptography.


-  What is the difference between localStorage and sessionStorage?
  - sessionStorage data is only available for the duration of the browser session, so the data would be deleted when the tab or window is closed (not persistent).
  - localStorage data is available in an ongoing basis, but can be cleared by the user.


- Why is it important that users cannot modify their cookies?
  - Users cannot modify their cookies because cookies are used for authentication purposes and persistence of user data. If the cookies are modified, then users may be able to access other users' data and functionality on a web application. This is to prevent sensitive data from being accessed by other users.



- When are cookies sent to the server?
  - Cookies for a page are sent from the browser to the server for every request to the same domain (original page request, ajax requests, images, stylesheets, scripts, and fonts).


- What is the danger of an XSS?
  - Cross-site Scripting (XSS) is dangerous because an attacker can manipulate a web application that utilizes user input to insert a string that will be used within a web page and treated as code by the victim's browser. Once this is done, an attacker can gain access to a user's cookies, location, webcam, microphone, and their files.


- What is a CSRF Attack?
  - a Cross-site Request Forgery Attack is when an attacker tricks a victim into performing actions on behalf of the attacker. This is done by having the victim click a link or load a page. Then the attacker sends a request through the victim's browser to a targeted web application, using information from the victim such as Cookies. The web application recognizes the information and thus would allow HTTP requests sent by the attacker on the victim's behalf.


- How can you prevent CSRF Vulnerabilities?
  - To prevent CSRF vulnerabilities, one way is to use a CSRF Token that is associated with a particular user and can be found as a hidden value in every state changing form. This token should be invalidated after a period of time and after the user logs out of an application. Another way is to use same-site Cookies, which can only be sent if the request is made from the same origin that is related to the Cookie being sent.


- What is an XMLHttpRequest?
  - An XMLHttpRequest is an object used to exchange data with a server behind the scenes. This makes it possible to update parts of a web page without needing to reload the entire page.
  (Ex. var xhttp = new XMLHttpRequest() ).
  - AJAX (Asynchronous JavaScript And XML) uses the XMLHttpRequest object to communicate with servers (JSON, XML, HTML, and text files).


-  When are two pages considered to have the same origin?
  - Two pages are considered to have the same origin if the protocol, port, and host are the same for both pages ("**scheme/host/port** tuple")


- How might you allow cross-origin resource sharing?
  - Cross-origin resource sharing can be allowed through the CORS protocol, which consists of a set of headers that indicates whether a response can be shared cross-origin.


- What is CORS?
  - Cross-Origin Resource Sharing is a mechanism that uses additional HTTP headers to tell a browser to let a web application running at one origin have permission to access resources from a server at a different origin (domain).


-  What are the advantages and disadvantages of NoSQL databases vs. SQL databases?
  - A SQL database (Relational Databases, or RDBMS, eg. MySQL) ensures that only one change can be written to a data field at a time, so no conflicting transactions can be made (ex. ATM). It uses database locks to ensure consistency no matter which database server the data comes from. However, this can be a disadvantage when lots of requests for the same data occurs (web-scale attacks), slowing down a server. SQL databases are vertically scalable, meaning that they can handle an increase in data by increasing memory on a single server.
  - A NoSQL database (eg. MongoDB) can handle "big data" tasks, but it does not have a standard interface to handle complex tasks. NoSQL databases fit better for hierarchical data storage as they can store data in a key-value pair. NoSQL databases are horizontally scalable, meaning that an increase in traffic can be resolved by adding more servers to handle the load.
