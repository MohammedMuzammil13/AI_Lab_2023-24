# Ex.No: 3  Implementation of Minimax Search
## DATE:  
14/08/2024
## REGISTER NUMBER : 
212222040103
## AIM: 
Write a mini-max search algorithm to find the optimal value of MAX Player from the given graph.
## Algorithm:
Step 1: Start the program
Step 2: import the math package
Step 3: Specify the score value of leaf nodes and find the depth of binary tree from leaf nodes.
Step 4: Define the minimax function
Step 5: If maximum depth is reached then get the score value of leaf node.
Step 6: Max player find the maximum value by calling the minmax function recursively.
Step 7: Min player find the minimum value by calling the minmax function recursively.
Step 8: Call the minimax function  and print the optimum value of Max player.
Step 9 Stop the program. 
## Program:
```

import math
def minimax (curDepth, nodeIndex,
             maxTurn, scores,
             targetDepth):
    # base case : targetDepth reached
    if (curDepth == targetDepth):
        return scores[nodeIndex]
    if (maxTurn):
        return max(minimax(curDepth + 1, nodeIndex * 2,
                    False, scores, targetDepth),
                   minimax(curDepth + 1, nodeIndex * 2 + 1,
                    False, scores, targetDepth))
     
    else:
        return min(minimax(curDepth + 1, nodeIndex * 2,
                     True, scores, targetDepth),
                   minimax(curDepth + 1, nodeIndex * 2 + 1,
                     True, scores, targetDepth))
     
# Driver code
scores = [3, 5, 2, 9, 12, 5, 23, 20]
treeDepth = math.log(len(scores), 2) # calculate depth of node  log 8 (base 2) = 3)
print("The optimal value is : ", end = "")
print(minimax(0, 0, True, scores, treeDepth))

```
## Output:

![](MinMax.png)

## Result:
Thus the optimum value of max player was found using minimax search.
