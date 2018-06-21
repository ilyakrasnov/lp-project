### Sprint Plannig - Integer Linear Optimization

Ilya Krasnov (341008159)

#### Problem descriptionIn

A small startup follows the SCRUM methodology for their software development process. The process is devided in weekly *sprints*. Multiple feature suggestions are being recorded in a *backlog* and before each sprint the team gets together to estimate the amount of work needed to be donw by every team member (*frontend developer*, *backend developer* and *designer*) for every feature. In addition, every feature has a number attached to it, indicating (not like in real SCRUM) the importance of a given feature to the business. One of the startup's core principles beyond building the business is a sustainable work/life balance, so no team member works more than 40 hours - the availability of team members is known upfront. 

Our goal is to decide which features to work on in a given sprint so that we achieve the maximum amount of story point.

#### Backlog and team availabilities

**Feature**|**Points**|**Frontend (h)**|**Backend (h)**|**Design (h)**
:-----:|:-----:|:-----:|:-----:|:-----:
f1|3|5|3|2
f2|8|10|10|4
f3|13|0|25|0
f4|5|18|6|3
f5|1|8|6|12
f6|21|10|4|8
f7|13|2|10|4
f8|2|4|6|2

**Team availabilities for the given week** 

* Backend developer: 35 hours
* Designer: 40 hours
* Frontend developer: 40 hours


#### Integer Linear Optimization Problem

Features $f_i, i \in [1..8]$ will be decision variables. The objective is to maximize the amount of story points, team member availbilities are constraints. 
The problem is a special case of *Integer Linear Optimization* - *Binary Integer Optimization* where we can decide if we implement or not implement a feature. The variables thus can only take values of $0$ and $1$.


$ max. 3 f_1 + 8 f_2 + 13 f_3 + 5 f_4 + 1 f_5 + 21 f_6 + 13 f_7 + 2 f_8 $

$ s.t. $

$ 5  f_1 + 10 f_2 + 18 f_4 + 8 f_5 + 10 f_6 + 2 f_7 + 4 f_8 \le 40 $

$ 3 f_1 + 10 fv2 + 25 f_3 + 6 f_4 + 6 f_5 + 4 f_6 + 10 f_7 + 6 f_8 \le 30 $

$ 2 f_1 + 4 f_2 + 3 f_4 + 12 f_5 + 8 f_6 + 4 f_7 + 2 f_8 \le 38 $

$ f_i \in \{ 0, 1 \} \forall i \in [1..8] $ 


#### Solving the problem

The problem was solved using the *pulp* packege. The code is available in the [GitHub repository](https://github.com/ilyakrasnov/lp-project) (https://github.com/ilyakrasnov/lp-project).

#### Result and Weekly Plan

The maximum amount of story points that can be achieved under the constraints is *47* and can be done by implementing features $f_2,f_4,f_6$ and $f_7$. The resulting weekly plan for the coming sprint is:

**Feature**|**Story Points**|**Frontend (h)**|**Backend (h)**|**Design (h)**
:-----:|:-----:|:-----:|:-----:|:-----:|:-----:
f2|8|10|10|4
f4|5|18|6|3
f6|21|10|4|8
f7|13|2|10|4
**Total**|**47**|**40**|**30**|**19**

#### Runtime

The performance of the package for the given problem (having only 3 constraints) was acceptable. However other users report the package being slow for a large number of constraints: *'..[t]aking 3 minutes to add only 1500 constraints...'* 
 ([https://groups.google.com/forum/#!topic/pulp-or-discuss/DgI25x_zvL8] ([https://groups.google.com/forum/#!topic/pulp-or-discuss/DgI25x_zvL8]))