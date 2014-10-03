#Location service

**Service URI prefix:**    `org.fi24.location`

This service is implemented by devices that report their physical location. Typical use case for stationary devices is for the device to send its location event when it conects to the channel. For mobile devices the device should send this event whenever its location changes sufficiently to be significant (at the discretion of the device)

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

`org.fi24.location.LocationUpdate`
> Event sent by the device to provide / update information about the device's whereabouts.
> Mobile devices would send this event upon their location change, but also stationary devices 
> may send this event to provide information about their installation place, e.g. each time when they join the channel, or every day, etc.
> 
> **Event parameters:**
>```
>{  
>   "country" : <country>,
>   "address" : <street_address>,
>   "geo" :     [ <lattitude>, <longitude>  ]
>}
>```
>
> `country` - string, ISO 3166 country code  
> `street_address` - optional field, specifies street address as a free-form text, or any other equivalent information  
> `geo` - optional field, specifies geographic coordinates in accordance with ISO 6709: lattitude first, longitude second, expressed in degrees and fractions of degrees (not minutes and seconds), north and east are positive, south and west - negative.  
> `lattitude` - float, lattitude, degrees  
> `logitude` - float, longitude, degrees  

---

*Document revision 0.2*

