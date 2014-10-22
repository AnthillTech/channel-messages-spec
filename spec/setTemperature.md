#Set temperature service

**Service URI prefix:**    `org.fi24.setTemperature`  

This service is implemented by devices that allow the user to specify the set point temperature (e.g. device like thermostats)

*service definition ver 0.1*   
*status: candidate*   

---

###Accepted command messages

`org.fi24.setTemperature.Set`  
> Sets the new set point temperature for the device
> 
> **Message parameters:**   
>```
>{  
>   "value" : <temp_value>,
>   "units" : <temp_units>,
>}
>```
>
> `temp_value ::= float` - value of the temperature set point accepted by the device  
> `temp_units ::= "C" | "K" | "F"` - units in which the temperature value is expressed (Celsius degrees, Kelvin, Farenheit degrees)  

>**Possible responses:** `org.fi24.setTemperature.ValueError`

---


###Returned response messages

`org.fi24.setTemperature.ValueError`  
> Indicates that the device rejected the request to set new temperature set point due to new value being out of range or expressed in unsupported units
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

`org.fi24.setTemperature.TempSet`  
> Event sent by the device to indicate that it accepted the new set point. The value of the new set point is sent as parameters
> 
> **Event parameters:**   
>```
>{  
>   "value" : <temp_value>,
>   "units" : <temp_units>,
>}
>```
>
> `temp_value ::= float` - value of the temperature set point accepted by the device  
> `temp_units ::= "C" | "K" | "F"` - units in which the temperature value is expressed (Celsius degrees, Kelvin, Farenheit degrees)  


---

*Document revision 0.1*

