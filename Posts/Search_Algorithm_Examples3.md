---
title: "Search Algorithms 3"
slug: "search-algorithms"
date: "2025-07-06"
tags: [AI, Search]
---

# Foreword

As part of an artificial intelligence course, I have decided to write down my thoughts, ideas, and learnings as I progress through it.
This is in no way a form of note-taking as I do all my note-taking with a pen and a book, old-fashioned style (at least that's how it feels these days) but
I want to leave a bit of a digital footprint on some of my learnings of AI concepts. Why I'm saying this?
I shall try my best to write down my thoughts in a structured manner and communicate comprehensively. But the general tone of the writing shall be one
of me talking to myself and trying to make sense of concepts or information I have learned while breaking it down to its most basic form.

> For most of this year, words like "AI", and "Large language models" have been among my muted words on Twitter (now X). There was a toxic hype around the subject I don't
> subscribe to. Even tho I have always been interested in learning about the inner workings of intelligent systems, the engagement farming-focused posts and shallow conversations about the topic were things I
> just couldn't take. It was almost similar to the period of the NFTs and if you experienced this you know exactly what I’m talking about.

Taking an AI course that focuses more on the foundation of the technology, and discussing the ideas, concepts, and algorithms that give rise to intelligent systems has always been on my list
and [_havard's cs50AI - Introduction to artificial intelligence with python_](https://cs50.harvard.edu/ai/2024/) is just what I was looking for.
I am not new to cs50 courses and I still believe everyone starting to learn about software should first take [_cs50X - Introduction to Computer Science_](https://pll.harvard.edu/course/cs50-introduction-computer-science).

Modern artificial intelligence has become very heavily abstracted. Starting, you’re bound to interface with several large libraries and frameworks.
Starting at this level means building on this giant abstraction as a foundation and that's a no for me. So for the first post, we discuss the first lecture which
talks about search algorithms and how they portray intelligence in machines in the form of smart decision-making.

### Search Algorithms

We shall consider situations where we are trying to achieve a goal as a solution to a problem. An example of such problems can be navigating a maze, driving directions to
a location, etc but a problem that assumes the form of taking a sequence of actions or steps to arrive at a solution. Search algorithms are how we navigate or reach this solution. We
shall follow a systematic approach while considering some things. The outcome is a scenario where we can simulate the decision-making process at various points
in our search. As humans, when we try to solve certain problems that require a sequence of actions we take advantage of our cognitive abilities, it is these same abilities we try to realize in machines
artificially. Even tho realistically, under the hood, it is a sequence of bits being manipulated that doesn't matter because the observed behavior is a system that
is intelligent and that is the point here. _Artificial intelligence is just the simulation of human cognitive abilities in machines._

Ok so now let's take a look at 4 algorithms in total grouped under 2 categories

- Informed Search
- Uninformed Search

## **Informed Search**

Simply put, an informed search algorithm is an algorithm that uses or applies problem-specific knowledge to solve the problem. What that means is the algorithm does not attempt to solve the problem with intuition
or solve it blindly, it relies on certain important details about the problem it is solving at every decision point. E.g. considering the race of an individual when searching for a criminal suspect or
how geographically close a point is to a location when trying to plot directions to it.

## **Uninformed Search**

Uninformed search, on the other hand, is a search algorithm that does not have problem-specific knowledge and, hence, attempts to solve the search problem systematically.
<br>

Before I explore examples of these algorithms, I’ll define some terms to provide more context, as they tend to appear a lot in explanations  going forward

## Components For Context.

**Agent:** An agent can be thought of as an entity that acts on its environment in a particular state.

**State:** State is the configuration of an environment or how it appears.

**Action:** Actions refer to legal moves an agent can perform in a particular state.

**Goal Test:** Since we are considering problems where we are trying to achieve a goal, we need a way to determine if we have reached this goal in every stage. This is
the goal test.

**Frontier:** A frontier can be thought of as a data structure that contains nodes that are yet to be explored in our search for a solution. The type of data structure used is important and dictates
what type of algorithm is being used. This is because it affects things like how next-to-be-explored nodes are added or removed from the frontier.

**Node:** A node can also be thought of as a data structure that holds data like the value of a current node, what is the parent of this node, what actions were taken to get to the node, etc. For example
in a problem where we are trying to find directions to a location, a typical node might contain location cordinate values indicating where our agent at a point. 

**Node Expansion:** Expanding a node means generating other nodes from it. A scenario is a point in your search where multiple decisions can be made, here every decision becomes a node.

**Decision Point:** This is a point in your search where you have to choose which node to explore next.

---

**Examples of uninformed search algorithms**

1. _Breadth First Search (BFS)_

BFS is a search algorithm that explores the shallowest node in the frontier. What this means is in BFS, the nodes we pick to examine next are closer to the nodes
that are being examined or nodes that are at a shallow level of depth before going further. As mentioned above the frontier is a data structure. To achieve this effect of selecting
shallow nodes the data structure we employ here is a **Queue**. A queue has the *First in First out (FIFO)* principle so in effect the nodes that go into the fronteir freshly do not stay long as they are immediately
explored next.<br> The nodes that enter the froniter and explored are the nodes that are close to the decision point.  For this reason if there solution lies deep in the search space BFS may explore many unnecessary
nodes at a shallow level before finding the solution.Another limitation is that it tends to be memory-intensive as all nodes at a current depth are stored and tracked.

_Pseudocode for BFS looks like this_

> 1. We start with a frontier that contains the initial state(our start point in the search)

> 2. Enter a loop

> 3. Is the frontier empty?
>> If yes, there is no solution to this problem. Return

> 4. Take a node from the frontier

> 5. Check if this is the solution node by doing a goal test on it
>> If yes return node as the solution

>> If not expand the node and add the children nodes to the frontier

_Note that the above pseudocode is simplified and, in some situations, to prevent a recursive node expansion situation where we keep adding nodes that have already been expanded back to the frontier
we use a set data structure to keep track of all expanded nodes. So then any node that goes into the frontier must not be present in the set of expanded nodes._

2. _Depth First Search (DFS)_

DFS is a search algorithm that explores nodes that are deep in the frontier. What this means is in DFS we keep exploring the frontier or search space deeply until when we hit a wall(can't go deep any
further) without passing the goal state, we then backtrack to our last decision point. Because of how the algorithm explores the problem or search space you are only guaranteed to find a solution if the search space is finite else
you might keep going deep without stopping or backtracking. Just like above the pseudocode, DFS follows a similar strategy and the only significant difference is the type of data structure it uses for a frontier. While the frontier used
in BFS is a **Queue**, DFS uses a **Stack**. Stack data structure follows the principle _Last in First out_ and so the effect this has on the algorithm is that nodes that are picked and explored from are the ones
further from the decision point.Note that this results in one of the limitations of this algorithm as the shortest path to a solution is not always guaranteed as you might end up with a suboptimal one path first.

---

**Examples of informed search algorithms**

1. Greedy Best First Algorithm (GBFS)

As stated above, an informed search algorithm uses problem-specific information to help find the solution more quickly and efficiently. If you observe from the above-uninformed algorithms, the mechanisms of decision-making to select
a node from the frontier determines how close we get to the solution and how long it takes us to get there, hence this is an important consideration that will help improve the efficiency of a search algorithm.<br>

GBFS is a search algorithm that chooses a node from the frontier to explore based on an estimate provided by a **heuristic function (h(n))**. A heuristic function gives a value by using problem-specific
information plus other factors, e.g., the state we are currently in. This means when adding nodes to a frontier we will have to consider this estimated value to ensure that nodes are selected
based on how little or small the value is as this value dictates how close or far we are from the solution. The type of data structure we use in a GBFS is a **priority queue**.

_Pseudocode for GBFS looks like this_

> 1. We start with a frontier that contains the initial state(our start point in the search).

> 2. Enter a loop.

> 3. Is the frontier empty?
>> If yes there is no solution to this problem. Return.

> 4. Select a node from the frontier **with the smallest h(n) value**.

> 5. Check if this is the solution node by doing a goal test.
>> If yes, return node as the solution

>> If not expand the node and add the children nodes to the frontier **based on the value as provided by h(n) / heuristic**

As you can see, the code structure will be similar to the one described for the uninformed search examples but with a slight difference.
The frontier is now a priority queue, and we add and select nodes to the frontier based on their heuristic value(an estimate of how far we are from the solution)

2. A\* Search algorithm

Just like the GBFS algorithm, the A* search algorithm also uses a priority queue as the data structure of its frontier but now we pick a node to expand or explore based on the value provided by **g(n) + h(n)**.
From above we know that **h(n)** is the heuristic function and gives us an estimate of how far or close we are to the solution but what is **g(n)**.<br>
**g(n)** is yet another function that gives us a value to consider. The efficiency of a GBFS is determined by how good the heuristic function you have is. It is fast, but in the case where you have a poor heuristic, it is flawed.
A* search algorithm is an improvement that tends to do away with the sole dependence on the heuristic and considers another value which is _g(n)_. Where _g(n)_ can be thought of as the cost it takes to reach the node to explore next, from
the initial position of the search. Considering this value, our pseudocode remains almost the same with a slight difference.

_Pseudocode for A_ Search looks like this\*

> 1. We start with a frontier that contains the initial state(our start point in the search).

> 2. Enter a loop.

> 3. Is the frontier empty?
>    > If yes there is no solution to this problem. Return.

> 4. Take a node from the frontier **with the smallest h(n)+ g(n) value**.

> 5. Check if this is the solution node by doing a goal test on it
>    > If yes return node as the solution
>    > If not expand the node and add the children nodes to the frontier **based on the value as provided by h(n) + g(n)**

---

### In conclusion

The first lecture explored an approach to designing and programming a system to solve particular types of problems. It demonstrated that through search algorithms, we can simulate the ability of decision-making and allow machines to navigate a problem space systematically or using problem-specific knowledge that is encoded into it.


### Links

* [What is the difference between informed and uninformed searches?](https://stackoverflow.com/questions/39760905/what-is-the-difference-between-informed-and-uninformed-searches)
* [The Informed vs. Uninformed Search Algorithms](https://www.baeldung.com/cs/informed-vs-uninformed-search)
* [Lecture 0 notes](https://cs50.harvard.edu/ai/2024/notes/0/)

