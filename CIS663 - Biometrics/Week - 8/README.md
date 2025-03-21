# Keystroke Verification and Outlier Detection

## Keystroke Verification Techniques

### Static Verification (Fixed-Text Mode)
- Based on password typing rhythm
- Authentication occurs only at login time

### Dynamic Verification (Free-Text Mode)
- Pattern recognition regardless of the typed text
- Continuous or periodic monitoring (on-the-fly authentication)
- No need to memorize a pre-determined text (username & password)

## Keystroke Dynamics (Features)
Keystroke dynamics convert biometric data into feature vectors for classification. Features include:
- Keystroke latencies (flight)
- Duration of specific keystrokes (dwell)
- Pressure (force of keystrokes)
- Typing speed
- Frequency of errors
- Overlapping of specific key combinations
- Method of error correction

## Keystroke Analysis
Various methods are used for keystroke analysis, including:
- Mean typing rate
- Inter-interval comparison
- Digraph
- Trigraph
- Mean error rate

## Parallel Decision Tree Study
- Users entered the phrase: "master of science in computer science" 9 times without mistakes
- Features included key press duration (`tx`) and time between key presses (`txy`)

## Keystroke Drawbacks
- Susceptibility to fatigue
- Dynamic changes in typing patterns
- User injury and typing skill variations
- Changes in keyboard hardware
- Some studies suggest keystroke patterns can be spoofed with training

## Keystroke Challenges
- No standardized data collection, benchmarking, or measurement
- Determining methods with lower error rates
- Difficulty in comparing error rates
- Limited sample texts
- No identical biometric samples
- Requires adaptive learning

---

## Outlier Detection

### What Are Outliers?
An outlier is a data object that deviates significantly from normal data, often generated by a different mechanism. It differs from noise, which represents random errors or variance. Outliers are of interest because they violate the normal data generation process.

### Types of Outliers

#### 1. Global Outliers (Point Anomalies)
- An object significantly deviates from the rest of the dataset.
- Example: Intrusion detection in networks.
- Issue: Finding an appropriate deviation measurement.

#### 2. Contextual Outliers (Conditional Outliers)
- An object deviates in a specific context.
- Example: 80°F in Urbana (outlier depends on the season).
- Attributes:
  - Contextual attributes define context (e.g., time, location).
  - Behavioral attributes characterize the object (e.g., temperature).
- Issue: Defining meaningful context.

#### 3. Collective Outliers
- A subset of objects collectively deviates from the dataset.
- Example: Denial-of-service attacks.
- Detection requires understanding relationships among data objects.
- A dataset may contain multiple types of outliers, and an object may belong to more than one type.

## Challenges in Outlier Detection
- Proper modeling of normal and outlier objects.
- Defining the boundary between normal and outlier objects.
- Application-specific detection methods.
- Choosing appropriate distance measures.
- Handling noise that can blur the distinction between normal data and outliers.
- Justifying and understanding outlier detection results.

## Outlier Detection Methods
Two major categorization approaches:

### 1. Based on Availability of Labeled Examples
- **Supervised**: Uses labeled examples of outliers.
- **Semi-supervised**: Uses some labeled data.
- **Unsupervised**: Does not rely on labeled data.

### 2. Based on Data Assumptions
- **Statistical Methods**: Use probabilistic models.
- **Proximity-Based Methods**: Detect deviations based on distance measures.
- **Clustering-Based Methods**: Identify outliers by grouping similar objects.

