#pump service

**Service URI prefix:**    `org.fi24.pump`

Remotely controlled pump which can be turned on or off

*service definition version: 0.1*  
*status: candidate*

---

###Accepted command messages

`org.fi24.pump.TurnOn`

> Starts the pump
> 
> **Message parameters:** None  
> **Responds with:** None


`org.fi24.pump.TurnOff` 

> Stops the pump
> 
>**Message parameters:** None  
>**Responds with:** None

`org.fi24.pump.Toggle`

> Toggles the pump from start to stop and back
> 
>**Message parameters:** None  
>**Responds with:** None

---


###Returned response messages

None

---

###Generated events

`org.fi24.pump.Switched`

> Reports that the pump operation was switched. The new state is reported as parameter of the event
>  
> **Event parameters**
> 
>```
>{
>   "state" : <cur_state>
>}
>```
>
>`cur_state ::= "on" | "off"` - indicates the current state of the light  




---

*Document revision 0.1*
