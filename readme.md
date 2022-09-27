# Rear Wing for UTD FSAE Fall 2022

Slow is smooth and smooth is fast is a great idiom, but might sound backwards when designing a race car. Using the CFD capabilities of the cloud platform SimScale and intelligent airfoil design, I develop a high performance rear wing for a  Formula SAE car.


# Airfoil Design

The general goal of passive aerodynamic elements is to optimize their shape to serve their required function. This might mean a more tapered profile or varying the curvature of the under side. Every airfoil there could ever be has already been designed, dimensions parametrized, and categorized according to a 4 digit number.   If airfoils are wings and wings create lift, why would we want an airfoil. All you have to do to get downforce from an airfoil is flip it over!

For this application we want an airfoil with a low Reynolds number(low is smooth flow, high is turbulent flow) to minimize drag and avoid any unwanted torques on the car from turbulence. For this application and based on previous research we will use the BE-50 airfoil, which has a low Reynold's number of 50,000.
![BE-50 Airfoil Profile](https://i.imgur.com/TnH77gI.png)

## Mock up in Fusion 360

A single element wing is effective, but to allow for a possible active rear wing in the future, we will create a two wing system. After downloading the .dat file from an [airfoil repository](http://airfoiltools.com/airfoil/details?airfoil=be50-il), we use a [script](https://apps.autodesk.com/FUSION/en/Detail/Index?id=3044478757760121899&os=Win64&appLang=en) for Fusion 360 which imports the profile of the BE-50 airfoil into a sketch.
![enter image description here](https://i.imgur.com/1EjofD0.png)
We repeat twice to place both wings on the same sketch plane. The pitch of the upper wing is a good approximation of where an active wing might be at a high speed. Then we extrude the sketch to a width of 1000 mm, the maximum width of the rear wing.
![enter image description here](https://i.imgur.com/afpNnb7.png)

## Evaluating using CFD

To calculate the performance of our wing system we will use a cloud simulation platform called SimScale. To setup our simulation first we need to export our design from Fusion360 in an Inventor file format.
![enter image description here](https://i.imgur.com/qzNSRwP.png)
Then we will start up a new project in SimScale and import our geometry.

![enter image description here](https://i.imgur.com/2A8SzL3.png)
![enter image description here](https://i.imgur.com/IjaiQxj.png)
For instructions on how to set up the CFD simulation, refer to the SimScale [tutorial](https://www.simscale.com/docs/tutorials/aerodynamic-simulation-vehicle/) for a full car. The settings and set up they use is similar to what our wing requires.

**Basic Steps for the CFD:
**	
 - Define flow volume
 - Determine boundary conditions
 - Results Control(calculating lift and drag)
 - Mesh/Mesh Refinements
 - Full Run
 - Analyze Results
 
Here is an animation from after the simulation, using a particle trace to determine if there was turbulent flow separation behind the upper wing.
![enter image description here](https://i.imgur.com/PMrcHBN.gif)

The particle trace doesn't tell us much, the flow is relatively smooth and remains intact without major separation. Lets look at the drag and lift results.
![ ](https://i.imgur.com/MNLUaHO.png)
After the simulation stabilizes, there is a periodic ripple in the drag and lift values. Definitely something not right going on.
Lets change the angle of attack of the upper wing to be more streamlined.
New Version:
![enter image description here](https://s5.gifyu.com/images/resultde2e6662aff28b12.gif)
Much more streamlined flow and lets take a look at the actual performance data.
![enter image description here](https://i.imgur.com/36S1EtV.png)
As we can see there is no periodic ripple from turbulence. 
## Analyzing Results and Qualification As A Full Wing
Comparing the drag and lift coefficients from the two designs.

High AOA:
Drag Coefficient: 0.94 ± 0.8
Lift Coefficient: -2.5 ± 0.11

New Design(Lower AOA):
Drag Coefficient: 0.4 ± 0.3
Lift Coefficient: -9.2 ± 0.5

Reynolds number is an internally calculated number in CFD but we can assume that the second wing design, with its minimal flow separation and low turbulence even at the point the boundary air rejoins the freestream, will have a low Reynolds number. The airfoil profile BE-50 was chosen in part because of its low Reynolds number and free stream neutrality.

