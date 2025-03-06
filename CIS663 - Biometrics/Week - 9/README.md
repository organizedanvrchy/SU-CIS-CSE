# **Continuous Authentication**, **Multimodal Biometrics**, and **Hidden Markov Models (HMMs)** 

## Continuous Authentication  
### Introduction  
- **Goal**: Verify user identity continuously during a session, not just at login.  
- **Use Cases**: High-risk environments (e.g., aircraft cockpits, defense systems).  
- **Challenges**: Single biometrics may fail due to noise (e.g., face recognition if user looks away).  
- **Solution**: Combine multiple passive biometric modalities (e.g., fingerprint + face).  

---

## Multimodal Biometrics  
### Fusion Techniques  
1. **Feature-Level Fusion**:  
   - Combine raw features from modalities (e.g., fingerprint ridges + facial landmarks).  
   - *Pros*: Robust. *Cons*: Retraining required for new modalities.  
2. **Score-Level Fusion**:  
   - Combine classifier scores (e.g., sum, product, mean).  
   - *Example*: Fingerprint similarity score (0–199) + face Lp distance.  
3. **Decision-Level Fusion**:  
   - Vote on decisions from individual classifiers.  

### Example: Sim et al. Framework  
- **Biometrics**: Fingerprint (via SecuGen mouse) + face recognition.  
- **Model**: Hidden Markov Model (HMM) in a Bayesian framework.  
- **Integration**: Embedded in Linux kernel for real-time authentication.  

---

## Hidden Markov Models (HMMs)  
### Key Concepts  
- **States**: Hidden (e.g., "Safe" or "Attacked") and observable (e.g., biometric scores).  
- **Transition Probabilities**: Probability of moving between states.  
- **Observation Probabilities**: Probability of observing data given a state.  

### Formulation  
- **State Update**:  
  P(x_t | z_t) ∝ P(z_t | x_t) · P(x_t | z_{t-1}), <br>
where P(z_t | x_t) uses intraclass (Safe) or interclass (Attacked) PDFs.
- **Decay Factor**: Adjusts confidence over time: <br>
p = e^{k · Δ t}, where k = decay rate.  

### Example: Continuous Authentication  
- **Observations**:  
  - \( t = 0.3s \): Face Lp distance = 4,000.  
  - \( t = 0.9s \): Fingerprint score = 175.  
- **Calculations**:  
  - Combine probabilities using HMM transitions and decay factor.  
  - Result: P(Safe | Z_2) = 99.65%.  

---

## Metrics for Continuous Authentication  
1. **Time to Correct Reject (TCR)**:  
   - Time from impostor action to system rejection.  
   - *Ideal*: TCR < damage time (e.g., `rm -rf *` takes 3 seconds).  

2. **Probability of TCR (PTCR)**:  
   - Probability TCR ≤ threshold \( W \).  
   - Analogous to False Acceptance Rate (FAR).  

3. **Usability**:  
   - Fraction of time legitimate user retains access.  
   - Analogous to False Rejection Rate (FRR).  

4. **Usability-Security Curve (USC)**:  
   - Plots Usability vs. PTCR.  
   - Similar to ROC curve; area under USC measures system performance.  

---

## HMM Algorithms  
### Forward-Backward Algorithm  
- **Purpose**: Compute observation sequence probability.  
- **Forward Variable**:  
    α_k(i) = P(O_1, ..., O_k, Q_k = S_i).
- **Backward Variable**:  
    β_k(i) = P(O_{k+1}, ..., O_K | Q_k = S_i).

### Viterbi Algorithm  
- **Purpose**: Find most likely hidden state sequence.  
- **Steps**:  
  - Initialize δ_1(i) = π_i b_i(O_1).
  - Recursively compute δ_k(i) = max [δ_{k-1}(j) a_{ji}] b_i(O_k). 
  - Backtrack to determine optimal path.  

### Baum-Welch Algorithm  
- **Purpose**: Train HMM parameters (transition/observation probabilities).  
- **Expectation-Maximization**:  
  - Compute ξ_k(i,j) (transition probabilities) and γ_k(i) (state probabilities).
  - Update parameters iteratively.  
