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

## 2.[283. Move Zeroes] (https://leetcode.com/problems/move-zeroes/description/)

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
