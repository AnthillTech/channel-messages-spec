#Gas detector service

**Service URI prefix:**    `org.fi24.gasdetector`

Detects presence of combustible gas in the protected are. This is a generic service independent of the type of gas (methane, propane, etc)

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

`org.fi24.gasdetector.Updated`
> Reports concentration of gas above the pre-set level  
> 
> **Event parameters:**
>```
>{
>   "active" : <detection_state>
>}
>```
>
>`detection_state ::= True | False` - True: gas is being detected. False: gas is not being detected
>

---

*Document revision 0.1*

