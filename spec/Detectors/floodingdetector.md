#Flooding detector service

**Service URI prefix:**    `org.fi24.floodingdetector`

Detects presence of escaped liquid in the supervised area

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

`org.fi24.floodingdetector.Updated`
> Reports flooding condition or lack thereof
> 
> **Event parameters:**
>```
>{
>   "active" : <detection_state>
>}
>```
>
>`detection_state ::= True | False` - True: flooding is being detected. False: flooding is not being detected
>


---

*Document revision 0.1*

