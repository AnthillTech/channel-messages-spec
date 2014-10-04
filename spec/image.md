# Image service

**Service URI prefix:**    `org.fi24.image`

This service is to be implemented by cameras which can take and provide a still images upon request


*service definition ver 1.0*  
*status: stable*

---

### Accepted command messages

`org.fi24.image.GetImage`

> Returns the current image
> 
> **Message parameters:**  None  
> **Responds with:** `org.fi24.image.Image`


---


### Returned response messages

`org.fi24.image.Image`
> Returns the current image
> 
> **Message parameters:**  
> ```
> {
>    "data" : <image_data>
> }
> ```
>
> `image_data ::= string` - Data URI Scheme Base 64 encoded image data

---



*Document revision 1.0*

