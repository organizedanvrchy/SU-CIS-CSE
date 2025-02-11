# Formal Methods in Computer Science
**Formal Methods** are mathematically rigorous techniques used for the specification, development, and verification of software and hardware systems. They aim to improve the quality, correctness, and reliability of systems by providing a framework for precise and unambiguous specifications.

## Key Aspects of Formal Methods
### 1. Formal Specification
- **Definition:** Using mathematical notations to define the desired behavior and properties of a system.
- **Purpose:** Eliminates ambiguity present in natural language descriptions.
- **Techniques:**
  - Set Theory
  - Predicate Logic
  - Temporal Logic

### 2. Formal Verification
- **Definition:** Proving or disproving the correctness of a system with respect to a formal specification.
- **Purpose:** Ensures the system behaves as intended.
- **Methods:**
  - **Theorem Proving:** Using logical reasoning to prove properties.
  - **Model Checking:** Exploring all possible states of a system to verify properties like safety or liveness.

### 3. Development and Refinement
- **Process:** Moving from abstract specifications to concrete implementations while maintaining correctness.
- **Purpose:** Reduces the likelihood of introducing errors during development.

## Applications of Formal Methods

### 1. Software Systems
- **Safety-Critical Software:** In aerospace, automotive, and medical devices.
- **Security Protocols:** Ensuring confidentiality and integrity in communication.

### 2. Hardware Systems
- **Chip Design and Verification:** Ensuring the correctness of integrated circuits and processors.
- **Concurrency Verification:** Avoiding deadlocks and race conditions.

## Examples of Formal Methods Tools
### 1. Modeling Languages
- Z Notation
- VDM (Vienna Development Method)
- B-Method

### 2. Verification Tools
- SPIN (Model Checking)
- TLA+ (Temporal Logic of Actions)
- Coq (Theorem Proving)
- HOL (Higher-Order Logic)

### 3. Industrial Use Cases
- Intel uses model checking for processor design.
- NASA applies formal verification for mission-critical systems.

## Advantages of Formal Methods
- **Precision:** Eliminates ambiguity.
- **Reliability:** Ensures correctness of critical systems.
- **Early Error Detection:** Identifies errors before implementation.
- **Improved Confidence:** Increases trust in system behavior.

## Challenges and Limitations
1. **Scalability:** Difficult to apply to large, complex systems.
2. **Expertise Required:** High level of mathematical skill is necessary.
3. **Resource Intensive:** Verification processes can be time and resource consuming.

---

# Secured Systems
Secured systems focus on protecting resources and capabilities by managing access through well-defined policies and mechanisms. This involves ensuring that only authorized entities can use or interact with sensitive data or capabilities.

## Key Topics in Secured Systems
### 1. Access Control
- **Definition:** A fundamental concept in secured systems that governs who can access resources and what operations they can perform.
- **Focus:** Policies and mechanisms that permit or deny the use of a resource or capability.

### 2. Policies and Mechanisms
- **Policies:** Define the rules or conditions under which access is granted or denied.
- **Mechanisms:** Implement the policies to enforce access control decisions.

## Formal Methods in Access Control
### Logic for Access Control
A formal method is used to:
1. **Formulate Access Control Policies:**
   - Precisely define rules for granting or denying access to resources.
2. **Describe Access Control Mechanisms:**
   - Model how these mechanisms enforce the defined policies.

### Reasoning Tool
- **Purpose:** Helps in making informed access control decisions.
- **Applications:**
  - Verifying compliance with policies.
  - Identifying potential vulnerabilities in access control implementations.

## Applications in Secured Systems
1. **Data Protection:**
   - Ensuring sensitive data is accessed only by authorized users.
2. **System Integrity:**
   - Preventing unauthorized modifications to critical system resources.
3. **Operational Security:**
   - Safeguarding resources in multi-user environments.

---

# Mathematical Notions and Terminology
This guide outlines key notions and terminology from foundational areas of mathematics that are essential in computer science and related fields.

## Core Areas
### 1. Logic
- **Definition:** The study of reasoning, including the principles of valid inference and demonstration.
- **Key Concepts:**
  - **Propositions:** Statements that are either true or false.
  - **Logical Operators:** AND (∧), OR (∨), NOT (¬), IMPLIES (→), IF AND ONLY IF (↔).
  - **Quantifiers:** Universal (∀) and Existential (∃).

