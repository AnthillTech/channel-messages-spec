#Pulse counter service

**Service URI prefix:**    `org.fi24.pulsecounter`  

This service is implemented by devices that count occurenceces of 

*service definition ver 0.1*   
*status: candidate*   

---

###Accepted command messages

`org.fi24.pulsecounter.Reset`  
> Resets the count number to zeror  
> 
> **Message parameters:** None   


---


###Returned response messages:  
None, but should generate event with the new count  

---

###Generated events

`org.fi24.pulsecounter.Updated`  
> Event sent by the device to indicate that the pulse count was updated  
> 
> **Event parameters:**   
>```
>{  
>   "count" : <count_number>
>}
>```
>
> `count_number ::= integer` - number of occurences counted  


---

*Document revision 0.1*

