# question-no-3068
Solution to the question no 3068 on leet code 

3068. Find the Maximum Sum of Node Values
There exists an undirected tree with n nodes numbered 0 to n - 1. You are given a 0-indexed 2D integer array edges of length n - 1, where edges[i] = [ui, vi] indicates that there is an edge between nodes ui and vi in the tree. You are also given a positive integer k, and a 0-indexed array of non-negative integers nums of length n, where nums[i] represents the value of the node numbered i.

Alice wants the sum of values of tree nodes to be maximum, for which Alice can perform the following operation any number of times (including zero) on the tree:

Choose any edge [u, v] connecting the nodes u and v, and update their values as follows:
nums[u] = nums[u] XOR k
nums[v] = nums[v] XOR k
Return the maximum possible sum of the values Alice can achieve by performing the operation any number of times.

How it works:
The maxSumOfNodes function tries two options at each index:

Do not XOR the current element → add nums[index].

XOR the current element with k → add nums[index] ^ k, and toggle the isEven flag (since you've XORed one more element).

It uses recursion + memoization to store already computed results (memo[index][isEven]).

At the end (base case), it checks if the total number of XOR operations is even (isEven == 1). If not, it returns a very small number (Integer.MIN_VALUE) to invalidate that path.
