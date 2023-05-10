class Solution:
    def trap(self, height: List[int]) -> int:
        sum = 0
        n = len(height)
        back = [0] * n
        back[n - 1] = height[n - 1]
        for i in reversed(range(n-1)):
            back[i] = max(back[i+1],height[i])
        leftmax = height[0]
        for i in range(1, n-1):
            leftmax = max(leftmax, height[i])
            diff = min(leftmax, back[i]) - height[i]
            sum += diff
        return sum
