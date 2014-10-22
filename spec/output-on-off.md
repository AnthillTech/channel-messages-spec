#On-off output

**Service URI prefix:**    `org.fi24.output-on-off`

Remotely controlled on-off output having two states: active and inactive. Definition of what is active or inactive is implementation dependent

*service definition version: 0.1*  
*status: candidate*

---

###Accepted command messages

`org.fi24.output-on-off.TurnOn`

> Switches the output to active state
> 
> **Message parameters:** None  
> **Responds with:** None


`org.fi24.output-on-off.TurnOff` 

> Switches the output to inactive state
> 
>**Message parameters:** None  
>**Responds with:** None

`org.fi24.output-on-off.Toggle`

> Toggles the output to an opposite state
> 
>**Message parameters:** None  
>**Responds with:** None

---


###Returned response messages

None

---

###Generated events

`org.fi24.output-on-off.Switched`

> Reports that the output has been switched. The new state is reported as parameter of the event
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

*Document revision 0.1*
