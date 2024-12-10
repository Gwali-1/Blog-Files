<!-- markdownlint-disable-file -->
## Introduction




As part of an Artificial intelligence course I'm taking ,I have decided to write down thoughts, ideas and learnings from the course as
I progress. This is in no way a form of note taking as I do all my note taking with a pen and a book, old fashioned style(at least it feels like it has become so to me) but 
me just trying to leave a bit of digital footprint on my learnings of artificial intelligence as a field.Why I'm saying this?
I shall try my best to  write down my thoughts in a strutured manner and communicate as comprehensively as i can but i make no promises here . The general tone assumed shall be one 
of me talking to myself and trying to make sense of concepts or information learned and breaking it down to it's most basic form while trying to avoid all uneccesary technical jargons.



For the most part of this year , the words "AI",  have been among my muted words on twitter(now X). There was a sort of toxic hype around the subject i didn't like.
I have great interest in learning about the inner working of intelligent systems but engagement farming focused posts and shallow conversations about the topic was something i 
just coudn't take. It was almost similar to the period of the NFTs and if you experienced this you know exactly what i'm taking about. 

I have always had plans to take an AI course that will focus more on the foundation of the technology , discussing the ideas , concepts and algorithms that give rise
intelligent systems and _Havard's cs50AI Introduction to aitificial intelligence with python_ is perfect one for me. I am not new to cs50 courses and i still believe 
everyone starting out to lean about software should first take cs50X _Introduction to Computer Science_.

Modern artificial intelligence  has become a heavily abstracted field , which large libraries and frameworks that aid in your work and i am well aware of that. That is not what i was looking for.
this course takes it from the foundations, describing the concepts ,ideas  and foundation of artificial intelligence and that is exactly what i wanted.  
For the forst post we discuss the first lecture which talks about search algorithms and how they portray intelligence in machines in the form  of smart decision making.




### Search Algorithms

We shall consider situations where we are trying to achieve a goal as a solution to a problem.An example of such problems can be navigating a maze , driving directions to
a location etc but basically a problem that assumes the form of taking a squence of actions to arrive at the solution. Search algorithms allow us to navigate or reach this solution by 
following a systematic approach while taking some things into considerations. The outcome is we have end up with a scenario where we are able to simulate decision making process at varoius point
in our searh , we shall call these decision point . As a Human being when you are solving a problem you tend to apply reasoning , learning from actions that have workked or failed  ie mostly 
solve problems by applying cocnitive features , like past experiences , thought and learning as they progress .

Such can also be   realized in machines or percieved by modelling it with intelligent algorithms and encoding relevant details of information relevant to the problem being solved,
while the machine might not have a brain(or does it ) you will realize it is bale to navigagte a problem and find a solution almost as if it knew what it was doing . 


I mean under the hood it it interpretting informations a a squence of bits but the outputted behaviour is a system that we perciece as intelligent and that is sort of the driving idea we should keep in mind here.
Artificial intelligence is the simulation of humna cognitive features or intelligence in machines . We simulate it.

 We shall look at 4 algorithms in total grouped under 2 categpries

* informed search
* uninformed search

simply 
informed search algorithm is an algorthm that uses or applies problem specific knowledge to solve the problem. What that means it the algorithm does not attempt to solvethe problem with intuition
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









