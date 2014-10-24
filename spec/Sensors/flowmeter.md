#Flow meter service

**Service URI prefix:**    `org.fi24.flowmeter`  

This service is implemented by devices that measure and report flow of a medium

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

`org.fi24.flowmeter.Updated`  
> Event sent by the device to indicate the updated flow value
> 
> **Event parameters:**   
>```
>{  
>   "value" : <flow_value>,
>   "units" : <flow_units>,
>}
>```
>
> `flow_value ::= float` - value of the flow measured  
> `flow_units ::= string` - arbitrary units designator (volume or mass per unit of time) - implementation dependent


---

*Document revision 0.1*

