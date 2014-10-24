#Motion detector service

**Service URI prefix:**    `org.fi24.motiondetector`

This service is implemented by motion sensors. It's purpose is to send notification event when motion is detected in the protected area.

*service definition ver 0.3*  
*status: candidate*

---

###Accepted command messages

None

---


###Returned response messages

None

---

###Generated events

`org.fi24.motiondetector.Updated`
> Report new state of motion being detected by the sensor
> 
> **Event parameters:**
>```
>{
>   "active" : <detection_state>
>}
>```
>
>`detection_state ::= True | False` - True: motion is being detected. False: motion is not being detected
>





---

*Document revision 0.3*

