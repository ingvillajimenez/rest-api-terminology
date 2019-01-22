# REST API Terminology 

Fork and clone this repository. Then, push to github with all bad answers deleted and only the correct answers showing.

**1. What does it mean REST?**

REST, or REpresentational State Transfer, is an architectural style for providing standards between computer systems on the web, making it easier for systems to communicate with each other.

**2. Who coined the REST term?**

Roy Fielding defined REST in his 2000 PhD dissertation "Architectural Styles and the Design of Network-based Software Architectures" at UC Irvine.

**3. In which protocol REST is based?**

Fielding's dissertation explained the REST principles that were known as the "HTTP object model" beginning in 1994, and were used in designing the HTTP 1.1 and Uniform Resource Identifiers (URI) standards.

**4. What are the main building blocks of a REST Architecture?**

Resource
Representation
Messages
Hypermedia

**5. Identifying a resource is easy; you know how to access it and you even know how to request for a specific format. Since REST is using HTTP protocol as a standing point, there are some actions related to resources: CRUD operations.**

Complete the below table:+


|HTTP Verb|Proposed Action|
|---------|---------------|
|GET      |READ           |
|POST     |CREATE         |
|PUT      |UPDATE         |
|DELETE   |DELETE         |

**6. Status Code**

Another interesting standard that REST can benefit from when based on HTTP is the usage of HTTP status codes.

+ What’s is a status code?

Responses from the server contain status codes to alert the client to information about the success of the operation. HTTP defines forty standard status codes that can be used to convey the results of a client’s request. The status codes are divided into the five categories

+ Explain with your own words, the meaning of next codes:

|Status Code|Description|
|-----------|-----------|
|404(NOT FOUND)|The resource could not be found at this time. It is possible it was deleted, or does not exist yet.
|200(OK)    |This is the standard response for successful HTTP requests.|
|500(INTERNAL SERVER ERROR)|The generic answer for an unexpected failure if there is no more specific information available.|

**7. Status Code are grouped in five sets.**

Write what are their meaning.

|Group|Description|
|-----|-----------|
|1XX|Informational|Communicates transfer protocol-level information.
|2XX|Success|Indicates that the client’s request was accepted successfully.
|3XX|Redirection|Indicates that the client must take some additional action in order to complete their request.
|4XX|Client Error|This category of error status codes points the finger at clients.
|5XX|Server Error|The server takes responsibility for these error status codes.

**8. HTTP Status Codes and Their Related Interpretation**

There are the most common status codes in HTTP responses. Please, fill with the required description.

|Status Code|Meaning|
|-----------|-------|
|200|(OK)|This is the standard response for successful HTTP requests.
|201|(CREATED)|This is the standard response for an HTTP request that resulted in an item being successfully created.
|204|(NO CONTENT)|This is the standard response for successful HTTP requests, where nothing is being returned in the response body 			
|301|(Moved Permanently)|The 301 status code indicates that the REST API’s resource model has been significantly redesigned and a new permanent URI has been assigned to the client’s requested resource
|400|(BAD REQUEST)|The request cannot be processed because of bad request syntax, excessive size, or another client error.
|401|(Unauthorized)|A 401 error response indicates that the client tried to operate on a protected resource without providing the proper authorization. It may have provided the wrong credentials or none at all
|403|(FORBIDDEN)|The client does not have permission to access this resource.
|404|(NOT FOUND)|The resource could not be found at this time. It is possible it was deleted, or does not exist yet.
|405(Method Not Allowed)|The API responds with a 405 error to indicate that the client tried to use an HTTP method that the resource does not allow 
|500|(INTERNAL SERVER ERROR)|The generic answer for an unexpected failure if there is no more specific information available.
 
###### [To see the full list of HTTP status codes and their meaning, please refer to the RFC of HTTP 1.1](http://tools.ietf.org/html/rfc7231#section-6)

**9. How are called the points of contact between all client apps and the API?**

Endpoints

**10. The following is a good example or bad example of a named access point? And why?**

_meant to list the books in a bookstore_

+ `GET /books/action1`

bad example of a named access point. A path like /books/action1 is not clear in what it points to, even if you’ve never seen this specific path before, because it is not hierarchical and neither descriptive.

**11. Uniform Interface**



To solve this problem, you can apply the REST style to the endpoints, and thanks to HTTP, you also have verbs to indicate actions.

|Old Style|REST Style|
|---------|----------|
|`/getAllBooks`            |  GET /books          
|`/submitNewBook`          |  POST /books          
|`/updateAuthor`           |  PUT /authors/:id  
|`/getBooksAuthors`        |  GET /books/:id/authors
|`/getNumberOfBooksOnStock`|  GET /books
|`/addNewImageToBook`      |  POST /books/:id/cover
|`/getBooksImages`         |  GET /books/:id/cover
|`/addCoverImage`          |  POST /books/:id/cover
|`/listBookCovers`         |  GET  /books/:id/

:id means 'params' object

**12. What JSON does it mean?**

JSON (JavaScript Object Notation) is a lightweight data-interchange format. It is easy for humans to read and write. It is easy for machines to parse and generate

**13. Anatomy of a `REQUEST`**

Make a `curl` request to _GitHub API_

```sh
$ curl https://api.github.com/
```
A way to request information from an API endponint

According to the responded request, answer what does it mean the next parts from the handler:

+ _`Content-Type`_. The Media type of the body of the request (used with POST and PUT requests).
+ _`Status`_. CGI header field specifying the status of the HTTP response. Normal HTTP responses use a separate "Status-Line" instead, defined by RFC 723
+ _`Date`_. The date and time that the message was originated (in "HTTP-date" format as defined by RFC 7231 Date/Time Formats).
+ _`Content-Length`_. The length of the request body in octets (8-bit bytes).


###### If response is not showing those parts, ask to google how to print them in console.

```sh
# curl https://api.github.com/ --head
```
