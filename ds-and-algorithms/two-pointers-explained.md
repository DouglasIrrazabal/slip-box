# Two Pointers Explained
- **Core Concept:** A technique that utilizes two pointers to traverse and manipulate arrays or sequences, often leading to efficient solutions for problems involving comparisons or finding pairs of elements.
- **Key Characteristics:**
  - **Simplicity:** Often results in concise and intuitive code.
  - **Efficiency:** Can significantly reduce time complexity compared to naive approaches.
  - **Versatility:** Applicable to diverse problems.

## Code Example
```ts
function twoSum(nums: number[], target: number): number[] {
    let left = 0;
    let right = nums.length - 1;

    while (left < right) {
        const currentSum = nums[left] + nums[right];
        if (currentSum === target) {
            return [left + 1, right + 1]; // Indices start from 1
        } else if (currentSum < target) {
            left++; // Move left pointer to increase sum
        } else {
            right--; // Move right pointer to decrease sum
        }
    }

    return []; // No solution found
}
```

## Code Explanation
1. **Initialization:** Set `left` and `right` pointers to the array's ends.
2. **Iterative Search:**
   - Calculate the current sum (`currentSum`) using the values at `left` and `right`.
   - If `currentSum` matches the `target`, return the indices.
   - If `currentSum` is less, move `left` to increase the sum.
   - If `currentSum` is greater, move `right` to decrease the sum.
3. **Return:** If no solution is found, return an empty array.

## Common Errors and Prevention Strategies
- **Off-by-One Errors:** Be cautious with pointer boundaries and array indices.
- **Infinite Loops:** Ensure pointers converge towards a solution.
- **Incorrect Comparisons:** Verify comparison logic for specific problems.

## Additional Notes
- **Applications:**
  - Finding pairs with a given sum
  - Finding three-sum combinations
  - Removing duplicates
  - Reversing arrays
  - Merging sorted arrays
  - Identifying palindromes
- **Variants:** Sliding window, fast-slow pointers, and meeting in the middle are common variations.
