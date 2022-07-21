

1. cumulative_reward_by_robot_test

This is ploted by the reward in the real training process.
-1 for move, -2 for missing the goal, 20 for goal, -20 for falling down(never happen)
G = r1+r2+...+rt
The agent try to visit the least visited states to explore and learn the reward function.
it starts with just moving in or out first, because of greedy policy(when all Q is zero at the beginning) 
so the curve keeps droping, Then it begins to explore shotting states. 
Doing sth like shoot-move-move-shoot as shown in the video 

This process is similar for different goal keeper, that's why there are 3 drops(because we set three goal keeper positions)
After all the states are visited, the convergence will be reached by value iteration, so the training stops.

2. cumulative_reward_by_simulation is the cumulative reward by a kind of simulation
We are doing it because we want to test the situation after convergence.
but the reward is given according to the learned reward by DT in the real test on the robot

Another little difference is in the simulation, we stopped the training after max steps.
While in the experiments on the robot, we stopped the training once the Q values are converged
The reason for that is to show after convergence, the robot will keep doing the same kick in the same goal keeper.
That's why the curve keep going up after convergence, this is the key information in this diagram.



