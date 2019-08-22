# 3. 无重复字符的最长子串

```
class Solution {
    public int lengthOfLongestSubstring(String s) {
        
        int len = s.length();
        int maxLen = 0;
        Map<Character, Integer> map = new HashMap<>();
        
        for(int i = 0, j = 0; j< len; j++){
            if(map.containsKey(s.charAt(j))){
                i = Math.max(map.get(s.charAt(j)), i);
            }
            maxLen = Math.max(j-i+1, maxLen);
            map.put(s.charAt(j), j+1);
        }
        return maxLen;
    }
}
```
