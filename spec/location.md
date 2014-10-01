#Location service

**Service URI prefix:**    `org.fi24.motion`

This service is implemented by devices that can report their physical location. Typical use case is for the device to send its location event when it conects to the channel. 

*service definition ver 0.1*  
*status: in-development*


---

###Accepted command messages

None

---


###Returned response messages

None

---

###Generated events

`org.fi24.motion.LocationUpdate`
> Indicates that motion was detected by the sensor
> 
> **Event parameters:**
>```
>{  
>   "address" : {  
>                   "street" : <street>,
>                   "number" : <number>,
>                   "postcode" : <postcode>
>                   "city"   : <city>
>                   "country" : <country>
>               },
>   "geo" :     {
>                   "latt"  : <lattitude>
>                   "long"  : <longitude>
>                   "alt"   : <altitude>
>               }
>}
>```
>
> `address` - optional field, specifies street address  
> `geo` - optional field, specifies geographic coordinates  
> `street` - strig, street name  
> `number` - string, street number  
> `postcode` - string, post code  
> `city` - string, city name  
> `country` - string, ISO 3166 country code  
> `lattitude` - float, lattitude degrees (decimal), north is positive  
> `logitude` - float, longitude degrees (decimal), east is positive  
> `alt` - optioal, float, metres  

---

*Document revision 0.1*

