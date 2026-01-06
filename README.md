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
  
