# Pioneers

# Group project revolving around the UWA pioneer robots

#Tasks to complete
Your robot has landed on an unknown surface and it must explore the area and log any
details for the arrival of future modules. In order to safely deploy the modules a 15x15
meter area around the initial landing place needs to be searched. Your robot must be
able to identify certain colour markers noting the location and colour. There are several
areas of interest that will be marked as waypoints and after the initial exploration the
robot will need to inspect them a second time as quickly as possible. Your team will
need to build a simulation as well to demonstrate the robots capabilities before real
world testing can begin.
1. For safety reasons, implement a Bluetooth link between the robot’s on-board PC
and a gamepad controller for manual instruction:
a. Button ‘X’ enables autonomous mode.
In autonomous mode, use the back pedals (R2 or L2) as a dead-man
switch. If released, the robot has to stop.
b. Button ‘O’ enable manual mode (disable automated mode).
In manual mode, the steering controls can be used to manually drive the
robot forward and left/right.
2. From a set home position you need to explore an unknown area, mapping it as
you drive.
3. Within the unknown environment are a number of hand drawn numbers, as seen
in Figure 1. These numbers will be located randomly around the environment on
different surfaces at approximately knee height. You will need to use image
recognition to determine the number and note its location.
Figure 1: Hand drawn numbers1.
4. Use the Lidar sensor to avoid collisions with stationary objects that may be
located in the area.
5. You should take photos and note the location of any yellow or red colour
obstacles in the area as these are of special interest to the team back home.
6. Avoid collision with moving obstacles and record an incident if an emergency
stop is needed (an emergency stop should occur if a moving object comes within
1m of the robot). Note you don’t need to press the estop, this is a software
requirement.
7. If a estop event occurs, save the last 5 seconds of recorded data so that it can be
reviewed by the team.
8. Upon completion of mapping the unknown environment, print the map, all marker
photos and locations to the screen.
9. Implement a user interface with graphics and text on the robot’s display that
always displays the robot’s internal state and its intended actions.
10. Once your first run is completed you will be given 3 waypoints noted by the hand
drawn numbers to drive to. Your team must plan the fastest path to each of these
locations and the path back to home. Your robot must then drive through the
1 https://www.digitalocean.com/community/tutorials/mnist-dataset-in-python
unknown environment a second time to each of these waypoints and return
home in the fastest time possible.
11. Display the robots planned path graphically to a screen.
12. Your system should record the drives so it can be review again offline.
