## Starvation and Aging in Operating System

 ## Starvation:


It happens when a low priority task ready to enter CPU is unable to get the CPU time for execution and remains in the queue.

127->low priority

0->high priority

Generally we take 127 as low priority and 0 as high priority in Operating System.

Suppose two task A and B arrive for execution with priority 0 and 5 respectivelly,so task A will execute before task B, but during the execution time another process/task (C) arrives which has a priority of 1, this
 will enter the execution queue before task B. Suppose this (arrival of high priority tasks) continues indefinitely, in this way task B will not be able to execute.This is starvation.

So how can we solve the problem?

The answer is Aging

## The Concept of Aging:
 

Let us consider the above situation, when task A and B arrives with priority 0 and 1, what we do is we give an aging constant/priority no to both tasks,and now the execution will be decided by both first come preference and aging constant/priority no. And the aging constant /priority no decreases (priority will increase with decreasing priority no) with time, so if a task B remains in the queue for a long time its aging constant will decrease and in this way, it will be executed some time later.
This is explained by below graph in which priority increases (priority no decreases) with time.



![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1664879768381/mAt4Kho7W.png align="left")


Fun fact /rumors-
 During the shutdown of  the IBM 7094 at MIT  in 1973, a low-priority process that has
 been submitted in 1967 had not run yet, due to starvation.
