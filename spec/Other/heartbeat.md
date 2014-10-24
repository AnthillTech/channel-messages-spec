#Heartbeat service

**Service type URI:**    `org.fi24.heartbeat`

Periodically sends Tick event. Implemented by devices which rarely send updates or events, but need to be monitored. By sendig hearbeat event they manifest their presence to the other participants of the channel  

*service definiton ver: 1.0*
*status: stable*

---

###Accepted command messages

> None

---


###Returned response messages

> None

---

###Generated events

`org.fi24.heartbeat.Tick`
> Indicates that device is working correctly
> 
> **Event parameters:** None


---

*Document revision 1.0*
