# NivaREU2020

Hello this is Niva's REU 2020 Project Code
This is an instruction manual on how to run the code
The code goes through different Temporal Difference Learning methods



To get started:
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
    
    Call the Class based on the name in the file
    
    input any hyper parameters you want to change
    
    the policy and MDP size is required to enter
    
    learner = TDLearner(policy = policy,states = states, actions = actions,iterations = iterations)
    
    
    
    
    
    
    learner.runEnvironment()
    learner.plot()
