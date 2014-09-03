#Discovery service

**Service URI prefix:**    `org.fi24.discovery`

Every device should implement this service. It is used by other channel participants to discover what services are provided in the channel by other connected devices

*service definition version 1.0*

---  

###Accepted command messages

`org.fi24.discovery.GetServices`

>**Message parameters:** None  
>**Possible responses:** `org.fi24.discovery.ServiceList`

---

###Returned response messages

`org.fi24.discovery.ServiceList`

>**Message parameters**
>
>```
>[
>    {
>        "type" : <service_type>
>    }
>]
>```

>`service_type ::= string` - URI identifying the type of the service  


---

###Generated events

> None

###How to use this service

Assume we have 2 devices connected to the channel

* deviceA which implementes some services
* deviceB which wants to use services on deviceA


Message flow:

* To get information about supported services DeviceB send **GetServices** message to deviceA. 
* DeviceA respond by sending back message **ServiceList** with with list of supported services specifying their type and names (as there may be more services of the same type exposed by a single device)

---

*Document revision 0.4*
