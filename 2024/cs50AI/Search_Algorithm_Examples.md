<!-- markdownlint-disable-file -->
## Foreword

As part of an artificial intelligence course I'm taking, I have decided to write down my thoughts, ideas and learnings as I progress through it.
This is in no way a form of note taking as I do all my note taking with a pen and a book, old fashioned style (at least that's how it feels these days) but 
me just trying to leave a bit of digital footprint on some of  my learnings of AI concepts.Why I'm saying this?
Because I shall try my best to  write down my thoughts in a strutured manner and communicate as comprehensively as I can but the general tone of the writing shall be one 
of me talking to myself and trying to make sense of concepts or information I have learned while breaking it down to it's most basic form.

> For the most part of this year, words like "AI", "Large language models"  have been among my muted words on twitter(now X). There was a sort of toxic hype around the subject I don't really
> subscribe to.Even tho I have always been interested in learning about the inner working of intelligent systems, the  engagement farming focused posts and shallow conversations about the topic was something I 
> just coudn't take. It was almost similar to the period of the NFTs and if you experienced this you know exactly what i'm taking about. 

Taking an AI course that focuses more on the foundation of the technology, discussing the ideas, concepts and algorithms that give rise to intelligent systems has always been on my list
and [_havard's cs50AI - Introduction to artificial intelligence with python_](https://cs50.harvard.edu/ai/2024/) is just what I was looking for. 
I am not new to cs50 courses and I still believe everyone starting out to learn about software should first take [_cs50X - Introduction to Computer Science_](https://pll.harvard.edu/course/cs50-introduction-computer-science).

Modern artificial intelligence has become very heavily abstracted. Starting out, your'e bound to interface with several large libraries and frameworks. 
Starting at this level means building on this giant abstraction as a foundation and that's a no for me. So for the first post we discuss the first lecture which 
talks about search algorithms and how they portray intelligence in machines in the form of smart decision making.





### Search Algorithms

We shall consider situations where we are trying to achieve a goal as a solution to a problem. An example of such problems can be navigating a maze, driving directions to
a location etc but basically a problem that assumes the form of taking a sequence of actions or steps to arrive at a solution. Search algorithms is how we navigate or reach this solution. We 
shall follow a systematic approach while taking some things into considerations. The outcome is a scenario where we are able to simulate decision making process at varoius point
in our search. As humans , when we try to solve certain problems that require a sequence of actions we take advantage of our cognitive abilities, it is this same abilities we try to realize in machines 
artificially so they can find solutions to problems.Realistically , under the hood it is sequence of bits being manipulated but that doesn't matter because the observed behaviour is a system that 
is intelligent and that is the point here. Artificial intelligence is just the simulation of human cognitive abilities in machines.

Ok so now let's take a look at 4 algorithms in total grouped under 2 categories

* Informed Search
* Uninformed Search


*Informed Search*
---

Simply put, an informed search algorithm is an algorthm that uses or applies problem specific knowledge to solve the problem. What that means is the algorithm does not attempt to solve the problem with intuition
or solve it blind, it relies on certain important details about the problem it is solving at every decision point. Eg: considering the race of an individual when searching for a criminal suspect or
how geograhically close a point is to a location when tring to plot directions to a it.

*uninformed Search*
---


Uninformed search on the other hand is a search algorithm that does not have problem specific knowledge hence attempts to solve the search problem systematically.

<br>

Before i explore examples of these algorithms ill define some terms in other to provide context as they appear in explanations a lot going forward

components for context.
---
**Agent:** An agent can be thought of an entity that acts on it's environement in particular state

**State:**  State is the configuration of an environement or how it appears

**Action:** Actions refers to legal moves and agent can perform in a particular state

**Goal Test:**  Since we are considering problems where are are trying to achieve a goal, we need a way to detemine if we have reached this goal in every stage. This is 
the goal test.

**Fronteir:** A fronteir can be thought of as a data stucture which contains nodes that are yet to be explored in our search for the solution.The type of data structure used is important dictates 
what type of algorthm being used as it dictates things like how nodes next to explored are added or removed from the fronter. 

**Node:** A node can also be thought of as a data structure which holds data like value of a current node, what is the parent of this node , what actions where taken to get to the node etc.

**Node Expansion:** Expanding a node means to generate other nodes from it. A scenario is a point in your search where multiple decisions can be made , here every decision becomes a node.



---

*Starting with examples of uninformed search algorthms* we have 

1. *Breadth First Search (BFS)*

BFS is a search alorthms that explores the shallowest node in the fronteir. What this means is in BFS ,the nodes we pick to examine next are closer to the node 
that are being examined or nodes that are at a level of depth before going further. As mentioned above the fronteir is a datastrcuture. In other tp achieve this effect of selecting 
shallow nodes the data structure we emplre here is a Queue. Queue has first in first out principle so in effect the nodes that go into the fronteir  freshly do not stay long as they are immediatley 
explored next.<br> The fronteir of a BFS is a queue. Queue data structures follor a first in first out principle and hence nodes that enter the fronter  and looked at at nodes that are close to the decision 
point.

*Pseudocode for BFS looks like this*

> 1. We start with a fronteir that contains the intitial state(our start point in the search)

> 2. Enter a loop

> 3. Is the fronter empty? 
>> if yes there is no solution to this problem . return

> 4. Take a node from the fronteir 

> 5. Check if this is the solution node by  doing a goal test on it 
>> if yes return node as the solution 
>> if not expand the node and add the children nodes to the fronteir 


Note that above pseudocode is simplified and in some situations in other to prevent a recursive node explansion situation where we keep adding nodes that have already been expanded back to the Fronteir
we use a set data structure to keep track of all exp,anded nodes. Then any node that goes into  the fronteir must not exist in the set of expanded nodes.




2. *Depth First Searh (DFS)*
DFS is a searhc algorithm that explores nodes that are deep in the fronter. what this means is in DFS we keep exporing the fronteir or search space in a deep fashion and when we hit a wall(can't go deep any
futher) without passing the goal state we backtrack to our last decision point. Because of how the algorithm explores the problem or search space you are only guranteed to find a solution if search space is finite or
you'll keep going deep without stoping or backtracing. Just like above the pseudocode of DFS follows a similar strategy and the only significant difference is the type of data structure the fronteir is. While the fronteir used 
in BFS is a **Queue**, DFS uses a **Stack**. Stack data structure follows the principle Last in first out and so the effect this has on out algorthm is the nodes which are picked and explored from  the fronteir are the ones 
further from the decision point 



---
*Examples of informed search algorthms* 

1. Greedy Best First Algorthm (GBFS)
As stated  above , informed search algorithm uses problem specific information to help find the solution more quickly and efficiently. If you observe from the above uninformed algorthms, the mechnaisms of decision making to select 
a node from the fronteir determines how close we get to the solution and how long it takes us to get there hence this is an important consideration that will improve the efficiciency of an algorithm.<br>

GBFS is a search algorthm that chooses a node from the fronteir to explore based on estimate provided by a **heurtistic function**(h(n)). A heurtistic function gives as a value by using problem specific
information plus other factores eg like the node or state we are currently in.  This means when adding nodes to a fronteir we will have to consider this estimated valkue to ensure that  nodes are selected 
based on how little or small the value is as this value dictates how close or far we are from the solution. The type of data structure we shall use in a GBFS is a **priority queue**. 


*Pseudocode for GBFS looks like this*

> 1. We start with a fronteir that contains the intitial state(our start point in the search)

> 2. Enter a loop

> 3. Is the fronter empty? 
>> if yes there is no solution to this problem . return

> 4. Take a node from the fronteir **with the smallest h(n) value**

> 5. Check if this is the solution node by  doing a goal test on it 
>> if yes return node as the solution 
>> if not expand the node and add the children nodes to the fronteir **based on the value as provided by h(n) / heurtistic **


As you can see the code structure will be similar to the one described for out uninformed search examples but with a slight difference.
The frontier is now a priority queue and we add nodes to the fronteir based on their heurtistic value(an estimate of how far we are from the solution)




2. A* Search Algorthm
Just like GBFS algorthm , the A* search algorthm also uses a priority queue as the data structure of it's fronteir but now we pick a node to expand based on the value provided by g(n) + h(n).
From above we know that h(n) is the heurtistic function and gives us an estimate of how far or close we are from the solution but what is g(n).<br>
g(n) is yet another function that gives us a value to consider. The efficiciency of a GBFS  is determined by good a heurtistic function you have.It is fast but in the case where you have a poor heurtistic it is flawed.
A* search algorithm is an improvement that tends to do away with the sole dependence on the heurtistic and cosiders another value which is g(n). Where g(n) can be thought of as the cost it took to reach the node to explored from 
the intitial position. Cosidering this value our pseudocode remains the same  as above with a slight difference



*Pseudocode for A* Search looks like this*

> 1. We start with a fronteir that contains the intitial state(our start point in the search)

> 2. Enter a loop
> 3. Is the fronter empty?
>> If yes there is no solution to this problem . return

> 4. Take a node from the fronteir  *with the smallest h(n + g(n)) value*
> 5. Check if this is the solution node by  doing a goal test on it 
>> If yes return node as the solution 
>> If not expand the node and add the children nodes to the fronteir *based on the value as provided by h(n) + g(n)*


---

### In conclusion










