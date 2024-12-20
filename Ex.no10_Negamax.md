# Ex.No: 10 Implementation of Negamax algorithm 

## DATE: 18.10.2024
## REGISTER NUMBER : 212223240118
## AIM:

Write a negamax algorithm to find the optimal value of Player from the graph.

## Steps:

Start the program

Define the minimax function

If maximum depth is reached then return the score value of leaf node. [depth taken as 3]

In Max player turn, assign the  maximum value by calling the negamax function recursively.

In Min player turn, finding the maximum value by taking the negation of its children.

Specify the score value of leaf nodes and Call the negamax function.

Print the best value of Max player.

Stop the program.

## Program:

```
import math

def negamax(curDepth, nodeIndex, scores, targetDepth):
    # Base case: target depth reached
    if curDepth == targetDepth:
        return scores[nodeIndex]

    # Negamax assumes max turn is represented by positive values
    value1 = negamax(curDepth + 1, nodeIndex * 2, scores, targetDepth)
    value2 = negamax(curDepth + 1, nodeIndex * 2 + 1, scores, targetDepth)

    return max(-value1, -value2)  # Flip the sign for the other player's turn

# Driver code
scores = [3, 5, 2, 9, 12, 5, 23, 20]
treeDepth = math.log(len(scores), 2)  # Calculate depth of node, log(8, base 2) = 3
print("The optimal value is: ", end="")
print(negamax(0, 0, scores, int(treeDepth)))
```

## Output:

![image](https://github.com/user-attachments/assets/97f10fde-2107-4ad2-9a4d-ab134981c069)


## Result:


Thus the best score of max player was found using negamax algorithm
