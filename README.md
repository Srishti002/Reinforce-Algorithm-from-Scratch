# Reinforce-Algorithm-from-Scratch

## The Reinfore Algorithm
- It is a policy gradient algorithm
- state-->NN-->probability of actions
- The objective of Reinforce is to maximize the expected reward
- Policy gradient methods learns policy that is a probability distribution over action. They explicitly parametrize what actions to take rather than just how good good is this action
- Policy gradient methods works naturally with continuous action spaces
- For episodes n=0,1,2.....
  - Sample trajectory Tn using current policy πθn ( from t=0 to H)
  - Tn=[s0,a0,r0,s1,a1,r1.........sH,aH,rH)
  - Gradient:
    
    ∇θ J(θ) = E[Σ ∇θ log πθ(at|st) * (Q(st,at)-b(st)) ]
    
    Here ∇θ= Gradient wrt to θ
    
    J(θ)=expected total reward
    
    πθ(at|st)=policy probability of action a given state s
    
    Q(st,at)=Discounted sum of rewards from t to end of episode

    b(st)= baseline for variance reduction. Common choices for baseline moving average that is running average of past returns, mean reward, etc.
    
  - Update θn+1 = θn + α*Gradient
 
  ## Training Details:
  - Environment : CartPole-v0
  - Policy Network:
    - Number of hidden layers: 1
    - Number of neurons: 4
    - Input dimension: 1,4
    - Activation function: ReLU
    - Softmax at the output layer
    - Number of actions: 2
 
      <img width="479" height="597" alt="image" src="https://github.com/user-attachments/assets/2961ed6e-1c1c-4871-8822-16760c9b3aa6" />


  - Learning rate= 0.001
  - gamma = 0.99
  - Number of episodes=1000
  - Results:
    
    <img width="1188" height="490" alt="image" src="https://github.com/user-attachments/assets/bb003f7f-186f-4188-a2fc-b28e742269e5" />

        
      
      
    
  
  
