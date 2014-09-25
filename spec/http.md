# HTTP server service

**Service URI prefix:**    `org.fi24.httpServer`

Exposes HTTP server

*service definition ver 0.1*  
*status: in-development*

---

### Accepted command messages

`org.fi24.httpServer.request`

> Send request to the server
> 
> **Message parameters:**  
> ```
> {
>    "path" : <path>
>    "method" : <request_method>
>    "headers" : <additional_headers>
>    "params" : <params>
> }
> ```
>
> `path` - URL path on remote server
> `method` - GET or POST
> `headers` - Key, value map with additional headers
> `params` - Key - value map with request params
>
> **Responds with:** `org.fi24.httpServer.response`  

---


### Returned response messages

`org.fi24.httpServer.response`

> Send response from the server
> 
> **Message parameters:**  
> ```
> {
>    "headers" : <request_headers>
>    "body" : <body>
> }
> ```
>
> `headers` - All request headers
> `body` - Request body

---

###Generated events

None

---

*Document revision 0.1*

