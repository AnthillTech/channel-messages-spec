#Voltage sensor service

**Service URI prefix:**    `org.fi24.voltagesensor`  

This service is implemented by devices that measure and report voltage  

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

`org.fi24.voltagesensor.Updated`  
> Event sent by the device to indicate that the value of the voltage measured has changed  
> 
> **Event parameters:**   
>```
>{  
>   "value" : <value>,
>   "units" : <units>,
>}
>```
>
> `value ::= float` - value of the voltage measured by the device  
> `units ::= "V" | "mV" | "kV"` - units in which the voltage value is expressed  


---

*Document revision 0.1*