### 2. Sets
- **Definition:** A collection of distinct objects, considered as an object in its own right.
- **Key Concepts:**
  - **Elements:** Members of a set.
  - **Operations:** Union (∪), Intersection (∩), Difference (−), Complement (').
  - **Special Sets:** Empty Set (∅), Universal Set (U), Subsets.

### 3. Functions
- **Definition:** A mapping from elements in one set (domain) to elements in another set (codomain) where each element in the domain maps to exactly one element in the codomain.
- **Key Concepts:**
  - **Domain and Codomain:** Input and output sets of the function.
  - **Types of Functions:**
    - Injective (One-to-One)
    - Surjective (Onto)
    - Bijective (Both Injective and Surjective)
  - **Composition:** Combining two functions \( f(g(x)) \).
  - **Inverse Functions:** Reversing the mapping, \( f^{-1}(y) = x \).

### 4. Relations
- **Definition:** A relationship between elements of two sets.
- **Key Concepts:**
  - **Types of Relations:**
    - Reflexive
    - Symmetric
    - Transitive
    - Anti-symmetric
  - **Equivalence Relation:** A relation that is reflexive, symmetric, and transitive.
  - **Order Relation:** Defines a sequence (e.g., partial order, total order).

## Importance in Computer Science
1. **Logic:** Forms the foundation of algorithms, programming languages, and formal verification.
2. **Sets:** Essential for data structures, databases, and problem-solving.
3. **Functions:** Used in algorithms, functional programming, and mathematical modeling.
4. **Relations:** Critical for databases, graph theory, and system modeling.

---

# Definitions, Theorems, and Proofs
## Definitions
- **Definition:** A precise and unambiguous explanation of a concept, object, or property. Definitions serve as the foundation for building theorems and proofs.
- **Key Features:**
  - Exactness: Definitions must leave no room for ambiguity.
  - Contextual Relevance: Definitions apply to a specific area or domain.
- **Examples:**
  - **Set:** A collection of distinct objects, often called elements.
  - **Prime Number:** A positive integer greater than 1 with no divisors other than 1 and itself.

## Theorems
- **Theorem:** A statement that has been proven to be true using definitions, axioms, and previously established theorems.
- **Structure:**
  1. **Hypothesis (Assumptions):** The conditions that must be true for the theorem to hold.
  2. **Conclusion:** The result or claim of the theorem.
- **Examples:**
  - **Pythagorean Theorem:** In a right triangle, \(a^2 + b^2 = c^2\), where \(a\) and \(b\) are the lengths of the legs, and \(c\) is the hypotenuse.
  - **Fundamental Theorem of Calculus:** Relates differentiation and integration, providing a method to evaluate definite integrals.

## Proofs
- **Proof:** A logical argument that demonstrates the truth of a theorem using definitions, axioms, and logical reasoning.
- **Key Elements:**
  - **Logical Steps:** Each step must follow logically from the previous one.
  - **Justification:** Every assertion must be backed by an axiom, definition, or prior result.
- **Types of Proofs:**
  1. **Direct Proof:** Proves the theorem directly by logical reasoning.
  2. **Indirect Proof (Contradiction):** Ass

## Types of Proof
### 1. Proof by Construction
- **Definition:** A constructive proof demonstrates the existence of an entity or the validity of a statement by explicitly constructing an example or process.

- **Steps:**
  1. Clearly state what is to be proven.
  2. Construct the required entity or demonstrate the process step-by-step.
  3. Conclude with the validity of the statement based on the construction.

- **Example:**
  Prove that p ∨ ¬p (Law of the Excluded Middle) is a tautology by constructing its truth table:
  <br>
  
  | p      | ¬p     | p ∨ ¬p |
  |:------:|:------:|:------:|
  | True   | False  | True   |
  | False  | True   | True   |
  
  The truth table shows that p ∨ ¬p is always true, confirming it is a tautology.

### 2. Proof by Contradiction
- **Definition:** A proof that begins by assuming the negation of the statement to be proven and then derives a logical contradiction.
  
- **Steps:**
  1. Assume the negation of the statement.
  2. Use logical reasoning to derive a contradiction.
  3. Conclude that the original statement must be true since its negation leads to a contradiction.
  
- **Example:**
  Prove that √2 is irrational:
  
  1. Assume √2 is rational, i.e., √2 = p/q, where p and q are integers with no common factors.  
  2. Square both sides:  
     2 = p²/q², or p² = 2q².  
  3. This implies p² is even, so p must also be even (p = 2k for some integer k).  
  4. Substituting p = 2k into p² = 2q², we get  
     (2k)² = 2q², or 4k² = 2q², which simplifies to q² = 2k².  
  5. This implies q² is also even, so q must be even.  
  6. If both p and q are even, they share a common factor of 2, contradicting the assumption that p and q have no common factors.  
  7. Therefore, √2 is irrational.

### 3. Proof by Induction
- **Definition:** A proof technique used to show that a statement holds for all integers \( n \geq n_0 \), using a base case and an inductive step.
  
- **Steps:**
  1. **Base Case:** Verify that the statement holds for the initial value n₀.  
  2. **Inductive Hypothesis:** Assume the statement is true for n = k.  
  3. **Inductive Step:** Prove the statement holds for n = k + 1 using the inductive hypothesis.  
  4. Conclude that the statement is true for all n ≥ n₀.
  
- **Example:**
  Prove that the sum of the first n natural numbers is given by  
  S(n) = n(n + 1)/2.
  
  1. **Base Case:** For n = 1,  
     S(1) = 1(1 + 1)/2 = 1.  
     True.
  
  2. **Inductive Hypothesis:** Assume  
     S(k) = k(k + 1)/2  
     is true for n = k.
  
  3. **Inductive Step:** Prove  
     S(k + 1) = (k + 1)((k + 1) + 1)/2.  
     Starting from the definition of the sum:  
     S(k + 1) = S(k) + (k + 1).  
     Substitute the inductive hypothesis:  
     S(k + 1) = k(k + 1)/2 + (k + 1).  
     Simplify:  
     S(k + 1) = (k(k + 1) + 2(k + 1))/2 = (k + 1)(k + 2)/2.
  
  4. Therefore, by induction, the formula is true for all n ≥ 1.

---

# Basic Set Notation, Subsets, and Set Operations
Sets are fundamental to mathematics and computer science, forming the basis for concepts in logic, data structures, and relational databases.

## Basic Set Notation
- **Set Definition:** A collection of distinct objects, called elements, represented as A = {a, b, c}.
- **Key Symbols:**
  - **∈:** Indicates membership, e.g., a ∈ A means a is an element of A.
  - **∉:** Indicates non-membership, e.g., d ∉ A.
  - **∅:** The empty set, containing no elements.
  - **|A|:** Cardinality of A, i.e., the number of elements in A.
- **Examples:**
  - A = {1, 2, 3}
  - B = {x | x is a positive even number} = {2, 4, 6, ...}

## Subsets
- **Definition:** A set A is a subset of B if every element of A is also in B.
- **Notation:**
  - A ⊆ B: A is a subset of B.
  - A ⊂ B: A is a proper subset of B (A ≠ B).
  - A ⊈ B: A is not a subset of B.
- **Examples:**
  - A = {1, 2}, B = {1, 2, 3} → A ⊆ B
  - C = {1, 4}, B = {1, 2, 3} → C ⊈ B

## Set Operations
### 1. Union (A ∪ B)
- **Definition:** The set of all elements in A or B (or both).
- **Formula:** A ∪ B = {x | x ∈ A or x ∈ B}
- **Example:** A = {1, 2}, B = {2, 3} → A ∪ B = {1, 2, 3}

### 2. Intersection (A ∩ B)
- **Definition:** The set of all elements in both A and B.
- **Formula:** A ∩ B = {x | x ∈ A and x ∈ B}
- **Example:** A = {1, 2}, B = {2, 3} → A ∩ B = {2}

### 3. Difference (A - B or A \ B)
- **Definition:** The set of all elements in A but not in B.
- **Formula:** A - B = {x | x ∈ A and x ∉ B}
- **Example:** A = {1, 2, 3}, B = {2, 3} → A - B = {1}

### 4. Complement (A')
- **Definition:** The set of all elements not in A, relative to a universal set U.
- **Formula:** A' = {x | x ∈ U and x ∉ A}
- **Example:** If U = {1, 2, 3, 4}, A = {1, 2} → A' = {3, 4}

### 5. Cartesian Product (A × B)
- **Definition:** The set of all ordered pairs where the first element is from A and the second is from B.
- **Formula:** A × B = {(a, b) | a ∈ A, b ∈ B}
- **Example:** A = {1, 2}, B = {x, y} → A × B = {(1, x), (1, y), (2, x), (2, y)}

## Properties of Set Operations
1. **Commutative:**
   - A ∪ B = B ∪ A
   - A ∩ B = B ∩ A
2. **Associative:**
   - (A ∪ B) ∪ C = A ∪ (B ∪ C)
   - (A ∩ B) ∩ C = A ∩ (B ∩ C)
3. **Distributive:**
   - A ∩ (B ∪ C) = (A ∩ B) ∪ (A ∩ C)
   - A ∪ (B ∩ C) = (A ∪ B) ∩ (A ∪ C)
4. **Identity:**
   - A ∪ ∅ = A
   - A ∩ U = A
5. **De Morgan's Laws:**
   - (A ∪ B)' = A' ∩ B'
   - (A ∩ B)' = A' ∪ B'

## Applications in Computer Science
1. **Data Structures:** Representing collections (e.g., arrays, hash sets).
2. **Databases:** Queries and operations on relations.
3. **Logic and Algorithms:** Formal reasoning and proofs.

---

# Functions and Function Composition
## Functions
### Definition:
A **function** is a relation between a set of inputs (domain) and a set of outputs (codomain) where each input is mapped to exactly one output.

### Notation:
- A function f from set A to set B is written as:
  f: A → B
  where f(x) = y, x ∈ A, and y ∈ B.

### Key Terms:
- **Domain:** The set of all possible inputs (A).
- **Codomain:** The set of all possible outputs (B).
- **Range:** The set of actual outputs produced by f.

### Types of Functions:
1. **Injective (One-to-One):** Every element of the codomain is mapped to at most one element of the domain.
2. **Surjective (Onto):** Every element of the codomain is mapped by at least one element of the domain.
3. **Bijective:** A function that is both injective and surjective.

## Function Composition
### Definition:
**Function composition** combines two functions f and g such that the output of g becomes the input of f. The composed function is written as (f ∘ g)(x), defined as:
  (f ∘ g)(x) = f(g(x))

### Properties:
1. **Associative:** f ∘ (g ∘ h) = (f ∘ g) ∘ h
2. **Identity Function:** Composing a function with the identity function I(x) = x leaves the function unchanged:
   f ∘ I = f and I ∘ f = f

### Example:
Let f(x) = 2x + 3 and g(x) = x².
- Composition (f ∘ g)(x):
  (f ∘ g)(x) = f(g(x)) = f(x²) = 2x² + 3
- Composition (g ∘ f)(x):
  (g ∘ f)(x) = g(f(x)) = g(2x + 3) = (2x + 3)²

## Applications in Computer Science
1. **Pipeline Design:** Combining smaller functions to process data sequentially.
2. **Algorithm Design:** Breaking problems into modular steps using composed functions.
3. **Functional Programming:** Core principle in languages like Haskell and Scala.

---

# Relations, Binary Relations, and Relational Composition

## Relations
### Definition:
A **relation** is a subset of the Cartesian product of two sets. If A and B are two sets, a relation R from A to B is defined as:
  R ⊆ A × B
It associates elements of A (domain) with elements of B (codomain).

### Notation:
If (a, b) ∈ R, we write a R b, meaning a is related to b.

## Binary Relations
### Definition:
A **binary relation** is a relation between two sets A and B, or within a single set A:
- R ⊆ A × A (when A = B).

### Properties of Binary Relations:
1. **Reflexive:** ∀ a ∈ A, (a, a) ∈ R.
2. **Symmetric:** ∀ a, b ∈ A, (a, b) ∈ R ⇒ (b, a) ∈ R.
3. **Antisymmetric:** ∀ a, b ∈ A, (a, b) ∈ R and (b, a) ∈ R ⇒ a = b.
4. **Transitive:** ∀ a, b, c ∈ A, (a, b) ∈ R and (b, c) ∈ R ⇒ (a, c) ∈ R.

### Examples:
1. R = {(1, 2), (2, 3)}, where A = {1, 2, 3}:
   - 1 R 2 and 2 R 3.
2. Equality relation: a = b.
3. Less-than relation: a < b.

## Relational Composition
### Definition:
The **composition of two relations** R₁ and R₂ is a relation R₁ ∘ R₂ such that:
  R₁ ∘ R₂ = {(a, c) ∣ ∃ b such that (a, b) ∈ R₂ and (b, c) ∈ R₁}

### Example:
Let R₁ = {(2, 3), (3, 4)} and R₂ = {(1, 2), (2, 3)}:
- R₁ ∘ R₂ = {(1, 3)}.

### Properties:
1. **Associative:** R₁ ∘ (R₂ ∘ R₃) = (R₁ ∘ R₂) ∘ R₃.
2. **Identity Relation:** Composing with the identity relation I = {(a, a) ∣ a ∈ A} leaves the relation unchanged:
   R ∘ I = R and I ∘ R = R.

## Applications in Computer Science
1. **Databases:** Queries on relational databases use relations and compositions to filter and join data.
2. **State Machines:** Transitions between states are modeled using relations.
3. **Graph Theory:** Relations represent edges in directed graphs, and relational composition is used for pathfinding.

---

# Access Control, Security, and Trust
## Introduction
Access control, security, and trust are foundational concepts in the design and implementation of secure systems. These concepts govern how users and systems interact with resources, ensuring that only authorized entities have access to sensitive data and systems.

## Access Control
Access control refers to the mechanisms and policies that restrict or allow access to resources or information based on predefined criteria. It ensures that users or systems can only access resources they are permitted to interact with, based on their roles or identities.

### Types of Access Control:
1. **Discretionary Access Control (DAC):**
   - The owner of a resource has the discretion to grant or revoke access permissions to other users.
   - Example: File permissions in operating systems like Linux and Windows.

2. **Mandatory Access Control (MAC):**
   - Access is restricted based on a set of policies enforced by the system, not at the discretion of the resource owner.
   - Example: SELinux, which enforces strict security policies on file systems.

3. **Role-Based Access Control (RBAC):**
   - Access permissions are granted based on roles rather than individual user identities.
   - Example: Users are assigned roles like "Admin," "Editor," or "Viewer," each with different access rights.

4. **Attribute-Based Access Control (ABAC):**
   - Access decisions are made based on attributes (such as the user's department, time of access, etc.) rather than roles or identity alone.
   - Example: A user in the "HR" department may have access to sensitive employee records.

## Security
Security in computing involves protecting systems and data from unauthorized access, disclosure, modification, or destruction. It encompasses a wide range of practices, including encryption, authentication, integrity checking, and more.

### Key Concepts in Security:
1. **Confidentiality:**
   - Ensuring that sensitive data is only accessible by authorized users or systems.
   - Achieved through encryption and secure transmission channels.

2. **Integrity:**
   - Ensuring that data remains unaltered and accurate, preventing unauthorized modifications.
   - Techniques like hashing and digital signatures are used to maintain integrity.

3. **Availability:**
   - Ensuring that resources and data are available when needed by authorized users.
   - Measures include fault tolerance, redundancy, and protection against denial-of-service attacks.

4. **Authentication:**
   - Verifying the identity of users or systems attempting to access a resource.
   - Common methods: passwords, biometrics, and multi-factor authentication.

5. **Authorization:**
   - Granting or denying access to resources based on authentication.
   - Often implemented using access control models such as DAC, MAC, or RBAC.

6. **Auditing and Monitoring:**
   - Tracking user activities and system behavior to detect and respond to potential security breaches.
   - Tools like intrusion detection systems (IDS) and security information and event management (SIEM) help monitor activities.

## Trust
Trust in security refers to the confidence that a system, user, or entity will act in a predictable and secure manner. In the context of access control and security, trust is built through the use of robust authentication mechanisms, secure communication protocols, and transparent security practices.

### Types of Trust:
1. **User Trust:**
   - Trust in the behavior and intentions of users interacting with the system. Users are typically trusted based on their identity, role, or previous behavior within the system.

2. **System Trust:**
   - Trust in the integrity and security of a system, such as a database, operating system, or network. Ensuring that the system has not been compromised is crucial for maintaining trust.

3. **Third-Party Trust:**
   - Trust in third-party services or providers, such as cloud services or external authentication providers. This type of trust requires ensuring that third parties adhere to proper security practices and have been vetted.

4. **Trust Models:**
   - **Centralized Trust Models:** A single entity (like a Certificate Authority) is responsible for managing trust within a system.
   - **Decentralized Trust Models:** Trust is established without a single authority, often using mechanisms like blockchain or peer-to-peer networks.

## Access Control, Security, and Trust in Practice
In practice, the integration of access control, security, and trust forms a comprehensive security framework for systems. Some real-world implementations include:

- **Secure Web Applications:** Authentication mechanisms (e.g., OAuth, OpenID Connect) are used to control access to resources, ensuring that only authorized users can perform actions.
- **Data Protection:** Encryption is used to ensure the confidentiality and integrity of data, while access control policies define who can read, write, or modify the data.
- **Network Security:** Firewalls, VPNs, and intrusion detection systems protect systems and networks from unauthorized access while maintaining trust between communication entities.
- **Cloud Computing Security:** Cloud providers use robust access control models (such as RBAC) to ensure secure multi-tenant environments, along with encryption and monitoring to ensure security and trust.
