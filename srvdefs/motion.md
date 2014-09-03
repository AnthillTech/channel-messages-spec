#Motion service

**Service URI prefix:**    `org.fi24.motion`

This service is to be implemented by motion sensors. It's purpose is to send notification event when motion is detected in the protected area.
Motion sensor may be put in the inhibit state, when it stops sending notifications.

*service definition ver 0.2*  
*status: in-development*


---

###Accepted command messages

None

---


###Returned response messages

None

---

###Generated events

`org.fi24.motion.MotionDetected`
> Indicates that motion was detected by the sensor
> 
> **Event parameters:**None


---

*Document revision 0.2*

