# Autonomous-Driving-RL
### 1) DQN Model built on Discrete Actions and primitive reward function : [DQN_Discrete_drive](https://github.com/akjayant/Autonomous-Driving-via-RL/tree/main/DQN_Discrete_drive)
    # ver 1.0
    single path concat - Concat CAMERA and LiDAR frames and extracts features froom it.
    # ver 2.0
    Uses 'state' which contains lateral distance error,speed, presence of vehicle infront etc observation from environment as well.
    multipath - Treats CAMERA and LiDAR frames seperately, extracts features from respective CNN and then concat.
    single path concat - Concat CAMERA and LiDAR frames and extracts features from it.
    
      - Does okay on straight roads & slightly curve roads and follows lane on roundabouts occasionally.
      - Fails on sharp turns.
      - Avoids collisions after training (when speed is slow) but during explorations,it does collide.
      - At faster speeds, collision still occurs.
     # ver 3.0
     Safe exploration during training -
     python safety_train.py False
     python saftey_train.py True
     python train.py
      - Explores safely than previous versions during training. (Applies brakes when out of lane/ obstacle ahead in same lane).
      - at faster speed collsion still occurs. Requires better vision features like semantic segmentation, depth map etc. and longer past frames.
     # ver 4.0 
      Safe Exploration + Better Vision features + More past frames in state represenation - WIP

ver 2.0 -
![p](https://github.com/akjayant/Autonomous-Driving-via-RL/blob/main/DQN_Discrete_drive/ver%202.0/Single%20path%20concat/20201209_001339.gif)

### 2) DDPG Agent built on contionous actions and primitve reward function -[DDPG_Continuous_drive]
