---
tags:
  - algebra
---
The number of columns must be equal to multiply two matrices:
$$
M_{m \times n} \times M_{n \times p} \rightarrow M_{m \times p}
(A, B) \mapsto A \cdot B
$$

##### Properties of the matrix product:
- Identity $I \cdot A = A = A \cdot I$ where $I$ is the identity matrix corresponding to the matrix space where $A$ is from.
- Associative: $A(BC) = (AB)C = ABC$
- Distributive: $A(B + C) = AB + AC$
- Non Commutative: For any matrices $A$ and $B$ where it exists $A\cdot B$, $A\cdot B \neq B\cdot A$

##### Product and Transpose:
$$
(A\cdot B)^T = B^T \cdot A^T
$$

Prof: 
$$
(A\cdot B)^T_{ij}
$$

$$
A\cdot B \rightarrow m \times p
$$

$$
\therefore [A\cdot B]^T \text{ has size } p \times m
$$

$$
\therefore B^T \cdot A^T \text{ has size } p \times m
$$

$$
\Rightarrow [(A\cdot B)^T]_{ij} = [A\cdot B]_{ij}
$$

$$
= \sum^{m}_{k=1} A_{jk} B_{ki} = \sum^{m}_{k=1} B_{ki} A_{jk} = \sum^{m}_{k=1} B^T_{ik} A^T_{kj} \Rightarrow (A\cdot B)^T = A^T \cdot B^T
$$


#### Invertible Matrices
$$ A \in M_m \text{ is invertible if } \exists B \in M_m \text{ such that:} $$
$$ A \cdot B = I_m = B \cdot A $$

Properties:
- $(A^T)^{-1} = (A^{-1})^T$
- $A$ and $B$ are both invertible $\Rightarrow A\cdot B$ is invertible and $(A\cdot B)^{-1} = B^{-1} A^{-1}$

Prof of properties:
a) 
$$(AA^{-1})^T = I_m^T $$
$$(A^{-1})^T A^T = I_m = A^{-1}A  $$
So $A^T$ is invertible and $(A^T)^{-1} = (A^{-1})^T$. 

b)
$$ (AB)(B^{-1}A^{-1}) = A(BB^{-1})A^T = AI_m A^{-1} = AA^{-1} = I_m $$
$$ (B^{-1}A^{-1})(AB) = B^{-1}I_m B = B^{-1}B = I_m \Rightarrow (AB)^{-1} = B^{-1}A^{-1} $$

Moreover in general: 
$$
(A_1, A_2, A_3, \cdots, A_n)^{-1} = A_{1}^{-1}, A_{2}^{-1}, \cdots, A_n^{-1}
$$

#### Elementary operations on matrices (by rows)
- $R1$: Scalar multiplication (non-zero). $R_i \mapsto \lambda R_i, \lambda\neq 0$
- $R2$: Add to a row $R_i$ a multiple of another row $R_j$. $R_i \mapsto R_i + \mu R_j, i\neq j$
- $R3$: Row permutation $R_i  ↔ R_j, i\neq j$

  Observations:
  1. If we apply these operations to an augmented matrix, the solutions do not change.
  2. The operations are invertible:
$$R1: R_i \mapsto \frac1\lambda R_i$$
$$R2: R_i \mapsto R_i + \mu R_j$$
$$R3: R_i  ↔ R_j$$
These operations are done in the following way by an elemental matrix $P$:
$$ A \mapsto PA = A'$$
Thus we can see that:
$$ A = P^{-1}A'$$
and that $P$ must be invertible. 
We can find the matrix $P$ that describes an elementary operation $R_i$ by applying the operation to the identity with the respective size.

**To columns:**
These operation can be also applied to columns but with a small difference, the elementary matrix is multiplied on the left of $A$:
$$ A \mapsto AQ = A'$$
Where $Q$ is a column elementary matrix.

These operation can be concatenated (form a sequence), if we first do an operation described by the matrix $P_1$ and then another operation described by $P_2$ the final system A' is:
$$
A' = P_2(P_1 A) = P_2P_1A
$$

