# CrackYourInternship

# DAY 1: 20/07/2024

## 1. [26. Remove Duplicates from Sorted Array](https://leetcode.com/problems/remove-duplicates-from-sorted-array/description/)

```JAVA

class Solution {
    public int removeDuplicates(int[] nums) {

        int i=0;
        for(int n: nums){

            if(i<1 ||n>nums[i-1]){
                nums[i]=n;
                i++;
            }
        }
        return i;
    }
}


        //or

class Solution {
    public int removeDuplicates(int[] nums) {
    int count=0;
    for(int i=0;i<nums.length;i++){
        if(i<nums.length-1 && nums[i]==nums[i+1]){
            continue;
        }else{
            nums[count]=nums[i];
            count++;
        }
    }
    return count;
  }
}
```
## 2.[283. Move Zeroes](https://leetcode.com/problems/move-zeroes/description/)

```
class Solution {
    public void moveZeroes(int[] nums) {
        int count=0;
        for(int i=0;i<nums.length;i++){
            if(nums[i]!=0){
                nums[count++]=nums[i];
            }
        }
        while(count<nums.length){
            nums[count++]=0;
        }
    }
}
```
## 3.[121. Best Time to Buy and Sell Stock](https://leetcode.com/problems/best-time-to-buy-and-sell-stock/description/)

```
class Solution {
    public int maxProfit(int[] prices) {
        int buyPrice = prices[0];
        int profit = 0;

        for (int i = 1; i < prices.length; i++) {
            if (buyPrice > prices[i]) {
                buyPrice = prices[i];
            }

            profit = Math.max(profit, prices[i] - buyPrice);
        }

        return profit;
    }
}
```
