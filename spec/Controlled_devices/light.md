#Light service

**Service URI prefix:**    `org.fi24.light`

Remotely controlles on-off light source.

*service definition version: 2.0*  
*status: stable*

---

###Accepted command messages

`org.fi24.light.TurnOn`

> Switches the light on
> 
> **Message parameters:** None  
> **Responds with:** None


`org.fi24.light.TurnOff` 

> Switches the light off
> 
>**Message parameters:** None  
>**Responds with:** None

`org.fi24.light.Toggle`

> Toggles the light state
> 
>**Message parameters:** None  
>**Responds with:** None

---


###Returned response messages

None

---

###Generated events

`org.fi24.light.Switched`

> Reports that the light has switched. The new state is reported as parameter of the event
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

*Document revision 2.0*
