# Backus-Naur Form (BNF) Overview
Backus-Naur Form (BNF) is a notation used for defining the syntax of formal languages, including programming languages and grammars. It consists of a set of production rules that define how symbols in the language can be combined. Each rule specifies how a non-terminal symbol can be replaced with sequences of terminal and/or non-terminal symbols.

## BNF Example

Given grammar: <br>
`<s>::=<np> <vp>` <br>
`<np>::=(<dp> <adjp> <n>)|<pn>` <br>
`<dp>::=the|a` <br>
`<adjp>::=<adj>|(<adj> <adjp>)` <br>
`<adj>::=big|fat|green|wonderful|faulty|martyr|pretentious` <br>
`<n>::=dog|cat|man|university|father|mother|child|television` <br>
`<pn>::=John|Jane|Sally|Spot|Fred|Elmo` <br>
`<vp>::=(<tv> <np>)|<iv>` <br>
`<tv>::=hit|honored|kissed|helped` <br>
`<iv>::=died|collapsed|laughed|wept` <br>

### Example Sentences
1. the big green fat dog wept - Valid
`<s> ::= <np> <vp>` <br>
`<dp> <adjp> <n> <vp>` <br>
`<dp> <adj> <adjp> <n> <vp>` <br>
`<dp> <adj> <adj> <adjp> <n> <vp>` <br>
`<dp> <adj> <adj> <adj> <n> <iv>` <br>

2. Elmo hit a fat cat - Valid
`<s> ::= <np> <vp>` <br>
`<pn> <vp>` <br>
`<pn> <tv> <np>` <br>
`<pn> <tv> <dp> <adjp> <n>` <br>
`<pn> <tv> <dp> <adjp> <n>` <br>

3. A fat cat helped - Invalid (No direct object)
`<s> ::= <np> <vp>` <br>
`<dp> <adjp> <n> <vp>` <br>
`<dp> <adj> <n> <tv> <np>`

---

# Kripke Structure to Haskell
A Kripke structure is a mathematical model used in modal logic to represent systems with different possible states and transitions. It consists of:
- **W**: A non-empty set of possible worlds.
- **I**: An interpretation function that assigns propositional variables to sets of worlds.
- **J**: A transition relation that describes how agents perceive state transitions.

## Kripke Structure Example

M = <W,I,J> <br>
W = {sw, sc, ns} <br>
I(g) = {sw} <br>
J(Gil) = {(sw, sw), (sc, sc), (ns, ns)} <br>
J(Flo) = {(sw, sw), (sw, sc), (sc, sw), (sc, sc), (ns, ns)} <br>
J(Hal) = {(sw, sw), (sc, sw), (ns, ns)}

### Haskell Representation

```haskell
type PName = String
type PropVar = Char

data Prin = Name PName
           | Together Prin Prin
           | Quote Prin Prin
           deriving (Eq, Show)

type WKripke = Set Int
type IKripke = Set (PropVar, Int)
type JKripke = Set (PName, (Int, Int))
type Kripke = (WKripke, IKripke, JKripke)
```

### Haskell Encoding of Kripke Model

```haskell
I = [(g, sw)]
J = [(Gil, (sw, sw)), (Gil, (sc, sc)), (Gil, (ns, ns)),
     (Flo, (sw, sw)), (Flo, (sw, sc)), (Flo, (sc, sw)),
     (Flo, (sc, sc)), (Flo, (ns, ns)), (Hal, (sw, sw)),
     (Hal, (sc, sw)), (Hal, (ns, ns))]
```

## Kripke Logic to Haskell

### Logical Operators

- **Negation**: `EM[[¬φ]] = W - EM[[φ]]`
- **Conjunction**: `EM[[φ1 Ʌ φ2]] = EM[[φ1]] ∩ EM[[φ2]]`
- **Disjunction**: `EM[[φ1 ꓦ φ2]] = EM[[φ1]] ∪ EM[[φ2]]`
- **Implication**: `EM[[φ1⊃φ2]] = (W - EM[[φ1]]) ∪ EM[[φ2]]`
- **Equivalence**: `EM[[φ1≡φ2]] = EM[[φ1⊃φ2]] ∩ EM[[φ2⊃φ1]]`
- **Says Operator**: `EM[[P says φ]]`
- **Controls Operator**: `EM[[P controls φ]] = EM[[(P says φ) ⊃ φ]]`

### Haskell Encoding

```haskell
em :: Kripke -> Form -> WKripke
em (w,i,j) (Not f) = diff w (em (w,i,j) f)
em (w,i,j) (Or f g) = union (em (w,i,j) f) (em (w,i,j) g)
em (w,i,j) (And f g) = inter (em (w,i,j) f) (em (w,i,j) g)
em (w,i,j) (Imply f g) = union (diff w (em (w,i,j) f)) (em (w,i,j) g)
em (w,i,j) (Equiv f g) = inter (em (w,i,j) (Imply f g)) (em (w,i,j) (Imply g f))
em (w,i,j) (Says p f) = makeSet [n | n <- flatten w, subset (jhelper (jfunction j p) n) (em (w,i,j) f)]
em (w,i,j) (Contr p f) = em (w,i,j) (Imply (Says p f) f)
em (w,i,j) (For p1 p2) = if (subset (jfunction j p2) (jfunction j p1)) then w else empty
```



