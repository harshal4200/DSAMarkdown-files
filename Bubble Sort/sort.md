# Bubble Sort Algorithm #
> First do it your self👍

**Problem Statement:** Given an array of N integers, write a program to implement the Bubble Sorting algorithm.

## Examples: ##

**Example 1:**
**Input:** `N = 6`, `array[] = {13,46,24,52,20,9}`
**Output:** `9,13,20,24,46,52`
**Explanation:** After sorting we get `9,13,20,24,46,52`


**Input:** `N = 5`, `array[] = {5,4,3,2,1}`
**Output:** `1,2,3,4,5`
**Explanation:** After sorting we get `1,2,3,4,5`

## Solution ##
>**Disclaimer:** Don't jump directly to the solution, try it out yourself first.

## Practice: ##

**Approach:**

The algorithm steps are as follows:

- First, we will select the range of the unsorted array. For that, we will run a loop(say i) that will signify the last index of the selected range. The loop will run backward from index n-1 to 0(where n = size of the array). The value i = n-1 means the range is from 0 to n-1, and similarly, i = n-2 means the range is from 0 to n-2, and so on.
Within the loop, we will run another loop(say j, runs from 0 to i-1 though the range is from 0 to i) to push the maximum element to the last index of the selected range, by repeatedly swapping adjacent elements.
Basically, we will swap adjacent elements(if arr[j] > arr[j+1]) until the maximum element of the range reaches the end.
Thus, after each iteration, the last part of the array will become sorted. Like: after the first iteration, the array up to the last index will be sorted, and after the second iteration, the array up to the second last index will be sorted, and so on.
After (n-1) iteration, the whole array will be sorted.
- Within the loop, we will run another loop(say j, runs from 0 to i-1 though the range is from 0 to i) to push the maximum element to the last index of the selected range, by repeatedly swapping adjacent elements.
Basically, we will swap adjacent elements(if arr[j] > arr[j+1]) until the maximum element of the range reaches the end.
- Thus, after each iteration, the last part of the array will become sorted. Like: after the first iteration, the array up to the last index will be sorted, and after the second iteration, the array up to the second last index will be sorted, and so on.
- After (n-1) iteration, the whole array will be sorted.

**Note:** Here, after each iteration, the array becomes sorted up to the last index of the range. That is why the last index of the range decreases by 1 after each iteration. This decrement is achieved by the outer loop and the last index is represented by variable i in the following code. And the inner loop(i.e. j) helps to push the maximum element of range [0….i] to the last index(i.e. index i).

**Dry Run:**

**Iteration 1:**

- *Click on image*: ![image](https://lh6.googleusercontent.com/oM3nMhm5vEofXCV_aV1JH1PIQEhmYLgTUGqWNtb0KRGAe_YN0D8XHtNIA9SBYCDzjrMzUXjgwroBDvRPeEpeSwfOYcvxmNCgxPO8D91O4tyAX8zE6mTPpZxH31NR-xr-SsDCUtek)

**Iteration 2:**

- *Click on image*: ![image](https://lh4.googleusercontent.com/LHJEryke4hIsjf2u3Mefyo7_MU7HxX3qcCgxYiTyGVaL8c1n1jU9lIOlTazZxNbNa4bUIIM_NAAFYt5iWFqDL1Y1JEOEgymIlvH7b4yMt7BSUcWrsya1hsCPS1dFDmyHw6rG2_SH)

**Iteration 3:**

- *Click on image*: ![image](https://lh3.googleusercontent.com/VmYabkBnLRYPfarWlQ7pTFHbI5ODTqZ2TdMTx6H2sgHgyEwI7EC9YKvf36qGbKPkQ2qm4hVUHYlnw8T4YLyNFgqtqAozZuOaCWkV5Ye5WN-tS_fVgZ2j6EzbewtHuKhmKZ8jUKt6)

**Iteration 4:**

- *Click on image*: ![image](https://lh3.googleusercontent.com/Juw-bqmSz6H85bDRedC7l5SppP0DOsTDpyOj7t5xYJGj_WLDWMe3NneyEzNg5HPIZBsj3Ve2f7lb4KpdjM4cKfaGuwKE3-jLMtJY5a75oOaZsJq39cLjPCoquvjqyar24QIhj6T9)

**Iteration 5:**

- *Click on image*: ![image](https://lh3.googleusercontent.com/i72GuG_M25X940lzQHlFx3zSMR8R-jWoYvsIOc-hGCvd9bW8Ch4q2JW3edrQ3t1BN-wkLPXlRsjBuHurWmMPPge9vUSp58yPT4b32POGQ6B3qVv1l6WWanPQu2222QGbtcm-Cvxr)

**Code:**

```java
import java.util.*;

public class tUf {
    static void bubble_sort(int[] arr, int n) {
        for (int i = n - 1; i >= 0; i--) {
            for (int j = 0; j <= i - 1; j++) {
                if (arr[j] > arr[j + 1]) {
                    int temp = arr[j];
                    arr[j] = arr[j + 1];
                    arr[j + 1] = temp;
                }
            }
        }

        System.out.println("After bubble sort: ");
        for (int i = 0; i < n; i++) {
            System.out.print(arr[i] + " ");
        }
        System.out.println();
    }
    public static void main(String args[]) {
        int arr[] = {13, 46, 24, 52, 20, 9};
        int n = arr.length;
        System.out.println("Before Using Bubble Sort: ");
        for (int i = 0; i < n; i++) {
            System.out.print(arr[i] + " ");
        }
        System.out.println();
        bubble_sort(arr, n);
    }

}

```
**Output:**

Before Using Bubble Sort:
13 46 24 52 20 9
After Using bubble sort:
9 13 20 24 46 52

**Time complexity:** `O(N2)`, (where N = size of the array), for the worst, and average cases.
Reason: If we carefully observe, we can notice that the outer loop, say i, is running from n-1 to 0 i.e. n times, and for each i, the inner loop j runs from 0 to i-1. For, i = n-1, the inner loop runs n-1 times, for i = n-2, the inner loop runs n-2 times, and so on. So, the total steps will be approximately the following: `(n-1) + (n-2) + (n-3) + ……..+ 3 + 2 + 1`. The summation is approximately the sum of the first n natural numbers i.e. `(n*(n+1))/2`. The precise time complexity will be `O(n2/2 + n/2)`. Previously, we have learned that we can ignore the lower values as well as the constant coefficients. So, the time complexity is `O(n2)`. Here the value of n is N i.e. the size of the array.

**Space Complexity: `O(1)`**














