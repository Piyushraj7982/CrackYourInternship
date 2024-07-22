# CrackYourInternship

# Day 3 : 22/07/2024

## 1. [Print all the duplicate characters in a string](https://www.geeksforgeeks.org/print-all-the-duplicates-in-the-input-string/)
```JAVA
// Java code to implement the above approach
import java.util.*;

public class Main {

    public static void printDuplicates(String str)
    {
        int len = str.length();

        char[] chars = str.toCharArray();
        Arrays.sort(chars);
        String sortedStr = new String(chars);

        // Loop through the sorted string to find duplicates
        for (int i = 0; i < len; i++) {
            int count = 1;

            // Counting the occurrences of each character
            while (i < len - 1
                   && sortedStr.charAt(i)
                          == sortedStr.charAt(i + 1)) {
                count++;
                i++;
            }

            // Printing the duplicate character and its count

            if (count > 1) {
                System.out.println(sortedStr.charAt(i) + ", count = " + count);
            }
        }
    }

    public static void main(String[] args)
    {
        String str = "test string";
        printDuplicates(str);
    }
}

## Output
s, count = 2
t, count = 3

```

## 2. [28. Find the Index of the First Occurrence in a String](https://leetcode.com/problems/find-the-index-of-the-first-occurrence-in-a-string/description/)
```
class Solution {
    public int strStr(String haystack, String needle) {
         if (haystack.length() < needle.length()) {
            return -1;
        }
        
        for (int i = 0; i <= haystack.length() - needle.length(); i++) {
            if (haystack.substring(i, i + needle.length()).equals(needle)) {
                return i;
            }
        }
        
        return -1;
        
    }
}
```

## 3. [14. Longest Common Prefix](https://leetcode.com/problems/longest-common-prefix/description/)
```
class Solution {
    public String longestCommonPrefix(String[] strs) {
        StringBuilder ans = new StringBuilder();
        Arrays.sort(strs); //sort the array
        String first = strs[0]; //get the frist string
        String last = strs[strs.length-1]; //get the last string
        // start comparing
        for (int i=0; i<Math.min(first.length(), last.length()); i++) {
            if (first.charAt(i) != last.charAt(i)) {
                return ans.toString();
            }
            ans.append(first.charAt(i));
        }
        return ans.toString();
    }
}
```

## 4. [680. Valid Palindrome II](https://leetcode.com/problems/valid-palindrome-ii/description/)
```
class Solution {
    public boolean validPalindrome(String s) {
       int i = 0;
        int j = s.length() - 1;
        
        while(i <= j){
            if(s.charAt(i) == s.charAt(j)){
                i++;
                j--;
            }
            else return isPalindrome(s, i + 1, j) || isPalindrome(s, i, j - 1);
        }
        return true;
    }
    public boolean isPalindrome(String s, int i, int j){
        while(i <= j){
            if(s.charAt(i) == s.charAt(j)){
                i++;
                j--;
            }
            else return false;
        }
        return true;
    }
}
```

## 5. [67. Add Binary](https://leetcode.com/problems/add-binary/description/)
```
class Solution {
    public String addBinary(String a, String b) {
        StringBuilder sb = new StringBuilder();
    int carry = 0;
    int i = a.length() - 1;
    int j = b.length() - 1;

    while (i >= 0 || j >= 0 || carry == 1) 
    {
      if(i >= 0)
        carry += a.charAt(i--) - '0';
      if(j >= 0)
        carry += b.charAt(j--) - '0';
      sb.append(carry % 2);
      carry /= 2;
    }
    return sb.reverse().toString();
    }
}
```
