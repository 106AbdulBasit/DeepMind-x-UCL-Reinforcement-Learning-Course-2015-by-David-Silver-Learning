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
     - [ Introduction to MDPs](#introtomdps)
     - [Markov Property](#markovpropertylec2)
     - [State Transition Matrix](#statetransionmatrixle2)
     - [ Markov Process](#1)
     - [ Example: Student Markov Chain](#2)
     - [Student Markov Chain Episodes](#3)
     - [ Example: Student Markov Chain Transition Matrix](#4)
      
  - 2 Markov Reward Processes
      - [Markov Reward Process](#5)
      - [Example Student MRP](#6)
      - [Return](#7)
      - [Value Function](#8)
      - [Example Student Markov Chain returns / Value Function](#9)
      - [State Value Function for Student MRP (1)](#10)
      - [State Value Function for Student MRP (2)](#11)
      - [State Value Function for Student MRP (3)](#12)
      - [Bellman Equation for MRPs](#13)
      - [Bellman Equation for MRPs (2)](#14)
      - [Example: Bellman Equation for Student MRP](#15)
      - [Bellman Equation in Matrix Form](#16)
      - [Solving the Bellman Equation](#17)
          - 
   - 3 Markov Decision Processes
    
      - [Markov Decision Process](#18)
      - [Student MDP](#19)
      - [ Policies (1)](#20)
      - [Policies (2)](#21)
      - [Value Function](#22)
      - [State-Value Function for Student MDP](#23)
      - [Bellman Expectation Equation](#24)
      - [Bellman Expectation Equation for V*](#25)
      - [Bellman Expectation Equation for Q*](#26)
      - [Bellman Expectation Equation for v* (2)](#27)
      - [Bellman Expectation Equation for q* (2)](#28)
      - [ Example: Bellman Expectation Equation in Student MDP](#29)
      - [Bellman Expectation Equation (Matrix Form)](#30)
      - [Optimal Value Function](#31)
      - [Example: Optimal Value Function for Student MDP](#32)
      - [Example: Optimal Action-Value Function for Student MDP](#33)
      - [ Optimal Policy](#34)
      - [Finding an Optimal Policy](#35)
      - [Example: Optimal Policy for Student MDP](#36)
      - [Bellman Optimality Equation for v*](#37)
      - [Bellman Optimality Equation for Q*](#38)
      - [ Bellman Optimality Equation for V* (2)](#39)
      - [ Bellman Optimality Equation for Q* (2)](#40)
      - [Bellman Optimality Equation](#41)
      - [ Solving the Bellman Optimality Equation](#42)
    
    
        
   - 4 Extensions to MDPs
    
     - [Extensions to MDPs](#43)
     - [Infnite MDPs](#44)
     - [POMDPs](#45)
     - [ Belief States](#46)
     - [Reductions of POMDPs](#47)
     - [Ergodic Markov Process](#48)
     - [Ergodic MDP](#49)
     - [Average Reward Value Function](#50)
  
      

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

<a id = "introtomdps"></a>
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

<a id = "markovpropertylec2"></a>
- The future is independent of the past given the present"
- Defnition
  - A state St is Markov if and only if P [St+1 j St ] = P [St+1 j S1; :::; St ]
    - What happens next in our enviroment depends only in our previous state
  - The state captures all relevant information from the history adn not on all the thing which came before that.
  - Once the state is known, the history may be thrown away
  - i.e. The state is a suf cient statistic of the future
  
  ## State Transition Matrix
  <a id = "statetransionmatrixle2"></a>
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
<a id = "1"></a>
 # Markov Process
 - Markov process is a memoryless random process, i.e. a sequence of random states S1; S2; ::: with the Markov property.
 - A Markov Process (or Markov Chain) is a tuple {S;P}
  - S is a (fnite) set of states
  - P is a state transition probability matrix,
    - Pss0 = P [St+1 = s0 j St = s]
  - For e,g the dynamics of the robot walking, or chess playing game can be defined by the state base and transition base probablity matrix (Markov Process)
  <a id = "2"></a>
  ## Example: Student Markov Chain
  ![Student markov chain](https://user-images.githubusercontent.com/36159918/210615968-5c01994e-6ca7-43f8-b9b6-f55be663d5f2.PNG)
  - The things in a circle represent the state 
  -  Imagne that to pass the course you had to take the three classes and in each class there is probablity of going to another state
  -  The state in a square named as Sleep represent teh terminal state if you succesfully pass then you would go to the terminal state
  
   <a id = "3"></a>
 # Student Markov Chain Episodes
   - Consider the above picture
   - Sample episodes for Student Markov Chain starting from S1 = C1
        S1; S2; :::; ST
   - C1 C2 C3 Pass Sleep
   - C1 FB FB C1 C2 Sleep
   - C1 C2 C3 Pub C2 C3 Pass Sleep
   - C1 FB FB C1 C2 C3 Pub C1 FB FB
   - FB C1 C2 C3 Pub C2 Sleep

<a id = "4"></a>
# Example: Student Markov Chain Transition Matrix
 ![Student Markov Transition Matrix](https://user-images.githubusercontent.com/36159918/210618432-d7bb5719-e7b4-431b-91c8-a03fd7d8254c.PNG)
 - The transition matrix tell us that anyone of these states which we might be in whats the probablity of transition into any other on the state
 - Question : How do we deal with the  modification of these probablities over time
  - Answer : One answer is that you can have  Non stationery markov process, non stationery mdp, in that case what can you do , you can use same kind of algorithms we use in the stationery case but incrementally adjsut your solution algorithm so you can track the best solution you found so far.
   - Soliution 2 : The fact you got the non staioner dynamics just make the more complicated markov process. You can agument the stage and more complicate markov       process.
   
   
   <a id = "5"></a>
 # Markov Reward Process
 - Markov process with some value judgments
 - A Markov reward process is a Markov chain with values.
 - A Markov Reward Process is a tuple hS;P;R;Y (Gamma)
    - S is a fnite set of states
    - P is a state transition probability matrix,
        - Pss0 = P [St+1 = s0 j St = s]
    - R is a reward function, Rs = E[Rt+1 j St = s]
        - Reward function tells that the how much award do i get in the state , its a immediate reward from that state that moment
    - Y is a discount factor,  2 [0; 1]
    <a id = "6"></a>
    ## Example Student MRP
      ![Student MRP](https://user-images.githubusercontent.com/36159918/210809967-db639c1e-7167-40b1-93df-4cf266bd71a1.PNG)
      - added some value judgement   
<a id = "7"></a>
    ## Return
    - You can say that the return is the goal of RL , maximize the reward 
    - The return Gt is the total discounted reward from time-step t.
      - Gt = Rt+1 + Rt+2 + ::: =1Xk=0 kRt+k+1
       - Question : Why there is no expectation here?
          - Becasue we just talking about the random sample here
    - The discount Y 2 [0; 1] is the present value of future rewards
      - how much reward I will get after 2 time step
    - The value of receiving reward R after k + 1 time-steps is  kR.
    - This values immediate reward above delayed reward.
      - Y  close to 0 leads to "myopic" evaluation.
        - The closesr to zero we more prefer reward now
      - Y close to 1 leads to "far-sighted" evaluation.
        - We more prefered reward after some time
       
    **Why discount?**
    - Most Markov reward and decision processes are discounted. Why?
      	- Mathematically convenient to discount rewards
        - Avoids infnite returns in cyclic Markov processes
        - Uncertainty about the future may not be fully represented
        - If the reward is Fnancial, immediate rewards may earn more interest than delayed rewards
        - Animal/human behaviour shows preference for immediate reward
        - It is sometimes possible to use undiscounted Markov reward processes (i.e.  = 1), e.g. if all sequences terminate.
        
  <a id = "8"></a>    
   # Value Function
   - The value function v(s) gives the long-term value of state s
      - How much value you will get from this state. expected reward from this state
   - The state value function v(s) of an MRP is the expected return starting from state s
      - v(s) = E[Gt j St = s]
    
  

         
     
    <a id = "9"></a>   
  # Example Student Markov Chain returns / Value Function
     
   ![Student Valu function](https://user-images.githubusercontent.com/36159918/210826558-ed9eca0b-b067-4397-9894-586bc30dd129.PNG)
  - y (Gamma ) dsicount = 0.5  
  - Take the bunch of the sample and take the average of the values and that would give you the legtimate value of the value function of that state
  
   
 <a id = "10"></a> 
  # State Value Function for Student MRP (1)
  
  
      
   ![statevalue function](https://user-images.githubusercontent.com/36159918/210815782-4b6cafb2-7bb1-4214-966a-dbeb0db539b8.PNG)
   - shortsighted value of the value function
   - we care about only one step
<a id = "11"></a>
   # State Value Function for Student MRP (2)
   ![statevaluefunction2](https://user-images.githubusercontent.com/36159918/210816215-fc20f8ac-5c42-4ef7-8858-fdacb5032ab3.PNG)
   - long sighted value of the value function
   <a id = "12"></a>
    # State Value Function for Student MRP (3)
   ![statevaluefunction3](https://user-images.githubusercontent.com/36159918/210816869-0f27d476-ae53-4981-b7cb-30bfcbd5e6d6.PNG)
   
   
   <a id = "13"></a>
 # Bellman Equation for MRPs
 - Idea is recurssive decomposition
 - The value function can be decomposed into two parts:
  - immediate reward Rt+1
  - discounted value of successor state v(St+1)
  
  - v(s) = E[Gt j St = s
    	  -  = [{Rt+1 + Rt+2 + 2Rt+3 + ::: j St = s]
        - E[Rt+1 +  (Rt+2 + Rt+3 + :::) j St = s]
        - E[Rt+1 +  Gt+1 j St = s]
        - E[Rt+1 +  v(St+1) j St = s]
        
        - You take the sequence of the reward step and break that ino two parts basically the immideiate award that you would get and the value that you will get             after that time step
        - for example if there is robot and it moves one step ahead he can get the immideiate award of plus 10 and end up in the new state but the question is that          how good i am in this new state so the over all value function of being here is the immideiate reward and the vlaue of that robot is ended up

<a id = "14"></a>
 # Bellman Equation for MRPs (2)
 
   ![Bellman equationmdp](https://user-images.githubusercontent.com/36159918/210818632-11a56020-3797-4324-bd66-4166243f08f1.PNG)
   E = expected 
   Rt+1 = Immideait reward
   v(St+1) = value function
  
 <a id = "15"></a>
# Example: Bellman Equation for Student MRP

![Bellman equationstudent](https://user-images.githubusercontent.com/36159918/210818950-476ea776-bbe0-4cbc-b70f-65ddefce648a.PNG)

<a id = "16"></a>

# Bellman Equation in Matrix Form

 ![Bellman equationmmatrix](https://user-images.githubusercontent.com/36159918/210819272-a0aee8f9-65f2-410c-8cc2-7280d611ee3e.PNG)
 - We can use Bellman equation to verify that these are the value function of the MDPS
 - One step look ahead avergae that the all thing that might happen next and ending up back here again
  - possible the two states
    -  one = -2 + 0.6*10
    -  Two = 0.4*0.8
    - adding these two we can get the orignal state which is 4.3
    
   <a id = "17"></a> 
    
# Solving the Bellman Equation
- The Bellman equation is a linear equation
- It can be solved directly:
    - v = R +  Pv
    - (I 􀀀 P) v = R
    - v = (I 􀀀 P)􀀀1 R
- Computational complexity is O(n3) for n states
  - not for the large Markov process
- Direct solution only possible for small MRPs
- There are many iterative methods for large MRPs, e.g.
  - Dynamic programming
  - Monte-Carlo evaluation
  - Temporal-Diference learning
  

 
<a id = "18"></a>

# Markov Decision Process

- A Markov decision process (MDP) is a Markov reward process with decisions. It is an environment in which all states are Markov.
- A Markov Decision Process is a tuple {hS;A;P;R; i} 
  - S is a fnite set of states
  - A is a fnite set of actions
  - P is a state transition probability matrix,
    - transition probablity for each action you might take.
  - Pass0 = P [St+1 = s0 j St = s;At = a]
  - R is a reward function, Ras = E[Rt+1 j St = s; At = a]
  - Y is a discount factor  Y (e) [0; 1].

<a id = "19"></a>

 # Student MDP
 ![image](https://user-images.githubusercontent.com/36159918/211061363-29b91e30-7337-40ce-ad26-c8c787d12ee7.png)
  - descision are the red labels on the archs
  - The goal is to find the best path that maximizes the  reward that you get
  
 <a id = "20"></a> 
# Policies (1)
- A policy pie is a distribution over actions given states,
   - pie (ajs) = P [At = a j St = s]
      - A policy fully defnes the behaviour of an agent
      - MDP policies depend on the current state (not the history)
      - it only depends on the state not on the time state, that is what markov property is
      - i.e. Policies are stationary (time-independent), At  (jSt ); 8t > 0 need to update the equation
      
 - Question :  Why there was no reward in this equation ?
 -  Answer : Thats becasue state S full charchterised the future reward. In markov descion process the morkov property that the S fully charctersied the evolution 
           from this state ownwards in the process  , so looking for a policy which given the state that you are in you want to pick action which gave you some                future reward, so the rewards are in future , we dont care bout the rewards which are in past , they are gone
           
   
  <a id = "21"></a> 
   # Policies (2)
   
   - Given an MDP M= hS;A;P;R;  i and a policy pie
   - The state sequence S1; S2; ::: is a Markov process hS;Pi
   - The state and reward sequence S1; R2; S2; ::: is a Markov reward process hS;P;R;i
   - where
      - The average dynamics defines some average markov process
    - Need to update the equations
           
<a id = "22"></a>
   # Value Function
   - The state-value function v pie(s) of an MDP is the expected return starting from state s, and then following policy pie
   - vpie(s) = Epie [Gt j St = s]
      - So v pies S tell us that how good is it to be in state S if I am follwing policey Pie , How much rward I will get
   - The action-value function q(s; a) is the expected return starting from state s, taking action a, and then following policy Pie
      - Which tell us that how good is an action in a particaluar state
   - q(s; a) = E [Gt j St = s;At = a]
   
   
  <a id = "23"></a> 
   # State-Value Function for Student MDP
  ![statevaluefunctionmdp](https://user-images.githubusercontent.com/36159918/211065368-43ff05da-2239-4d02-a57d-aec78f31570b.PNG)
  - This is the uniform random value function
  
  
<a id = "24"></a>  
  # Bellman Expectation Equation

  - The state-value function can again be decomposed into immediate reward plus discounted value of successor state,
  - Bell Man equations for these value functions
  - v(s) = E [Rt+1 +  v(St+1) j St = s]
  - The action-value function can similarly be decomposed,
  - q(s; a) = E [Rt+1 +  q(St+1;At+1) j St = s;At = a]
    - if I am in state and I take an action then i get the reward on the performed action then I looked up Where I end and the action value the state where I dump        in
  
  
  <a id = "25"></a>
  
  # Bellman Expectation Equation for V
  
  ![Bellman equationV](https://user-images.githubusercontent.com/36159918/211065752-70ff19ff-a684-4ed9-bde5-e8465e610672.PNG)
  - average over the action that we might take
  - we might take the action adn the probablites might define by these action probablity of going left and probablity going right
  - look at the action value and average them to that tells the value of being in that state
  - 

  <a id = "26"></a>
  
 # Bellman Expectation Equation for Q
  ![Bellman equationQ](https://user-images.githubusercontent.com/36159918/211065884-1eafdded-9dd0-4d34-ba79-cf239b2610e1.PNG)
    - The action value function at the root tip
    - V is telling that how particular good to be in that state
    - Q tell us how good is to take that particular action in a given state


<a id = "27"></a>

# Bellman Expectation Equation for v (2)
![Bellman equationV2](https://user-images.githubusercontent.com/36159918/211066075-1f98aefa-61e2-4e9a-9aa5-4b45e5e4d2ea.PNG)
- We putting V and Q togather
- Check the state and action to carry out the policy 
-  

<a id = "28"></a>

# Bellman Expectation Equation for q (2)

![Bellman equationQ2](https://user-images.githubusercontent.com/36159918/211066206-2094214a-542b-49ac-b7c5-67e9e8431809.PNG)
- Bell man equation for action values

<a id = "29"></a>

# Example: Bellman Expectation Equation in Student MDP
![Bellman equationStudentmdp](https://user-images.githubusercontent.com/36159918/211066437-6afee070-170b-4d17-a3b3-79555ef1c277.PNG)

- consider just red state
- we going to use it verify 
- look ahead for state value functions
- each of this case end upin different state

<a id = "30"></a>

# Bellman Expectation Equation (Matrix Form)
- The Bellman expectation equation can be expressed conciselyusing the induced MRP,
  - v = R + Pv
- with direct solution
  - v = (I 􀀀 P)􀀀1 R
  - Form these matrices pf the transistion probablies average those to get R pie and P pie solve thsi equationa dn it would give us the ation value
  - Bellmans equations give us the discription of the system that we can solve once we solve we get teh value function you are done 
  
 
Qustion 
- The pub is action and you can not stay there . In mdpas the reward is dependent on action adn state
- Its combination of your action adn what enviroments affects on that
  
<a id = "31"></a>  
# Optimal Value Function
- How to find best path through the system
- The optimal state-value function v*(s) is the maximum value function over all policies
  - v*(s) = max_pie v_pie(s)
- The optimal action-value function q(s; a) is the maximum action-value function over all policies
  - q*(s; a) = max _pie q_pie(s; a)
- If you kow q* you are done , beacus it would give you the all immideiate rewards and you can get the ebst reward value
  
- The optimal value function species the best possible performance in the MDP.
- An MDP is \solved" when we know the optimal value fn.

<a id = "32"></a>

# Example: Optimal Value Function for Student MDP
 ![Optimal Value Function for Student](https://user-images.githubusercontent.com/36159918/211582380-26dff742-772f-4cc7-9464-ca02e664efec.PNG)
 - in this the optimal value is R = 10
 - It does not tells you that how to behave in that state
 
 
 <a id = "33"></a>
# Example: Optimal Action-Value Function for Student MDP

![optimal action value function for student](https://user-images.githubusercontent.com/36159918/211582649-c3c58517-4d07-4ac8-aee3-7a09f62363b3.PNG)
- This gives the action value function , it gives the optimal value arc
- we are dealing with discounting state 

<a id = "34"></a>


# Optimal Policy
- Defne a partial ordering over policies
- whats the best policy?
  - pie ->pie if v(s)  v0(s); 8s
  - These are two polices , one policy is beeter is then other if the value fuction of the one policy is greater then value function of policy in all other state
  - 
  
- Theorem
  - For any Markov Decision Process
  - There exists an optimal policy Pie that is better than or equal to all other policies,   ; 8
  - All optimal policies achieve the optimal value function, v(s) = v(s)
  - All optimal policies achieve the optimal action-value function, q_pie_*(s; a) = q*(s; a)
- For any MDP there is always an one  optimal policy  that is better and equal to all other polices
- it is possible there can be more then one optimal policy
  the value functon for thoes policye must be same
  
  
 <a id = "35"></a> 
 # Finding an Optimal Policy
 
 - An optimal policy can be found by maximising over q(s; a)
 - You start the  q star and pick the action that maxinmise the q*
  -  math equation
  
 - There is always a deterministic optimal policy for any MDP
 - If we know q*(s; a), we immediately have the optimal policy
 
 
 <a id = "36"></a>
 # Example: Optimal Policy for Student MDP
 
 ![Optimal Policy for Student MDP](https://user-images.githubusercontent.com/36159918/211583916-f9a34658-e355-43fc-bbf0-92a8e0ee8b97.PNG)
  - 

 <a id = "37"></a>
 # Bellman Optimality Equation for v*
 
 ![Bellman equationforV](https://user-images.githubusercontent.com/36159918/211584185-28724d54-556f-4745-9c68-f12f802b4c87.PNG)
 - This is tells you really how to solve the MDPS
 - we are looking the optimal values 
 - look at the value at each state and pick the maximum of that state

 <a id = "38"></a>
 # Bellman Optimality Equation for Q*
 ![Bellman equationforQ](https://user-images.githubusercontent.com/36159918/211584406-2b78db55-18a9-41b8-8d94-d74796752cde.PNG)
 - How good the on red arcs is
 - what the dynamics migh look us
 - what envirmoent perform in that state
 - The value of each end up state and avergae all of the probality of states  multiply by the reward  and optimal value of being in that state

<a id = "39"></a>

 # Bellman Optimality Equation for V* (2)
 ![Bellmanoptimalityequation](https://user-images.githubusercontent.com/36159918/211584758-69a400d9-8282-4af3-a9e2-e4c59db2bd2c.PNG)
 -  Put those peices togather , this give us equation that we can solve
 -  all the action that enivroment can do us and find the optimal value where we can end up
 -  we back these thing up and tell us that how good to be in that state
  
<a id = "40"></a>



 # Bellman Optimality Equation for Q* (2)
![BellmanoptimalityequationQ](https://user-images.githubusercontent.com/36159918/211584984-2902a484-35b0-4498-9f79-711fa9069461.PNG)
- we do the same thing and to find the q* values 

<a id = "41"></a>

# Bellman Optimality Equation
Example: Bellman Optimality Equation in Student MDP
![Bellmanoptimalityequation StudentPNG](https://user-images.githubusercontent.com/36159918/211585256-d5709318-e0c7-407f-8d61-0df693a7e8c7.PNG)

<a id = "42"></a>

# Solving the Bellman Optimality Equation

- Bellman Optimality Equation is non-linear
- No closed form solution (in general)
- Many iterative solution methods
    - Value Iteration(dynamic Programming)
    - Policy Iteration(Dynamic Programming)
    - Q-learning
    - Sarsa
Q : In reality the  MDP is just the model we are trying to model some real phenomena some in real envireoment , How do we represent the fact the our model is imprefect?
   - some of the classical approches to uncertaity includes  implicity representing  uncertanity in the MDPS, so you could be the baysian for example have some poteriri mdp dynamics are not for single mdps but for the whole distribution mdps  and find the policy that is optimal to all of them that is computational is very costly. ANother representation is facture in the uncertainity in the representation of the world into your MDPS itself, So you are in a state not only the minus my rorbo(move backword) but my robot in a state where I think that  the world has these dynamics and I have see these observation so far adn you tell me about the unceratinty whats going on in mDPS, SO that can be much more attarctable dou dont necesassarly need to explict the uncertantinty in all the enviroment but may be its is little less intuviatively to understand the uncertainty. ANd may  be teh oitehr thing that just some time is sufficent to just accept taht our model is imperfect and use the discount factor to capture some uncertanity you can also make the discount factor variable representing the fact that you are more unceratin to others


Q - Getting the maximum reward without considering implicity the risk of those returns
- You can always tranform any mdp with no risk , if the some amount you care about risk of transformation of any risk sensitive mdps into  an other MDPS , how ever that can be complicated
- Some people do consider the risk senstive MDPS
Q - What is the intitution behind teh BELL man equation
 TO find the optimal value for on state till the trajectory and you would find the optimal value function , for eg in pac man game if he moves right it would get the 10 poinst and 100 point to after ward but moving left you would get 20 points but 50 point afterward
 Q so we have million state  and milllion action how would so solve the Large MDPS
  - The reward function can be easily made for sate
  
  
  <a id = "43"></a>
  
# Extensions to MDPs
- Infnite and continuous MDPs
- Partially observable MDPs
- Undiscounted, average reward MDPs


<a id = "44"></a>

# Infnite MDPs

- The following extensions are all possible:
  - Countably infnite state and/or action spaces
    - Straightforward
- Continuous state and/or action spaces
  - Closed form for linear quadratic model (LQR)
- Continuous time
  - Requires partial diferential equations
  - Hamilton-Jacobi-Bellman (HJB) equation
  - Limiting case of Bellman equation as time-step --> 0
  
<a id = "45"></a>
# POMDPs
  - A Partially Observable Markov Decision Process is an MDP with hidden states. It is a hidden Markov model with actions.
  - A POMDP is a tuple hS;A;O;P;R;Z; i
    - S is a nite set of states
    - A is a nite set of actions
    - O is a nite set of observations
    - P is a state transition probability matrix,
        -Pass0 = P [St+1 = s0 j St = s;At = a]
    - R is a reward function, Ras = E[Rt+1 j St = s; At = a]
    - Z is an observation function, 
        - Za s0o = P [Ot+1 = o j St+1 = s0;At = a]

    - Y is a discount factor 2 [0; 1].
    
    
 
 <a id = "46"></a>
# Belief States
- A history Ht is a sequence of actions, observations and rewards,
  - Ht = A0;O1; R1; :::;At􀀀1;Ot ; Rt
- A belief state b(h) is a probability distribution over states, conditioned on the history h
  - b(h) = (P  St = s1 j Ht = h  ; :::; P [St = sn j Ht = h])

<a id = "47"></a>

# Reductions of POMDPs
![Reduction of MDPS](https://user-images.githubusercontent.com/36159918/211587314-dc43bf8a-1e32-4416-9651-7f8336e85ebc.PNG)

<a id = "48"></a>

# Ergodic Markov Process
- An ergodic Markov process is
  - Recurrent: each state is visited an innite number of times
  - Aperiodic: each state is visited without any systematic period
- Theorem
  - An ergodic Markov process has a limiting stationary distribution
     - d(s) with the property d(s) = X s02S d(s0)Ps0s
     
     
    <a id = "49"></a> 
# Ergodic MDP
- An MDP is ergodic if the Markov chain induced by any policy is ergodic.
  - For any policy , an ergodic MDP has an average reward per time-step  that is independent of start state.
  - Math equation
  
<a id = "50"></a>  
  
# Average Reward Value Function
- The value function of an undiscounted, ergodic MDP can be expressed in terms of average reward.
  - v(s) is the extra reward due to starting from state s,
  
  
  
  


![DP1024_1](https://user-images.githubusercontent.com/36159918/211876449-f57738a3-be75-4030-9d63-0e1352aa258a.jpg)
# Outline
![DP1024_2](https://user-images.githubusercontent.com/36159918/211876455-65caab03-3240-461c-bf33-a7d5c5ae44ba.jpg)

# What is Dynamic Programming?
![DP1024_3](https://user-images.githubusercontent.com/36159918/211876464-35e73141-89e0-4cac-916e-6d508c5be6af.jpg)
 
 - Problems that have sequential aspects , step by step fraction
 -  we talking about mathmateical propgrammin , and program means policy
 - any problem that we can break down into sub prblems is in dynamic probolme 
 
# Requirements for Dynamic Programming
![DP1024_4](https://user-images.githubusercontent.com/36159918/211876471-60e32427-c70b-434f-8977-46c07d96618e.jpg)
- Optimal structure : Principal of optimality applies, it basically telss you that you can solve the alll sub problems by breaking it down int two or more peices     and solving thoses pecies and the optimal solution of all these peieces tells you  how to get the over optimal  solution.
  shotest path is the example
-  Overlapping: subproblem that occour , can occour again and again lke actully subproblem can occur again for many high problem that i want to solve
- solution can be resued again
- bell equation tells us how to break down the  optimal value function into two pieceis . The optimal behaviour for one step followed by the optimal behviour for     next step
- value function for any state , I already  figure it out the solution for that state, value fuction tells you the optimal behave the optimal reward you can get     from that
 

# Planning by Dynamic Programming
![DP1024_5](https://user-images.githubusercontent.com/36159918/211876478-2e429492-a858-4c3e-8afc-29cb58407f15.jpg)
- planning is the problem , where some one tellus the dynamics of the mDP
- strat with the prediction
- We can plan to solve the prediction problems
- How much reward you would get with the value function
- Control is second type of planning , we trying to figure out the best solution
- When we dolve the MDP we think of teh control , what is the best  value function for this problem



# Other Applications of Dynamic Programming
 
![DP1024_6](https://user-images.githubusercontent.com/36159918/211876490-ce676eac-460d-4c1a-b4b2-63405cf451c9.jpg)
  - - its used for many different things
  
# Iterative Policy Evaluation
![DP1024_7](https://user-images.githubusercontent.com/36159918/211876498-3b0cae08-2a03-45d5-b097-bfb9d692edba.jpg)
  -  We will use Bell man Expectation eqution for policy evaultion
  - we Will use Bell man Optimality equation for control later on
  - Take the bellman equation into iterative  whihc give us policy 
  - Synchorous Back up
    -  In every iteration we consider all sattes of MDP
    - update teh value function of each state at each step
    
# Iterative Policy Evaluation (2)
![DP1024_8](https://user-images.githubusercontent.com/36159918/211876503-a929bdd6-2052-407d-8b39-598ee0573af8.jpg)
- its a expectatcion equation of bellman
-  Turn it into a iterative process
- plug in the equation and update after each step for second value
- That give us a caomplete new value function
- This process gaurante eto converge on treu value function
# Evaluating a Random Policy in the Small Gridworld

![DP1024_9](https://user-images.githubusercontent.com/36159918/211876512-38799dfd-e548-47ed-9917-6ab52a8429ae.jpg)
- Shaded are teh terminal state , end of the episode 
- 4 action in the campous, north east south and west
- How many steps it would take to end up in one of thses reward state
- probality of all corner is unform means  east, west , south east = 0.25

# Iterative Policy Evaluation in Small Gridworld
![DP1024_10](https://user-images.githubusercontent.com/36159918/211876553-ac2f671a-7323-4cdc-9fac-528ad3b2f67e.jpg)
 - In the left colum we got the  state value function
 - V0 = intial estimate
 - one step of iterative policy of bellman equation to all states  and we get the V1
 - look teh value according to old estimate
 - Which ever direation we are going , we get the -1 reward as we taken teh step then we look at the valuea ccording to our old estimate
 - same logic apply except for the terminal step
 - Righ hand colum tell us how to make teh better policy
 - we start off random policy
 -  On the second colum we can see that by going right it has the value of -1 but going to left it would end up in greay state
 
 # Iterative Policy Evaluation in Small Gridworld (2)
![DP1024_11](https://user-images.githubusercontent.com/36159918/211876569-c7cfd7e4-5e2b-4c80-b53b-1e0877f792b6.jpg)
- This this satblizes at true value function
- This basically tells us that if we go out the random walk how many steps it going to take on average  to end up in the geray state

# How to Improve a Policy
![DP1024_12](https://user-images.githubusercontent.com/36159918/211876586-7b871fcb-39a5-436c-8fbc-4ffb1ea9b1db.jpg)
- How can we ceratin about the policy is that it is teh ebst policy
- Break down it on two step
    - complete the value function
    -  we improve the policy with repesect to value function
- Round and roudn it is a iterative process and eventually it will converge to optimal policy

There is alwasy every one is destertministic policy
it will be greedy and every other step is determinisctic policy
# Policy Iteration
![DP1024_13](https://user-images.githubusercontent.com/36159918/211876610-22a543fd-8c88-40ad-bfd2-04721c82f5b2.jpg)
- Inputs are some arbiraty values
- policy = V= Vpie
- Policy evaluation of Up arrow
- policy of improvmenet down arrow
- we start with the policy ,we act greedy with respect to that polcy 
- Question - will it alwaays converge irresepctive of starting point
- Answer Yes it will always converge to optimal policy
# Jack's Car Rental
![DP1024_14](https://user-images.githubusercontent.com/36159918/211876618-56e12e0f-07d5-44e7-b8e2-43788a884213.jpg)

- Its a toy example
- whast the optmial policy for shifting car for rent a car

# Policy Iteration in Jack's Car Rental
![DP1024_15](https://user-images.githubusercontent.com/36159918/211876624-7ee8c3e7-f708-4a4d-ab43-521fc5b52946.jpg)
- Five squares repesent the policies
- Number of car s at X  ais for one location
- Number of cars at Y aixs for second location
- every time with new policy we come with new surface
- In this example we known the probablities of demanding the car  in some way dynamics are decribed
- Q : How can I read the policy here ?
- Answer : we read of the state and state in given by any point , we look at the number s; its like a contol map
- Q waht are the dollar's
- Ans : so if you in a sitution you would stell get the money , its the total life time doolar on this value and discount factor
- Q : How sensitive is this convergae rate to pie zera
- Ans The convergaenc rate is independent to Pie zero ,  its independent to intial value
# Policy Improvement
![DP1024_16](https://user-images.githubusercontent.com/36159918/211876632-1f464218-8fa8-4db9-a3d4-6ad0c9f57b82.jpg)
- we satrt off wity some deterministic policy
- acting greedly always made you determininstic.
- give action in agiven way so that it give us the maximum award
- 
# Policy Improvement 2
![DP1024_17](https://user-images.githubusercontent.com/36159918/211876652-8687ba66-787c-4d14-ac86-80fe1e263563.jpg)
- If first equation statifyed then bell man equation has been satisfied
- That tell us V pie is the optimal policy
being greedy doesnet mean for only one action  it acount for teh all possilbe steps 

# Modifed Policy Iteration
![DP1024_18](https://user-images.githubusercontent.com/36159918/211876663-75163e9e-0fa1-4d7a-8310-61fd4aaa58ef.jpg)
- The basic idea is to stop early , if you are close enough then you can stop
-  or we can take Naive approach , it still converages to optimial but the only acse where it would not be convergance is take 1 step

# Generalised Policy Iteration
![DP1024_19](https://user-images.githubusercontent.com/36159918/211876675-fa2cbe8e-95b2-4270-89fe-909e463acb7a.jpg)

# Principle of Optimality
![DP1024_20](https://user-images.githubusercontent.com/36159918/211876683-654bbde5-2795-4b1d-8ebf-bb26071d863c.jpg)
- if my first action is optimal then our over all behaviour is optimal
- You can break down into sub pieceis

# Deterministic Value Iteration
![DP1024_21](https://user-images.githubusercontent.com/36159918/211876684-8a506cd3-8861-4013-8d99-911bb5b9afed.jpg)
-consider this as Backward induction algorithim
- looping all over state base
- we update every state on every iteration  eventually we end up on  optimal value but we dont know what could that state can take to me , where that state would end up
- Q we were wroking backward from the final stage, if there is no final stage would that algorithm still work? 
- In practice the algorithm doesnot now about the fincal state , if there is no finals state the algorithm still work , it will still find the optimal value



# Example: Shortest Path
![DP1024_22](https://user-images.githubusercontent.com/36159918/211876690-3534bfd1-104e-4a05-a3a5-f1389fe0c050.jpg)
 - whats the optimal path steps
 - we want to find the shortest path
 -
# Value Iteration
![DP1024_23](https://user-images.githubusercontent.com/36159918/211876694-8dc022ab-471a-48fa-8a11-6fec84ed7f2f.jpg)
- We are not currently implementing the fully RL, some one tellling us about teh enviroment about teh dynamics
- its another mechanics to solve MDP
- The  idea of value iteration is to take bellman optimality equation and iterate it again and again
- That give the optimal value function
- Q : do you always need to build the entire value function and the answer is no
- Difference between valkue iteration and policy iteration
- we are no building policy here, value  iteration go from value function from one to second  and so on
- Intermideiate V you ma get may not equal to Pie , any given moment taht may not be the value function of any real policy , its not like policy iteration
- Q Great One : In the grid example we see the values are getting smaller and smaller but the theorem shows us that value of a policy is getting bigger and bigger 
- The value function would be change but we neve sya that teh it will go up and up we nver syathe value of value iteration strictly go up in value, this illustrate the building intermidetaite value and actually evalutiong a true policy , 
# Value Iteration (2)
![DP1024_24](https://user-images.githubusercontent.com/36159918/211876705-7b0bf50b-e3c7-41b8-bec9-86cd33f49e6d.jpg)
-  we put in old value function in the leaves
- This is the bell man optimallity equation ,turning into the iterative update

# Example of Value Iteration in Practice
![DP1024_25](https://user-images.githubusercontent.com/36159918/211876718-f1034047-aaa0-48bb-83a3-55fa65392b41.jpg)
# Synchronous Dynamic Programming Algorithms
![DP1024_26](https://user-images.githubusercontent.com/36159918/211876726-eded039d-02ee-4446-81eb-e7f22fbdd32e.jpg)
- Prediction means that how much reward you will get 
- You have two problesm and all of these the planning problem
-  Turn The bell mabn expection equation into to iterative it would give us policy evaluation
- Two different families of the   algorithm that maximise the reward  one is with policy Itearation , The Bellman Optimality tell us teh amximum and it end up is Value Iteration
- Between these two there is a spectrum wher k value can be 1


# Asynchronous Dynamic Programming
![DP1024_27](https://user-images.githubusercontent.com/36159918/211876738-aae51361-f464-4799-830d-b58b0214bb77.jpg)
- Do you need to update every single state in each swwep of the algo
- Ans : No it would take more computational resources and you can pick any state and back of the that satate 

# Asynchronous Dynamic Programming
![DP1024_28](https://user-images.githubusercontent.com/36159918/211876743-8d7f58a2-47ff-4e2f-8a00-ffb33fc18314.jpg)
- These are the differnt method whihc will tell us that which state we had to pick

# In-Place Dynamic Programming
![DP1024_29](https://user-images.githubusercontent.com/36159918/211876752-d0fd4b92-ca02-48c5-8adf-0a935ee41848.jpg)
- Programming check
- You have to store two value , the new value and the old value 
- we are going to plug new value at any given time
- The order eally matters

-
# Prioritised Sweeping
![DP1024_30](https://user-images.githubusercontent.com/36159918/211876758-8952553c-a610-4bd3-834a-041600f0d54f.jpg)
- Come with the measure that how important is to update any given satate?
- which state you update first
- we use the mangitude of the change to slect the state, for instacne afer one update the state value turn from zero to 1000  that going to affect my computation
- we use them and order them 

# Real-Time Dynamic Programming
- ![DP1024_31](https://user-images.githubusercontent.com/36159918/211876770-a56e7002-c471-4143-a497-624ea2460894.jpg)
- Slect the state which agent actually visit , and update state which sorrounding the agent

# Full-Width Backups
![DP1024_32](https://user-images.githubusercontent.com/36159918/211876783-9fbedb9a-696b-4a8a-9e72-bdc66948ee1f.jpg)
- we considereong the whole branching factor thats a very expensive process we need to known the dynamics ,  we solve that by sampling will see in future, sample on single trajectory

# Sample Backups
![DP1024_33](https://user-images.githubusercontent.com/36159918/211876800-94eeecb3-aeb1-4932-9edd-0d9d17b57146.jpg)
-  sample one action according to our policy
# Approximate Dynamic Programming
![DP1024_34](https://user-images.githubusercontent.com/36159918/211876805-901ee4ae-d4cd-4fc1-ab73-25308a868005.jpg)
![DP1024_35](https://user-images.githubusercontent.com/36159918/211876813-4012556f-f5f0-429f-8745-4dcf89fcf0f5.jpg)
![DP1024_36](https://user-images.githubusercontent.com/36159918/211876819-fcb6c77e-051b-4eae-9454-ee7b030586d2.jpg)
![DP1024_37](https://user-images.githubusercontent.com/36159918/211876823-db8f43cd-34f7-4d4a-b473-87672d39d720.jpg)
![DP1024_38](https://user-images.githubusercontent.com/36159918/211876834-789ec07a-0de0-44fd-9b7b-0d047ccd0a7a.jpg)
![DP1024_39](https://user-images.githubusercontent.com/36159918/211876871-d00f99c7-15ee-41d2-adc7-5a5a9d07b19d.jpg)
![DP1024_40](https://user-images.githubusercontent.com/36159918/211876888-d7a953f5-c322-4fe4-9db3-90bc531497ed.jpg)
![DP1024_41](https://user-images.githubusercontent.com/36159918/211876894-2a001659-101e-497a-926e-6941236e09e7.jpg)
![DP1024_42](https://user-images.githubusercontent.com/36159918/211876906-8d4cda02-8296-463f-9318-bc300331f6f9.jpg)




# Lecture 4
# Outline
![MC-TD-2](https://user-images.githubusercontent.com/36159918/212911651-f3b24283-912c-4f53-bed4-0577b2ae2860.jpg)
- What does Model Free Prediction means that there is an enviroment that is respresented by Marko chain but MDP is not given


# Model-Free Reinforcement Learning
![MC-TD-3](https://user-images.githubusercontent.com/36159918/212911662-fe322ea3-8235-42d7-aae2-839b092d7631.jpg)
- How to figure out the value function for unknown  MDP when some one give us the policy
# Monte-Carlo Reinforcement Learning
![MC-TD-4](https://user-images.githubusercontent.com/36159918/212911685-a731792f-cfff-4de6-b54a-a2c579b040fc.jpg)
- very widely used in practice
-  look at all complete episodes , just to take sample retuen on each sample , sample returns and average over them to get the value function
- This only work with episodic scenarioos

# Monte-Carlo Policy Evaluation
![MC-TD-5](https://user-images.githubusercontent.com/36159918/212911721-4460a585-438c-4d52-92ff-9dcd5e21a3da.jpg)
- v Pie is the value function , episdoes of teh experince from random actions
- Gt is the reward at the end of episode 
- estimate the value function by basicaly just taking the Expected retrun from Time t onwards if we set out state at a particular point
- empirical mean= collect as  many sample for each of the state what ahppend from that point
- issue  = The only issue is that the how we going to do this when are not going to set that point back to that repeatedly  and we want to figure it out for all      the state of the enviroment
# First-Visit Monte-Carlo Policy Evaluation
![MC-TD-6](https://user-images.githubusercontent.com/36159918/212911766-bf064600-8fd9-4ed1-9d10-3c064ba6abfd.jpg)
 - Imagine you have some for loop in that MDP
 - add up the return on every visiting the state
 - and take mean of all returns
 - If we see enough episodes from the random states the average will converge to the true value function provoded that each state is visited we generate the trajectory along the visiting teh policy
 - Q if the states are to many will that tehre visiting go in form of exponentional
  - Answer : No , beacuse we using teh central limit theory  1/n : sampling breaks the dependence on the size of the problem
  - Q ; How can you make sure that you visit all states?
  - just by following the policy Pie we gaurantee that we amke sure that visit all satate ,this is in the current conetxt but details will be given in next lecutures
# Every-Visit Monte-Carlo Policy Evaluation
- add on different value return on every visit

# Blackjack Example
![MC-TD-7](https://user-images.githubusercontent.com/36159918/212911787-64ac9c05-f86d-49e0-b2c8-79edd6a265b0.jpg)
- if that is less than 12 we automatically twist

# Blackjack Value Function after Monte-Carlo Learning
![MC-TD-8](https://user-images.githubusercontent.com/36159918/212911807-e20f19d1-5aa0-4b0d-9659-5fd68c8b0c5e.jpg)
- we going to applie naive policy
- every visit monte carlo learning
- play out game 10,00 hand
- play out game 500,00 thousand
- you dont see enough case where you get ace
- no one told us any thing , just by running espiosed leraning through experiments

# Incremental Mean
![MC-TD-9](https://user-images.githubusercontent.com/36159918/212911829-61b8cdc7-0d4b-4a53-8cc4-3dbcede4b2da.jpg)
- step by step update the mean
- mean can be computed incrementally
- error term = (xk 􀀀 k􀀀1)
-we update the mean in the direction of the  error
# Incremental Monte-Carlo Updates

![MC-TD-10](https://user-images.githubusercontent.com/36159918/212911842-87f5873c-086b-4491-b67c-547392c3f51f.jpg)

- epiosde by episdoe with out keep tracking of a sum
- every time we see that setate we measure the return of the state from that ownwards and we look at trhe error betwen value the  function whihc we thought and the return that we actually obsereve  we generate some error we going to update the eman estimate for that state a little bit in teh direction of that return
- every episode we update our mean
- we have to wait till the end of the epiosde for the updaete thevalue , this is the one of the fow of the montecarlo, on way to deal is to forgert old episodes
-  This applies to non stationery etsimate sratehr then taking true mean 
-  
![MC-TD-11](https://user-images.githubusercontent.com/36159918/212911914-06abbaec-2552-4f56-8532-e8001cbef9ec.jpg)
![MC-TD-12](https://user-images.githubusercontent.com/36159918/212911930-717cdcda-dd01-472b-bf38-82152b317741.jpg)
![MC-TD-13](https://user-images.githubusercontent.com/36159918/212911963-9bd33bb6-72c5-419d-b080-378f40a2030c.jpg)
![MC-TD-14](https://user-images.githubusercontent.com/36159918/212911990-4702306e-d5b6-49ca-ae2b-e0762887f7be.jpg)
![MC-TD-15](https://user-images.githubusercontent.com/36159918/212912003-49022df5-28ad-43dc-b34b-366469194a4b.jpg)
![MC-TD-16](https://user-images.githubusercontent.com/36159918/212912031-d9c4b632-9bd4-43cf-b0c6-71b1251be5a1.jpg)
![MC-TD-17](https://user-images.githubusercontent.com/36159918/212912057-b245d187-1a5c-4583-8fae-77d35f02f84f.jpg)
![MC-TD-18](https://user-images.githubusercontent.com/36159918/212912071-02cc727a-e63c-47b7-bad4-8f3fdc11fcad.jpg)
![MC-TD-19](https://user-images.githubusercontent.com/36159918/212912090-dc51d276-6db2-4702-9ed1-ad9ff31672bd.jpg)
![MC-TD-20](https://user-images.githubusercontent.com/36159918/212912104-a8dde1fb-d98e-4697-b728-452c8d66efa4.jpg)
![MC-TD-21](https://user-images.githubusercontent.com/36159918/212912123-863e7336-a8e5-40ac-833f-e464118f4483.jpg)
![MC-TD-22](https://user-images.githubusercontent.com/36159918/212912132-48a214c2-8638-4628-9792-83b5105f5ce9.jpg)
![MC-TD-23](https://user-images.githubusercontent.com/36159918/212912144-f11a2611-86a8-4659-895f-4f3c00d658d5.jpg)
![MC-TD-24](https://user-images.githubusercontent.com/36159918/212912152-6a5eb764-d36c-4153-a308-32bde92e9105.jpg)
![MC-TD-25](https://user-images.githubusercontent.com/36159918/212912174-b84eb834-f526-43ee-a8bd-dc80316ceab3.jpg)
![MC-TD-26](https://user-images.githubusercontent.com/36159918/212912191-be3cf3d8-f3ba-4df0-9f78-674f7e63e6eb.jpg)
![MC-TD-27](https://user-images.githubusercontent.com/36159918/212912204-103fad2e-68b1-4b49-aab1-22ef9f2d0ce9.jpg)
![MC-TD-28](https://user-images.githubusercontent.com/36159918/212912215-4a90d856-b105-46ed-8f32-27713618091c.jpg)
![MC-TD-29](https://user-images.githubusercontent.com/36159918/212912223-38d44241-b7fd-48c5-8d69-e4a2633b5ea7.jpg)
![MC-TD-30](https://user-images.githubusercontent.com/36159918/212912239-60ab0927-a624-45e0-a99c-b615342816e4.jpg)
![MC-TD-31](https://user-images.githubusercontent.com/36159918/212912257-91f0c9cb-8370-4502-be9c-d801dfa84b25.jpg)
![MC-TD-32](https://user-images.githubusercontent.com/36159918/212912269-f9331f23-49e3-4b84-8f3b-aaab2ef56d9a.jpg)
![MC-TD-33](https://user-images.githubusercontent.com/36159918/212912277-9d9ec8d0-2fa7-4bbe-9680-f4f247fc04f7.jpg)
![MC-TD-34](https://user-images.githubusercontent.com/36159918/212912290-e394b954-462f-4ab9-8bd5-6011fed8da14.jpg)
![MC-TD-35](https://user-images.githubusercontent.com/36159918/212912311-bd6e4d63-c9bc-4210-8b50-ca58b1f1fac9.jpg)
![MC-TD-36](https://user-images.githubusercontent.com/36159918/212912327-e6c231bb-760b-4404-89d7-d9b7b657ded1.jpg)
![MC-TD-37](https://user-images.githubusercontent.com/36159918/212912344-43b9c332-d82b-4544-9287-098235b3fbaa.jpg)
![MC-TD-38](https://user-images.githubusercontent.com/36159918/212912356-cbcc9263-98d0-421c-ab6f-13161afdb803.jpg)
![MC-TD-39](https://user-images.githubusercontent.com/36159918/212912377-e9911571-1c4d-4ad7-8baf-36751027782b.jpg)
![MC-TD-40](https://user-images.githubusercontent.com/36159918/212912394-5d4ca770-0a52-44a9-a381-13132d558219.jpg)
![MC-TD-41](https://user-images.githubusercontent.com/36159918/212912417-14d25752-f3ad-43dd-8fe0-c359687048ae.jpg)
![MC-TD-42](https://user-images.githubusercontent.com/36159918/212912425-e6812b39-a495-477b-8213-84a3fae1046f.jpg)
![MC-TD-43](https://user-images.githubusercontent.com/36159918/212912429-d543b857-7a47-4f5b-8d6e-3c6278b985ae.jpg)
![MC-TD-44](https://user-images.githubusercontent.com/36159918/212912456-6b5b111f-5d50-4cac-9d5f-adcc58cc36c3.jpg)
![MC-TD-45](https://user-images.githubusercontent.com/36159918/212912474-8b3f5bdf-ea62-4e86-8174-78b37420f25e.jpg)
![MC-TD-46](https://user-images.githubusercontent.com/36159918/212912493-294e3f09-5590-4a0a-9a12-968d5f4a762f.jpg)
![MC-TD-47](https://user-images.githubusercontent.com/36159918/212912522-b7fcd54b-f3e3-400c-9863-4e4743e33f0e.jpg)
![MC-TD-48](https://user-images.githubusercontent.com/36159918/212912567-b6a42068-52fd-43ec-9750-03fa4b69c355.jpg)
![MC-TD-49](https://user-images.githubusercontent.com/36159918/212912621-47dc4d83-1372-484b-bfa9-971d62208d6a.jpg)
![MC-TD-50](https://user-images.githubusercontent.com/36159918/212912641-b5be5674-a62d-454d-9d78-c9894c671acd.jpg)
![MC-TD-51](https://user-images.githubusercontent.com/36159918/212912653-6f1f9855-2aa4-4d04-8434-66564079ee9e.jpg)





