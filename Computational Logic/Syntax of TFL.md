---
tags:
  - logic
---
# Truth Functional Logic
Sentences can be build from each other:
- Taylor Swift is not French 
- Taylor Swift is French
The truth value of the sentence can be taken from another one.

### Compound Sentence: 
A sentence whose truth value is a function of the truth of its component sentences. 
The truth of a compound sentence it comes uniquely from the truth of the sentences that composed. 

#### Natural Language:
A laguange is natural if it evolved naturally (not designed by people), e.g. spanish, english...

#### Formal Language: 
Designed by people for specific applications. There are explicit and precise rules for its syntax and semantics. Programming languages are formal languages

## Vocabulary (3 elements): 
- atomic sentences ($A, B, C_{3123}, C_1, \cdots$)
- connectives ($\lnot$ negation, $\land$ conjunction, ...)
- parentheses **used to AVOID AMBIGUITY** e.g. $(A∨B)\rightarrow C$

#### Connectives:
**Its read as:**
- $\lnot$ negation "It is not the case that..."
- $\land$ conjunction "Both ... and ..."
- $\vee$ disjunction "Either ... or ..."
- $\rightarrow$ conditional "If ... then ..."
- $\leftrightarrow$ biconditional "... if and only if ..."

**Cheatsheet:**
$\lnot A$:  No A. 
$A ∧ B$: A and B.
$A ∨ B$:  A or B.
$A \rightarrow B$: If A, then B. 
$A \leftrightarrow B$: A if and only if B. 

#### Parentheses:
They are used only to avoid ambiguity. 
The sentence $A \vee B \rightarrow C$ can be read as _"if A or B, then C"_ or as _"A or, if B, then C"_. To avoid ambiguity you use the parentheses:
- $(A \land B) \rightarrow C\;$ _"if A or B, then C"_
- $A\land (B\rightarrow C)\;$ _"A or, if B, then C"_

Avoid ambiguity = Every sentence of TFL must be read in one, and only one way. Sentences in English can be ambiguous: _"I saw someone on a hill with a telescope"_, but in TFL they cannot be. This feature of TFL can help us express our thoughts clearly and help us design clear loops in software or verify data unambiguously.
External parentheses do not avoid ambiguity, therefore there is no need for them.

## Syntax (RULES): 
1. Every sentence letter is a sentence.
2. If $A$ is a sentence then $\lnot A$ is a sentence.
3. If $A$ and $B$ are sentences, then $(A \vee B)$ is a sentence.
4. If $A$ and $B$ are sentences, then $(A \land B)$ is a sentence.
5. If $A$ and $B$ are sentences, then $(A \rightarrow B)$ is a sentence.
6. If $A$ and $B$ are sentences, then $(A \leftrightarrow B)$ is a sentence.
7. Nothing else is a sentence.

Use these rules to figure out if symbols from TFL vocabulary are sentence:
>$A\rightarrow(B\land C)$ is a sentences? Yes, because:
>$A, B, C$ are sentences by Rule 1.
>Then, $(B \land C)$ is a sentence by Rule 3.
>Then $A\rightarrow(B\land C)$ is a sentence by Rule 5.
