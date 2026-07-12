# usaco_know_your_abcs
## link : https://usaco.org/index.php?page=viewproblem2&cpid=1059
## Problem Statement :
Farmer John's cows have been holding a daily online gathering on the "mooZ" video meeting platform. For fun, they have invented a simple number game to play during the meeting to keep themselves entertained.
Elsie has three positive integers A, B, and C (A≤B≤C). These integers are supposed to be secret, so she will not directly reveal them to her sister Bessie. Instead, she gives Bessie seven (not necessarily distinct) integers in the range 1,10^9, claiming that they are A, B, C, A+B,B+C, C+A, and A+B+C in some order.

Given a list of these seven numbers, please help Bessie determine A, B, and C. It can be shown that the answer is unique.

### INPUT FORMAT :
The only line of input consists of seven space-separated integers.
### OUTPUT FORMAT:
Print A, B, and C separated by spaces.

### SAMPLE INPUT:
2 2 11 4 9 7 9
### SAMPLE OUTPUT:
2 2 7

### Problem credits: Benjamin Qi 
## Algorithm :
Read the seven integers into a list.
Sort the list in increasing order.
We know, A+B+C is always ≥ every other quantity (A, B, C, A+B, B+C, C+A), since it's the sum of all three positive numbers — so it must be the maximum value in the list, and A is always ≤ every other quantity, since A ≤ B ≤ C and adding positive numbers only increases values — so A must be the minimum value in the list.
We also know B is always ≤ every remaining quantity except A, since B ≤ C, and B plus any positive number is still ≥ B — so B must be the second-smallest value in the list.
A = smallest element (nums[0]).
B = second-smallest element (nums[1]).
C = largest element (nums[6]) minus A minus B, since the largest element equals A+B+C.
Print A, B, C.

