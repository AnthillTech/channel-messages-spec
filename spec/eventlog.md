#Eventlog service

**Service URI prefix:**    `org.fi24.eventlog`

This service offers event logging on behalf of devices whose connection to the channel may be intermittent. The device may request the Eventlog service to send back a list of events that have occurred in the past. Such request can be parametrized by a filter.  
Eventlog service may have limited capacity. If its capacity is exceeded, then the service shall discard the oldest event logged to make space for a new one. 


*service definition ver 0.2*
*status: in-development*

---

###Accepted command messages


`org.fi24.eventlog.GetEvents`

> Request the list of events logged by the service filtered by device name, event id or timestamp. If specified each filter is applied in conjunction with others (AND not OR)
> 
> **Message parameters:**  
> ```
> {
>    "devicename" : <device_name>
>    "eventid" : <event_identifier>
>    "newerthan" :  <date_time>
> }
> ```
>
> `device_name ::= string` - *(OPTIONAL)* - name of device whose events are to be retrieved. If parameter is missing all devices are assumed  
>
> `event identifier ::= string` - *(OPTIONAL)* - URI string specifying event id of the events to be retrieved. If this parameter is missing all event types are assumed  
>
> `date_time ::= ISO_8601` -  *(OPTIONAL)* - a string expressed in the ISO 8601 format specifying the date and time of the last event that the device had received. The Eventlog service will respond with the list of all event it has logged with later timestamp than the one given.
>
> ** *At least one of the optional parameters must be specified* **  
>
> **Responds with:** `org.fi24.eventlog.Events`  

---

###Returned response messages


`org.fi24.eventlog.Events`

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

*Document revision 0.2*

