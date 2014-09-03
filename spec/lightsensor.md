#Light Sensor service

**Service URI prefix:**    `org.fi24.lightsensor`

Periodically sends value from the light sensor as event. Implemented by devices with light sensor hardware.

*service definition ver: 0.1*  
*status: in-development*

###Generated events

`org.fi24.lightsensor.SensorState`
> Current sensor value
> 
> **Event parameters:** 
> ```
> {
>    "value" : <current_sensor_value>
> }
> ```

> `current_sensor_value ::= Integer` - current value of light measured by the sensor. Expressed in % of full range of the sensor.

---

*Document revision 0.1*