Definition of Row Equivalence: 
For $A, B \in M_{m\times n}(\mathbb{R})$, we can say that $A$ and $B$ are row equivalent (written as $A\sim B$), if we can pass from $A$ to $B$ by a sequence of elementary row transformations. This is the same as saying that $B = P\cdot A$ where $P$ can be the result of several elementary matrices (or just one).

Properties of $\sim$ (row equivalence):
1. Reflexive $A\sim A$
2. Symmetry $A \sim B = B \sim A$. If $B =PA \Rightarrow A = P^{-1}B$
3. Transitive: if $A\sim B$ and $B\sim C$ then $A\sim C$: If $B =PA$ and $C=P'B \Rightarrow C = P'B = (P'P)A$
These properties form part of a equivalence relation. 

**Motivation for the Simplified Form of a Matrix:**
$$
\begin{vmatrix}
1 & 0 & 0 & 3 \\ 0 & 1 & 0 & 0\\ 0 & 0 & 1 & 1
\end{vmatrix} \Rightarrow \begin{cases}
x = 3 \\ y = 0 \\ z = 1
\end{cases}
$$
When a linear system is described by an identity matrix it is very simple to solve. The goal of matrix simplification is arriving to a state equal to an identity or similar (reduced row echelon form). 

Example:
#### Reduced Row Echelon Form
A matrix is in reduced row-echelon form the elements below the main diagonal are zero, the main diagonal is composed of ones (not taking into account the independent column), and finally with the last row composed of all zeros (even the right-most column). (LOOK MORE)
For example: 
$$
\begin{pmatrix}
1 & 1 & -8 & -5 \\
0 & 1 & -17 & -17 \\
0 & 0 & 1 & 1
\end{pmatrix}
$$
This particular matrix can be reduced even further to an identity matrix by $R_2 \mapsto R_2 + 17 R_3$, $R_1 \mapsto R_1 + 8R_3$ and then $R_1 \mapsto R_1 - R_2$:
$$
\begin{pmatrix}
1 & 1 & -8 & -5 \\
0 & 1 & -17 & -17 \\
0 & 0 & 1 & 1
\end{pmatrix} \rightarrow
\begin{pmatrix}
1 & 1 & 0 & 3 \\ 0 & 1 & 1 & 0 \\ 0 & 0 & 1 &1
\end{pmatrix} \rightarrow \begin{pmatrix}
1 & 0 & 0 & 3\\
0 & 1 & 0 & 0\\
0 & 0 & 1 & 1
\end{pmatrix}
$$

A more general way to describe the row-echelon form:
$$
\begin{bmatrix}
I_c & C & B_1 \\ 0 & 0 & 0
\end{bmatrix}
$$
#### Groups
Definition:
> Consider a set $\mathcal{G}$ and an operation $\otimes: \mathcal{G} \times \mathcal{G} \rightarrow \mathcal{G}$ defined on $\mathcal{G}$. Then $G:=(\mathcal{G}, \otimes)$ is called a group if the following hold:
> 1. Closure of $\mathcal{G}$ under $\otimes$: $\forall x,y \in \mathcal{G}: x\otimes y \in \mathcal{G}$
> 2. Associativity: $\forall x,y,z \in \mathcal{G} : (x\otimes y) \otimes z = x\otimes(y\otimes z)$
> 3. Neutral element: $\exists e \in \mathcal{G} \;\forall x\in \mathcal{G}: x\otimes e = x \text{ and } e\otimes x = x$
> 4. Inverse element: $\forall x \in \mathcal{G} \; \exists y \in \mathcal{G} : x \otimes y = e \text{ and } y\otimes x = e$ where $e$ is the neutral element. We often write $x^{-1}$ to denote the inverse element of $x$

**Abelian group**:
$\forall x,y \in \mathcal{G}: x\otimes y = y \otimes x$ . A group that is commutative (for all elements in the group) is called an _Abelian group_. 

There are **General Linear Groups**: 
>The set of regular (invertible) matrices $A\in \mathbb{R}^{n\times n}$ is a group with respect to the matrix multiplication as defined previously. This general linear group will be write as $GL(n, \mathbb{R})$. However, it is not a Abelian group since matrix multiplication is not commutative.

