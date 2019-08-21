# 1. 两数之和
- 方法1：暴力破解

---
- 方法二：哈希


```
class Solution {
    public int[] twoSum(int[] nums, int target) {
        Map<Integer, Integer> map = new HashMap<>();
        
        int len = nums.length;
        
        for(int i = 0; i < len; i++){
            
            if(map.containsKey(target - nums[i]) && map.get(target - nums[i])!=i){
                return new int[]{i, map.get(target - nums[i])};
            }
            map.put(nums[i], i);
        }
        
        return null;
    }
}
```
