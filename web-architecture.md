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
