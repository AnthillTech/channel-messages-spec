#Controlled valve service

**Service URI prefix:**    `org.fi24.variablevalve`  

This service is implemented by remotely controlled valves with variable opening degree, that in addition to set-point value can also report the actual opening degree value.

*service definition ver 0.1*   
*status: candidate*   

---

###Accepted command messages

`org.fi24.variablevalve.Set`  
> Sets the new opening degree of the valve
> 
> **Message parameters:**   
>```
>{  
>   "value" : <opening_percent>,
>}
>```
>
> `opening_percent ::= float` - degree of opening in %  


>**Possible responses:** `org.fi24.variablevalve.ValueError`

---


###Returned response messages

`org.fi24.variablevalve.ValueError`  
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

`org.fi24.variablevalve.SetpointValueSet`  
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


`org.fi24.variablevalve.ControlledValueUpdated`  
> Event sent by the device to indicate new value of the temperature it controls
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

