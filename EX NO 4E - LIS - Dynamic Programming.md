
# EX 4E Longest Increasing Subsequence - Dynamic Programming.
## DATE: 11.05.26
## AIM:
To write a Java program to for given constraints.
Given an integer array nums, return the length of the longest strictly increasing subsequence.
Example 1:
Input: nums = [10,9,2,5,3,7,101,18]
Output: 4
Explanation: The longest increasing subsequence is [2,3,7,101], therefore the length is 4.
# Algorithm

### 1. Input:

- Read the integer `n` (size of array).
- Read `n` integers into the array `nums`.

### 2. Initialization:

- Create an array `dp[n]`, where `dp[i]` stores the **length of the longest increasing subsequence (LIS)** ending at index `i`.

- Initialize all values of `dp` to `1`, since each element is an LIS of length `1` by itself.

- Initialize `maxLen = 1` to keep track of the overall maximum LIS length.

### 3. Dynamic Programming Logic:

- For each element `nums[i]` (from index `1` to `n-1`):

  - Compare it with all previous elements `nums[j]` (where `j < i`).

  - If `nums[i] > nums[j]`, it means we can extend the subsequence ending at `j`.
  
    - Update `dp[i] = max(dp[i], dp[j] + 1)`

- After each iteration, update `maxLen = max(maxLen, dp[i])`.

### 4. Output:

- Print `maxLen`, which represents the **length of the longest increasing subsequence**.

## Program:
```
/*
Program to implement Reverse a String
Developed by: SARISH VARSHAN V
Register Number:  212223230196
*/

import java.util.*;

public class LongestIncreasingSubsequence {

    public static int lengthOfLIS(int[] nums) {
        // Type Your Code here...!
        int[] dp = new int[nums.length];
        Arrays.fill(dp,1);
        for (int i = 1; i < nums.length; i++){
            for (int j = 0; j < i ; j++){
                if (nums[i] > nums[j]){
                    dp[i] = Math.max(dp[i], dp[j]+1);
                }
            }
        }
        int longest = 0;
        for (int c : dp){
            longest = Math.max(longest, c);
        }
        return longest;
    }

public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Prompt user input
        int n = scanner.nextInt();
        int[] nums = new int[n];

        for (int i = 0; i < n; i++) {
            nums[i] = scanner.nextInt();
        }

        // Calculate and display the length of LIS
        int result = lengthOfLIS(nums);
        System.out.println("Length of Longest Increasing Subsequence: " + result);

        scanner.close();
    }
}
```

## Output:

<img width="1176" height="251" alt="image" src="https://github.com/user-attachments/assets/94fcce83-af6f-49f3-846a-e26a77e73d27" />


## Result:
The program successfully implemented and the expected output is verified.
