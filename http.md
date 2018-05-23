#### HTTP

![](HTTP_and_layers.png)

A connection is controlled at the transport layer, and therefore fundamentally
out of scope for HTTP. Though HTTP doesn't require the underlying transport
protocol to be connection-based; only requiring it to be reliable, or not lose
messages (so at minimum presenting an error). Among the two most common
transport protocols on the Internet, TCP is reliable and UDP isn't. HTTP
subsequently relies on the TCP standard, which is connection-based, even though
a connection is not always required.

Here is a list of common features controllable with HTTP:

- Cache
      How documents are cached can be controlled by HTTP. The server can instruct
      proxies, and clients, what to cache and for how long. The client can instruct
      intermediate cache proxies to ignore the stored document.

- Relaxing the origin constraint
      To prevent snooping and other privacy invasions, Web browsers enforce strict
      separation between Web sites. Only pages from the same origin can access all the
      information of a Web page. Though such constraint is a burden to the server,
      HTTP headers can relax this strict separation server-side, allowing a document
      to become a patchwork of information sourced from different domains (there could
      even be security-related reasons to do so).

- Authentication
      Some pages may be protected so only specific users can access it. Basic
      authentication may be provided by HTTP, either using the WWW-Authenticate and
      similar headers, or by setting a specific session using HTTP cookies.

- Proxy and tunneling
      Servers and/or clients are often located on intranets and hide their true IP
      address to others. HTTP requests then go through proxies to cross this network
      barrier. Not all proxies are HTTP proxies. The SOCKS protocol, for example,
      operates at a lower level. Others, like ftp, can be handled by these proxies.

- Sessions
      Using HTTP cookies allows you to link requests with the state of the server.
      This creates sessions, despite basic HTTP being a state-less protocol. This is
      useful not only for e-commerce shopping baskets, but also for any site allowing
      user configuration of the output.

##### Requests

Requests consists of the following elements:

- An HTTP method, usually a verb like GET, POST or a noun like OPTIONS or HEAD
  that defines the operation the client wants to perform. Typically, a client
  wants to fetch a resource (using GET) or post the value of an HTML form (using
  POST), though more operations may be needed in other cases.
- The path of the resource to fetch; the URL of the resource stripped from
  elements that are obvious from the context, for example without the protocol
  (http://), the domain (here developer.mozilla.org), or the TCP port (here 80).
- The version of the HTTP protocol.
- Optional headers that convey additional information for the servers.
- Or a body, for some methods like POST, similar to those in responses, which
  contain the resource sent.

![](HTTP_Request.png)

##### Responses

Responses consist of the following elements:

- The version of the HTTP protocol they follow.
- A status code, indicating if the request has been successful, or not, and why.
- A status message, a non-authoritative short description of the status code.
- HTTP headers, like those for requests.
- Optionally, a body containing the fetched resource.

![](HTTP_Response.png)

##### Methods

HTTP defines a set of request methods to indicate the desired action to be
performed for a given resource. Although they can also be nouns, these request
methods are sometimes referred as HTTP verbs. Each of them implements a
different semantic, but some common features are shared by a group of them: e.g.
a request method can be safe, idempotent, or cacheable.

- **GET**
The GET method requests a representation of the specified resource. Requests
using GET should only retrieve data.

- **HEAD**
The HEAD method asks for a response identical to that of a GET request, but
without the response body.

- **POST**
The POST method is used to submit an entity to the specified resource, often
causing a change in state or side effects on the server.

- **PUT**
The PUT method replaces all current representations of the target resource with
the request payload.

- **DELETE**
The DELETE method deletes the specified resource.

- **CONNECT**
The CONNECT method establishes a tunnel to the server identified by the target
resource.

- **OPTIONS**
The OPTIONS method is used to describe the communication options for the target
resource.

- **TRACE**
The TRACE method performs a message loop-back test along the path to the target
resource.

- **PATCH**
The PATCH method is used to apply partial modifications to a resource.
