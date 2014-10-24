#Tank level sensor service

**Service URI prefix:**    `org.fi24.tanklevelsensor`  

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

`org.fi24.tanklevelsensor.Updated`  
> Event sent by the device to indicate the updated level of substance in the tank
> 
> **Event parameters:**   
>```
>{  
>   "value" : <level_value>,
>   "units" : <level_units>,
>}
>```
>
> `level_value ::= float` - level of substance in the tank  
> `level_units ::= "%" | <units>` - units in which the level is expressed or percent sign  
> `units ::= string` - arbitrary units designator (volume, height, mass, etc.) - implementation dependent


---

*Document revision 0.1*

