# Integer Linear Optimization

### Course Project: Ilya Krasnov
### Course Linear Programming @jce by Dr. Yehuda Hassin

#### June 21, 2018
---

![left](pres_images/team.jpg)


## Sprint Planning

* Goal: maximise the amount of important features released
* Given: hour estimation for every feature/team member
* Given: max availability for every team member

---

## Backlog

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

---

## Team Availabilities

**Frontend (h)**|**Backend (h)**|**Design (h)**
:-----:|:-----:|:-----:|:-----:|:-----:
40|35|40|

![inline](pres_images/dev.png)

---

## Problem Definition


$$ max. 3 f_1 + 8 f_2 + 13 f_3 + 5 f_4 + 1 f_5 + 21 f_6 + 13 f_7 + 2 f_8 $$

$$ s.t. $$

$$ 5  f_1 + 10 f_2 + 18 f_4 + 8 f_5 + 10 f_6 + 2 f_7 + 4 f_8 \le 40 $$

$$ 3 f_1 + 10 fv2 + 25 f_3 + 6 f_4 + 6 f_5 + 4 f_6 + 10 f_7 + 6 f_8 \le 30 $$

$$ 2 f_1 + 4 f_2 + 3 f_4 + 12 f_5 + 8 f_6 + 4 f_7 + 2 f_8 \le 38 $$

$$ f_i \in \{ 0, 1 \} \forall i \in [1..8] $$


---

![](pres_images/code.jpg)

## Lets run the code

---

## Solution

**Feature**|**Story Points**|**Frontend (h)**|**Backend (h)**|**Design (h)**
:-----:|:-----:|:-----:|:-----:|:-----:|:-----:
f2|8|10|10|4
f4|5|18|6|3
f6|21|10|4|8
f7|13|2|10|4
**Total**|**47**|**40**|**30**|**19**


--- 

## Thank you
