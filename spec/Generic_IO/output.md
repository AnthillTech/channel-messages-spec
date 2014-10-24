#Output service

**Service URI prefix:**    `org.fi24.output`

Bi-state switchable output. Has two states: on / off

*service definition version: 0.1*  
*status: candidate*

---

###Accepted command messages

`org.fi24.output.TurnOn`

> Switches the output on
> 
> **Message parameters:** None  
> **Responds with:** None


`org.fi24.output.TurnOff` 

> Switches the output off
> 
>**Message parameters:** None  
>**Responds with:** None

`org.fi24.output.Toggle`

> Toggles the output state
> 
>**Message parameters:** None  
>**Responds with:** None

---


###Returned response messages

None

---

###Generated events

`org.fi24.output.Switched`

> Reports that the output has switched to opposite state. The new state is reported as parameter of the event
>  
> **Event parameters**
> 
>```
>{
>   "state" : <cur_state>
>}
>```
>
>`cur_state ::= "on" | "off"` - indicates the current state of the output  




---

*Document revision 2.0*
