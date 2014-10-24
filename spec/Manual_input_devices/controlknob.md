#Manual control knob service

**Service URI prefix:**    `org.fi24.controlknob`

Manually operated control knob providing % value of its range

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

`org.fi24.controlknob.Operated`

> Reports that the knob was operated manually and provides the current position as % of the full range
>  
> **Event parameters**
> 
>```
>{
>   "value" : <cur_value>
>}
>```
>
>`cur_value ::= float` - % value of the full range of the knob


---

*Document revision 0.1*

