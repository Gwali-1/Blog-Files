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

Simply put, an informed search algorithm is an algorthm that uses or applies problem specific knowledge to solve the problem. What that means is the algorithm does not attempt to solve the problem with intuition
or solve it blind, it relies on certain important details about the problem it is solving at every decision point. Eg: considering the race of an individual when searching for a criminal suspect or
how geograhically close a point is to a location when tring to plot directions to a it.

*uninformed Search*

Uninformed search on the other hand is a search algorithm that does not have problem specific knowledge hence attempts to solve the search problem systematically.




Starting with uninformed algorithms, let's explore some examples but before we proceed let's define a few important 
components for context.
---
*Agent:*

*State:* 

*Action:*

*Goal Test:* 

---

1. *Breadth First Search (BFS)*

BFS is a search alorthms that explores the shallowest node in the fronteir. What this means is in BFS ,the nodes we pick to examine next are closer to the node 
that are being examined or nodes that are at a level of depth before going further. As mentioned above the fronteir is a datastrcuture. In other tp achieve this effect of selecting 
shallow nodes the data structure we emplre here is a Queue. Queue has first in first out principle so in effect the nodes that go into the fronteir  freshly do not stay long as they are immediatley 
explored next.


2. *Depth First Searh (DFS)*




