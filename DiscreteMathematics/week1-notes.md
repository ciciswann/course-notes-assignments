# Logic

* [Lecture](#lecture-notes)
* [Logic Gates](#logic-gates)
## Lecture Notes
* A **proposition** is a statement that is either true or false
* Use notation to represent propositions (p, q, r)
* We can create new statements by altering or combining simple propositions
#### **Knight and Knave Puzzle**
  * An island is inhibited by knights and knaves. Knights always tell the truth and Knaves always lie. You meet A and B.
  * A says: B is a Knave. \
  B says: A and I are both knights. \
  ***What is A? What is B?*** 

| B is a knight  | A is a knight | Since A says B is a Knave, then A cannot be a knight. | ❌|
| --- | ---- | ---- | ----|
| B is a knight  | A is a knave | If B is a knight, then A must be a knight | ❌ |
| B is a knave  | A is a knight  | A is telling the truth, B is lying | ✔️ |
| B is a knave | A is a knave | If A is a knave, then B must be a knight | ❌ |

#### Truth tables (Negation, Conjunction, Disjunction, Implication)

| p | ¬p |
|--|:--:|
| T| F|
|F| T|

| p | q | p ∧ q |
| ---|---|:---:|
| T | T | T|
|T | F | F|
|F | T | F| 
|F | F | F |

| p | q | p ∨ q |
| ---|---|:---:|
| T | T | T|
|T | F | T|
|F | T | T| 
|F | F | F |

| p | q | p → q |
| ---|---|:---:|
| T | T | T|
|T | F | F|
|F | T | T| 
|F | F | T |

* Truth tables are useful for showing logical equivalence between different logical expressions

## Logic Gates