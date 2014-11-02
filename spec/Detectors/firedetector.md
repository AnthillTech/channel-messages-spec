#Fire detector  service

**Service URI prefix:**    `org.fi24.firedetector`

Indicates possible presence of fire in the protected area. This service includes all types of fire detectors: smoke, temperature, etc. used to indicate fire danger

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

`org.fi24.firedetector.Updated`
> Reports presence of a fire-related condition (smoke, temperature, etc.)
> 
> **Event parameters:**
>```
>{
>   "active" : <detection_state>
>}
>```
>
>`detection_state ::= True | False` - True: fire-related condition (substance) is being detected. False: no fire-related condition is not being detected
>

---

*Document revision 0.1*

