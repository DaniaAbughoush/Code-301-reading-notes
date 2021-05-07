 # what does REST stand for?
 Representational State Transfer
 # REST APIs are designed around a **~resources~**

 # what is an identifer of a resource? Give an example.
which are any kind of object, data, or service that can be accessed by the client.

A resource has an identifier, which is a URI that uniquely identifies that resource. For example, the URI for a particular customer order might be

 # what are the most common HTTP verbs?
 POST, GET, PUT, PATCH, and DELETE
 # what should the URIs be based on?
 A URI must represent an object, uniquely and permanently

One of the most fundamental philosophies behind a URI is that it represents a data object on the Internet. The URI must be unique so that it is a one-to-one match – one URI per one data objec
 # Give an example of a good URI.
 `https://adventure-works.com/orders`
 # what does it mean to have a ‘chatty’ web API? Is this a good or a bad thing?
 Another factor is that all web requests impose a load on the web server. The more requests, the bigger the load. Therefore, try to avoid "chatty" web APIs that expose a large number of small resources. Such an API may require a client application to send multiple requests to find all of the data that it requires.
 # what status code does a successful GET request return?
 A successful GET method typically returns HTTP status code 200 (OK
 # what status code does an unsuccessful GET request return?
 f the resource cannot be found, the method should return 404 (Not Found)
 # what status code does a successful POST request return?
 , it returns HTTP status code 201 (Created). The URI of the new resource is included in the Location header of the response. The response body contains a representation of the resource.
 # what status code does a successful DELETE request return?
 If the delete operation is successful, the web server should respond with HTTP status code 204, indicating that the process has been successfully handled, but that the response body contains no further information. If the resource doesn't exist, the web server can return HTTP 404 (Not Found).

# RegExr 
 the application fields of regex can be multiple and I’m sure that you’ve recognized at least one of these tasks among those seen in your developer career, here a quick list:
data validation (for example check if a time string i well-formed)
data scraping (especially web scraping, find all pages that contain a certain set of words eventually in a specific order)
data wrangling (transform data from “raw” to another format)
string parsing (for example catch all URL GET parameters, capture text inside a set of parenthesis)
string replacement (for example, even during a code session using a common IDE to translate a Java or C# class in the respective JSON object — replace “;” with “,” make it lowercase, avoid type declaration, etc.)
syntax highlightning, file renaming, packet sniffing and many other applications involving strings (where data need not be textual)

## Things I want to know more about
i need to know more about these topics
