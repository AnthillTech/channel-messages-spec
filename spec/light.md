#Light service

**Service URI prefix:**    `org.fi24.light`

Remotely controlles on-off light source.

*service definition version: 1.3*  
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

`org.fi24.light.TurnedOn`

> Reports that the light has been turned on
>  
> **Event parameters**
> 
> None

`org.fi24.light.TurnedOff`

> Reports that the light has been turned off
>  
> **Event parameters**
> 
> None


---

*Document revision 0.7*
