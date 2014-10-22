#Set Pressure service

**Service URI prefix:**    `org.fi24.setPressure`  

This service is implemented by devices that allow the user to specify the set point pressure (e.g. device like pump controller)

*service definition ver 0.1*   
*status: candidate*   

---

###Accepted command messages

`org.fi24.setPressure.Set`  
> Sets the new set point pressure for the device
> 
> **Message parameters:**   
>```
>{  
>   "value" : <press_value>,
>   "units" : <press_units>,
>}
>```
>
> `press_value ::= float` - value of the temperature set point accepted by the device  
> `press_units ::= "bar" | "PSI" | "atm" | "Pa" | "mmHg"` - units in which the pressure value is expressed

>**Possible responses:** `org.fi24.setPressure.ValueError`, or event `org.fi24.setPressure.PressSet`

---


###Returned response messages

`org.fi24.setPressure.ValueError`  
> Indicates that the device rejected the request to set new pressure set point due to new value being out of range or expressed in unsupported units
> 
> **Message parameters:**   
>```
>{  
>   "min" : <min_value>,
>   "max" : <max_value>,
>   "units" : <list_of_units>
>}
>```
>
> `min_value ::= float` - minimum value of set point accepted by the device  
> `max_value ::= float` - minimum value of set point accepted by the device  
> `list_of_units ::= [<units>, <units>,...]` - list of strings, each indicates units accepted by the device  
> `units :: = string` - units accepted by the device  


---

###Generated events

`org.fi24.setPressure.PressSet`  
> Event sent by the device to indicate that it accepted the new set point. The value of the new set point is sent as parameters
> 
> **Event parameters:**   
>```
>{  
>   "value" : <press_value>,
>   "units" : <press_units>,
>}
>```
>
> `press_value ::= float` - value of the pressure set point accepted by the device  
> `press_units ::= "bar" | "PSI" | "atm" | "Pa" | "mmHg"` - units in which the pressure value is expressed


---

*Document revision 0.1*

