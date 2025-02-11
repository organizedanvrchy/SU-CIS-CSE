# Semantics
## Informal Meanings
### Propositional Variables
Propositional variables represent statements or propositions that can be either true or false.

#### P says φ
- **Meaning:** Principal P makes the statement φ.
- **Description:** Indicates that the principal (P) is asserting or declaring the truth of the proposition φ.

#### P controls φ
- **Meaning:** Principal P has jurisdiction over statement φ.
- **Description:** Indicates that the principal (P) has the authority or control over the truth or status of the proposition φ.

#### P → Q (P speaks for Q)
- **Meaning:** P speaks for Q.
- **Description:** Suggests that P has the authority or ability to make statements on behalf of Q, or that P’s position or actions are considered equivalent to Q’s in some context.

---

# Kripke Structure
A **Kripke structure** is a formal model used in modal logic, consisting of a set of worlds and relations between them.

## Kripke Structure **M**
- **Three-tuple** M = ⟨ W, I, J ⟩, where:
  - **W**: A set of **worlds** representing possible weather conditions.
    - W = { sw, sc, ns }
    - sw: Sunny and warm
    - sc: Sunny and cool
    - ns: Not sunny

  - **I**: An **interpretation function** that maps propositional variables to a set of worlds.
    - I(g) = { sw }, where g represents the proposition "The children can go outside when it is sunny and warm."

  - **J**: A function that maps each principal name into a relation on worlds. Specifically:
    - J(Gil) = { (sw, sw), (sc, sc), (ns, ns) }
    - J(Flo) = { (sw, sw), (sw, sc), (sc, sw), (sc, sc), (ns, ns) }
    - J(Hal) = { (sw, sw), (sc, sw), (ns, ns) }

### Weather Conditions
- **Sunny and warm** (sw)
- **Sunny and cool** (sc)
- **Not Sunny** (ns)

### Propositions
- The children can go outside when it is **sunny and warm**.

This Kripke structure models the possible worlds and the principal knowledge of Gil, Flo, and Hal, reflecting their differing beliefs and information about the weather.

### Principal Functions
1. **Gil** possesses perfect knowledge, since he can see both the weather and the thermometer. Therefore, for Gil, each world is only related to itself (perfect knowledge of the current state).
2. **Flo** cannot see the thermometer and thus cannot assess the temperature directly. This is reflected in the relations where she can confuse sunny and cool worlds.
3. **Hal** believes that sunny weather is always warm, so for him, all worlds with sunny weather (either sunny and warm or sunny and cool) are related to sunny and warm worlds.

---

# Semantics of Core Logic for Kripke
The semantics for propositional logic terms are evaluated over possible worlds and their relationships, where each term has a meaning with respect to the worlds in the structure.

>[!NOTE]
> **Eₘ** denotes the evaluation function, which maps formulas to sets of worlds in the Kripke structure.

### Propositional Variable
- **Eₘ[[p]]** = **I(p)**  
  The interpretation of a propositional variable `p` is given by the set of worlds in which `p` is true. This is determined by the interpretation function **I**.

### Negation
- **Eₘ[[¬φ]]** = **W - Eₘ[[φ]]**  
  The negation of a formula `φ` is the set of all worlds in **W** where `φ` is not true.

### Conjunction
- **Eₘ[[φ₁ ∧ φ₂]]** = **Eₘ[[φ₁]] ∩ Eₘ[[φ₂]]**  
  The conjunction of formulas `φ₁` and `φ₂` is the intersection of the worlds where both `φ₁` and `φ₂` are true.

### Disjunction
- **Eₘ[[φ₁ ∨ φ₂]]** = **Eₘ[[φ₁]] ∪ Eₘ[[φ₂]]**  
  The disjunction of formulas `φ₁` and `φ₂` is the union of the worlds where either `φ₁` or `φ₂` (or both) are true.

### Implication
- **Eₘ[[φ₁ ⊃ φ₂]]** = **(W - Eₘ[[φ₁]]) ∪ Eₘ[[φ₂]]**  
  The implication of `φ₁` implies `φ₂` is the set of worlds where either `φ₁` is false or `φ₂` is true.

### Equivalence
- **Eₘ[[φ₁ ≡ φ₂]]** = **Eₘ[[φ₁ ⊃ φ₂]] ∩ Eₘ[[φ₂ ⊃ φ₁]]**  
  The equivalence between formulas `φ₁` and `φ₂` is the intersection of the worlds where `φ₁` implies `φ₂` and `φ₂` implies `φ₁`.

