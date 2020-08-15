# NivaREU2020

Hello this is Niva's REU 2020 Project Code
This is an instruction manual on how to run the code
The code goes through different Temporal Difference Learning methods



# To get started:
Each algorithm is separated into different files


# Download and Install Everything Necessary

1. Must have Python 3 or above
2. Must have Anaconda installed on your computer or laptop 
3. Install all the appropriate libraries
     1. either install them to your computer by
        on command line type  or before the code is run in the Anaconda IDE
        
               pip3 install library name
               
     You need the following libraries:
     
     numpy
     
     matplotlib
     
     mdptoolbox
     
     To install:
     
               pip3 install numpy
               
               pip3 install matplotlib
               
               pip3 install pymdptoolbox

Here are basic steps to run an algorithm and understanding as to what is in the file

1. Choose the algorithm and then choose that file


     | File Name | Algorithm/Method |
     | ----------- | ------------------ |
     | TDonMDP.ipynb | On-Policy TD(0) 
     | OffPolicyTD(0).ipynb | Off-Policy TD(0) with importance sampling |
     | SynchronousTD.ipynb | Synchronous On-Policy TD(0) |
     | OnPolicyn-stepTD.ipynb | On-Policy n-step TD |
     | TDn-StepbySampling.ipynb | Off-Policy n-step TD with Importance Sampling |
     | V-trace.ipynb | V-trace algorithm |
      
      
2. Each file has a very basic way to run
    
    1. Create a policy based on your liking
    
        Must be a dictionary inside of a dictionary in the format
    
        {state: {action: probability of that action, action: probabiity, ... } state:{...}}
        
        Example: 
        
                policy = {0: {0: 0.4835164835164835, 1: 0.5164835164835165}, 1: {0: 0.48854961832061067, 1: 0.5114503816793893}, 2: {0: 0.881578947368421, 1: 0.11842105263157894}}
    
    2. Call the Class based on the name in the file
    
       input any hyper parameters you want to change
    
       the policy and MDP size is required to enter
       
       Example:
    
                  learner = TDLearner(policy = policy,states = states, actions = actions,iterations = iterations)
    
    3. Next Run the Environment
           
       this will run the algorithm and get the results
       
       runEnvironment() will be called in all files the same way
       
       Example: 
       
                  learner.runEnvironment()
       
       
    4. To see the results or need to do some debugging of the algorithm call the plot function
        
       this is the same in all files
       
       Example:
       
                  learner.plot()
       
       
# Other extra stuff 
 
1. Note that in all algorithm files the estimate Vπ has been estimated through value iteration and set as default, but if you found your own Vπ then you can change it by calling the setVi() function
 
   Vπ must have length of the state space S
 
   Example: 

            v_pi = [1,2,3,4]

            learner. setVpi(v_pi)
         
2. the reward matrix has also been set by default to have random values between [0,1] to change this call the setRewardMatrix() function
    
   must be in shape AxSxS where A is the action space, S is the state space
       
   Example:
       
                  matrix = [[[1,[2,4]],[2,[2,3]]] 2x2x2
       
                  learner.setRewardMatrix(matrix)
       
 3. These following hyperparameters are set to a default but you can change them depending on your liking like this
 
       | Parameter | Description |
       | ------------- | ------------- |
       | states | REQUIRED, amount of states in the MDP |
       | actions | REQUIRED, amount of actions in MDP|
       | policy | REQUIRED, the mapping of states to action to use for the agent|
       | alpha | step size parameter, value between [0,1]  |
       | gamma | discount factor, value between [0,1]  |
       | beta | other step size parameter, value between [0.5,1]  |
       | iterations | amount of iterations to run in the environment |
       | episodes | if n-step only, amount of episodes to run in the environment |
       | n-step | only for n-step algorithms, n value for number of steps to look ahead |
       | diminish | if diminishing step size wanted, input the function for calculating the step size|
       | c_bar | only for v-trace, the truncated c value |
       | rho_bar | only for v-trace, the truncated rho value 
       
     
   Example:
                  
                  learner = TDLearner(policy = policy,states = states, actions = actions,iterations = iterations, alpha = 0.0001)
                  
              
    
4. For Diminishing Step Size
      
      equation must be given in a function object format, with three parameters, alpha, t timestep, and beta
      
      in python there are two possibilities
      
      
      1. create the function
      
      
             def diminish(alpha, t, beta):
                        return alpha/beta**t
                        
                        
             learner = TDLearner(policy = policy,states = states, actions = actions,iterations = iterations, diminish = diminish)  
      
      2.use a lambda function
      
      
      
            diminish = lambda alpha,t,beta: alpha/beta**t
            
            
            learner = TDLearner(policy = policy,states = states, actions = actions,iterations = iterations, diminish = diminish) 
            
            
      if nothing is given then it is assumed that constant step size of alpha is used
      
      
      
      
 That is everything needed to know about my code
 
 It is very simple! 
 
            
      
            
    
    
    
    
    
