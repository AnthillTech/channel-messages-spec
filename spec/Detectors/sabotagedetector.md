#Sabotage detector service

**Service URI prefix:**    `org.fi24.sabotagedetector`

This service is implemented by devices that can detect sabotage condition

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

`org.fi24.sabotagedetector.Updated`
> Reports the existence of the sabotage condition or lack thereof
> 
> **Event parameters:**
>```
>{
>   "active" : <detection_state>
>}
>```
>
>`detection_state ::= True | False` - True: sabotage condition detected. False: sabotage condition cleared
>





---

*Document revision 0.1*

