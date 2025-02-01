Jump game-
Algorithm:
Initialize jumps as 0 (the number of jumps needed), current_end as 0 (the farthest index you can reach in the current jump), and farthest as 0 (the farthest index you can reach so far).
Loop through each index in nums (except the last index):
Update farthest to the maximum of farthest and i + nums[i].
If the current index i is the last index of the current jump (i == current_end):
Increment the jumps.
Set current_end to farthest.
Return jumps when current_end reaches or exceeds the last index (n - 1).

Pseudo Code:
function jump(nums):
    jumps = 0
    current_end = 0
    farthest = 0
    for i from 0 to length of nums - 1:
        farthest = max(farthest, i + nums[i])
        if i == current_end:
            jumps += 1
            current_end = farthest
        if current_end >= length of nums - 1:
            break
    return jumps
Time Complexity:
Time Complexity: O( n ), where n is the number of elements in the nums array. We iterate through the array once.

Implement queue using stack-
Algorithm:
Use two stacks: stack1 for pushing elements, stack2 for popping elements.
For push(x), simply push x onto stack1.
For pop(), if stack2 is empty, transfer all elements from stack1 to stack2. Then, pop the top element from stack2.
For peek(), if stack2 is empty, transfer all elements from stack1 to stack2. Then, return the top element of stack2.
For empty(), check if both stack1 and stack2 are empty.

Pseudo Code:
class MyQueue:
    stack1 = []
    stack2 = []
    function push(x):
        push x onto stack1
    function pop():
        if stack2 is empty:
            while stack1 is not empty:
                pop from stack1 and push onto stack2
        return pop from stack2
    function peek():
        if stack2 is empty:
            while stack1 is not empty:
                pop from stack1 and push onto stack2
        return top element of stack2
    function empty():
        return stack1 is empty and stack2 is empty
Time Complexity:
push(x): O(1)
pop(): O( n ) in the worst case when elements are transferred from stack1 to stack2.
peek(): O( n ) in the worst case.
empty(): O(1)
Space Complexity: O(1), since we use only a few extra variables.
[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/NRXpWgaF)
