---
title: "Solving the Minimum Number of Operations to Make Array Empty Problem"
datePublished: Thu Jan 04 2024 16:03:17 GMT+0000 (Coordinated Universal Time)
cuid: clqzecfb6000109l81hbt15ju
slug: solving-the-minimum-number-of-operations-to-make-array-empty-problem
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1704384168993/a3bb3361-d24b-485e-bb45-e17fae07163a.png
tags: leetcode, leetcodedaily, leetcode-solution

---

Here is the problem link :

[problem](https://leetcode.com/problems/minimum-number-of-operations-to-make-array-empty/description/?envType=daily-question&envId=2024-01-04)

**Introduction:** The "Minimum Number of Operations to Make Array Empty" problem presents an interesting challenge where we are tasked with efficiently manipulating an array by applying two types of operations repeatedly. In this blog post, we will explore the problem statement, understand the required operations, and provide a detailed solution in Java.

**Problem Statement:** Given a 0-indexed array `nums` consisting of positive integers, we are allowed to perform two types of operations:

1. Choose two elements with equal values and delete them from the array.
    
2. Choose three elements with equal values and delete them from the array.
    

The goal is to find the minimum number of operations required to make the array empty. If it is not possible to empty the array, the function should return -1.

**Approach:** To solve this problem, we need to identify and process groups of equal elements in the array. We sort the array in ascending order to easily locate and count these groups. The algorithm then iterates through the sorted array, calculating the minimum number of operations required for each group.

**Implementation:** The key to the solution lies in efficiently processing each group of equal elements. The provided Java code achieves this through sorting the array and using a while loop to iterate through the sorted elements. Here is the code snippet:

```java
private static int minimumOperations2(int[] nums) {
    Arrays.sort(nums);
    int ans = 0;
    int i = 0;

    while (i < nums.length) {
        int j = i;
        while (j < nums.length && nums[j] == nums[i]) {
            j++;
        }

        int count = j - i;

        if (count == 1) {
            return -1;
        }

        ans += count / 3;

        if (count % 3 != 0) {
            ans++;
        }

        i = j;
    }

    return ans;
}
```

**  
Title: Solving the Minimum Number of Operations to Make Array Empty Problem**

**Introduction:** The "Minimum Number of Operations to Make Array Empty" problem presents an interesting challenge where we are tasked with efficiently manipulating an array by applying two types of operations repeatedly. In this blog post, we will explore the problem statement, understand the required operations, and provide a detailed solution in Java.

**Problem Statement:** Given a 0-indexed array `nums` consisting of positive integers, we are allowed to perform two types of operations:

1. Choose two elements with equal values and delete them from the array.
    
2. Choose three elements with equal values and delete them from the array.
    

The goal is to find the minimum number of operations required to make the array empty. If it is not possible to empty the array, the function should return -1.

**Approach:** To solve this problem, we need to identify and process groups of equal elements in the array. We sort the array in ascending order to easily locate and count these groups. The algorithm then iterates through the sorted array, calculating the minimum number of operations required for each group.

**Implementation:** The key to the solution lies in efficiently processing each group of equal elements. The provided Java code achieves this through sorting the array and using a while loop to iterate through the sorted elements. Here is the code snippet:

```java
javaCopy codeprivate static int minimumOperations2(int[] nums) {
    Arrays.sort(nums);
    int ans = 0;
    int i = 0;

    while (i < nums.length) {
        int j = i;
        while (j < nums.length && nums[j] == nums[i]) {
            j++;
        }

        int count = j - i;

        if (count == 1) {
            return -1;
        }

        ans += count / 3;

        if (count % 3 != 0) {
            ans++;
        }

        i = j;
    }

    return ans;
}
```

**Explanation:**

1. The array is sorted to group equal elements together.
    
2. The algorithm iterates through the array, identifying the boundaries of each group.
    
3. For each group, it calculates the count of elements and performs the necessary operations.
    
4. The final result is the minimum number of operations required to make the array empty.
    

**Conclusion:** Solving the "Minimum Number of Operations to Make Array Empty" problem involves an effective approach to identify and process groups of equal elements. The provided Java code illustrates this approach, demonstrating how to efficiently find the minimum operations needed to empty the array. Understanding and implementing such algorithms not only sharpens programming skills but also enhances problem-solving capabilities.