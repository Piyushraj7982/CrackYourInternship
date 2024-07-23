# CrackYourInternship

# Day 4 : 23/07/2024

## 1. [628. Maximum Product of Three Numbers](https://leetcode.com/problems/maximum-product-of-three-numbers/description/)
```JAVA
class Solution {
    public int maximumProduct(int[] nums) {
        Arrays.sort(nums);
        int max1 = nums[nums.length - 1] * nums[nums.length - 2] * nums[nums.length - 3];
        int max2 = nums[0] * nums[1] * nums[nums.length - 1];
        return Math.max(max1, max2);
    }
}

```
## 2. [168. Excel Sheet Column Title](https://leetcode.com/problems/excel-sheet-column-title/description/)
```
class Solution {
    public String convertToTitle(int columnNumber) {
        StringBuilder result = new StringBuilder();
        
        while (columnNumber > 0) {
            columnNumber--; // Adjust to 0-based indexing
            int remainder = columnNumber % 26;
            char currentChar = (char) (remainder + 'A');
            result.insert(0, currentChar); // Prepend the character
            columnNumber /= 26;
        }
        
        return result.toString();
    }
}

```
## 3. [Product array puzzle](https://www.geeksforgeeks.org/problems/product-array-puzzle4525/1)
```
class Solution 
{ 
	public static long[] productExceptSelf(int nums[], int n) 
	{ 
        // code here
        if (n == 1) {
            return new long[]{1};  
        }
        
        long[] leftProducts = new long[n];
        long[] rightProducts = new long[n];
        long[] result = new long[n];
        
        leftProducts[0] = 1;
        for (int i = 1; i < n; i++) {
            leftProducts[i] = leftProducts[i - 1] * nums[i - 1];
        }
        
        rightProducts[n - 1] = 1;
        for (int i = n - 2; i >= 0; i--) {
            rightProducts[i] = rightProducts[i + 1] * nums[i + 1];
        }
        
        for (int i = 0; i < n; i++) {
            result[i] = leftProducts[i] * rightProducts[i];
        }
        
        return result;
	} 
} 

```
## 4. [Permute two arrays such that sum of every pair is greater or equal to K](https://www.geeksforgeeks.org/permute-two-arrays-sum-every-pair-greater-equal-k/)
```
import java.util.*;

class PermuteArrays 
{

static boolean isPossible(Integer a[], int b[],
                                  int n, int k) 
{
Arrays.sort(a, Collections.reverseOrder());

    Arrays.sort(b);

    for (int i = 0; i < n; i++)
    if (a[i] + b[i] < k)
        return false;

    return true;
}

// Driver code
public static void main(String[] args) {
    Integer a[] = {2, 1, 3};
    int b[] = {7, 8, 9};
    int k = 10;
    int n = a.length;

    if (isPossible(a, b, n, k))
    System.out.print("Yes");
    else
    System.out.print("No");
}
}

# Output
"Yes"
```
## 5. [Ceiling in a sorted array](https://www.geeksforgeeks.org/ceiling-in-a-sorted-array/)
```
class Main
{
	static int ceilSearch(int arr[], int low, int high, int x)
	{
	int i; 
	if(x <= arr[low])
		return low; 
	for(i = low; i < high; i++)
	{
		if(arr[i] == x)
		return i;

		if(arr[i] < x && arr[i+1] >= x)
		return i+1;
	}		 
	return -1;
	}

	public static void main (String[] args)
	{
	int arr[] = {1, 2, 8, 10, 10, 12, 19};
	int n = arr.length;
	int x = 3;
	int index = ceilSearch(arr, 0, n-1, x);
	if(index == -1)
		System.out.println("Ceiling of "+x+" doesn't exist in array");
	else
		System.out.println("ceiling of "+x+" is "+arr[index]);
	} 
}

#Output
ceiling of 3 is 8
```
