In this project, two algorithms are applied to a MATLAB simulation of a mobile robot. Using the robot's sensor measurements and odometry measurements, an occupancy grid was constructed for the purpose of mapping. Also, a particle filter was designed to estimate the location of the mobile robot at each time step. 

To observe the occupancy grid and particle filter algorithms in action, download the results folder. This folder contains error plots as well as .avi files that illustrate the evolution of these two algorithms. 

## Occupancy Grid Mapping:
The mobile robot yields laser scan information, the mobile robot’s location in an inertial frame, and the mobile robot’s orientation. To accomplish the task of constructing an occupancy grid, a simple algorithm was designed. At each time step, a transformation matrix that transforms points from the robot’s frame into the inertial frame is constructed. Then, each laser in the scan corresponding to the current time step is iterated over. The points at the end of each laser are indicative of obstacles. As such, the point at the end of the laser being analyzed is translated into coordinates and increases the likelihood that that particular map entry is occupied. Each subsequent point prior to the end of the laser is also translated into coordinates. These points increase the probability that those particular squares are unoccupied. After every laser is iterated over, the map is thresholded. Squares that are more likely to be occupied are marked as occupied and squares that are more likely to be unoccupied are marked as unoccupied. Figure 1, below, is the result produced for this section:

![](results/ass2_q2.png)

## Particle Filter Location Estimation:

