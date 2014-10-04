#Location service

**Service URI prefix:**    `org.fi24.location`

This service is implemented by devices that report their physical location. Typical use case for stationary devices is for the device to send its location event when it conects to the channel. For mobile devices the evice should send this event whenever its location changes sufficiently to be significant (at the discretion of the device).


*service definition ver 0.3*  
*status: in-development*


---

###Accepted command messages

None

---


###Returned response messages

None

---

###Generated events

`org.fi24.location.AddressUpdate`
> Event sent by the device to provide / update information about the device's whereabouts expressed in terms of their administrative location.
> Typically set by stationary devices when they join channel. Other services may use the service `org.fi24.lastevent` to retrieve the last known location of the device.  
> 
> **Event parameters:**
>```
>{  
>   "country" : <country>,
>   "address" : <street_address>,
>}
>```
>
> `country` - string, ISO 3166 country code  
> `street_address` - string, specifies street address as a free-form text, or any other equivalent information that may help locate devices  


`org.fi24.location.GeoUpdate`
> Event sent by the device to provide / update information about the device's geographic coordinates.
> Typically sent by mobile devices that utilize some kid of positioning method. Devices will send this event each time when their position changes sufficiently  
> Other services may use the service `org.fi24.lastevent` to retrieve the last known location of the device.  
> 
> **Event parameters:**
>```
>{  
>   "geo":[ <lattitude>, <longitude>  ]
>}
>```
>
> Coordinates are specified in accordance with ISO 6709: lattitude first, longitude second, expressed in degrees and fractions of degrees (not minutes and seconds), north and east are positive, south and west - negative.  
> `lattitude` - float, lattitude, degrees  
> `logitude` - float, longitude, degrees  




---

*Document revision 0.3*

