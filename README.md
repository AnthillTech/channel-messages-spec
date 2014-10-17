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
    <tr>
        <td><a href="spec/discovery.md">Discovery</a></td>
        <td>This service is strongly recommended to be supported by all devices. It allows other devices to obtain information about types services provided by their peers connected to the same channel.</td>
    </tr>
    <tr>
        <td><a href="spec/light.md">Light</a></td>
        <td>Remotely controlled on-off light source</td> 
    </tr>
    <tr>
        <td><a href="spec/switch.md">Switch</a></td>
        <td>Manual on-off switch. Generates events on state change.</td>
    </tr>
    <tr>
        <td><a href="spec/heartbeat.md">Heartbeat</a></td>
        <td>Implemented by devices which want to periodically send Tick event.</td>
    </tr>
    <tr>
        <td><a href="spec/image.md">Image</a></td>
        <td>Implemented by cameras which can provide still image.</td>
    </tr>
    <tr>
        <td><a href="spec/location.md">Location</a></td>
        <td>Address and geo location</td>
    
    </tr>


</table>

## Candidate definitions

<table class="table table-bordered">
    <tr>
        <th>Service name</th>
        <th>Description</th>
    </tr>
        

    <tr>
        <td><a href="spec/config.md">Config</a></td>
        <td>Getting and setting device configuration data</td>
    
    </tr>
    <tr>
        <td><a href="spec/temperature.md">Temperature</a></td>
        <td>Reporting value of temperature measured</td>
    
    </tr>
    <tr>
        <td><a href="spec/offline.md">OffLine</a></td>
        <td>For devices that spend most of their time sleeping and off-line, occasionally reporting their events</td>
    
    </tr>


</table>



## Definitions under discussion


<table class="table table-bordered">
    <tr>
        <th>Service name</th>
        <th>Description</th>
    </tr>
    <tr>
        <td><a href="spec/dimmer.md">Dimmer</a></td>
        <td>Light dimmer service </td>
    
    </tr>
    <tr>
        <td><a href="spec/eventlog.md">Eventlog</a></td>
        <td>Event logging and retrieval of missed events</td>
    
    </tr>
    
    <tr>
        <td><a href="spec/lightsensor.md">Light Sensor</a></td>
        <td>Implemented by devices with light sensor</td>
    
    </tr>
    <tr>
        <td><a href="spec/motion.md">Motion</a></td>
        <td>Motion sensor</td>
    
    </tr>
    <tr>
        <td><a href="spec/time.md">Time</a></td>
        <td>Current time and timer functionality</td>
    
    </tr>

    


</table>

#Channel applications

Physical devices will typically provide rather simple sensor or actuator services. More sophisticated data processing is best left to server-side applications. Event logging, timing, logic processing are all examples of services that could be provided by special server-apps. These server apps will appear to all other channel-connected parties as virtual devices. In order to be able to tell them from real devices we propose that the virtual devices created by channel apps have names beginning with at character: @







