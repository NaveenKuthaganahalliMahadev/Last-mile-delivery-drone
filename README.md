# Last-mile-delivery-drone

### INTRODUCTION:

These days we are pretty habituated of home-delivery system through e-commerce platform, however there is a big dependency on delivery boys and vehicles for timely delivery of the items.With the rise in the number of vehicles on the road, it is becoming a hassle for delivering products on time. We could potentially use Drones for last mile delivery of items. While current prevalent addressing mechanism such as lat/long and post code are good enough for humans, these won’t work for drone delivery as all houses in a multi-story building will have same lat/long or post-code. We have designed a solution which can help drones to identify each address/flat as a separate unit and deliver the item accordingly. It will include a GPS module for tracking, an ultrasonic sensor for obstacle avoidance, an altimeter for determining the altitude of flight and a gyro sensor for countering any imbalance during flight. Six brush-less DC motors will be used so that heavy equipment can be carried with ease. A camera will assist the deployer to have a visual overview of the drone in action. 

![image](https://user-images.githubusercontent.com/97881084/149749999-c5aec0f3-aa7f-47be-a0a3-033c2b0f847f.png)


#Additional_Info

Drones can be made to travel and deliver goods faster in the optimized path saving time and fuel. On- road delivery can take many zig-zag paths to reach the destination wasting time and energy.It can also be used for delivering medical and food supplies during emergencies like accidents or natural calamities. Multiple drones can be used to work as a network by having many base stations close by.

### BLOCK DIAGRAM:

![image](https://user-images.githubusercontent.com/97881084/149749887-74dfcdff-4308-46cd-9e67-337c641d2dd8.png)

### TECHNOLOGY STACK:

#### Hardware:
• Omnibus F4: Flight Controller 
• BN-880 GPS module
• GSM module 
• Flysky Telemetry 
• IoT Boards 
• Camera module 
• Battery monitoring System

#### Software:
• INAV Configurator 
• Linux(RaspbianOS) 
• VirtualNetworkComputing 
• Python3(coding) 
• OpenCV


## How are Autonomous drones made?

### 1) Flight Controller
Flight controller is the heart of the drone. Any movement or action of the drone is controlled by signals sent from flight controller. To make a drone autonomous, flight controller is the most important device.

![image](https://user-images.githubusercontent.com/97881084/149920805-5d122e8b-4822-401c-acd1-2fb470186a4b.png)

A flight controller is basically a circuit board with a range of sensors that detect movement of the drone, as well as user commands. Using this data, it then controls the speed of the motors to make the craft move as instructed. To make a drone autonomous, this flight controller should be coded so that it can control the drone to do the task that is commanded from the software(user end).

### 2) DroneKit
DroneKit helps developers to create applications that can run on a UAV’s onboard companion computer and it can communicate with the integrated software 
the ArduPilot(or autopilot) flight controller using a low-latency link.

![image](https://user-images.githubusercontent.com/97881084/149921837-5972a7da-216a-4e9c-a9a9-62888193434a.png)

Onboard applications can significantly enhance the autopilot, by adding greater intelligence 
to vehicle behaviour, and performing tasks that are time-sensitive or computationally intensive (for example, path planning, 3D modelling). DroneKit￾Python can also be used for ground station applications, communicating with drones over a higher latency Radio Frequency-link.DroneKit API(Application programming interface) is compatible with drones that communicate using the MAVLink protocol. It runs on various operating systems like Linux, Mac OS X, or Windows. It provides programmatic access to a connected vehicle’s telemetry, state and parameter information, and enables both mission management and direct control over vehicle operations and movement. 

#### Features of DroneKit API 

- Get vehicle state/telemetry and parameter information. 
- Set vehicle state. 
- Connect to a drone (or multiple drones) from a script. 
- Receive asynchronous notifications of state changes. 
- Guide a UAV to specified location (GUIDED mode). 
- Send arbitrary custom messages to control the vehicle movement and other hardware (GUIDED mode). 
- Create and manage waypoint missions (AUTO mode). 
- Override RC channel settings. 


![QDC SITL](https://user-images.githubusercontent.com/97881084/149918722-a7767499-1d65-4630-87f0-b8afd1ece34e.png)
Figure : Simulated output from QGroundControl app(to track the drone in real time)


#### Used functionalities of DroneKit 

- Connecting to vehicle:

The connection to the vehicle (or multiple vehicles) is set up within the 
DroneKit script. Scripts import and call the connect() method. After connecting 
this returns a Vehicle object from which you can get/set parameters and 
attributes, and control vehicle movement
The most common way to call connect() is shown below: 

*from dronekit import connect<br/>
vehicle = connect('127.0.0.1:14550', wait_ready=True)* //Connect to the Vehicle (in this case a UDP endpoint)<br/>

- Connection status check:

DroneKit will no longer be running in MAVProxy so the scripts don’t need to monitor external thread.
The code below shows how to check the vehicle connection status.

*while not vehicle.armed<br/>
print " Waiting for arming..."<br/>
time.sleep(1)*<br/>

- To get vehicle location:

DroneKit uses an attribute with the *vehicle.location* attribute to provide location 
in global, global-ralative and local(NED)frames:

![image](https://user-images.githubusercontent.com/97881084/149917659-195ad3f5-f727-40e7-b49a-9ed00b172582.png)

- Takeoff and movement commands 

DroneKit-Python provides *Vehicle.simple_takeoff* and *Vehicle.simple_goto*. The simple_goto allows to optionally set the default target groundspeed and 
airspeed. Use Vehicle.airspeed and Vehicle.groundspeed to set/fix the default target speed used when moving with *Vehicle.simple_goto* (or other position-based movement commands). 

- Position control 

Controlling the vehicle by explicitly setting the target position is useful when the final position is known/fixed.


![OUT](https://user-images.githubusercontent.com/97881084/149918753-64a14eb5-68f0-4df4-9814-ff7499163414.png)
Figure : Real time tracking of drone's position(like altitude, orientation etc)

### RESULTS:

![IMG-20210722-WA0005](https://user-images.githubusercontent.com/97881084/149759767-9bba6a40-0a2e-472a-81c0-83c5611db51c.jpg)

