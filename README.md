# MultiRobotSystem-AllocationOfTasks
Optimizing the allocation of tasks to robots in Alloy considering: 1) area covered by the robot to complete the allocated tasks; and 2) managing working time "fairly".


## First results


Robots, r1-r4, are shown in red squares. A robot consists on the following relations:
* ![image](https://user-images.githubusercontent.com/63869574/132561119-0bc64d4d-bff9-4abe-9da8-ba5ef7c8af3a.png) : capabilities of the robot
* ![image](https://user-images.githubusercontent.com/63869574/132563680-e24c63ac-e399-4258-b08d-b5c2d5880f22.png) : x and y are two relations showing the position of the robot.
*  ![image](https://user-images.githubusercontent.com/63869574/132561280-a2236c36-ef18-4527-b870-220d3a4415b0.png) : x distance of the area covered by the robot to complete the tasks in each allocation
* ![image](https://user-images.githubusercontent.com/63869574/132561444-26da06e2-ff01-44a2-9588-d49cce2f5de0.png) : y distance of the area covered by the robot to complete the tasks in each allocation
* ![image](https://user-images.githubusercontent.com/63869574/132563836-687b2c02-5aab-4d35-9ff2-5c139cfdb2a1.png) : total work time (sum of the time of every atomic tasks allocated to the robot)

The next Figure shows the projection over Mission Tasks and Composite Tasks (i.e., they are not shown in the figure).

![image](https://user-images.githubusercontent.com/63869574/132566305-dedb6e93-56f3-4d27-bc52-b37f3928b587.png)

Figure 1. One of the MRS allocation model.

For this simple example, I placed atomic tasks "at1-at4" to be done in position at1=(1,1), at2= (2,2), at3=(3,3) and at4=(4,4).
(Notice that the names may seem different as they have an index, e.g., at1 have 3 instances: at1_0, at1_1, at1_2.)
Also, robots are placed in r1=(1,1), r2=(2,2), r3=(10,3), r4=(4,4).
Notice that r3 is placed in (10,3). This is just to test the total area parameter.

![image](https://user-images.githubusercontent.com/63869574/132567170-dc4aee2d-cf8d-4d9a-bc19-d61fc00c05a5.png)

Figure 2. Relations in orage show "x" position of the robots r1-r4.


### Results
* The (x,y) distances of the area covered by each of the robots is calculated.
* The total time a robot will be working on the tasks.


![image](https://user-images.githubusercontent.com/63869574/132567470-b72ac186-1c7b-4552-84d7-92af40a91132.png)

Figure 3. Total distance X covered by each the robot for the specific allocation show in Figure 1.

![image](https://user-images.githubusercontent.com/63869574/132567557-6b5028d5-2e2c-4df5-8b0e-1866f7874b69.png)

Figure 4. Total distance Y covered by each the robot for the specific allocation show in Figure 1.

![image](https://user-images.githubusercontent.com/63869574/132567684-8a3ce86d-c499-41a0-8d72-a6305a2a7629.png)


Figure 5. Total time for the robot to work on the allocated tasks, for the specific allocation show in Figure 1.
