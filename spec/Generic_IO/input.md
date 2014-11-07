#Input service

**Service URI prefix:**    `org.fi24.input`

Implements a generic bi-state input. Has active state and inactive state

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

`org.fi24.input.Updated`
> Report new state of input
> 
> **Event parameters:**
>```
>{
>   "active" : <input_state>
>}
>```
>
>`detection_state ::= True | False` - True: input is active. False: input is inactive
>

---

*Document revision 0.1*

