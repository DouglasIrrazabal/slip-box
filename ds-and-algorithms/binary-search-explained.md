# Binary Search Explained

- **Core Concept:** An efficient search algorithm that repeatedly divides the search interval in half, significantly reducing the number of elements to consider until the target value is found or its absence is confirmed.
- **Key Requirements:**
    - The data must be sorted in ascending or descending order.

## Code Example:

```ts
function binarySearch(arr: number[], target: number): number | undefined {
    let low = 0;
    let high = arr.length - 1;

    while (low <= high) {
        const mid = Math.floor((low + high) / 2);

        if (arr[mid] === target) {
            return mid; // Target found
        } else if (arr[mid] < target) {
            low = mid + 1; // Search in the right half
        } else {
            high = mid - 1; // Search in the left half
        }
    }

    return undefined; // Target not found
}
```

## Code Explanation:
1. **Initialization:** Set `low` and `high` to the array's bounds.
2. **Iterative Search:**
   - Calculate the middle index (`mid`).
   - Compare `arr[mid]` with the `target`:
     - If equal, return `mid` (target found).
     - If less, update `low` to `mid + 1` to search the right half.
     - If greater, update `high` to `mid - 1` to search the left half.
3. **Return:** If the loop completes without finding the target, return `undefined`.

## Common Errors and Prevention Strategies:
- **Off-by-One Errors:** Incorrect calculations of `mid`, `low`, or `high` can lead to missed elements or infinite loops.
  - **Prevention:** Use precise integer division (`Math.floor`) and carefully check boundary conditions.
- **Unsorted Data:** Binary search fails on unsorted arrays.
  - **Prevention:** Ensure data is sorted before applying the algorithm.
- **Incorrect Comparisons:** Errors in comparing elements can produce inaccurate results.
  - **Prevention:** Double-check comparison logic and handle edge cases (e.g., empty arrays).

## Additional Notes:
- **Efficiency:** Binary search has a time complexity of O(log n), making it highly efficient for large datasets.
- **Applications:** Finding specific elements in sorted arrays, implementing efficient lookup tables, and solving problems like finding the first or last occurrence of a value.
- **Alternatives:** For unsorted data, linear search (O(n)) or hash tables (average O(1)) can be considered.