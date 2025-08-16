# Leetcode-55.-Jump-Game
# Description
You are given an integer array nums. You are initially positioned at the array's first index, and each element in the array represents your maximum jump length at that position.

Return true if you can reach the last index, or false otherwise.
# Solution
You are given an integer array nums. You start at the first index, and each element in the array represents the maximum jump length you can take from that position.Return True if you can reach the last index, otherwise return False.

At index i, nums[i] tells us the maximum steps we can move forward.

For example, if nums[i] = 3, we can jump either 1, 2, or 3 steps from i.

Solution (Greedy - Backward Approach):

Start from the last index and treat it as the "goal".

Move backward through the array. 

If from index i we can reach the current goal (i + nums[i] >= goal),then update goal = i.

In the end, if goal becomes 0, it means we can reach the last index.

# Algorithm
1. Initialize goal = last index (i.e., len(nums) - 1).
2. Traverse the array backward from the second-last index to the first index.
3. If i + nums[i] >= goal, update goal = i (means we can reach the current goal from i).
4. After the loop, if goal == 0, return True (we can reach the last index).Otherwise, return False.
# Code
class Solution:

    def canJump(self, nums: List[int]) -> bool:
        goal=len(nums)-1
        for i in range(len(nums)-1,-1,-1):
        
            if i+nums[i]>=goal:
                goal=i
        if goal==0:
            return True
        else:
            return False
# Complexity
Time Complexity:

We traverse the array once from right to left → O(n)

Space Complexity:

Only using a few variables (goal, i) → O(1)
