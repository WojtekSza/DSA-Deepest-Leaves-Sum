# DSA-Deepest-Leaves-Sum
Given the root of a binary tree, return the sum of values of its deepest leaves.
```
Input: root = [1,2,3,4,5,null,6,7,null,null,null,null,8]
Output: 15
```
```
from collections import deque
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def deepestLeavesSum(self, root: Optional[TreeNode]) -> int:
        if not root:
            return 0
        queue=deque([root])
        while queue:
            current_lenght=len(queue)
            lvl_sum=0
            for _ in range(current_lenght):
                node=queue.popleft()
                lvl_sum+=node.val
                if node.left:
                    queue.append(node.left)
                if node.right:
                    queue.append(node.right)
        return lvl_sum
        
```
