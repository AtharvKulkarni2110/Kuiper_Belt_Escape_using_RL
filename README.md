# Kuiper_Belt_Escape_using_RL
  ### KuiperBelt Escape emvironment using Q-learning
  
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


# **Graphs**

![training_plots_and_sma110000](https://github.com/user-attachments/assets/0da93533-8d7a-42a1-8143-c0df56d87a1e)

