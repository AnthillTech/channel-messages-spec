#Tank level detector service

**Service URI prefix:**    `org.fi24.tankleveldetector`

Detects whether the level of mass in the tank exceeds pre-set thresholds. May be used to both signal low or high levels.

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

`org.fi24.tankleveldetector.Updated`
> Reports whether level of the mass in the tank exceeds the threshold value or not.
> 
> **Event parameters:**
>```
>{
>   "active" : <detection_state>
>}
>```
>
>`detection_state ::= True | False` - True: level exceeds threshold. False: level is withing normal range
>

---

*Document revision 0.1*

