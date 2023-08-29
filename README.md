## GFG Problem Of The Day

### Today - 29 August 2023
### Que - Delete nodes having greater value on right

The problem can be found at the following link: [Question Link](https://practice.geeksforgeeks.org/problems/delete-nodes-having-greater-value-on-right/1)

### My Approach

I applied a recursive backtracking approach to solve the problem, following these steps:
- Initiate the traversal of all nodes through recursion, and subsequently retrace the path, starting from the last node and moving in a right-to-left direction.
- Keep track of the maximum node encountered so far.
- If the current node's data is less than the maximum, delete the current node.
- Otherwise, update the maximum node.
- Continue this process for all nodes.

### Explanation with example

Consider the following example:
```js
Input: 12 -> 15 -> 10 -> 11 -> 5 -> 6 -> 2 -> 3

Starting from the right, 
- We first encounter 3, which is greater than any number to its right, so it's kept.
- Then, we encounter 2, which is less than 3, so it's deleted. 
- The process continues in this manner.

Output: 15 -> 11 -> 6 -> 3
```

### Time and Auxiliary Space Complexity

- **Time Complexity**: `O(N)`, where `N` is the number of nodes in the linked list. We visit each node once.
- **Auxiliary Space Complexity**: `O(N)` due to the recursive function call stack.

### Code (C++)
```cpp
class Solution
{
    public:
    Node *solve(Node *curr){
        if(!curr)
            return curr;
        
        Node* last = solve(curr->next);
        
        if(last){
            if(last -> data <= curr -> data)
                curr->next = last;
            else
                return last;
        }else
            curr->next = last;
        
        return curr;
    }
    
    Node *compute(Node *head)
    {
        return solve(head);
    }
};
```
### Contribution and Support

I always encourage contributors to participate in the discussion forum for this repository.

If you have a better solution or any queries / discussions related to the `Problem of the Day` solution, please visit our [discussion section](https://github.com/getlost01/gfg-potd/discussions). We welcome your input and aim to foster a collaborative learning environment.

If you find this solution helpful, consider supporting us by giving a `⭐ star` to the [getlost01/gfg-potd](https://github.com/getlost01/gfg-potd) repository.


![Total number of repository visitors](https://komarev.com/ghpvc/?username=gl01potdgfg&color=blue&&label=Visitors)
