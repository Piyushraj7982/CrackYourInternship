# CrackYourInternship

# Day 5 : 24/07/2024

## 1. [Find Pair Given Difference](https://www.geeksforgeeks.org/problems/find-pair-given-difference1559/1)
```JAVA
class Solution {
    public int findPair(int n, int x, int[] arr) {
        // code here
        Arrays.sort(arr);

        int i = 0;
        int j = 1;

        while (i < n && j < n) {
            // Calculate the difference
            int diff = arr[j] - arr[i];

            // Check if the difference is equal to x
            if (diff == x && i != j) {
                return 1;
            } else if (diff < x) {
                j++;
            } else {
                i++;
            }
        }
        return -1;
    }
}

```
## 2. [Permutations in array](https://www.geeksforgeeks.org/problems/permutations-in-array1747/1)
```JAVA
class Solution {
    public boolean isPossible(long a[], long b[], int n, long k) {
        // Your code goes here
        Arrays.sort(a);
        
        // Sort array b in descending order
        Arrays.sort(b);
        for (int i = 0; i < n / 2; i++) {
            long temp = b[i];
            b[i] = b[n - i - 1];
            b[n - i - 1] = temp;
        }

        // Check if the sum of corresponding elements is greater than or equal to k
        for (int i = 0; i < n; i++) {
            if (a[i] + b[i] < k) {
                return false;
            }
        }

        return true;
    }
}
```
## 3. [876. Middle of the Linked List](https://leetcode.com/problems/middle-of-the-linked-list/description/)
```JAVA

class Solution {
    public ListNode middleNode(ListNode head) {
        ListNode fast = head;
        ListNode slow = head;
        while(fast!=null && fast.next!=null){
            fast=fast.next.next;
            slow=slow.next;
        }
        return slow;
    }
}
```
## 4. [141. Linked List Cycle](https://leetcode.com/problems/linked-list-cycle/description/)
```JAVA

public class Solution {
    public boolean hasCycle(ListNode head) {
         ListNode fast = head;
        ListNode slow = head;

        while (fast != null && fast.next != null) {
            fast = fast.next.next;
            slow = slow.next;

            if (fast == slow) {
                return true;
            }
        }

        return false;
    }
}
```
## 5. [287. Find the Duplicate Number](https://leetcode.com/problems/find-the-duplicate-number/description/)
```JAVA
class Solution {
    public int findDuplicate(int[] nums) {
        Arrays.sort(nums);
        for(int i=0;i<nums.length;i++){
            if(nums[i]==nums[i+1]){
                return nums[i];
            }
        }
        return -1;
    }
}
```
