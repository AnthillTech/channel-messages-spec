#Manual valve service

**Service URI prefix:**    `org.fi24.valve`

Manually operated valve with shaft encoder providing % value of its fully open position.
May also be used with valves without shaft encoders being only able to report open or closed positions, in which case this service reports 0% or 100%

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

`org.fi24.valve.Operated`

> Reports that the valve was operated manually and provides the current degree of opening
>  
> **Event parameters**
> 
>```
>{
>   "value" : <cur_value>
>}
>```
>
>`cur_value ::= float` - % value of the full valve opening


---

*Document revision 0.1*

