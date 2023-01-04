# Lecture 1: Introduction to Reinforcement Learning
  - Course outline
  - 1 Admin
  - 2 About Reinforcement Learning
      - [About RL](#aboutrl)
      - [Branches of Machine Learninh](#branches)
      - [Charchteristics of Rienforcment learning](#charcter)
      - [Examples of RL](#examplesofrL)
  - 3 The Reinforcement Learning Problem
      - [RL Problem](#rlprob)
      - [Rewards](#reward)
      - [Example of Rewards](#exampleofre)
      - [Sequential Decision Making](#sd)
      - [Agents and Enviroment](#agentsandenv)
      - [History and State](#hns)
      - [ Environment State](#nviromentstate)
      - [Agent State](#agentstate)
      - [Information State](#infostate)
      - [Fully Observable Environments](#fullyobserve)
     
  - 4 Inside An RL Agent
      - [ Major Components of an RL Agent](#majorcomponetinrl)
      - [Policy](#policy)
      - [Value Function](#valuefunct)
      - [Model](#model)
      - [ Example of Model](#examplesofmaze)
      - [Categorizing RL agents](#catgorizingrl)  
  - 5 Problems within Reinforcement Learning
      - [problems within RL](#problemsinRL)
      - [Exploration and Exploitation](#expexp)
      - [Prediction and Control](#pandc)
      
  # Lecture 2: Markov Decision Processes
    - 1 Markov Processes
    - 2 Markov Reward Processes
    - 3 Markov Decision Processes
    - 4 Extensions to MDPs
  
      

<a id="aboutrl"></a>
# About RL
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
<a id="branches"></a>

 # Branches of Machine Learning
- ![Branches](https://user-images.githubusercontent.com/36159918/210170187-c099fe93-7088-48f4-9e8f-2f88c92b6db2.PNG)

<a id="charcter"></a>
# Charchteristics of Rienforcment learning.

- Few things that differentaiate supervise learning and unsupervise learning from RL
- There is no supervisor , only a reward signal
- NO one tells you about the right action to take based on eror pardigm
-  Feedback delayed Results are not instant , the out come can be come after many steps . may be positive or negative.
-  Time reallly matters (sequential non,ii data), its a dynamic sysytem the agent move in the world.
-  Agent's actions aect the subsequent data it receives
-  agent infuence on the data , active learning process

<a id="examplesofrl"></a>

# Examples of Reinforcement learning
- Fly stunt manoeuvers in a helicopter
- defeat the world champion at backgammon
- Manage the investment portfolio
- Control a power station
- Make a humanoid robot walk
- Play many different Atari games better than humans
-  Rougly takes 3, 4 days to train per game on GPU in order to achive human level performance

<a id = "rlprob"></a>
# The RL Problem

<a id = "reward"></a>
# REWARD
- A reward Rt is a scalar feedback signal
  - Ultmately you have to pick an anction among the action , you have to weights the situation so it alwayas a conversion into a scalar view
- Basically a number, sum the rewards 
- Indicates how well agent is doing at step t
- The agent's job is to maximise cumulative reward
- Reinforcement learning is based on the reward hypothesis
- All goals can be described by the maximisation of expected
cumulative reward
 - What about if the goal is to reach to the goal at possible shorter amount of time?
  - ans :  Typically the reward signal to be minus 1 per time step
  - at the termination of the episode at the end when you actually achive your goal you stop and now its a well defined objective to maximize the cummilative award  basically the minimis the time to reach its goal


<a id = "exampleofre"></a>
# Examples of Rewards

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

<a id = "sd"></a>

# Sequential Decision Making
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
    
    <a id = "agentsandenv"></a>
    # Agents and Enviroment
    - ![Agents and enviroment](https://user-images.githubusercontent.com/36159918/210171726-370e179d-cbeb-41a0-9140-ead050e3f888.PNG) 
    - Big Brain represent the agent
    - The agent will be responsible for the actions
      - for instance what action should be take while waling a robot
      - what investment should be made
    - every step is see through the obeservation
    - reward signal tells that how good is the descion

    - ![wordloop](https://user-images.githubusercontent.com/36159918/210171876-587b2455-47a9-41ce-87f1-e07cc3b38c9b.PNG)
    - The enviroment is world , agent is interacting with the world
    - Enviroment is genrating the obeservation and reward
    - we dont have any control on the eenviroment except on the action

<a id = "hns"></a>
# History and State
- The history is the sequence of observations, actions, rewards
   - History is that what agent has seen so far
   - ht =  history, A = Action , O = Observation, R = Reward
  - Ht = O1; R1;A1; :::;At􀀀1;Ot ; Rt t = time step
- i.e. all observable variables up to time t
  -  remember we trying to build a brain
- i.e. the sensorimotor stream of a robot or embodied agent
- What happens next depends on the history:
  - The agent selects actions
  - enviroments looks what is recived 
  - The environment selects observations/rewards
  - its not very usefull beacuse we deal into nano seconds
- State is the information used to determine what happens next
- Formally, state is a function of the history:
    - St = f (Ht )
    - look at last four observation for example

- There are three definations of the state
<a id = "enviromentstate"></a>

# Environment State

- ![Enviroment state](https://user-images.githubusercontent.com/36159918/210174720-864d253a-33af-4e9d-bccb-fa0d33272ff7.PNG)
- The environment state Se t is the environment's private representation.
 - for eg atari game
- i.e. whatever data the environment uses to pick the next observation/reward
- The environment state is not usually visible to the agent
-  algorithm does not see the enviroment , its only see the observation the numbers 
- Even if Se t is visible, it may contain irrelevant information


<a id = "agentstate"></a>
# Agent State
- ![agent state](https://user-images.githubusercontent.com/36159918/210174965-854d0e3f-132f-4010-947b-8d16bd39752a.PNG)
- agent is a set of numbers which are in the algorithm 
- The agent state Sa t is the agent's internal representation
- That's a really goal how to pick pur agent
- i.e. whatever information the agent uses to pick the next action
- i.e. it is the information used by reinforcement learning algorithms
- It can be any function of
history:
- Sa t = f (Ht )

<a id = "infostate"></a>

# Information State
 - An information state (a.k.a. Markov state) contains all useful information from the history.
 - Defination A state St is Markov if and only if
    P[St+1 j St ] = P[St+1 j S1; :::; St ]
     - The probablity of the next state( P[St+1) condition on a state you are in (St) is the same as the probablity of next sate(P[St+1 ) if you show all the previous states (S1; :::; St ]) to the system 
 - \The future is independent of the past given the present"
    - H1:t ! St ! Ht+1:1
 - Once the state is known, the history may be thrown away
 - you can throw all the previous states and you can go with the current state every thing will be fine
 - i.e. The state is a suf cient statistic of the future
 - The environment state Se
 - t is Markov
 - The history Ht is Markov

- For example in the Helicopeter example . The angular velocity the speed can be a morkov state it doesnot matter what was the condition 10 mints before. the current markov state would be enough to make a next descion 
- In contrast if you have non markov state/imperfect you just have the position not the velocity now the where is helicopter is not fully determenid now you have to look back in time what its velocity is.

<a id = "example"></a>
## Example
![Rat Example](https://user-images.githubusercontent.com/36159918/210175698-3968c71e-1173-423c-ab17-585b12e035c0.PNG)
- The next thing that would happen really depen on our representation.
 
 <a id = "fullyobserve"></a>
 
 # Fully Observable Environments
 -![Full Obseravalbe](https://user-images.githubusercontent.com/36159918/210175753-3c658380-2b65-4a35-b507-52eef9b275ab.PNG)
 - Full observability: agent directly observes environment state Ot = Sa t = Se
   -  This is a nice and best case
   -  The observation is the same as the enviroment state and as the agent state
 - Agent state = environment state = information state
 - Formally, this is a Markov decision process (MDP)
 
 <a id = "partiallyobserve"></a>
 # Partially Observable Environments

 - Partial observability: agent indirectly observes environment:
  - it doesnt get to see every thing in the enviroment
  - A robot with camera vision isn't told its absolute location
  - A trading agent only observes current prices
  - A poker playing agent only observes public cards
 - Now agent state ! = environment state
 - Formally this is a partially observable Markov decision process (POMDP)
 - Agent must construct its own state representation Sat , e.g.
 - How we can build that state so we can do the foloowing things
  - Complete history: Sat = Ht (Remembering every thing)
  - Beliefs of environment state: Sa (prbalistic and bassyian approach)  t = (P[Se t = s1]; :::; P[Se t = sn])
  - Recurrent neural network: Sa t = (Sa t􀀀1Ws + OtWo) (linera transforamtion from one state to new state and do some non linearities)
  
  
  <a id = "majorcomponetinrl"></a>
  
  # Major Components of an RL Agent
  - An RL agent may include one or more of these components:
     - Policy: agent's behaviour function
       - How the agents picks his actions
     - Value function: how good is each state and/or action
       - How good it is to taka particular action, how good is the reward
     - Model: agent's representation of the environment
       - How the agent thinks teh enviroment works
  
  <a id = "policy"></a>
  # Policy
  - A policy is the agent's behaviour
  - It is a map from state to action, e.g.
  - Deterministic policy: a = Pie(s)
    - we trying to maek a brain which figures out this policy
  - Stochastic policy: pie(ajs) = P[At = ajSt = s]

<a id = "valuefunct"></a>
# Value Function
- Value function is a prediction of future reward 
  - if we have two states and we want to choose one state we will chooese on the expected future reward amount 
- Used to evaluate the goodness/badness of states
- And therefore to select between actions, e.g.
 vpie(s) = Epie * [Rt+1 +  Rt+2 +  2Rt+3 + ::: j St = s]
  
 <a id = "model"></a>
 
# Model
- A model predicts what the environment will do next
- P predicts the next state
- R predicts the next (immediate) reward, e.g.
 - Pa ss0 = P[St+1 = s0 j St = s; At = a]
 - Ras = E[Rt+1 j St = s; At = a]
- Its not necessaryto build the enviroment

<a id = "examplesofmaze"></a>
# Example of Model
**Maze Example**
- ![Maze Example](https://user-images.githubusercontent.com/36159918/210176786-a26e1d38-e110-435f-9be6-120a0c5d47a0.PNG)
- Rewards: -1 per time-step
- Actions: N, E, S, W (North , East South , West)
- States: Agent's location

**Maze Example policy**
- ![MazeExamplePolicy](https://user-images.githubusercontent.com/36159918/210176846-9a5148e3-77bf-42a6-911a-9c3dd9fa727c.PNG)
- Arrows represent policy (s) for each state s
- What the agent want to choose if he is in any on of the state
- Example of the deterministic policy function
- On  you have mapping you can read out and behave


**Maze Example: Value Function**
- ![MazeVaue function](https://user-images.githubusercontent.com/36159918/210176933-f24aefca-9160-49f2-935b-2a8ad273a95f.PNG)
- -1 states that we are one step behin reaching to our goal
- -2 states that we are two steps behind to reach our goal
- -24 state thatwe are in the wrong direction



**Maze Example Model**

- ![MazeModelvalue](https://user-images.githubusercontent.com/36159918/210177066-d20442d6-fc3b-4190-a607-f2a41dacbcf1.PNG)
- Trying to figure out what happens in the enviroment
- map represents that what are the dynamics of the the enviromenmt.
- agent model reality

<a id = "catgorizingrl"></a>
 
# Categorizing RL agents
- Value Based
  - No Policy (Implicit) (just focous on the value)
  - Value Function
- Policy Based
  - Policy (focous on policy example teh arrows most possible awards)
  - No Value Function
- Actor Critic
  - Policy
  - Value Function
- Model Free
    - Policy and/or Value Function (we don not try to understand the enviroments , we dont try to build dynamics of how helicopter moves instead we see the experince    and figure out the policy through award )
     - No Model  
- Model Based
    - Policy and/or Value Function
    - Model (First we made the dynamics of the model and )

The model and model free are the  fundamental distinguish type in RL

## Rl agent taxonmy


![Rl agent taxonmy](https://user-images.githubusercontent.com/36159918/210177392-023c4b14-58fc-4e2d-bf61-963a61fc5399.PNG)


<a id = "problemsinrl"></a>
# problems within RL
- Two fundamental problems in sequential decision making
- Reinforcement Learning:
  - The environment is initially unknown (Dont tell any thing about env, Eg robot knows by itself)
  - The agent interacts with the environment
  - The agent improves its policy
- Planning:
 - A model of the environment is known(we tell the details )
 - The agent performs computations with its model (without anyexternal interaction)
 - The agent improves its policy a.k.a. deliberation, reasoning, introspection, pondering, thought, search 

- These two things are linked two gather

**Atari Example Rl*

- ![Atari Example](https://user-images.githubusercontent.com/36159918/210178345-dd55c66f-6c8f-46c3-b73e-816cf8b1eeae.PNG)
- ![atari planing](https://user-images.githubusercontent.com/36159918/210178363-cdeef36b-d55b-4a79-8c2a-aa780fa6ca6b.PNG)

<a id = "expexp"></a>
# Exploration and Exploitation
- Reinforcement learning is like trial-and-error learning
- The agent should discover a good policy
- From its experiences of the environment
-  Without losing too much reward along the way
-  Exploration finds more information about the environment
- Exploitation exploits known information to maximise reward
- It is usually important to explore as well as exploit

## Examples
- Restaurant Selection
  - Exploitation Go to your favourite restaurant
  - Exploration Try a new restaurant
- Online Banner Advertisements
  - Show the most successful advert
  - Show a different advert
- Oil Drilling
  - Exploitation Drill at the best known location
  - Exploration Drill at a new location
- Game Playing
 - Exploitation Play the move you believe is best
 - Exploration Play an experimental move

<a id = "pandc"></a>
# Prediction and Control
- Prediction: evaluate the future (How much reward I will get)
 - Given a policy
- Control: optimise the future
 - Find the best policy (Have to evaluate all policy before takeing one)

**Gridword Predicton  Example**
- ![Gridword PRediction](https://user-images.githubusercontent.com/36159918/210178235-52c9d9e6-522d-402c-a0a1-f7a2aea268ab.PNG)


**Grid Word Control Example**
![GridwordControl](https://user-images.githubusercontent.com/36159918/210178297-dc4470e9-2688-4917-b133-08fc4bdb9765.PNG)

- 


# Lecture 2  Markov Decision Process

# Introduction to MDPs

- Markov decision processes formally describe an environment for reinforcement learning
- Where the environment is fully observable
  - We told the state every thing about the enviroment all the relevant information is being presented to our agent nothing is hidden away
- i.e. The current state completely characterises the process
  - we told the state and its a fully observed
- Almost all RL problems can be formalised as MDPs, e.g.
  - Optimal control primarily deals with continuous MDPs
    - optimal control means , e.g  where you have a differntail dynamics and you have to control the flow and to dind the optimal way for the fluid , we can deal it      with an extantion of MDP which is continous MDP
  - Partially observable problems can be converted into MDPs
    - any partially observable problem can be converted into MDP's
  - Bandits are MDPs with one state
    -for ex,g exploration and exploitation
    
# Markov Property
- The future is independent of the past given the present"
- Defnition
  - A state St is Markov if and only if P [St+1 j St ] = P [St+1 j S1; :::; St ]
    - What happens next in our enviroment depends only in our previous state
  - The state captures all relevant information from the history adn not on all the thing which came before that.
  - Once the state is known, the history may be thrown away
  - i.e. The state is a suf cient statistic of the future
  
  ## State Transition Matrix
   - For a Markov state s and successor state s0, the state transition probability is defned by
    - Pss0 = P [St+1 = s0 j St = s]
      - For any markov process adn it got some succesor state S prime then you can actually define the probality of transition of one state to another state
      - State in which we are in charchtereized every thing that will happen next
      - That means there is some well defiened transitional  probalities which can define the next state, 
        - example if you push a person in right direction there is a probabilty that the person move in right direction
   - State transition matrix P defnes transition probabilities from all
     states s to all successor states s0,
      - P = from
                  
                 
                 P11 : : : P1n
                 ...
                  Pn1 : : : Pnn
        - where each row of the matrix sums to 1
          - each row in this matrix tell us what would happen for each state that I was in

 # Markov Process
 - Markov process is a memoryless random process, i.e. a sequence of random states S1; S2; ::: with the Markov property.
 - A Markov Process (or Markov Chain) is a tuple {S;P}
  - S is a (fnite) set of states
  - P is a state transition probability matrix,
    - Pss0 = P [St+1 = s0 j St = s]
  - For e,g the dynamics of the robot walking, or chess playing game can be defined by the state base and transition base probablity matrix (Markov Process)
  
  ## Example: Student Markov Chain
  ![Student markov chain](https://user-images.githubusercontent.com/36159918/210615968-5c01994e-6ca7-43f8-b9b6-f55be663d5f2.PNG)
  - The things in a circle represent the state 
  -  Imagne that to pass the course you had to take the three classes and in each class there is probablity of going to another state
  -  The state in a square named as Sleep represent teh terminal state if you succesfully pass then you would go to the terminal state
  
   
 # Student Markov Chain Episodes
   - Consider the above picture
   - Sample episodes for Student Markov Chain starting from S1 = C1
        S1; S2; :::; ST
   - C1 C2 C3 Pass Sleep
   - C1 FB FB C1 C2 Sleep
   - C1 C2 C3 Pub C2 C3 Pass Sleep
   - C1 FB FB C1 C2 C3 Pub C1 FB FB
   - FB C1 C2 C3 Pub C2 Sleep


# Example: Student Markov Chain Transition Matrix
 ![Student Markov Transition Matrix](https://user-images.githubusercontent.com/36159918/210618432-d7bb5719-e7b4-431b-91c8-a03fd7d8254c.PNG)
 - The transition matrix tell us that anyone of these states which we might be in whats the probablity of transition into any other on the state
 - Question : How do we deal with the  modification of the probablities over time
  - Answer : Onw answer is that you can have  Non stationery markov process, non stationery mdp in that case what can you do , you can use same kind of algorithms we use in the stationery case but incrementally adjsut your solution algorithm so you can track best solution you found so far.
   - Soliution 2 : The fact you got the non staioner dynamics just make the more complicated markov process
 

  
 
