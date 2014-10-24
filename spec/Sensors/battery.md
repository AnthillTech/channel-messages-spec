#Temperature sensor service

**Service URI prefix:**    `org.fi24.battery`  

This service is implemented by devices that can report the level of their remaining battery charge

*service definition ver 0.1*   
*status: candidate*   

---

###Accepted command messages

None  

---


###Returned response messages

None  

---

###Generated events

`org.fi24.battery.Updated`  
> Event sent by the device to indicate that the value of the temperature measured has changed  
> 
> **Event parameters:**   
>```
>{  
>   "value" : <charge_percent>
>}
>```
>
> `charge_percent ::= float` - percent value of the remaining charge in the battery


---

*Document revision 0.1*

