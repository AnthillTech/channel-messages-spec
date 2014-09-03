#Dimmer service

**Service URI prefix:**    `org.fi24.dimmer`

This service is to be implemented by a manually operated dimmer switch device. When the user manually alters the setting (e.g by turning the knob) this service sends out an event notification about the new level set by the user.  
It's primary purpose is to control the level of light.

*service definition ver 0.2*
*status: in-development*
---

###Accepted command messages

None

---


###Returned response messages

None

---

###Generated events

`org.fi24.dimmer.LevelSet`
> Indicates that new level has been set by the user
> 
> **Event parameters:**
> ```
> {
>    "level" : <current_level>
> }
> ```
> `current_level ::= 0 | 1 | .....| 100` - integer from the range 0-100. Indicates the current level set at the dimmer expressed in % of the full range.


---

*Document revision 0.2*

