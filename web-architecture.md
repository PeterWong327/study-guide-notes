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


  - Why do we need a DNS?
    - A DNS is like a phonebook of website addresses that matches domain names to the IP address (made up of numbers) of the website. When a user searches for a URL, the website domain name is sent to the DNS to ultimately retrieve the IP address of the website. The browser then sends a request to the website using the IP address.
