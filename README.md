# Minimum-Increment-to-Make-Array-Unique

You are given an integer array nums. In one move, you can pick an index i where 0 <= i < nums.length and increment nums[i] by 1.
Return the minimum number of moves to make every value in nums unique.
The test cases are generated so that the answer fits in a 32-bit integer.

class Solution:
    def minIncrementForUnique(self, nums: List[int]) -> int:
        if not nums:
            return 0
        
        nums.sort()
        moves = 0
        prev = nums[0]
        
        for i in range(1, len(nums)):
            if nums[i] <= prev:
                prev += 1
                moves += prev - nums[i]
            else:
                prev = nums[i]
        
        return moves

        