### Speaks For
- The term **speaks for** relates to the representation of authority or jurisdiction within a Kripke structure. For this term, a principal `P` is said to speak for a statement if they have the authority or ability to confirm it in all worlds where they have jurisdiction.

### Says
- The term **says** refers to the statement made by a principal. A principal `P` says a statement `φ` if the statement holds true in all worlds where `P` has jurisdiction or authority.

### Controls
- **Eₘ[[P controls φ]]** = **Eₘ[[(P says φ) ⊃ φ]]**  
  A principal `P` controls a statement `φ` if the implication that `P` says `φ` implies `φ` holds in all worlds where `P` has jurisdiction. This means that if `P` asserts `φ`, then `φ` must hold in those worlds.

## Compound Principals
Compound principals are represented and evaluated in the Kripke structure. Compound principals combine individual principals using logical operations.

### Definitions
#### P & Q: P with Q
- **J(P & Q)** = **J(P)** ⊗ **J(Q)**  
  The principal **P & Q** represents a principal who is a combination of both **P** and **Q**. The relation **J(P & Q)** is the combination (join) of the relations **J(P)** and **J(Q)**.

#### P | Q: P quoting Q
- **J(P | Q)** = **J(P)** ◯ **J(Q)**  
  The principal **P | Q** represents **P** quoting or referring to **Q**. The relation **J(P | Q)** is the relational composition (denoted as ◯) of the relations **J(P)** and **J(Q)**.

---

# Kripke Structure and Semantics Example
The example involves propositional logic, principal actions, and evaluations in a Kripke structure with three worlds.

## Kripke Structure:
- **Worlds**: `W = {w0, w1, w2}`
- **Interpretations**:
    - `I(s) = {w1, w2}`
    - `I(t) = {w2}`
- **Principal Actions**:
    - `J(Cy) = {(w1, w0), (w1, w1), (w2, w0)}`
    - `J(Di) = {(w0, w1), (w1, w0), (w2, w2)}`

### Propositional Logic Semantics:
**a.** `EM[[s ⊃ t]] = (W − EM[[s]]) ∪ EM[[t]] = {w0} ∪ {w2} = {w0, w2}`
- `W = {w0, w1, w2}`
- `I(s) = {w1, w2}`
- `I(t) = {w2}`
- The implication `s ⊃ t` is evaluated as the union of worlds where `s` is false and `t` is true, resulting in `{w0, w2}`.

**b.** `EM[[¬(s ⊃ t)]] = W − EM[[s ⊃ t]] = {w1}`
- The negation of `s ⊃ t` is the complement of the set `{w0, w2}`, resulting in `{w1}`.

**c.** `EM[[Cy says (s ⊃ t)]] = {w | J(Cy)w ⊆ EM[[s ⊃ t]]} = {w | J(Cy)w ⊆ {w0, w2}} = {w2}`
- `J(Cy)` is the set of worlds where principal `Cy` can act. The worlds for which `Cy` "says" `s ⊃ t` are those where `J(Cy)w` is a subset of `{w0, w2}`. The result is `{w2}` because `Cy` can only access `w0` and `w2`.

**d.** `EM[[Cy says ¬(s ⊃ t)]] = {w | J(Cy)w ⊆ EM[[¬(s ⊃ t)]]} = {w | J(Cy)w ⊆ {w1}} = {w0}`
- The worlds for which `Cy` "says" `¬(s ⊃ t)` are those where `J(Cy)w` is a subset of `{w1}`. The result is `{w0}` because `Cy` can access `w1` and `w0`.

**e.** `EM[[Di says (s ⊃ t)]] = {w | J(Di)w ⊆ EM[[s ⊃ t]]} = {w | J(Di)w ⊆ {w0, w2}} = {w2}`
- The worlds for which `Di` "says" `s ⊃ t` are those where `J(Di)w` is a subset of `{w0, w2}`. The result is `{w2}` because `Di` can access `w2`.

**f.** `EM[[Di says ¬(s ⊃ t)]] = {w | J(Di)w ⊆ EM[[¬(s ⊃ t)]]} = {w | J(Di)w ⊆ {w1}} = {w0}`
- The worlds for which `Di` "says" `¬(s ⊃ t)` are those where `J(Di)w` is a subset of `{w1}`. The result is `{w0}` because `Di` can access `w1` and `w0`.

**g.** `J(Cy & Di) = J(Cy) ∪ J(Di) = {(w0, w1), (w1, w0), (w1, w1), (w2, w0), (w2, w2)}`
- The union of the actions of `Cy` and `Di` gives the combined relation `J(Cy & Di)`.

