#Lastevent service

**Service URI prefix:**    `org.fi24.lastevent`

This service stores the last event of a particular event id, reported by a device of a particular device name. In other words, this service is a database where there is a maximum of one entry for each key being the pair of (device_name, event_id).  
The purpose of this service is to provide devices and applications that may have intermittent access to the channel with means of finding out about current state of other devices and services.


*service definition ver 1.0*  
*status: stable*

---

###Accepted command messages


`org.fi24.lastevent.GetEvents`

> Request the list of events logged by the service filtered by device name, event id or timestamp. If specified each filter is applied in conjunction with others (AND not OR)
> 
> **Message parameters:**  
> ```
> {
>    "devicename" : <device_name>
>    "eventid"    : <event_identifier>
> }
> ```
>
> `device_name ::= string` - *(OPTIONAL)*, name of device whose events are to be retrieved. If parameter is missing all devices are assumed  
>
> `event_identifier ::= string` - *(OPTIONAL)*, URI string specifying event id of the events to be retrieved. If this parameter is missing all event id's are assumed  
>
> ** *At least one of the optional parameters must be specified* **  
>
> **Responds with:** `org.fi24.lastevent.Events`  

---

###Returned response messages


`org.fi24.lastevent.Events`

> Returns the events requested
> **Message parameters:**  
> ```
> {  
>    "events" : [ <event_struct>* ]  
> }  
> event_struct :: =  
>   {  
>       "time" : <time_stamp>,  
>       "device : <from_device>,  
>       "id" : <fq_event_id>,  
>       "params" : <params>  
>   }  
>```
>`time_stamp :: = ISO_8601` - a string in the ISO 8601 format specifying the date and time when the event was received in the channel  
>`from_device ::= string` - the name of the device that reported the event  
>`fq_event_id ::= string` - fully qualified event identifier   
>`params ::= string` - parameters of the event  
>  




---

*Document revision 0.1*

