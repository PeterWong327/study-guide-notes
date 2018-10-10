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
