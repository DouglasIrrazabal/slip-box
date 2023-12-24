# Recursion Explained
- **Core Concept:** A problem-solving technique where a function calls itself directly or indirectly to solve smaller instances of the same problem, breaking it down into simpler subproblems.
- **Key Characteristics:**
    - **Base Case:** A terminating condition that stops the recursion, producing a final result.
    - **Recursive Call:** The function calling itself with a modified input, moving towards the base case.
    - **Stack:** Used to track function calls and variables, crucial for recursion management.

## Code Example:
```ts
function factorial(n: number): number {
    if (n === 0) { // Base case: factorial of 0 is 1
        return 1;
    } else {
        return n * factorial(n - 1); // Recursive call: multiply n by factorial of (n-1)
    }
}
```

## Code Explanation:
1. **Base Case:** `if (n === 0)` handles the simplest case, returning
2. **Recursive Call:** `return n * factorial(n - 1)` calls `factorial` with `n - 1`, moving towards the base case.
3. **Recursive Breakdown:**
   - `factorial(4)` calls `factorial(3)` * 4.
   - `factorial(3)` calls `factorial(2)` * 3.
   - `factorial(2)` calls `factorial(1)` * 2.
   - `factorial(1)` calls `factorial(0)` * 1.
   - `factorial(0)` returns 1, ending recursion.
4. **Result:** Values unwind back up the stack, resulting in 24 (4 * 3 * 2 * 1).

## Common Errors and Prevention Strategies:
- **Missing Base Case:** Causes infinite recursion and stack overflow.
    - **Prevention:** Ensure a clear base case to terminate recursion.
- **Incorrect Recursive Call:** Leads to incorrect results or infinite loops.
    - **Prevention:** Verify calls move towards the base case, reducing problem size.
- **Excessive Recursion:** Can impact performance and stack space.
    - **Prevention:** Consider iterative solutions for simpler problems.
    - **Mitigation:** Tail recursion optimization (if supported) can reduce stack usage.