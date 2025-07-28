# Recursion — Simple and Essential Concepts
1. What is Recursion?
A function that calls itself directly or indirectly to solve smaller instances of the same problem.

Often used to break down complex problems into simpler, similar subproblems.

2. Key Components of Recursion
Base Case: The stopping condition when recursion ends (prevents infinite calls).

Recursive Case: The part where the function calls itself with a smaller/simpler input.

3. Why Use Recursion?
Elegant solution for problems with repetitive, self-similar structure (e.g., trees, sequences).

Simplifies code for problems like factorial, Fibonacci, tree traversals, and divide-and-conquer algorithms.

4. Simple Examples
java
// Factorial of n (n!)
public int factorial(int n) {
    if (n == 0) return 1;                   // base case
    return n * factorial(n - 1);            // recursive case
}

// Sum of first n natural numbers
public int sumN(int n) {
    if (n == 0) return 0;
    return n + sumN(n - 1);
}
5. How to Think Recursively — Step-by-step
Identify the simplest case (base case).

Define how to reduce the problem into a smaller subproblem.

Combine the results to build the solution.

6. Important Tips
Always have a base case to avoid infinite recursion or stack overflow.

Trace calls to understand recursion depth and behavior.

Recursive solutions may be less efficient than iterative ones, but often simpler and clearer.

7. Common Problems for Practice (Simple to Moderate)
Computing Fibonacci numbers recursively.

Finding the number of terms in a multinomial using the recurrence relation:
A(n, k) = A(n, k - 1) + A(n - 1, k), with appropriate base cases.

Reversing a string using recursion.

Recursive binary search on sorted arrays.

Recursive tree traversals (preorder, inorder, postorder).
