#Switchable valve service

**Service URI prefix:**    `org.fi24.switchablevalve`

Remotely controlled valve which can be either open or closed

*service definition version: 0.1*  
*status: candidate*

---

###Accepted command messages

`org.fi24.switchablevalve.TurnOn`

> Opens the valve
> 
> **Message parameters:** None  
> **Responds with:** None


`org.fi24.switchablevalve.TurnOff` 

> Closes the valve
> 
>**Message parameters:** None  
>**Responds with:** None

`org.fi24.switchablevalve.Toggle`

> Toggles the valve from open to close and back
> 
>**Message parameters:** None  
>**Responds with:** None

---


###Returned response messages

None

---

###Generated events

`org.fi24.switchablevalve.Switched`

> Reports that the valve position was switched. The new state is reported as parameter of the event
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