- `EM[[(Cy & Di) says (s ⊃ t)]] = {w | J(Cy & Di)w ⊆ EM[[s ⊃ t]]} = {w | J(Cy & Di)w ⊆ {w0, w2}} = {w2}`

- The worlds for which `Cy & Di` "says" `s ⊃ t` are those where `J(Cy & Di)w` is a subset of `{w0, w2}`. The result is `{w2}`.

**h.** `EM[[(Cy & Di) says ¬(s ⊃ t)]] = {w | J(Cy & Di)w ⊆ EM[[¬(s ⊃ t)]]} = {w | J(Cy & Di)w ⊆ {w1}} = {w0}`
- The worlds for which `Cy & Di` "says" `¬(s ⊃ t)` are those where `J(Cy & Di)w` is a subset of `{w1}`. The result is `{w0}`.

**i.** `J(Di | Cy) = J(Di) ◦ J(Cy) = {(w0, w0), (w0, w1), (w2, w0)}`
- The composition of the actions of `Di` and `Cy` gives the relation `J(Di | Cy)`.

- `EM[[(Di | Cy) says (s ⊃ t)]] = {w | J(Di | Cy)w ⊆ EM[[s ⊃ t]]} = {w | J(Di | Cy)w ⊆ {w0, w2}} = {w1, w2}`

- The worlds for which `Di | Cy` "says" `s ⊃ t` are those where `J(Di | Cy)w` is a subset of `{w0, w2}`. The result is `{w1, w2}`.

**j.** `EM[[(Di | Cy) says ¬(s ⊃ t)]] = {w | J(Di | Cy)w ⊆ EM[[¬(s ⊃ t)]]} = {w | J(Di | Cy)w ⊆ {w1}} = {w1}`
- The worlds for which `Di | Cy` "says" `¬(s ⊃ t)` are those where `J(Di | Cy)w` is a subset of `{w1}`. The result is `{w1}`.

**k.** `J(Cy) ⊄ J(Di)` so we have `EM[[Di ⇒ Cy]] = {}`
- The implication `Di ⇒ Cy` is empty because `J(Cy)` is not a subset of `J(Di)`.

**l.** `EM[[Cy says (Di ⇒ Cy)]] = {w | J(Cy)w ⊆ EM[[Di ⇒ Cy]]} = {w | J(Cy)w ⊆ {}} = {w0}`
- Since `Di ⇒ Cy` is empty, `Cy` "says" `Di ⇒ Cy` only in `w0`.

**m.** `EM[[Di says (Di ⇒ Cy)]] = {w | J(Di)w ⊆ EM[[Di ⇒ Cy]]} = {w | J(Di)w ⊆ {}} = {}`
- Since `Di ⇒ Cy` is empty, `Di` cannot "say" `Di ⇒ Cy`, so the result is empty.

**n.** `J(Cy) ⊆ J(Di) ∪ J(Cy) = J(Di & Cy)`, and hence `EM[[Di & Cy ⇒ Cy]] = W`.
- The conjunction `Di & Cy` is equivalent to `Di ∪ Cy`. Since `J(Cy)` is a subset of `J(Di) ∪ J(Cy)`, the implication `Di & Cy ⇒ Cy` holds in all worlds.

- `EM[[Di says (Di & Cy ⇒ Cy)]] = {w | J(Di)w ⊆ EM[[Di & Cy ⇒ Cy]]} = {w | J(Di)w ⊆ W} = W`.

- All worlds satisfy the implication `Di & Cy ⇒ Cy`, so the result is `W = {w0, w1, w2}`.

## Conclusion:
This example illustrates how to evaluate statements in a Kripke structure using modal logic, with specific operations for conjunction, disjunction, negation, and implication. The evaluation is dependent on the worlds and the relations defined by the principals `Cy` and `Di`.

---

# Set Data Type
A **set** is a collection of distinct elements with specific properties.

## Key Properties
- **Unordered Collection:** Sets are not necessarily ordered. The order of elements in a set does not matter.
- **No Duplicates:** Sets do not allow multiple instances of the same value. Any duplicate elements are ignored, ensuring all elements are unique.

## Difference from Lists
A set is **not the same as a list**. Unlike lists, sets:
- Do not maintain the order of elements.
- Do not allow duplicate values.

---

# Formal Proofs
A **formal proof** is a deductive argument used to show that a statement (the conclusion) follows from a set of assumptions. 

