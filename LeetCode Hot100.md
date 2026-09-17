---
date: 2026-09-15
tags:
  - LeetCode
  - 算法
---

# 1. 两数之和
**hash map**
1. **python**: 
2. **Java**: new int[]{i, j}
# 49. 字母异位词分组
**访问列表**
1. **python**:

# 128. 最长连续序列
1. **python**: set(list) 创建一组元素为list的字典
   while something in dict:
# 283.移动零
1. **python**: del nums[i] 删除某一下标元素但会导致数组下标移动, 可以倒着删
# 11.盛最多水的容器
**双指针**
1. **python**: 
# 15.三数之和
**双指针**
1. **python**: 
``` 暴力解法
def threeSum(self, nums: list[int]) -> list[list[int]]:
	result = []
	n = len(nums)
	
	for i in range(0, n - 2):
		for j in range(i + 1, n - 1):
			for k in range(j + 1, n):
				num = sorted([nums[i], nums[j], nums[k]])
				
				if num not in result:
					result.append(num)
	return result
```
# 42.接雨水
**双向遍历**
**单调栈**
**双指针**