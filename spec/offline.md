#OffLine service

**Service URI prefix:**    `org.fi24.offline`

This service is implemented by devices that have an off-line working mode to conserve battery. In this mode the device occasionally wakes up, connects to the channel, sends update about its state and disconnects from the channel till the next update.
This service is used by other channel participants to identify devices that are work in this mode and understand what services they provide


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

`org.fi24.offline.Sleep`
> This event should be sent by the device every time when it is about to enter sleep mode and go off-line. Usually this will be the last event it sends during any on-line session with the channel
> 
> **Event parameters:**
>```
>{  
>   "wakein" : <time_s>,
>   "services" : [<service_uri>,*],
>}
>```
>
> `time_s` - integer, time expressed in seconds in which the device will wake up and report again. If this value is 0, it means that the wake-up time is unknown because the device sends its events irregularly as response to external conditions, rather than time elapsed  
> `service_uri` - string, URI id of a service that the device supports.

---

*Document revision 0.1*

