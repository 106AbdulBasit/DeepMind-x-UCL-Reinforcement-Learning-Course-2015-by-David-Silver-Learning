# RL-Course-by-David-Silver
- look at the above picture
- ![Many Faces](https://user-images.githubusercontent.com/36159918/210170118-1707880a-3111-447d-8309-744fa3824234.PNG)
- Reinforcement Learning is  set of Intersection of many different science.
- What is rienforcment learning?
- Its a Science of descion making.
- In computer science its come under the section of machine learning
- In Engineering its come under the name of Optimal Control
- Optimal control descides the best sequence of action for any task to get the best result
-  In Neuro Science the great research is that how human brain works , Neuro transmit the dopamine actually reflects to on of the main algorithm called Reward system
- In psychology the study of classical/operant conditioning which is   about how animal behaviour when we gave some rewards. Its also underline in the RL
-  In mathamatics the study which is named as Operations Research , which focous on the study of optimal control.
- In  Economics the study of game theory/ utility theory and bounded rationality which focous on how and why people made descions if they want to optimise there utility.
- Branches of Machine Learning
- ![Branches](https://user-images.githubusercontent.com/36159918/210170187-c099fe93-7088-48f4-9e8f-2f88c92b6db2.PNG)


## Charchteristics of Rienforcment learning.

- Few things that differentaiate supervise learning and unsupervise learning from RL
- There is no supervisor , only a reward signal
- NO one tells you about the right action to take based on eror pardigm
-  Feedback delayed Results are not instant , the out come can be come after many steps . may be positive or negative.
-  Time reallly matters (sequential non,ii data), its a dynamic sysytem the agent move in the world.
-  Agent's actions aect the subsequent data it receives
-  agent infuence on the data , active learning process

## Examples of Reinforcement learning
- Fly stunt manoeuvers in a helicopter
- defeat the world champion at backgammon
- Manage the investment portfolio
- Control a power station
- Make a humanoid robot walk
- Play many different Atari games better than humans
-  Rougly takes 3, 4 days to train per game on GPU in order to achive human level performance


## The RL Problem

- **REWARD**
- A reward Rt is a scalar feedback signal
- Basically a number, sum the rewards 
- Indicates how well agent is doing at step t
- The agent's job is to maximise cumulative reward
- Reinforcement learning is based on the reward hypothesis
- All goals can be described by the maximisation of expected
cumulative reward
 - What about if the goal is to reach to the goal at possible shorter amount of time?
  - ans :  Typically the reward signal to be minus 1 per time step
  - at the termination of the episode at the end when you actually achive your goal you stop and now its a well defined objective to maximize the cummilative award  basically the minimis the time to reach its goal



## Examples of Rewards

- Fly stunt manoeuvres in a helicopter
  - +ve reward for following desired trajectory
  - -ve reward for crashing
- Defeat the world champion at Backgammon
  - +=􀀀ve reward for winning/losing a game
  - Manage an investment portfolio
  - +ve reward for each $ in bank
- Control a power station
   - +ve reward for producing power
   - 􀀀ve reward for exceeding safety thresholds
- Make a humanoid robot walk
   - +ve reward for forward motion
   - 􀀀ve reward for falling over
- Play many diferent Atari games better than humans
  - +=􀀀ve reward for increasing/decreasing score
- How to make a uniform framework for these kind of tasks uning RL



## Sequential Decision Making
 - Goal: select actions to maximise total future reward
    - Goal unify them based on reward
 - Actions may have long term consequences
 - Reward may be delayed
 - It may be better to sacrifce immediate reward to gain more
 - long-term reward
    - cant be greedy 
 - Examples:
  - A fnancial investment (may take months to mature)
  - Refuelling a helicopter (might prevent a crash in several hours)
  - Blocking opponent moves (might help winning chances many
    moves from now)
    
    
    ## Agents and Enviroment
    - ![Agents and enviroment](https://user-images.githubusercontent.com/36159918/210171726-370e179d-cbeb-41a0-9140-ead050e3f888.PNG) 
    - Big Brain represent the agent
    - The agent will be responsible for the actions
      - for instance what action should be take while waling a robot
      - what investment should be made
    - every step is see through the obeservation
    - reward signal tells that how good is the descion

    - ![wordloop](https://user-images.githubusercontent.com/36159918/210171876-587b2455-47a9-41ce-87f1-e07cc3b38c9b.PNG)
    - The enviroment is world , we have m


   

 



