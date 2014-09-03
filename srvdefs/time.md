#Time service

**Service URI prefix:**    `org.fi24.time`

Time service has two purposes:  
1. To be the source of real time data to devices that have no real-time clock of their own  
2. To provide timer functionality to devices that need to synchronize their actions using the same time source  


*service definition ver 0.1*  
*status: in-development*

---

###Accepted command messages

`org.fi24.time.GetTime`

> Returns the current time and date
> 
> **Message parameters:**  None  
> **Responds with:** `org.fi24.time.CurrentTime`


`org.fi24.time.SetTimerAbs`

> Sets the timer to send an event back at the specific time and date. 
> 
> **Message parameters:**  
> ```
> {
>    "time" : <absolute_time>
> }
> ```
>
> `absolute_time ::= ISO_8601` - a string containing the current time and date expressed in the ISO 8601 format
>
> **Responds with:** None  

`org.fi24.time.SetTimerDelta`

> Sets the timer to send an event back in specific time from now.
> 
> **Message parameters:**  
> ```
> {
>    "delta" : <delta_time>
> }
> ```
>
> `delta_time ::= integer` - number of seconds to elapse before timer event is sent. 
>
> **Responds with:** None  


Note: a single device may only have one timer set at a time. Subsequent calls to SetTimerAbs and / or SetTimerDelta will result in the last call being effective overriding all previous calls.  
Use SetTimerAbs with the parameter value of 0 to cancel a running timer


---


###Returned response messages

`org.fi24.time.CurrentTime`
> Returns the current time and date
> 
> **Message parameters:**  
> ```
> {
>    "time" : <current_time>
> }
> ```
>
> `current_time ::= ISO_8601` - a string containing the current time and date expressed in the ISO 8601 format

---


###Generated events

`org.fi24.time.TimeElapsed`
> Indicates that time set by the call to SetTimerAbs or SetTimerDelta has elapsed  
> **Event parameters:** None



---

*Document revision 0.1*

