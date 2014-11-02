#Manual fire call point service

**Service URI prefix:**    `org.fi24.firecallpoint`

Manually operated fire call point. Generates event when activated. Does not generate an event when restored to normal condition. An application receiving the activation event from this service is expected to latch the indication of fire call point activation until explicitly re-set by the user of the application. 

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

`org.fi24.firecallpoint.Activated`

> Reports that the fire call point has been pressed
>  
> **Event parameters:**   None


---

*Document revision 0.1*

