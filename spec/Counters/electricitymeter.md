#Electricity meter service

**Service URI prefix:**    `org.fi24.electricitymeter`  

This service is implemented by devices that sum up the usage of electrical energy

*service definition ver 0.1*   
*status: candidate*   

---

###Accepted command messages

`org.fi24.electricitymeter.Reset`  
> Resets the summed value to zero  
> 
> **Message parameters:** None   

---

###Returned response messages:  
None, but should generate event with the new sum on reset  

---

###Generated events

`org.fi24.electricitymeter.Updated`  
> Event sent by the device to indicate that sum value was updated  
> 
> **Event parameters:**   
>```
>{  
>   "value" : <value>,
>    "units" : <units>
>
>}
>```
> `value ::= float` - value of the electricity usage measured from the reset  
> `units ::= string` - arbitrary energy units designator - implementation dependent


---

*Document revision 0.1*

