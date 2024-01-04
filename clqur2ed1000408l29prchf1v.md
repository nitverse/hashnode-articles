---
title: "Maximizing Content Children: A Greedy Solution - LeetCode Daily Challenge [January 1, 2024]"
datePublished: Mon Jan 01 2024 10:00:33 GMT+0000 (Coordinated Universal Time)
cuid: clqur2ed1000408l29prchf1v
slug: maximizing-content-children-a-greedy-solution-leetcode-daily-challenge-january-1-2024
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1704103149715/04b63dff-9238-47f7-9573-b4ad8f0f3532.png
tags: daily-leetcode-challenge, leetcode-solution

---

Here is the Problem Link :

[https://leetcode.com/problems/assign-cookies/](https://leetcode.com/problems/assign-cookies/?envType=daily-question&envId=2024-01-01)

## **Introduction**

The "Assign Cookies" problem is a classic example of a greedy algorithm, where we aim to maximize a certain objective by making locally optimal choices. In this problem, our goal is to distribute cookies to children in a way that maximizes the number of content children.

## **Problem Description**

We are given an array of greed factors representing the minimum size of a cookie that each child will be content with, and an array of cookie sizes. Our task is to find the maximum number of content children by assigning cookies to them.

## **Greedy Algorithm**

The provided solution utilizes a greedy algorithm to efficiently solve the problem. Here's a breakdown of the algorithm:

1. **Sort Arrays**: First, we sort both the greed factors (`g`) and cookie sizes (`s`) in descending order. Sorting helps in making efficient comparisons.
    
2. **Initialize Counters and Pointers**: We initialize counters and pointers (`i` and `j`) to the end of the sorted arrays.
    
3. **Greedy Iteration**: We use a while loop to iterate through the arrays. At each step, we check if the greed factor of the current child is less than or equal to the size of the current cookie. If it is, we assign the cookie to the child and move to the next cookie and child. We increment the counter for content children (`c`) in this case.
    
4. **Continue Iteration**: Regardless of the comparison result, we always move to the next child. This ensures that we consider all possible assignments.
    
5. **Return Result**: Finally, the function returns the count of content children.
    

## **Optimized Code :**

```java
import java.util.Arrays;

public class Solution {
    public int findContentChildren(int[] g, int[] s) {
        // Sort the greed factors and cookie sizes in descending order
        Arrays.sort(g);
        Arrays.sort(s);
        
        // Initialize counters and pointers
        int i = g.length - 1, j = s.length - 1, contentChildren = 0;

        // Greedy algorithm: Assign cookies to children
        while (i >= 0 && j >= 0) {
            // If the current cookie can satisfy the greed factor of the current child
            if (g[i] <= s[j]) {
                // Assign the cookie to the child, and move to the next cookie and child
                j--;
                contentChildren++;
            }
            // Move to the next child (greed factor) regardless
            i--;
        }

        // Return the count of content children
        return contentChildren;
    }
}
```

## **Conclusion**

The provided solution efficiently solves the "Assign Cookies" problem by applying a greedy algorithm. Sorting the arrays and making locally optimal choices lead to an optimal overall solution. The code is well-commented for better understanding, and the greedy approach provides an elegant and efficient solution to the problem.