## Notation
A formal proof is expressed as:
`(H₁, H₂, ..., Hₖ) / C`
Where:
- `H₁, H₂, ..., Hₖ` are the **assumptions** (the premises or hypotheses).
- `C` is the **conclusion** that is derived from the assumptions.

## Formal Proof Example: Derived Inference Rules
In this example, we are given a set of assumptions and use these assumptions to prove the statement `purchase`.

### Assumptions:

1. `MC controls (Lee controls purchase)`
2. `CA controls (KL ⇒ Lee)`
3. `KCA ⇒ CA`
4. `KCA says (KL ⇒ Lee)`
5. `KL says purchase`
6. `MC says (Lee controls purchase)`

#### Goal:
Prove the statement `purchase`.

#### Formal Proof Steps:

We proceed by applying the appropriate inference rules based on the given assumptions:

**Step 1**: `Lee controls purchase`  
- From assumption (1) and assumption (6), apply the *Controls* rule to conclude that "Lee controls purchase".

**Step 2**: `CA says (KL ⇒ Lee)`  
- This follows directly from assumption (4).

**Step 3**: `KL ⇒ Lee`  
- This is derived from assumptions (2) and (8) by applying the *Controls* rule, which states that since `CA controls (KL ⇒ Lee)`, the relation must hold.

**Step 4**: `Lee says purchase`  
- From assumption (5), it is given that "KL says purchase." Therefore, using the *Speaks For* derived inference, we can deduce that Lee says `purchase`.

**Step 5**: `purchase`  
- Finally, by applying the *Controls* rule from assumption (7) and assumption (10), we can conclude that the statement `purchase` holds.

#### Summary of the Proof:

- `Lee controls purchase` (from (1) and (6) by Controls)
- `CA says (KL ⇒ Lee)` (directly from (4))
- `KL ⇒ Lee` (derived from (2) and (8) by Controls)
- `Lee says purchase` (derived from (5) by Speaks For)
- `purchase` (derived from (7) and (10) by Controls)

#### Conclusion:
By applying the *Controls* and *Speaks For* inference rules, we have proven the statement `purchase` based on the provided assumptions.

---

# Proof Trees

Proof trees are a way of visualizing the structure of a formal proof, particularly when using logical inference rules in systems like Kripke structures. Working backwards from a conclusion, we can create a proof tree by breaking down the reasoning step by step.

## Working Backwards to Create Proof Trees

To build a proof tree, we start with the statement we aim to prove (the conclusion) and trace backward through the assumptions and inference rules that lead to the conclusion. Each node in the tree represents a statement, and the edges show the inference rules used to derive that statement.

### Steps for Creating Proof Trees:

1. **Start with the conclusion**: Begin by writing down the statement you want to prove at the top of the tree.
   
2. **Apply inference rules**: For each node, apply the relevant inference rule (such as *Controls*, *Speaks For*, etc.) that allows you to derive that statement. Each rule typically has one or more premises.

3. **Create new nodes for premises**: For each premise derived by the inference rule, create a new node in the tree. These premises either come directly from assumptions or are sub-conclusions that must be proven.

4. **Repeat until you reach assumptions**: Continue working backward, adding nodes for each premise and breaking them down further until you reach the original assumptions (these will be the leaves of the proof tree).

5. **End at assumptions**: Once all premises are reduced to assumptions, the proof tree is complete.

### Example Proof Tree

Let's demonstrate creating a proof tree using the assumptions and proof steps from the earlier example, where we aim to prove the statement `purchase`:

1. **Conclusion**: `purchase` (Top node)
   
2. **Apply Controls**: From assumption (7) and assumption (10), we apply the *Controls* rule to conclude `purchase`.

3. **Apply Speaks For**: From assumption (5), we deduce that `Lee says purchase`.

4. **Apply Controls**: From assumption (1) and assumption (6), we conclude that `Lee controls purchase`.

5. **Apply Controls**: From assumption (2) and assumption (8), we conclude that `KL ⇒ Lee`.

6. **Apply Speaks For**: From assumption (4), we deduce that `KCA says (KL ⇒ Lee)`.

7. **End with assumptions**: The tree's leaves are the assumptions (1), (2), (4), (5), and (6) which are used to derive the above conclusions.

### Proof Tree Diagram:
```text
               purchase
                  |
            Controls (7, 10)
                  |
           Lee says purchase
                  |
            Speaks For (5)
                  |
         Lee controls purchase
                  |
            Controls (1, 6)
                  |
               KL ⇒ Lee
                  |
            Controls (2, 8)
                  |
          KCA says (KL ⇒ Lee)
                  |
   Assumptions (1), (2), (4), (5), (6)
```
