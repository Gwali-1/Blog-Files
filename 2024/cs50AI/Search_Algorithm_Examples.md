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

Taking an AI course that focuses more on the foundation of the technology, discussing the ideas, concepts and algorithms that give rise has always been on my list
and [_Havard's cs50AI Introduction to aitificial intelligence with python_](https://cs50.harvard.edu/ai/2024/) is just what I was looking for. 
I am not new to cs50 courses and I still believe everyone starting out to learn about software should first take [cs50X _Introduction to Computer Science_](https://pll.harvard.edu/course/cs50-introduction-computer-science).

Modern artificial intelligence has become very heavily abstracted. Starting out your'e bound to interface with severa large libraries and frameworks. 
Starting at this level means building on this giant abstraction as a foundation and that's a no for me. So for the first post we discuss the first lecture which 
talks about search algorithms and how they portray intelligence in machines in the form of smart decision making.





### Search Algorithms

We shall consider situations where we are trying to achieve a goal as a solution to a problem.An example of such problems can be navigating a maze , driving directions to
a location etc but basically a problem that assumes the form of taking a squence of actions to arrive at the solution. Search algorithms allow us to navigate or reach this solution by 
following a systematic approach while taking some things into considerations. The outcome is we end up with a scenario where we are able to simulate decision making process at varoius point
in our search, ie at decision points. As a Human being when you are solving a problem you tend to apply reasoning , learning from actions that have workked or failed  ie mostly 
solve problems by applying cocnitive features , like past experiences , thought and learning as they progress .

Such can also be   realized in machines or percieved by modelling it with intelligent algorithms and encoding relevant details of information relevant to the problem being solved,
while the machine might not have a brain(or does it ) you will realize it is able to navigagte a problem and find a solution almost as if it knew what it was doing . 


I mean under the hood it it interpretting informations a a squence of bits but the outputted behaviour is a system that we perciece as intelligent and that is sort of the driving idea we should keep in mind here.
Artificial intelligence is the simulation of humna cognitive features or intelligence in machines . We simulate it.

 We shall look at 4 algorithms in total grouped under 2 categpries

* informed search
* uninformed search

simply put  *informed search algorithm* is an algorthm that uses or applies problem specific knowledge to solve the problem. What that means it the algorithm does not attempt to solvethe problem with intuition
or blind. It relies on certain iportant details about the problem it is solving at every decision point. example condidering say the race of an individual when searching for a criminal suspect or
say how geograhically close a point is to a location when tring to navigate to a target

uninformed search on the other hand is a search algorthm that does not have problem specific knowledge hence attempts to solve the search problem systematically


Starting with uninformed algorithms , lets explores some examples.
examples of uninformed searh algorithms include

* Breadth frist searh(BFS) and  depth first searh(DFS)

Before we proceed there are a few components we nee to define so we understand the algorthmprocedure

Agent

state 

actions

transiton model 

goal test 

### Breadth first search algorthm

BFS is a search alorthms that explores the shallowest node in the fronteir. What this means is in BFS ,the nodes we pick to examine next are closer to the node 
that are being examined or nodes that are at a level of depth before going further. As mentioned above the fronteir is a datastrcuture. In other tp achieve this effect of selecting 
shallow nodes the data structure we emplre here is a Queue. Queue has first in first out principle so in effect the nodes that go into the fronteir  freshly do not stay long as they are immediatley 
explored next.







what is informed search
what is uninformed search



types of each 
what are they 

pseudocode for algorithms









