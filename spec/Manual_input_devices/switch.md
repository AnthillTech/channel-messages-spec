#Switch service

**Service URI prefix:**    `org.fi24.switch`

Two-state switch (on-off). Generates events when changing state. May also be implemented by a momentary push-button

*service definition ver 2.0*  
*status: stable*

---

###Accepted command messages

None

---


###Returned response messages

None

---

###Generated events

`org.fi24.switch.Switched`

> Reports that the switch has been manually operated. The new state is reported as parameter of the event
>  
> **Event parameters**
> 
>```
>{
>   "state" : <cur_state>
>}
>```
>
>`cur_state ::= "on" | "off"` - indicates the current state of the switch


---

*Document revision 2.1*

