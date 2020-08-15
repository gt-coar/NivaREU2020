# NivaREU2020

Hello this is Niva's REU 2020 Project Code
This is an instruction manual on how to run the code
The code goes through different Temporal Difference Learning methods



# To get started:
Each algorithm is separated into different files

Here are basic steps to run an algorithm and understanding as to what is in the file

1. Choose the algorithm and then choose that file

      TDonMDP.ipynb is On-Policy TD(0)
  
      OffPolicyTD(0).ipynb is Off-Policy TD(0) with importance sampling
  
      SynchronousTD.ipynb is Synchronous On-Policy TD(0)
  
      OnPolicyn-stepTD.ipynb is On-Policy n-step TD
  
      TDn-StepbySampling.ipynb is Off-Policy n-step TD with Importance Sampling ]
  
      V-trace.ipynb is V-trace algorithm
      
      
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
       
                  matrix = [[1,[2,4]],[2,[2,3]]] 2x2x2
       
                  learner.setRewardMatrix(matrix)
       
 3. These following hyperparameters are set to a default but you can change them depending on your liking like this
 
       | First Header  | Second Header |
| ------------- | ------------- |
| Content Cell  | Content Cell  |
| Content Cell  | Content Cell  |
     
   Example:
                  
                  learner = TDLearner(policy = policy,states = states, actions = actions,iterations = iterations, alpha = 0.0001)
                  
              
    
    
    
    
    
    
    
