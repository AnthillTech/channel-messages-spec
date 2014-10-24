#Electric current sensor service

**Service URI prefix:**    `org.fi24.currentsensor`  

This service is implemented by devices that measure and report values of electric current  

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

`org.fi24.currentsensor.Updated`  
> Event sent by the device to indicate that the value of the current measured has changed  
> 
> **Event parameters:**   
>```
>{  
>   "value" : <value>,
>   "units" : <units>,
>}
>```
>
> `value ::= float` - value of the current measured by the device  
> `units ::= "A" | "mA" | "kA"` - units in which the current value is expressed  


---

*Document revision 0.1*

