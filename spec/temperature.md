#Temperature service

**Service URI prefix:**    `org.fi24.temperature`  

This service is implemented by devices that measure and report temperature  

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

`org.fi24.temperature.TempUpdate`  
> Event sent by the device to indicate that the value of the temperature measured has changed  
> 
> **Event parameters:**   
>```
>{  
>   "value" : <temp_value>,
>   "units" : <temp_units>,
>}
>```
>
> `temp_value ::= float` - value of the temperature measured by the device  
> `temp_units ::= C | K | F` - units in which the temperature value is expressed (Celsius degrees, Kelvin, Farenheit degrees)  


---

*Document revision 0.1*

