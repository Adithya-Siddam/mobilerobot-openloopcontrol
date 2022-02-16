# MobileRobot-Openloopcontrol
## Aim:

To develop a python control code to move the mobilerobot along the predefined path.

## Equipments Required:
1. RoboMaster EP core
2. Python 3.7

## Procedure

### Step1:
 Start the coding.

<br/>

### Step2:
From robomaster import robot

<br/>

### Step3:
Initialize the type

<br/>

### Step4:
Run the program to move the robo moster through our condition

<br/>

### Step5:
Close the program.

<br/>

## Program
~~~
from robomaster import robot
import time
from robomaster import camera

if _name_ == '_main_':
    ep_robot = robot.Robot()
    ep_robot.initialize(conn_type="ap")

    ep_chassis = ep_robot.chassis
    ep_led = ep_robot.led

    '''
    x = x-axis movement distance,( meters) [-5,5]
    y = y-axis movement distance,( meters) [-5,5]
    z = rotation about z axis ( degree)[-180,180]
    xy_speed = xy axis movement speed,( unit meter/second) [0.5,2]
    '''
    ep_camera = ep_robot.camera

    print("Camera streaming started...")
    ep_camera.start_video_stream(display=True, resolution=camera.STREAM_360P)    

    ep_chassis.move(x=1.5, y=0, z=0, xy_speed=0.70).wait_for_completed()

    ep_chassis.drive_speed(x=0.2,y=0.1,z=-10)
    time.sleep(15)
        
    ep_chassis.move(x=1.5,y=0, z=0, xy_speed=0.70).wait_for_completed()   

    ep_chassis.move(x=0, y=0, z=90, xy_speed=0.70).wait_for_completed()

    ep_led.set_led(comp="all",r=255,g=0,b=0,effect="on")   
    time.sleep(2)
    
    ep_chassis.move(x=1,y=0, z=0, xy_speed=0.70).wait_for_completed()   

    ep_chassis.move(x=0, y=0, z=90, xy_speed=0.70).wait_for_completed()
    
    ep_led.set_led(comp="all",r=0,g=255,b=0,effect="on")   
    time.sleep(2)
    
    ep_chassis.move(x=0.5,y=0, z=0, xy_speed=0.70).wait_for_completed() 

    ep_camera.stop_video_stream()
    print("Stopped video streaming...")


    ep_robot.close()
~~~

## MobileRobot Movement Image:

![robo](./img/robomaster.png)

![OUTPUT](/IMAGES/img122.png)
![OUTPUT](/IMAGES/img119.png)


<br/>
<br/>
<br/>
<br/>

## MobileRobot Movement Video:

Upload your video in Youtube and paste your video-id here

[![IMAGE ALT TEXT HERE](2gJYAEUDXpk)]https://youtu.be/2gJYAEUDXpk

<br/>
<br/>
<br/>
<br/>

## Result:
Thus the python program code is developed to move the mobilerobot in the predefined path.


<br/>
<br/>

```
Mobile Robotics Laboratory
Department of Artificial Intelligence and Data Science/ Machine Learning
Saveetha Engineering College
```
