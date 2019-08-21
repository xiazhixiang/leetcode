# 2. 两数相加

```
/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode(int x) { val = x; }
 * }
 */
class Solution {
    public ListNode addTwoNumbers(ListNode l1, ListNode l2) {
        ListNode l3 = new ListNode(0);
        ListNode l4 = l3;
        int cnt = 0;
        
        while(l1 != null || l2 != null){
            int p1 = l1 != null ? l1.val : 0;
            int p2 = l2 != null ? l2.val : 0;
            int sum = p1 + p2 + cnt;
            cnt = sum / 10;
            l3.next = new ListNode(sum % 10);
            l3 = l3.next;
            if(l1 != null)
                l1 = l1.next;
            if(l2 != null)
                l2 = l2.next;
        }
        
        if(cnt == 1){
            l3.next = new ListNode(1);
        }
        return l4.next;
    }
}
```
