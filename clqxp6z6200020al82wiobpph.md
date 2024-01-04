---
title: "LeetCode Problem: Number of Laser Beams in a Bank"
datePublished: Wed Jan 03 2024 11:31:26 GMT+0000 (Coordinated Universal Time)
cuid: clqxp6z6200020al82wiobpph
slug: leetcode-problem-number-of-laser-beams-in-a-bank
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1704281137793/4fa4b2c0-3b30-48cf-b349-f08f559d7ff0.png

---

**<mark>(Medium)</mark>**

In this blog post, we will explore and solve the LeetCode problem titled "Number of Laser Beams in a Bank." The problem involves working with a 2D binary matrix representing the floor plan of a bank, where '0' denotes an empty cell, and '1' denotes a cell with a security device. The goal is to determine the total number of laser beams between pairs of security devices based on specific conditions.

### **Problem Overview:**

Given a binary string array `bank`, representing the floor plan of a bank, where `bank[i]` represents the ith row, the task is to find the total number of laser beams satisfying the following conditions:

1. The two devices are located on two different rows: r1 and r2, where r1 &lt; r2.
    
2. For each row i where r1 &lt; i &lt; r2, there are no security devices in the ith row.
    

### **Solution Approach:**

The provided solution employs a simple and efficient approach to solve the problem. The key idea is to iterate through each row of the bank, counting the number of '1's in each row. The algorithm accumulates the product of the current and previous row's '1' counts when there are '1's in the current row, as these pairs contribute to the laser beams.

### Code:

```java
class Solution {
    public int numberOfBeams(String[] bank) {
        // Initialize variables to keep track of the count of '1's in the previous row and the total number of laser beams.
        int previousOneCount = 0;
        int ans = 0;

        // Iterate through each row of the bank.
        for(String s : bank){
            // Initialize a variable to count the number of '1's in the current row.
            int currentOneCount = 0;

            // Iterate through each character in the current row.
            for(int i = 0; i < s.length(); i++) {
                // Check if the character is '1' and increment the count.
                if (s.charAt(i) == '1')
                    currentOneCount++;
            }

            // If the current row has '1's, accumulate the product of the current and previous row's '1' counts.
            if(currentOneCount > 0){
                ans += currentOneCount * previousOneCount;
                // Update the previousOneCount variable with the current row's '1' count.
                previousOneCount = currentOneCount;
            }
        }
        return ans;
    }
}
```

* The outer loop iterates through each row of the bank.
    
* The inner loop counts the number of '1's in the current row.
    
* If the current row has '1's, it accumulates the product of the current and previous row's '1' counts into the `ans` variable.
    
* The `previousOneCount` variable is updated with the current row's '1' count.
    

### **Conclusion:**

In this blog post, we've tackled the LeetCode problem "Number of Laser Beams in a Bank" using a concise and effective solution. The approach involves iterating through the bank matrix and counting '1's in each row, accumulating the laser beams based on specific conditions. The provided Java code provides a clear implementation of the solution, showcasing the simplicity and efficiency of the algorithm.

This problem highlights the importance of understanding the conditions and constraints provided in the problem statement to devise an optimal solution. We hope this blog post aids in comprehending the problem and implementing an effective solution.

Happy coding!