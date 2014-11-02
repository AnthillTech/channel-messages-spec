#Carbon monoxide detector service

**Service URI prefix:**    `org.fi24.codetector`

Detects presence of carbon monoxide in the protected area. 

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

`org.fi24.codetector.Updated`
> Reports presence of carbon monoxide in the protected area
> 
> **Event parameters:**
>```
>{
>   "active" : <detection_state>
>}
>```
>
>`detection_state ::= True | False` - True: CO is being detected. False: CO is not being detected
>

---

*Document revision 0.1*

