class Solution:
    def fourSum(self, nums: List[int], target: int) -> List[List[int]]:
        nums = sorted(nums)
        fourSums = []
        for i in range(len(nums) - 3):
            if i == 0 or (i > 0 and nums[i] != nums[i - 1]):
                for j in range(i + 1, len(nums) - 2):
                    if j == i + 1 or (j > i + 1 and nums[j] != nums[j - 1]):
                        low = j + 1
                        high = len(nums) - 1
                        sums = target - (nums[i] + nums[j])

                        while low < high:
                            if nums[low] + nums[high] == sums:
                                fourSums.append([nums[i], nums[j], nums[low], nums[high]])

                                while low < high and nums[low] == nums[low + 1]:
                                    low += 1

                                while low < high and nums[high] == nums[high - 1]:
                                    high -= 1

                                low += 1
                                high -= 1
                            elif nums[low] + nums[high] > sums:
                                high -= 1
                            else:
                                low += 1
        return fourSums
