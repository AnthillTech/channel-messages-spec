fi24.org-IoT-services
=====================

Public repository of Internet of Things service definitions being part of the fi24.org initiative

#Introduction
Anthill Technology provides Internet of Things hosting services. Our on-line service facilitates connectivity between web-attached devices and provides secure environment for running your own server-side IoT applications.  
Although the devices communicating through our secure channels infrastructure may use any format of data they want, there is a clear long term benefit to the end-users if as many devices as possible used the same language to talk to each other. The benefit is two-fold:  
1. Devices from different vendors could work together in a single channel offering optimum value to the end-user,  
2. Events from the multitude of private channels could be selectively published by the channel owners and be picked up by 3rd party service providers, thus giving rise to a whole new ecosystem of IoT services.  

We believe that the publish-subscribe service model is an appropriate approach to loose collaboration of devices performing many different simple functions (sensors, actuators, etc). Therefore the specifications below takes the service model as its base.   

We appreciate the power of joint community development, so we are putting the following definitions into public domain under the BSD license and we would like to invite everybody to use them and contribute to further growth of the standardized service portfolio.  
We will just manage this project for you, but you know your needs and your industries best. If we work together, soon there will be a service for everything!


#Service specification

While there may be hundreds of different services defined, in order for them to fit with each other, a few rules are needed. In our initial definitions we assumed that:   

1. One device may only implement a single service of particular type. If one physical devices should implement many services of the same type, from the perspective of the communication channel it should appear as multiple virtual devices  
2. Many simple devices may not have the capability or energy to stay on-line permanetly. Therefore services that periodically send events containing its state update are preferred over services that wait to be polled for data.  
3. All devices should implement the *Discovery* service to enable self configuration of applications  
4. In every communication channel there is at least one provider of the *Lastevent* service  
5. All service-related data is exchanged between devices in JSON format  

##Stable definitions

<table class="table table-bordered">
    <tr>
        <th>Service name</th>
        <th>Description</th>
    </tr>
    <tr>
        <td><a href="srvdefs/discovery.md">Discovery</a></td>
        <td>This service is strongly recommended to be supported by all devices. It allows other devices to obtain information about types services provided by their peers connected to the same channel.</td>
    </tr>
    <tr>
        <td><a href="spec/lastevent">Lastevent</a></td>
        <td>Returns details of last event of given type and/or sent from given device. Used by devices that re-connect to the channel, possibly having missed events during off-line time. Also useful for finding out current state of devices that send periodic updates </td>
    
    </tr>
    <tr>
        <td><a href="spec/light">Light</a></td>
        <td>Remotely controlled on-off light source</td> 
    </tr>
    <tr>
        <td><a href="spec/switch">Switch</a></td>
        <td>Manual on-off switch. Generates events on state change.</td>
    </tr>

</table>


##In-development definitions


<table class="table table-bordered">
    <tr>
        <th>Service name</th>
        <th>Description</th>
    </tr>
    <tr>
        <td><a href="spec/dimmer">Dimmer</a></td>
        <td>Light dimmer service </td>
    
    </tr>
    <tr>
        <td><a href="spec/eventlog">Eventlog</a></td>
        <td>Event logging and retrieval of missed events</td>
    
    </tr>
    <tr>
        <td><a href="spec/heartbeat">Heartbeat</a></td>
        <td>Implemented by devices which want to periodically send Tick event.</td>
    </tr>
    <tr>
        <td><a href="spec/image">Image</a></td>
        <td>Implemented by cameras which can provide still image.</td>
    </tr>
    <tr>
        <td><a href="spec/lightsensor">Light Sensor</a></td>
        <td>Implemented by devices with light sensor</td>
    
    </tr>
    <tr>
        <td><a href="spec/motion">Motion</a></td>
        <td>Motion sensor</td>
    
    </tr>
    <tr>
        <td><a href="spec/time">Time</a></td>
        <td>Current time and timer functionality</td>
    
    </tr>


</table>








