# MDP REPRESENTATION

### AIM:
To represent the elevator scheduling problem in Markov Decision Problem (MDP) form.

---

### PROBLEM STATEMENT:

**Problem Description:**  
The agent’s role is to control an elevator in a multi-floor building. The objective is to serve passenger requests efficiently while minimizing waiting time and energy consumption.

---

### State Space:

{0,1,2} = {Elevator at Floor 0, Floor 1, Floor 2}

### Sample State
{1} = {Elevator at Floor 1}
### Action Space
{0,1} = {Move UP, Move DOWN}

### Sample Action
{0} = {Move UP from current floor}

### Reward Function
R =
+10 → if serving a passenger request
-1 → for each move (time penalty)
0 → if idle without request

### Graphical Representation
<img width="468" height="581" alt="image" src="https://github.com/user-attachments/assets/f5c4f53a-f767-44b2-835a-cf5170c69e62" />


## PYTHON REPRESENTATION:
```
Developed by: SAKTHIVEL M
Reg no: 212222240088
```
```python
P = {
    0: { # Elevator at Floor 0
        0: [(1.0, 1, -1, False)],   # UP → Floor 1
        1: [(1.0, 0, 0, True)]      # DOWN invalid → stays (terminal)
    },
    1: { # Elevator at Floor 1
        0: [(1.0, 2, -1, False)],   # UP → Floor 2
        1: [(1.0, 0, -1, False)]    # DOWN → Floor 0
    },
    2: { # Elevator at Floor 2
        0: [(1.0, 2, 0, True)],     # UP invalid → stays (terminal)
        1: [(1.0, 1, -1, False)]    # DOWN → Floor 1
    }
}

print(P)
```
## OUTPUT:
<img width="339" height="519" alt="image" src="https://github.com/user-attachments/assets/74aa04a6-78e8-4592-be09-4e144bf4b24f" />


## RESULT:
Thus, the elevator scheduling problem is successfully represented in MDP form.
