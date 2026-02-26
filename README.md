# Machine Shop Optimization
Provide a scheduling solution for machine shops using linear programming to maximize profit while taking into consideration resource limitations such as available working hours and raw materials. 
Machine Shop Optimization Using Linear Programming

### Sunny Chen ### 

11/16/2024

### Introduction: ###
The purpose of this project is to provide a scheduling solution for machine shops using linear programming to maximize profit while taking into consideration resource limitations such as available working hours and raw materials. Machine shops must meet customer requirements and focus on delivering products in a reasonable time frame while also managing time and resources to maintain a stable and profitable business. Many machine shops take orders from multiple customers and must manage their production schedule to ensure they’re maximizing profit while also being able to manufacture all the parts they accept from customers. Using linear programming can allow a machine shop to plan ahead and have expectations for the business as well as their customers. 

### Project Specifications: ### 
The objective of this project is to maximize the total profit from producing parts while ensuring that the material and time constraints are included. We also want to optimize the allocation of part production so that we can produce the parts in the minimum number of days required. We will be simulating a production backlog of a machine shop and using linear programming to optimize the profit and time available to create a production schedule that allows completion of all parts. A list of 20 parts is created with attributes such as profit, cycle time, material type, and amount of material required. There are constraints set on available working hours and material availability. There will be a set 8 hours per day, three different types of materials, steel, aluminum, and stainless steel, and a set amount available for each of the three types of materials. We will create a schedule that optimizes the profit based on these constraints and show the total profit achieved based on the schedule. We will also be able to determine the remaining number of materials after production. 

### Implementation: ### 
We will first create a list of parts that will simulate a backlog of customer orders at a machine shop. Each part will have a number as its ID along with a profit value, cycle time to produce the part, material type, and amount of material required. There will be a list of resources which we will use as our constraints that include the material types, the amount available of each material, and the number of hours available in a day. We will then calculate the minimum number of days required to produce all the required parts. This is done by adding up the time required for each part for a total time for completion. We will then divide this total time by the time available for each day which is 8 hours. 
We will be using the PuLP library for solving this optimization problem. We will use LpProblem and LpMaximize to set up the problem and indicate that the goal is to maximize the profit. This method will also take into consideration time optimization so that we are not only looking at maximizing profit but also making sure that we are producing the most amount of parts as possible per day. Decision variables such as the start time of each part, and two binary variables to indicate whether a part has been completed and whether a part is scheduled for a specific day. We will then create an objective function to add the profits up for all completed parts while maximizing the profit. Before we solve the problem, we will define the constraints such as material availability, ensuring a part is only assigned to a single day, setting the daily work limit and making sure that earlier days are filled before moving on to the next day which prevents idle times and gaps in scheduling. The output of the code is shown in the Google CoLab HTML document linked in the reference section.
<img width="468" height="279" alt="image" src="https://github.com/user-attachments/assets/a8070186-12ac-4ccc-bab7-b05b03801494" />
<img width="468" height="279" alt="image" src="https://github.com/user-attachments/assets/f0aacbeb-9ee5-4c9b-aea9-7b3c83ddba3e" />


<img width="519" height="408" alt="image" src="https://github.com/user-attachments/assets/e22ee649-b073-46e9-a38a-b3c96a861fe5" />


In the equations above the x_i value corresponds with the part ID. For steel, we have 10 units available and if we want to make parts using steel, parts #1 and #4 require steel to be produced. So, the constraint for steel is that it takes 3 units for part #1 and 4 units for part #4 and that it must be less than or equal to the total units of steel available. 

For the time constraints, it is the cycle time per part that must be less than 8 hours available per day. 
The optimal solution is to produce part 1, 2, and 3 which gives us:

Z=200+250+150=$600

This is also the solution that gives us the greatest number of parts produced. It is also possible to only produce part 1 and 5 for a profit of 600 but we will only produce 2 parts.

Z=200+400=$600

<img width="468" height="279" alt="image" src="https://github.com/user-attachments/assets/60137590-7547-4102-ab12-4cf5c1b379e3" />
<img width="468" height="279" alt="image" src="https://github.com/user-attachments/assets/6f44698e-2a5a-405e-87c5-5838b5f66862" />

Summary:
	As we can see from our results, linear programming can be applied to optimize machine shop scheduling. PuLP was able to efficiently maximize profits while also taking into consideration constraints such as time and material. It is also able to optimize the schedule so that we can produce the greatest number of parts per day and complete the parts required in the shortest amount of time available. There are some limitations to the current implementation as we are only using a hard coded list and not accounting for the different shapes of stock material or multiple machine availability in a machine shop. 
