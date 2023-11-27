# The-Sykkle
World's best Stationary Bike KIT

## Planning

<details>
<summary>Check out our Project Planning!</summary>

### Success Criteria

Criteria to determine if our project is a success:

1) Drone is able to take off and fly
2) Drone is able to be controlled by a remote
3) Drone can safely land
4) Data can be safely extracted and read

### Available Materials

Most of the materials we would need for our project we have in our lab. Any additional materials we need can be bought from Amazon. Currently, the only planned purchase is the drone motors. 

### Materials List

1) ABS 3D print material for frame
2) Ninjaflex 3D print material for propellor guards
2) Rasberry Pi Pico
3) Altimeter
3) 500 mAh LiPo Battery
4) 4 motors
5) Custom Circuit board
6) Other small props (undecided)

### Code

The most difficult challenge to overcome in code is to be able to program the joysticks on a controller to accurately control the drone, and get a stable PID working.

#### Motor Control

The diagram below shows how the motors will need to operate in order to move the drone is specific ways

![download](Images/download.png)

#### Code Technicalities

I found this code snippet from online that moves a drone with joysticks using arduino:

``` c++

 LR = analogRead(A0);     // read analog joystick voltage from pin A0, returns an integer from 0-1023
 UD = analogRead(A1);     // read analog joystick voltage from pin A1, returns an integer from 0-1023
 LR = 5*LR/1023;          // convert to a voltage from 0-5V
 UD = 5*UD/1023;          // convert to a voltage from 0-5V


// convert analog voltages to motor speeds
 motor1speed = defaultSpeed+speedChange*(a*UD-a*LR);
 motor2speed = defaultSpeed+speedChange*(a*UD+a*LR-b);
 motor3speed = defaultSpeed+speedChange*(-a*UD+a*LR);
 motor4speed = defaultSpeed+speedChange*(-a*UD-a*LR+b);
  
```

Here's some links on PID to learn:

[PID Link 1](https://blog.devgenius.io/flying-a-drone-with-python-pid-control-7001a41f54ac)

[PID Link 2](https://www.technik-consulting.eu/en/optimizing/drone_PID-optimizing.html)

[PID Link 3](https://www.mathworks.com/videos/understanding-pid-control-part-1-what-is-pid-control--1527089264373.html)

### Build

#### Design

We are trying to constrain the size and mass of our design as much as possible to ensure maximum flight smoothness. We are referencing the [DJI Tello](https://m.dji.com/product/tello) for our rough dimensions. 

We have prototyped 2 rough drone designs in OnShape

First design Idea: 

![firstdronedesign](Images/firstdronedesign.JPG)

Second Design Idea:

![secondronedesign](Images/seconddronedesign.jpg)

#### Special Choices

1) We are using Tello Drone specific motors for easy specification accesebility. 
2) During testing, we will make the frame out of acrylic to be conscious of material used in 3D printing (we will need to make many iterations and don't want to waste material)
3) In our final design, we will utilize ABS material for our frame, but use Ninjaflex for our propellor guards and landing buffer. This allows us the have slightly more flexibility and durability. If the drone crashes, the ninjaflex could prevent it from cracking completely.
4) Our propellor gaurds will be made detachable to the main frame (snap fit). If the drone crashes, the chances are more likely it will land on the propellor guards than any other part of the drone, so making the guards detachable allow us to only need to reprint a piece rather than the entire frame.

### Risk Mitigation

| Risk  | Possibility | Mitigation |
| ------------- | ------------- | ------------ |
| Drone Loses Control  | HIGH | Add a Killswitch |
| Overheating | HIGH | Wear gloves in post flight recovery |
| Frame cracks | HIGH | Build detachable propellor guards |
| Drone activation unknown | Medium | Add ON light(green) |
| Drone Explodes  | Low  | Have fire extinguisher on Standby |


| Testing Risks | Possibility | Mitigation |
| ------------- | ------------- | ------------ |
| Doesn't respond w/ controller | HIGH | Build controlled testing piece (string) |
| Frame reconstruction | Medium | Laser cut body & 3D print motor part |


### Proposed Schedule & Milestones

| Week  | Tasks | Milestone |
| ------------- | ------------- | ------------ |
| 11/27 - 12/15 | General - Work on prototype and planning finalization | Planning Finalized and Progress on prototype |
| 12/18 - 12/31 | Winter Break | Chill |
| 1/1 - 1/5 | Build Drone in CAD / PID Stablization Code | No Milestone / Have stabilizing motors |
| 1/8 - 1/12 | Continue CAD Drone / Troubleshoot PID & Work on Joystick Control | Print 1st prototype drone / Finalize PID Stability |
| 1/15 - 1/19 | Assemble and Test 1st prototype[^1] | Complete Prototype |
| **1/20** | **Quarter Ends** | **Try to have a Prototype in Testing** |
| 1/22 - 1/26  | Reiterate design / Debug & Improve code  | No Milestone |
| 1/29 - 2/2 | Assemble and Test 2nd Prototype[^2] / Test Joystick Code | No Milestone |
| 2/5 - 2/9 | Continue iterating Design & Code | Complete 2nd Prototype if not already done |
| 2/12 - 2/16 | Work towards building Final Prototype[^3] | Finish Final Prototype (2/28) |
| 2/19 - 3/31 | Design Refinement & Final Tweaks | Ready to launch |
| **3/29** | **Quarter Ends**| **COMPLETED PROJECT** |
| **TBD** | ** UVA PRESENETATION | **PRESENT FINAL PROJECT** |


[^1]: First Prototype is to be a controlled flight (attached to string and not actually free flying)
[^2]: Second Prototype is to be a slightly free flighted prototype (will not be flying above 5 feet)
[^3]: Final Prototype is a fully functional drone prototype very similiar to the final product

 </details>




## Week 12

### What we accompished/discovered

This week we focused on refining our design/sketches. We finished an onshape design for the main back piece of our project, as well as a prototype for the front piece. We also made sketches for these pieces which will act as a blue print once we start building. We also contacted our UVA Mentor, Nicholas, to schedule a meeting and mull over ideas. We decided the frame design we are going with, and our design for the front attatchment piece. 

One issue we've ran into is how we will secure the front wheel of our bike in a stable and efficent fasion. Originally we had the idea to use a spring powered snap fit device to hold in the wheel, but Mr. Miller helped us realize this wouldn't work well because any movement of the bike would destablilize this. We also thought about a screw powered tightening device, but this also seemed like excsessive hassle. We landed on a design involving a 3 3D printed piece's that will hold different bike tire sizes with a perepidicular wall that will have a slot for the bike wheels. 

One thing that went well was our brainstorming. We were able to finalize a desgin that will allow us to build our protoytype next week. We struggled with staying on task 100% of the time,

<img src="Images/FrontPiece.PNG" alt="FrontPiece" width="300">
(Front Piece)

<img src="Images/Backpiece.PNG" alt="BackPiece" width="300">
(Back Piece)


### Future plans

Next week we plan to start building our prototype. We will build the frame of the back piece out of wood, 3D print the neccesary parts of the front piece, and then build the front pieces frame out of wood. We intend to finsish this intial protype next week, and move onto building the generator piece of our project. 

