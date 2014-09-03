# Image service

**Service URI prefix:**    `org.fi24.image`

This service will be implemented by cameras which can take still images.


*service definition ver 0.1*  
*status: in-development*

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


*Document revision 0.1*

