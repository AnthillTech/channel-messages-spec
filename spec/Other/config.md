#Device configuration service

**Service URI prefix:**    `org.fi24.config`  

Allows for setting and retrieval of the device configuration (programming) data  

*service definition version: 0.2*   
*status: candidate*   

---

###Accepted command messages

`org.fi24.config.Set`  

> Uploads the new configuration data to device  
> 
> **Message parameters:**   
>
>```
>{
>   "config" : <config_data>
>}
>```
>`config_data ::= string` - new configuration data for the device. May be of any arbitrary format, but it is encouraged to encode your programming set as a JSON structure  
>
>
> **Responds with:** `org.fi24.config.DataOk`, `org.fi24.config.Error`  

---

`org.fi24.config.Get`  

> Returns the device configuration data  
> 
>**Message parameters:** None  
>
>**Responds with:** `org.fi24.config.Data`  



---


###Returned response messages

`org.fi24.config.Data`  

> Used by the device to return the requested configuration data  
> 
> **Message parameters:**   
>
>```
>{
>   "config" : <config_data>
>}
>```
>`config_data ::= string` - configuration data for the device  
>

---

`org.fi24.config.DataOk`  

> Indicates successful update of the device's configuration data  
> 
>**Message parameters:** None  
>

---


`org.fi24.config.Error`  

> Indicates that the update of the device's configuration data has failed  
> 
> **Message parameters:**   
>
>```
>{
>   "reason" : <error_reason>
>}
>```
>`error_reason ::= string` - explanation of the error in the configuration data  
>



---

###Generated events

`org.fi24.config.Configured`  

> Announces that the configuration of the device has been successfully updated  
>  
> **Event parameters**: None  
>  

---

*Document revision 0.2*
