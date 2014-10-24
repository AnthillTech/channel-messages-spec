#Pressure sensor service

**Service URI prefix:**    `org.fi24.pressuresensor`  

This service is implemented by devices that measure and report pressure  

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

`org.fi24.pressuresensor.Updated`  
> Event sent by the device to indicate that the value of the pressure measured has changed  
> 
> **Event parameters:**   
>```
>{  
>   "value" : <press_value>,
>   "units" : <press_units>,
>}
>```
>
> `press_value ::= float` - value of the pressure measured by the device  
> `press_units ::= "bar" | "PSI" | "atm" | "Pa" | "mmHg"` - units in which the pressure value is expressed


---

*Document revision 0.1*

