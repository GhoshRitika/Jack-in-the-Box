# Jack-in-the-Box

https://user-images.githubusercontent.com/60728026/208178932-50984961-2988-4fab-b0ee-a10eeda87e9f.mp4

## Description:
There are 2 bodies, a dice and a box, with 6 degrees of freedom and is planar. The dice is inside the box and the box is moved by external force. This causes the dice to bounce inside the box. The figure below shows the frames of the bodies w.r.t world.

![Figure 1.1 The world, box and dice frames](https://user-images.githubusercontent.com/60728026/208177482-74399fa9-c42a-4b20-b09b-dfef9c08fd13.png)

## Calculations:
Euler-Lagrange equations- The rotational kinetic energy was for the box and the dice was calculated using the equation shown below, using the body velocities of the box and the dice along with their respective inertia tensors. The Lagrangian was calculating the difference between this rotational kinetic energy and the potential energy of the system.
This Lagrangian is the LHS of the Euler Lagrange equation. The external force matrix is the RHS.

![Figure 1.2 Rotational Kinetic energy formula](https://user-images.githubusercontent.com/60728026/208178042-0cc2c2c2-3ae8-41dd-85c5-305d267b4755.png)

Impact- There were 16 impact conditions which considered impact between each corner of the dice with every side of the box (in the x and y coordinates). Figure 1.3 shows the 4 coordinates of the dice and their frames. Each corner of the dice with respect to the box {B} frame will experience impact when it is at (length of the box)/2 in any of the 4 directions from {B} frame.

![Figure 1.3 Dice in box with all frames](https://user-images.githubusercontent.com/60728026/208178252-ee977e19-6da1-4aec-acfd-f3499d836a60.png)

Impact Update- There are 16 sets of 7 impact equations using equations shown in figure 1.4. In the simulate_with_impact function when a phi value is within threshold value, that set of impact equations are used to get velocities.

![Impact Equations](https://user-images.githubusercontent.com/60728026/208178584-a60b6a5c-ddf7-44b2-8be0-73bd0e47ef08.png)

### Note:
No constraints were added to the system as the impact conditions take care of the main constraint, i.e the dice should be within the box.

## Results:
The resulting animation is as expected of a dice bouncing inside a moving box. The external force in the y direction negates the force due gravity on the box, the force in the theta direction turns the box. Initially the dice falls due to gravity while the box turns, after that the dice hits one of the walls, bouncing off and the cycle keeps repeating itself. 
