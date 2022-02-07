# API Guide

## Request Types:
  - GET
  - POST
  - PUT
  - HEAD
  - DELETE
  - PATCH
  - OPTIONS

## GET:

  - GET requests are the most common and widely used methods in APIs and websites. Simply put, the GET method is used to retreive data from a server at the specified resource. For example, say you have an API with a /users endpoint. Making a GET request to that endpoint should return a list of all available users.
  - valid GET request returns a 200 status code.
  - GET is often the default method in HTTP clients.

## POST:

  - POST requests are used to send data to the API server to create or update a resource. The data sent to the server is stored in the request body of the HTTP request.
  - POST requests are used to send data to the API server and create or update a resource.

## PUT:

  - Simlar to POST, PUT requests are used to send data to the API to update or create a resource.
  - The difference is that PUT requests are idempotent.
  - Generally, when a PUT request creates a resource the server will respond with a 201 (Created), and if the request modifies existing resource the server will return a 200 (OK) or 204 (No Content).
  - PUT requests should fail if invalid data is supplied in the request -- nothing should be updated.

## PATCH:

  - it is similar to POST and PUT. The difference with PATCH is that you only apply partial modifications to the resource.
  - The difference between PATCH and PUT, is that a PATCH request is non-idempotent (like a POST request).

## DELETE:
  - Delete the resource at the specified URL.
  - If a new user is created with a POST request to /users, and it can be retrieved with a GET request to /users/{{userid}}, then making a DELETE request to /users/{{userid}} will completely remove that user.

## HEAD:

  - The HTTP HEAD method requests the headers that would be returned if the HEAD request's URL was instead requested with the HTTP GET method.
  - Making API requests with HEAD methods is actually an effective way of simply verifying that a resource is available.
  - For example, if a URL might produce a large download, a HEAD request could read its Content-Length header to check the filesize without actually downloading the file.
  - A response to a HEAD method should not have a body.
  - HEAD Used to determine whether a given resource is available?
  - HEAD method returns info about resource (version/length/type)
  - Server response:
    ```http
    HTTP/1.1 200 OK
    Accept-Ranges: bytes
    Content-Type: text/html; charset=UTF-8
    Date: Wed, 08 May 2013 10:12:29 GMT
    ETag: "780602-4f6-4db31b2978ec0"
    Last-Modified: Thu, 25 Apr 2013 16:13:23 GMT
    Content-Length: 1270
    ```
  - HEAD Checking whether a resource has changed. This is useful when maintaining a cached version of a resource
  - HEAD Retrieving metadata about the resource, e.g. its media type or its size.

## OPTIONS:
  - OPTIONS method returns info about API (methods/content type)
  - Server response:
    ```http
    HTTP/1.1 200 OK
    Allow: GET,HEAD,POST,OPTIONS,TRACE
    Content-Type: text/html; charset=UTF-8
    Date: Wed, 08 May 2013 10:24:43 GMT
    Content-Length: 0
    ```
  - OPTIONS Identifying which HTTP methods a resource supports, e.g. can we DELETE it or update it via a PUT?

## What are API Headers?
- API headers are like an extra source of information for each API call you make.
- Their job is to represent the meta-data associated with an API request and response.
- If you ever encounter issues with an API, the first place you should look is the headers, since they can help you track down any potential issues.
- API Headers tell you about:
  - Request and Response Body
  - Request Authorization
  - Response Caching
  - Response Cookies

## List of HTTP header fields:
- ```Accept: text/html```: Media type(s) that is/are acceptable for the response.
- ```Accept-Charset: utf-8```: Character sets that are acceptable.
- ```Accept-Datetime: Thu, 31 May 2007 20:35:00 GMT```: Acceptable version in time.
- ```Accept-Encoding: gzip, deflate```: List of acceptable encodings.
- ```Accept-Language: en-US```: List of acceptable human languages for response.
```Access-Control-Request-Method: GET, Access-Control-Request-Headers```: Initiates a request for cross-origin - resource sharing with Origin
- ```Authorization: Basic QWxhZGRpbjpvcGVuIHNlc2FtZQ==```: Authentication credentials for HTTP authentication.
```Connection: keep-alive, Connection: Upgrade```: Control options for the current connection and list of hop-by-hop - request fields.
- ```Content-Length: 348```: The length of the request body in octets (8-bit bytes).
- ```Content-MD5: Q2hlY2sgSW50ZWdyaXR5IQ==```: A Base64-encoded binary MD5 sum of the content of the request body.
```Host: en.wikipedia.org```: The domain name of the server (for virtual hosting), and the TCP port number on which - the server is listening.
- ```From: user@example.com```: The email address of the user making the request.
- ```Origin: http://www.example-social-network.com```: Initiates a request for cross-origin resource sharing
