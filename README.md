# Kuiper_Belt_Escape_using_RL
  ### KuiperBelt Escape environment using Q-learning
  
  ![1-ezgif com-resize](https://github.com/user-attachments/assets/df35d308-eb91-4565-871d-32c604e288cf)


  

  -**Environment Documentation** : https://github.com/jdegregorio/gym-kuiper-escape

  
  **1)Observation Space:**
    Agent sends off n beams of the virtual lidar system.
    observation_space = array(2*n ,1) 
    The observation data (for each beam in the lidar array):
    Distance (i.e. radial distance from player to terminating point of lidar beam)
    Collision detection
    -0 if terminated at edge of the screen, or at max radius distance
    -1 if collided with a rock

    
  <img width="264" alt="lidar" src="https://github.com/user-attachments/assets/57931408-1fda-4909-a591-12215ed69614">




    
   **2) Action space-**

   
  |          |              |        
  |----------|--------------|
  |    0     | Don't move   | 
  |    1     | Up           |
  |    2     | Right        | 
  |    3     | Down         |
  |    4     | Left         | 



 **3)Reward-**

  1)Inversely related to the distance of agent from the center-
    Reward=1/(.65+dist_from_centre) 
    
  2)Penalties for Collision

**Algorithms:**
Reinforcement learning offers a variety of algorithms that are useful for solving problems in model-free environments, where the agent does not have prior knowledge of the environment's dynamics. For this project, Q-learning was chosen as the primary algorithm because of its faster optimization rate (or convergence) compared to many other methods. Q-learning is an off-policy algorithm, meaning it learns the optimal policy by considering actions that may not necessarily follow the current policy. This property makes it highly effective for balancing exploration and exploitation. Since Q-learning focuses heavily on exploring the environment to gather more information, it aligns perfectly with the needs of this project, where the agent must adapt and improve its navigation strategies in a dynamic and unknown setting.

**Learning Process:**
Initially Agent takes random actions and mostly traverses along the edges navigating and exploring the environment

![1(i)](https://github.com/user-attachments/assets/04b5f4f8-ec50-4d76-a052-3f2506a69553)



This is not desirable because when agent traverses along edge, the LIDAR system is not working efficiently.

![2](https://github.com/user-attachments/assets/157638ee-501c-4773-9540-1e71622ad4ef)

After a certain number of episodes, the agent begins to improve its navigation skills within the environment, demonstrating a more strategic approach by effectively avoiding rocks.

![3](https://github.com/user-attachments/assets/272c0a64-3c14-492d-9212-a981d0920e3b)


![4](https://github.com/user-attachments/assets/413c2dc8-f12e-4691-8f8b-66a2d7022086)

After 12k episodes, the agent has now learned enough, navigating through the environment, skillfully avoiding the rocks with precision. Its movements have become more efficient, showing a clear understanding of the surroundings and an ability to adapt to challenges.


**Convergence problem with continuous observation space:**
When we consider continuous observation space (For eg: 2.21 and 2.2134 are different distances in observation space) it results in memory overflow and consequently we get an insufficient Q table for convergence. Thus to reduce our computational load , we discretized this continuous observation space which provided us with only few values for our policy convergence and hence made it more efficient and faster.


# **Graphs**

![training_plots_and_sma110000](https://github.com/user-attachments/assets/0da93533-8d7a-42a1-8143-c0df56d87a1e)


![Testing_graph](https://github.com/user-attachments/assets/6724fc08-5eed-48ff-b312-e43d2515ace4)


