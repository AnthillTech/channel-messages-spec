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
> <request_message>
> ```
>
> `request_message` - GET or POST request as send to the server
>
> **Responds with:** `org.fi24.httpServer.response`  

---


### Returned response messages

`org.fi24.httpServer.response`

> Send response from the server
> 
> **Message parameters:**  
> ```
> <response_message>
> ```
>
> `response_message` - Full response message (Headers and body)

---

###Generated events

None

---

*Document revision 0.1*

