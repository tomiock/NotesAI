## Origins 
Alan Turing described a mathematical model of computation that describes an abstract machine, a [[Turing Machine]]. 

Turing completeness:
> The ability for a computational model to simulate a Turing machine. If a program is Turing complete is theoretically capable of expressing all tasks accomplishable by computers (the limitations of finite memory are ignored for a programming language or computer to be called Turing complete).

On 1950 he addressed the problem of AI, and proposed an experiment (the **Turing Test**):
> For a machine to be called "intelligent" it doesn't have to raise suspicion from a human that doesn't know who is talking to.  Make the human think they are having a conversation with another human and no an AI. 

On 1956 there was a _Summer Research project on AI_ at Dartmouth College:
> There were taking the initial steps, coining the term **Perceptron**, making a program that can play **Checkers**. 

##### Perceptron:
Mimicking a brain neuron, the perceptron is a computational unit that takes multiple inputs $x_1, x_2, \cdots, x_m$ performing a weighed (with weights $\omega_1, \omega_2, \cdots, \omega_m$) sum $\sum$ with them and outputting a single output $y$ that is passed through a non-linear activation function $\varphi (\cdot)$:
![[Pasted image 20230922115442.png]]
Multiple perceptrons can be connected in the form of layer. A perceptron from layer $N-1$ gives its output to all perceptrons in layer $N$. Thus, a perceptron from layer $N$ has as many inputs has perceptrons is layer $N-1$. 
![[Pasted image 20230922115404.png]]

## First Advances
#### Search and planning
**State**:
>A specific configuration of a problem (e.g. a particular configuration of a chess board)

**State space**:
>All possible states of a problem (e.g. all possible chess board configurations). Represented by a graph. A line in the graph would be a single change in a state to produce another state. 

**Solution**:
>A trajectory in this graph (following possible single changes) ([[A* Search Algorithm]] type of algorithm that works by searching a path on a state space)

**Planning**: 
>Real object and actions to reach a goal (solution)

**STRIPS** (_[[Stanford Research Institute Problem Solver]]_):
> A planning (algorithm) that works by breaking down a problem into a series of smaller sub-problems (i.e. divide and conquer). A formal language has been created for this planner that is the base of (most) languages in automated planning (action languages).

**Subgoals**:
- [[Sussman anomaly]]:
> The particular case when more than one subgoal/goal are defined and are incompatible with each other
- [[Partial Order Planning]]:
>Approach that only commits to ordering the actions (subgoals/goals) when forced to. These types of plans are known to easily and optimally solve the [[Sussman anomaly]]. 

#### Machine learning: classification
The learning comes from **inductive inference** i.e. learning from examples.
Usually classification can be represented by decision trees. 
An [[ID3 Algorithm]] can be used to generate a decision tree from a dataset. 

#### Vision and robotics 
The main motivation of these subjects its to **robotic arms**.

Hand-eye research:
> Research focusing on how we interact with objects and people (that we can look). In other words Eye-Hand Coordination. 

Blocks world:
> Defined as a planning domain (a "universe" with rules used to define problems and how to solve them). These particular type is a "universe" or "world" where there are different types of blocks on a table that can only be moved one at a time, and can only be placed on top of another block or on the table.  
> It is a "toy problem" that can be used to program an AI which can solve it. This then can help to solve real world problem. It helps us to understand by simplifying problem into these toy worlds. 
> The blocks world is used to explain the [[Sussman anomaly]] anomaly for example. 

_Shakey_ the robot (1970):
> The first general-purpose mobile robot. It combined robotics, computer vision and natural language processing. It was the first implementation of the [[A* Search Algorithm]] and the [[Hough Transform]] (method used for the identification of lines in an image). 
![[Pasted image 20230922115043.png]]


#### Natural Language Processing 
**Written:**
There are several tasks that can be accomplished by written NLP:
- Data recovery (recovering data from old texts??? (idk))
- Question answering
- Information extraction (summarize long texts)
- Automatic language translation

Lexical, syntactical, semantical and pragmatically analyses can also be accomplished. 

**Spoken:**
- Signal processing (speech recognition/segmentation)
- Sequencing (language corpus)
- Speaker model (text-to-speech/speaker recognition)

A language corpus is dataset of existing resources for a given language (dictionaries, newspapers, magazines, books...).

## Winter
#### Lighthill Report
Sir James Lighthill wrote a report where it describes several problems relating to the AI field of that time:
- Criticizes its "great goals"
- Identifies the **combinatorial explosion**
- Issues with scalability for "toy problems", they don't translate well to problems of real size. The solution of the "toy problems" were fine, but upon applying them to real world problem they were flawed. 
- After this report research in AI continued at a slower pace than before. 

#### Combinatorial Explosion
When exploring a problem through a state space, the many possible combinations of the states increased exponentially when the problem size increased. 

Because of this fact, more **heuristic** solutions were pursuit. 
##### Heuristics:
Searching a solution in a reasonable time that is good enough (may be an approximate solution). 
There is a trade-off between execution time and other characteristics of the solution like accuracy/precision and completeness (finding all the solutions). 

Another way to deal with the combinatorial explosion is **pruning**, cutting off entire branches of the state space (described as a graph) depending on different criteria.  

#### Philosophical criticisms
Not really necessary to understand (i think)

**Searle and the Chinese room:**
>A computer executing a program cannot have a mid or understand a problem like humans do. 
>Does a machine literally understand the problem (e.g. understanding Chinese), or does it merely simulate the ability to understand the solution to the problem (e.g. simulating the ability to understand Chinese)?

**Dreyfus and AI assumptions:**
Hubert Dreyfus says that the following assumptions that the faith of AI researchers depend on the time (1965-1972):
> - _The brain processes information in discrete operations by way of some biological equivalent of on/off switches_
> - _The mind can be viewed as a device operating on bits of information according to formal rules_
> - _All knowledge can be formalized_
> - _The world consists of independe facts that can be represented by independent symbols_

**Penrose and the new physics**
In a book published on 1989 (_The Emperor's New Mind: Concerning Computers, Minds and The Laws of Physics_), Penrose argues that the human consciousness is non-algorithm and thus it cannot be modeled by a conventional Turing machine. 
Moreover, he states that it could be modeled by a Quantum Turing Machine (quantum computer) because quantum mechanics plays an esencial role in the human mind.

**Weizenbaum and the moral dilemma (1976)**
Joseph Weizenbaum argues that there is a difference between Deciding and Choosing. 
Deciding is a computational activity that can be programmed. On the other hand, choosing comes from human judgment, not calculations that can be programmed. There is creativity and human values in the act of choosing. 
Therefore, we cannot let computer decide criteria for the definition of tasks/problem because the human values that once made this choices cannot come from computers.
