---
layout: default
parent: Communication
title: MQTT Communication
nav_order: 1
permalink: communication/mqtt
---

# MQTT Communication

Please refer [this](https://docs.google.com/document/d/e/2PACX-1vTm_0MmPGw8-B8v63e-Jc8sfDNO9txeNVYmvAswR7ti8Glnw_4Wqmm6OpOiHOp8b9D15OUumNXIjC5y/pub) for latest communication protocols.


channel: You can create any communication channel by defining this variable. Default is 'v1' channel will be appended to every MQTT topic. (ex: _v1/robot/msg/broadcast_)


### /robot/msg/{robotID}

<table>
<tr><td>Source</td><td>Server</td></tr>
<tr><td>Destination</td><td>Robot</td></tr>
<tr><td>Data Type</td><td>String</td></tr>
<tr><td>Sample Message</td><td>
{eNum} {integer}
</td></tr>
<tr><td>Description</td><td>For an individual robot</td></tr>
</table>

### /robot/msg/broadcast

<table>
<tr><td>Source</td><td>Server</td></tr>
<tr><td>Destination</td><td>Robot</td></tr>
<tr><td>Data Type</td><td>String</td></tr>
<tr><td>Sample Message</td><td>
{eNum} {integer}
</td></tr>
<tr><td>Description</td><td>For all active robots
</td></tr>
</table>


Example broadcasts:
- ID? -1
- MODE 1
- START -1
- STOP -1
- RESET -1


### /robot/live

<table>
<tr><td>Source</td><td>Robot</td></tr>
<tr><td>Destination</td><td>Server</td></tr>
<tr><td>Data Type</td><td>String</td></tr>
<tr><td>Sample Message</td><td>
{robotId} {reality}
</td></tr>
<tr><td>Description</td><td>
Heartbeat signal from the robot to server. Server will keep a track of this to remove dead robots from the system.
reality: 0:virtual, 1:real
</td></tr>
</table>

### /robot/create

<table>
<tr><td>Source</td><td>Loc,Robot</td></tr>
<tr><td>Destination</td><td>Server,GUI</td></tr>
<tr><td>Data Type</td><td>JSON</td></tr>
<tr><td>Sample Message</td><td>
```javascript
{
   "id":0,
   "x":10,
   "y":10,
   "heading":0.0
}
```
</td></tr>
<tr><td>Description</td><td>
This will be originated by robots (physical, virtual) themself at the beginning, or by the localization system
Information taken by the simulator will create a robot instance, and GUI will create a robot object too.
x,y,z,heading : number in #.## format
</td></tr>
</table>

### /robot/delete

<table>
<tr><td>Source</td><td>Server,GUI</td></tr>
<tr><td>Destination</td><td>Any</td></tr>
<tr><td>Data Type</td><td>JSON</td></tr>
<tr><td>Sample Message</td><td>
{ "id":0 }
</td></tr>
<tr><td>Description</td><td>
This will inform other systems to remove the robot. Invoked by the prune scheduler on the server.
</td></tr>
</table>


### Title

<table>
<tr><td>Source</td><td> </td></tr>
<tr><td>Destination</td><td> </td></tr>
<tr><td>Data Type</td><td> </td></tr>
<tr><td>Sample Message</td><td>

</td></tr>
<tr><td>Description</td><td>

</td></tr>
</table>
