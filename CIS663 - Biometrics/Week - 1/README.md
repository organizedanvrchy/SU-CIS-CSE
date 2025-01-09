# Biometrics
## 1. Universality
Refers to the presence of a biometric characteristic in every individual.
Example: All humans have fingerprints, irises, and voices, though specific characteristics may vary.
## 2. Distinctiveness
Measures how uniquely a biometric characteristic can differentiate between individuals.
Example: No two fingerprints or irises are identical.
## 3. Permanence
Refers to the stability of the biometric characteristic over time.
Example: Fingerprints and iris patterns remain largely unchanged throughout a person's life, while voice or facial features may vary slightly due to aging or health conditions.
## 4. Collectability
Indicates the ease and practicality of capturing and measuring the biometric characteristic.
Example: Fingerprints and facial recognition can be collected with standard equipment, whereas DNA collection may be more intrusive.
## 5. Performance
Describes the system's ability to accurately and efficiently recognize individuals under various conditions.
Example: A biometric system's error rate, speed, and reliability in real-world applications.
## 6. Acceptability
Reflects how willing people are to use a particular biometric system.
Example: Facial recognition may be widely accepted due to its non-intrusive nature, while retina scans may face resistance due to perceived invasiveness.
## 7. Circumvention
Refers to how easily a biometric system can be deceived or spoofed.
Example: High-security systems are designed to resist attacks such as fake fingerprints, photographs, or voice recordings.

# Verification vs. Identification Mode

## Verification (likely Authentication)
Purpose: To confirm the identity claimed by an individual. <br>

Process:
- The user provides a claimed identity (e.g., a username, ID card, or PIN).
- The biometric system captures the user's biometric data and compares it against the stored biometric data for the claimed identity. <br>
Output: Either "Match" (identity is verified) or "No Match" (identity is not verified). <br>

Example Applications:
- Access control systems (e.g., unlocking a smartphone with a fingerprint).
- ATM transactions (e.g., verifying identity using a PIN and fingerprint). <br>

Key Characteristics:
- Faster as it involves a one-to-one comparison.
- Requires the user to provide a reference for the claimed identity.

##  Identification (likely Recognition)
Purpose: To determine an individual's identity from a database without requiring them to claim an identity. 
Often used in systems where the individual’s identity is unknown. <br>

Process:
- The biometric system captures the user's biometric data.
- The system compares the captured data against all stored records in the database to find a match. <br>
Output: Either "Identity Found" (with a specific match) or "Identity Not Found." <br>

Example Applications:
- Criminal identification (e.g., matching a suspect’s fingerprint against a database of prints).
- Border security (e.g., identifying travelers using facial recognition). <br>

Key Characteristics:
- Slower as it involves one-to-many comparisons.
- Requires a large database of biometric records. <br>


# Biometric Systems
All biometrics systems have the following characteristics:
## 1. Sensor Modules
__Captures raw biometric data__ from an individual (e.g., fingerprint, facial image, iris scan). <br>
Example: Cameras for facial recognition, fingerprint scanners, microphones for voice.
## 2. Feature Extraction Module:
Processes the raw biometric data to __extract unique features or patterns__. <br>
Example: Extracting ridge endings in fingerprints or unique points in iris patterns.
## 3. Matcher Module
Compares the extracted features with stored __templates__ to determine similarity.
Outputs a match score or decision based on a predefined threshold (match, no match).
## 4. Database Module
__Stores biometric templates__ generated during the enrollment phase for future matching.
Needs to ensure security and fast retrieval of data.
## 5. Enrollment Module
__Captures and processes the initial biometric data__ to create and store templates.
Essential for setting up user profiles in the biometric system. Involves Sensor Modules and Feature Extraction Modules.
## 6. Pattern Recognition/ML
__Utilizes algorithms__ (e.g., neural networks) to identify or verify patterns in biometric data.
__Enhances accuracy__, adaptability, and learning from new data over time.

# Biometric System Errors
These metrics are critical for evaluating a biometric system's accuracy and reliability, balancing security (low FMR) with usability (low FNMR).
## 1. Imposter distribution
Represents the similarity scores generated when comparing the biometric data of different individuals.
Lower similarity scores typically indicate non-matching cases.
## 2. Genuine distribution
Represents the similarity scores generated when comparing the biometric data of the same individual.
Higher similarity scores typically indicate matching cases.
## 3. False Match (or False Positive)
Occurs when the system incorrectly identifies two different individuals as the same person. <br>
Example: An impostor’s fingerprint matches a registered user's fingerprint.
## 4. False Non-match (or False Negative)
Occurs when the system incorrectly determines that the biometric data of the same individual does not match. <br>
Example: A user's face is not recognized despite being registered.
## 5. False Match Rate
The probability that the system incorrectly matches the biometric data of different individuals. <br>
FMR = (False Matches) / (Total Impostor Attempts)
## 6. False Non-match Rate
The probability that the system fails to match the biometric data of the same individual. <br>
FNMR = (False Non-Matches) / (Total Genuine Attempts)
