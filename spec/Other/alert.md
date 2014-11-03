#Alert service

**Service URI prefix:**    `org.fi24.alert`

This service is used to deliver information about critical events taking place in the installation.

1. Every application which subscribes to org.fi24.alert must react to Security, Lifesafety and Medical alert events. It may react to other alert events.
2. Application must not allow the user to disable notifications of Security, Lifesafety or Medical alert events. 
3. Application may allow the user to disable notifications of the remaining alert events.
4. Application must allow the user to acknowledge any alert event which is being notified to the user by application. Upon such acknowledgement application must forward the acknowledgent to the event-reporting device


*service definition version 0.1*

---  

###Accepted command messages

`org.fi24.alert.Acknowledge`

>**Message parameters:**   
>
>```
>{
>   "id" : <alert_id>
>}
>```
>
>`alert_id ::= string` - identifier of the alert being acknowledged.
>
>**Possible responses:** None, but may generate alert reset event in response.  


---

###Returned response messages

None

---

###Generated events

#### Alert reporting events.  
All events have the same syntax, please refer to the table below for list of URI's and meaning of their parameters  

`For possible URI's see table`
> 
> **Event parameters:**
>```
>{  
>   "id" : <alert_id>,
>   "type" : <alert_type>,
>   "desc: : <description>,
>   "local-time" : <time_stamp>,
>   "cause" : [<event_struct>,..,<event_struct>],
>}
>```
>`alert_id ::= string` - identifier of the alert. Used for acknowledgement purposes
>`alert_type ::= string` - see table for possible types for each URI  
>`description :: = string` - natural language description of the alarm
>`time_stamp ::= string` - ISO 8601 formatted local time of the device raising the alert. Empty string, if device has no clock  
>`event_struct ::= string` - JSON encoded event structure in the channel format  
>
>The field `cause` contains the list of all events that have caused the alert  
>

<td style="">
  <table border=1 cellspacing=0 cellpadding=3 >
  <tr valign=top>
  <td  >Alert table
    <table border=1 cellspacing=0 cellpadding=3 style="font-size: 10pt;">
    <tr valign=top>
    <td  >org.fi24.alert.Security
    </td>
    <td  >Alerts related to physical security
    </td>
    <td  >alert_type
      <table border=1 cellspacing=0 cellpadding=3 style="font-size: 9pt;">
      <tr valign=top>
      <td  >intrusion
      </td>
      <td  >Intusion into protected area was detected 
      </td>
      </tr>
      <tr valign=top>
      <td  >holdup
      </td>
      <td  >Hold-up alarm was activated by the user
      </td>
      </tr>
      <tr valign=top>
      <td  >DOTL
      </td>
      <td  >Access control system repors door open too long
      </td>
      </tr>
      <tr valign=top>
      <td  >other
      </td>
      <td  >Future use
      </td>
      </tr>
      </table>
    </td>
    </tr>
    <tr valign=top>
    <td  >org.fi24.alert.Lifesafety
    </td>
    <td  >Alerts related to life threatning events
    </td>
    <td  >alert_type
      <table border=1 cellspacing=0 cellpadding=3 style="font-size: 9pt;">
      <tr valign=top>
      <td  >fire
      </td>
      <td  >Fire-related phenomena detected in the protected area
      </td>
      </tr>
      <tr valign=top>
      <td  >gas
      </td>
      <td  >Release of combustible gas detected
      </td>
      </tr>
      <tr valign=top>
      <td  >CO
      </td>
      <td  >Release of carbon monoxide detected
      </td>
      </tr>
      <tr valign=top>
      <td  >other
      </td>
      <td  >Future use
      </td>
      </tr>
      </table>
    </td>
    </tr>
    <tr valign=top>
    <td  >org.fi24.alert.Medical
    </td>
    <td  >Medical emergency
    </td>
    <td  >alert_type
      <table border=1 cellspacing=0 cellpadding=3 style="font-size: 9pt;">
      <tr valign=top>
      <td  >manual
      </td>
      <td  >alert was raised by a pertson operating emergency call point
      </td>
      </tr>
      <tr valign=top>
      <td  >automatic
      </td>
      <td  >alert was raised by the system through automatic behaviour analysis
      </td>
      </tr>
      </table>
    </td>
    </tr>
    <tr valign=top>
    <td  >org.fi24.alert.System
    </td>
    <td  >Report system problems
    </td>
    <td  >alert_type
      <table border=1 cellspacing=0 cellpadding=3 style="font-size: 9pt;">
      <tr valign=top>
      <td  >mains
      </td>
      <td  >Mains failure detected
      </td>
      </tr>
      <tr valign=top>
      <td  >communication
      </td>
      <td  >Communication failure detected
      </td>
      </tr>
      <tr valign=top>
      <td  >battery
      </td>
      <td  >Battery failure detected
      </td>
      </tr>
      <tr valign=top>
      <td  >sabotage
      </td>
      <td  >System sabotage detected
      </td>
      </tr>
      <tr valign=top>
      <td  >error
      </td>
      <td  >System software failure
      </td>
      </tr>
      <tr valign=top>
      <td  >other
      </td>
      <td  >Future use
      </td>
      </tr>
      </table>
    </td>
    </tr>
    <tr valign=top>
    <td  >org.fi24.alert.Technical
    </td>
    <td  >Technical problems with the supervised installation (i.e. external to the system). Includes problems like flooding, freeze, overheat, equipment failure, etc.
    </td>
    <td  >alert_type
      <table border=1 cellspacing=0 cellpadding=3 style="font-size: 9pt;">
      <tr valign=top>
      <td  >technical
      </td>
      <td  >fixed string, reserved for future use
      </td>
      </tr>
      </table>
    </td>
    </tr>
    <tr valign=top>
    <td  >org.fi24.alert.Other
    </td>
    <td  >application-specific alert
    </td>
    <td  >alert_type
      <table border=1 cellspacing=0 cellpadding=3 style="font-size: 9pt;">
      <tr valign=top>
      <td  >other
      </td>
      <td  >fixed string, reserved for future use
      </td>
      </tr>
      </table>
    </td>
    </tr>
    </table>
  </td>
  </tr>
  </table>
</td>


#### Alert reset events

`org.fi24.alert.Reset`
> 
> **Event parameters:**
>```
>{  
>   "id" : <alert_id>,
>   "by" : <reset_by>
>}
>```
>`alert_id ::= string` - identifier of the alert to be acknowledged  
>`reset_by ::= string` - string identifying the device and / or user who reset the alert
>




---

*Document revision 0.1*
