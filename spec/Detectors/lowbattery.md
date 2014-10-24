#Low battery service

**Service URI prefix:**    `org.fi24.lowbattery`

Indicates battery state

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

`org.fi24.lowbattery.Updated`
> Reports low battery condition or lack thereof
> 
> **Event parameters:**
>```
>{
>   "active" : <detection_state>
>}
>```
>
>`detection_state ::= True | False` - True: low battery. False: battery normal
>

---

*Document revision 0.1*

