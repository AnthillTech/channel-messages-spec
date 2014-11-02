#Door-window detector service

**Service URI prefix:**    `org.fi24.doorwindowdetector`

This service is implemented by devices that detect whether door, gate, window, etc. is open

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

`org.fi24.doorwindowdetector.Updated`
> Report new state of the door being protected
> 
> **Event parameters:**
>```
>{
>   "active" : <detection_state>
>}
>```
>
>`detection_state ::= True | False` - True: door, gate, window etc. is open. False: it is closed
>





---

*Document revision 0.1*

