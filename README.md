#Introduction
Anthill Technology has developed an open-source communication server software, which facilitates information exchange between web-connected electronic devices. The software, code-named mewa, is available [here](https://github.com/AnthillTech/mewa). Mewa is also the engine of our commercial Internet of Things hosting services ([followit24.com](http://www.followit24.com)).  
Although the devices communicating through mewa's secure channels infrastructure may use any format of data, there is a clear long-term benefit to the end-users if devices use common language to talk to each other. The benefit is two-fold:  
1. Devices from different vendors could work together in a single channel offering optimum value to the end-user,  
2. Events from the multitude of private channels could be selectively published by the channel owners and be picked up by 3rd party service providers, thus giving rise to a whole new ecosystem of IoT services.  

We believe that the publish-subscribe service model is an appropriate approach to loose collaboration of devices performing many different simple functions (sensors, actuators, etc). Therefore the specification below takes the service model as its base.   

We appreciate the power of joint community development, so we are putting the following definitions into public domain under the BSD license and we would like to invite everybody to use them and contribute to further growth of the standardized service portfolio.  
  
We will manage this project, but you know your needs and your industries best. If we work together, soon there will be a service for everything!


#Service specification

While there may be hundreds of different services defined, in order for them to fit with each other, a few rules are needed. In our initial definitions we assumed that:   

1. One device may only implement a single service of particular type. If one physical devices should implement many services of the same type, from the perspective of the communication channel it should appear as multiple virtual devices  
2. Many simple devices may not have the capability or energy to stay on-line permanetly. Therefore services that periodically send events containing its state update are preferred over services that wait to be polled for data.  
3. All devices should implement the *Discovery* service to enable self configuration of applications  
4. In every communication channel there is at least one provider of the *Lastevent* service  
5. All service-related data is exchanged between devices in JSON format  
6. Virtual devices created by channel applications (see Channel applications section) by convention should have names beginning with @

##Stable definitions

<table class="table table-bordered">
    <tr>
        <th>Service name</th>
        <th>Description</th>
    </tr>
    
        <!--  =============== CONTROLLED DEVICES ======================= -->
    <tr><td colspan=2 bgcolor=A0A0A0><b>Controlled devices</b>&nbsp;-&nbsp; <i>Devices whose state or mode can be remotely set</td></tr>
    <tr>
        <td><a href="spec/Controlled_devices/light.md">Light</a></td>
        <td>Remotely controlled on-off light source</td> 
    </tr>

        <!--  =============== MANUAL DEVICES ======================= -->
    <tr><td colspan=2 bgcolor=A0A0A0><b>Manual Input Devices</b>&nbsp;-&nbsp; <i>manually operated devices which can provide information about their state as set by the user / operator</td></tr>
    <tr>
        <td><a href="spec/Manual_input_devices/switch.md">Switch</a></td>
        <td>Manual on-off switch. Generates events on state change.</td>
    </tr>

    <!--  =============== OTHER ======================= -->
    <tr><td colspan=2 bgcolor=A0A0A0><b>Other</b>&nbsp;-&nbsp; <i>services not clasified under any of the above headings</td></tr>
    
    
    <tr>
        <td><a href="spec/Other/discovery.md">Discovery</a></td>
        <td>This service is strongly recommended to be supported by all devices. It allows other devices to obtain information about types services provided by their peers connected to the same channel.</td>
    </tr>
    <tr>
        <td><a href="spec/Other/heartbeat.md">Heartbeat</a></td>
        <td>Implemented by devices which want to periodically send Tick event.</td>
    </tr>
    <tr>
        <td><a href="spec/Other/image.md">Image</a></td>
        <td>Implemented by cameras which can provide still image.</td>
    </tr>
    <tr>
        <td><a href="spec/Other/location.md">Location</a></td>
        <td>Address and geo location</td>
    
    </tr>


</table>

## Candidate definitions

<table class="table table-bordered">
    <tr>
        <th>Service name</th>
        <th>Description</th>
    </tr>
              
    
    
    <!--  =============== SENSORS ======================= -->
    <tr><td colspan=2 bgcolor=A0A0A0><b>Sensors</b>&nbsp;-&nbsp; <i>sensors measure and provide values of physical quantities</td></tr>
    <tr>
        <td><a href="spec/Sensors/temperaturesensor.md">Temperature Sensor</a></td>
        <td>Reporting value of temperature measured</td>
    
    </tr>
    <tr>
        <td><a href="spec/Sensors/pressuresensor.md">Pressure Sensor</a></td>
        <td>Reporting value of pressure measured</td>
    
    </tr>
    
    <tr>
        <td><a href="spec/Sensors/battery.md">Battery</a></td>
        <td>Reporting level of battery charge in % of full charge</td>
    
    </tr>

    <tr>
        <td><a href="spec/Sensors/tanklevelsensor.md">Tank Level Sensor</a></td>
        <td>Reporting level of substance in tank in % of full capacity</td>
    
    </tr>
    
    <tr>
        <td><a href="spec/Sensors/flowmeter.md">Flow Meter</a></td>
        <td>Reporting flow rate of the measured medium</td>
    
    </tr>

    <tr>
        <td><a href="spec/Sensors/voltagesensor.md">Voltage Sensor</a></td>
        <td>Reporting value of voltage measured</td>
    
    </tr>
    
    <tr>
        <td><a href="spec/Sensors/currentsensor.md">Current Sensor</a></td>
        <td>Reporting value of electric current measured</td>
    
    </tr>
    
    <!--  =============== DETECTORS ======================= -->
    <tr><td colspan=2 bgcolor=A0A0A0><b>Detectors</b>&nbsp;-&nbsp; <i>detectors indicate that certain physical phenomena take place. Provide binary value: yes / no</td></tr>
    <tr>
        <td><a href="spec/Detectors/motiondetector.md">Motion Detector</a></td>
        <td>Detects motion. Devices like passive infra-red detectors, ultrasound or microwave motion detectors</td>
    
    </tr>
        <tr>
        <td><a href="spec/Detectors/doorwindowdetector.md">Door-window detector</a></td>
        <td>Detects whether door, gate, window, etc. is open </td>
    
    </tr>
    <tr>
    
        <td><a href="spec/Detectors/floodingdetector.md">Flooding Detector</a></td>
        <td>Detects presence of escaped liquid in the supervised area </td>
    
    </tr>
    <tr>
        <td><a href="spec/Detectors/sabotagedetector.md">Sabotage Detector</a></td>
        <td>Indicates tripping of the anti-sabotage circuit</td>
    
    </tr>

    <tr>
        <td><a href="spec/Detectors/tankleveldetector.md">TankLevelDetector</a></td>
        <td>Detects tank level above or below threshold </td>
    
    </tr>

    <tr>
        <td><a href="spec/Detectors/lowbattery.md">Low battery detector</a></td>
        <td>Detects battery charge falling below pre-set threshold</td>
    
    </tr>
    
    <tr>
        <td><a href="spec/Detectors/codetector.md">Carbon monoxide detector</a></td>
        <td>Detects presence of carbon monoxide in the protected are</td>
    
    </tr>
    <tr>
        <td><a href="spec/Detectors/firedetector.md">Fire detector</a></td>
        <td>Indicates presence of fire-related phenomena</td>
    
    </tr>
    <tr>
        <td><a href="spec/Detectors/gasdetector.md">Gas detector</a></td>
        <td>Indicates detecion of combustible gas release in the protected area</td>
    
    </tr>

    <!--  =============== MANUAL DEVICES ======================= -->
    <tr><td colspan=2 bgcolor=A0A0A0><b>Manual Devices</b>&nbsp;-&nbsp; <i>manually operated devices which can provide information about their state as set by the user / operator</td></tr>

    <tr>
        <td><a href="spec/Manual_input_devices/valve.md">Valve</a></td>
        <td>Manually operated valve with shaft encoder providing % value of its fully open position</td>
    </tr>

    <tr>
        <td><a href="spec/Manual_input_devices/controlknob.md">Control Knob</a></td>
        <td>Manually operated control knob providing % value corresponding to its position</td>
    </tr>

    <tr>
        <td><a href="spec/Manual_input_devices/firecallpoint.md">Fire call point</a></td>
        <td>Manually operated fire call point</td>
    </tr>
    
    
    <!--  =============== CONTROLLED DEVICES ======================= -->
    <tr><td colspan=2 bgcolor=A0A0A0><b>Controlled devices</b>&nbsp;-&nbsp; <i>Devices whose state or mode can be remotely set</td></tr>

    <tr>
        <td><a href="spec/Controlled_devices/thermostat.md">Thermostat</a></td>
        <td>Thermostat whose set-point temeperature can be remotely set</td>
    
    </tr>
    
    <tr>
        <td><a href="spec/Controlled_devices/thermostatex.md">ThermostatEx</a></td>
        <td>Thermostat whose set-point temeperature can be remotely set. Extended functionality allows it to report the current value of the temperature that it controls</td>
    
    </tr>
    
       
    <tr>
        <td><a href="spec/Controlled_devices/switchablevalve.md">Switchable Valve</a></td>
        <td>Valve that can be remotely put in fully open or fully closed positions</td>
    
    </tr>

    <tr>
        <td><a href="spec/Controlled_devices/pump.md">Pump</a></td>
        <td>Pump that can be turned on or off. Capable of ascertaining and reporting whether it produces output or not</td>
    
    </tr>
    
    <!--  =============== COUNTERS ======================= -->
    <tr><td colspan=2 bgcolor=A0A0A0><b>Counters / Meters</b>&nbsp;-&nbsp; <i>Devices that count, sum, integrate etc </i> </td></tr>

    <tr>
        <td><a href="spec/Counters/watermeter.md">Water meter</a></td>
        <td>sums water usage over time</td>
    </tr>
    
    <tr>
        <td><a href="spec/Counters/electricitymeter.md">Electricity meter</a></td>
        <td>Sums electric energy usage over time</td>
    </tr>
    
    
    <tr>
        <td><a href="spec/Counters/heatmeter.md">Heat meter</a></td>
        <td>Sums thermal energy usage over time</td>
    </tr>
    
    <tr>
        <td><a href="spec/Counters/pulsecounter.md">Pulse counter</a></td>
        <td>Count occurences</td>
    </tr>
    
    
    
    <!--  =============== GENERIC I/O ======================= -->
    <tr><td colspan=2 bgcolor=A0A0A0><b>Generic I/O</b>&nbsp;-&nbsp; <i>allow to work with other types of I/O that do not have their specific service definitions</td></tr>

    
    <tr>
        <td><a href="spec/Generic_IO/output.md">Output</a></td>
        <td>A generic two-state switchable output</td>
    
    </tr>
    <tr>
        <td><a href="spec/Generic_IO/input.md">Input</a></td>
        <td>A generic active/inactive input</td>
    
    </tr>
    
    
    
    
    <!--  =============== OTHER ======================= -->
    <tr><td colspan=2 bgcolor=A0A0A0><b>Other</b>&nbsp;-&nbsp; <i>services not clasified under any of the above headings</td></tr>
    
    <tr>
        <td><a href="spec/Other/config.md">Config</a></td>
        <td>Getting and setting device configuration data</td>
    
    </tr>
    <tr>
        <td><a href="spec/Other/offline.md">OffLine</a></td>
        <td>For devices that spend most of their time sleeping and off-line, occasionally reporting their events</td>
    
    </tr>
    <tr>
        <td><a href="spec/Other/alert.md">Alert</a></td>
        <td>Used to generate alerts and alarms. Typically used by applications, rather than individual devices</td>
    
    </tr>



</table>



#Channel applications

Physical devices will typically provide rather simple sensor or actuator services. More sophisticated data processing is best left to server-side applications. Event logging, timing, logic processing are all examples of services that could be provided by special server-apps. These server apps will appear to all other channel-connected parties as virtual devices. In order to be able to tell them from real devices we propose that the virtual devices created by channel apps have names beginning with at character: @







