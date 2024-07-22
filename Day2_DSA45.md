# CrackYourInternship

# Day 2: 21/07/2024

## 1. [Chocolate Distribution Problem](https://www.geeksforgeeks.org/problems/chocolate-distribution-problem3825/1)
```JAVA
class Solution
{
    public long findMinDiff (ArrayList<Integer> a, int n, int m)
    {
        // your code here
        Collections.sort(a);
        long res=Long.MAX_VALUE;
        for(int i=0;i<n-m+1;i++){
            int minElement=a.get(i);
            int maxElement=a.get(i+m-1);
            res=Math.min(res,maxElement-minElement);
        }
        return res;
    }
}
```
## 2. [1. Two Sum](https://leetcode.com/problems/two-sum/description/)
```
import java.util.Arrays;

public class TwoSum {
    public int[] twoSum(int[] nums, int target) {
        // Iterate through the array
        for (int i = 0; i < nums.length; i++) {
            int complement = target - nums[i];
            
            // Check if the complement exists in the array
            for (int j = i + 1; j < nums.length; j++) {
                if (nums[j] == complement) {
                    // Return the indices if the complement is found
                    return new int[] {i, j};
                }
            }
        }
        
        // If no solution is found, return an empty array
        return new int[0];
    }
}

```
## 3. [88. Merge Sorted Array](https://leetcode.com/problems/merge-sorted-array/description/)
```
class Solution {
    public void merge(int[] nums1, int m, int[] nums2, int n) {
        for (int j = 0, i = m; j < n; j++) {
            nums1[i] = nums2[j];
            i++;
        }
        Arrays.sort(nums1);
    }
}
```
## 4. [169. Majority Element](https://leetcode.com/problems/majority-element/description/)
```
class Solution {
    public int majorityElement(int[] nums) {
        Arrays.sort(nums);
        int n=nums.length;
        return nums[n/2];
    }
}
```
## 5. [20. Valid Parentheses](https://leetcode.com/problems/valid-parentheses/description/)
```
class Solution {
    public boolean isValid(String s) {
        if (s.length() == 0) {
            return false;
        }
        Stack<Character> st = new Stack<>();
        for (int i = 0; i < s.length(); i++) {
            char c = s.charAt(i);
            if (c == '(' || c == '{' || c == '[') {
                st.push(c);
            } else {
                if (st.isEmpty()) {
                    return false;
                }
                char ch = st.pop();
                if ((c == ')' && ch != '(') || (c == '}' && ch != '{') || (c == ']' && ch != '[')) {
                    return false;
                }
            }
        }
        return st.isEmpty();

    }
}
```
