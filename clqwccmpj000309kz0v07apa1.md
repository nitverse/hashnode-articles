---
title: "LeetCode Daily (2nd Jan 2024) 
Convert an Array Into a 2D Array With Conditions"
datePublished: Tue Jan 02 2024 12:44:09 GMT+0000 (Coordinated Universal Time)
cuid: clqwccmpj000309kz0v07apa1
slug: leetcode-daily-2nd-jan-2024-convert-an-array-into-a-2d-array-with-conditions
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1704199387323/832d5f67-f3a4-47c8-8ed1-1f5d35b61f55.png
tags: array, arrays, leetcode, leetcodedaily, leetcode-solution

---

## **Problem Statement**

You are given an integer array `nums`. The goal is to create a 2D array from `nums` with the following conditions:

1. The 2D array should contain only the elements of the array `nums`.
    
2. Each row in the 2D array must contain distinct integers.
    
3. The number of rows in the 2D array should be minimal.
    

The task is to return the resulting 2D array, and if there are multiple valid answers, any of them is acceptable.

## **Approach**

To tackle this problem, we can use a frequency-based approach. We maintain a HashMap (`frequency`) to keep track of the frequency of each number in the array. We then iterate through the frequency map, constructing rows for the 2D array. We ensure that each row contains distinct integers, decrementing their frequencies accordingly.

Let's break down the steps of the provided Java solution:

```java
class Solution {
    public List<List<Integer>> findMatrix(int[] nums) {
        List<List<Integer>> matrix = new ArrayList<>();
        HashMap<Integer, Integer> frequency = new HashMap<>();

        // Populate the frequency map based on the input array
        for (int num : nums) {
            frequency.put(num, frequency.getOrDefault(num, 0) + 1);
        }

        // Iterate until all frequencies are processed
        while (!frequency.isEmpty()) {
            List<Integer> row = new ArrayList<>();

            // Iterate over a copy of the keys to avoid ConcurrentModificationException
            for (int num : new HashMap<>(frequency).keySet()) {
                // Add the integer to the current row
                row.add(num);

                // Decrement its frequency
                frequency.put(num, frequency.get(num) - 1);

                // Remove the number from the frequency map if its frequency becomes 0
                if (frequency.get(num) == 0) {
                    frequency.remove(num);
                }
            }

            // Add the current row to the matrix
            matrix.add(row);
        }

        // Return the resulting matrix
        return matrix;
    }
}
```

## **Example**

Let's take the provided example for illustration:

**Input:**

```java
 [1, 3, 4, 1, 2, 3, 1]
```

**Output:**

```java
[[1, 3, 4, 2], [1, 3], [1]]
```

## **Conclusion**

This problem challenges us to think creatively about efficiently constructing a 2D array with distinct integers while minimizing the number of rows. The provided solution demonstrates the use of a frequency map and an iterative process to achieve the desired result.

By understanding the problem, breaking it down into smaller steps, and implementing an effective solution, we can enhance our problem-solving skills and gain valuable insights into algorithmic thinking.

I hope this blog post has provided clarity on the problem and the solution approach. Happy coding!