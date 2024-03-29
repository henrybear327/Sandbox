# Reminders

1. Deal with `NULL` pointer and `sz = 0` cases first!
2. Carefully consider the input conditions that are given
    * range and sign of input! (leetcode 166, 7, 163)
    * input datatype (int, float; string, vector, array)
    * **duplicated** or not (leetcode 163, 425)
3. Come up with the sub-optimal or naive solution first
4. Basic testcases:
    * no element
    * one element
    * extreme value
    * duplicated values
5. When doing recursion, think of the terminating conditions first
6. Set the initial values carefully (leetcode 228)
7. For binary search, consider the monotonic property carefully first!
8. For linked list, don't forget to more the the cursor forward
9. If you mean to use reference, double check for it!
10. When doing `min()` `max()`, make sure the answer is updated every time and AFTER the last iteration
11. When doing `mn` and `mx` updating, make sure we keep the original value first!!!! (leetcode 152)
12. `int *a, *b;` for a and b both to be declared as pointer!
13. When brute forcing, think if you can keep a memo of the search space (leetcode 139, 96)
14. Brute force: for every position... (leetcode 42)
15. Clarify if `int` might be enough! If using long long, make sure that the conversion is done properly! (leetcode 50)
16. Might need to deal with negative numbers! (Leetcode 326)
17. Use bit trick to save space (Leetcode 289)
18. Use `(ternary stuff)` so avoid precedence issues!
19. If you use `while` and need to manually maintain the pointer, add comments first!
20. When checking strings, vectors: watch out for `out-of-bound` error
21. Think of all cases before you type `+=` and `return` (leetcode 124, cases could be thought of when typing)
22. When pushing things onto the stack, we can just push the index, instead of value-index pair! (leetcode 84)
23. Do **NOT** be afraid when you see problems being labelled as hard!
24. May need to check for mod == 0! (823)
25. Brute force: for every starting point...
26. BFS, when enqueue, mark as seen! (505)
27. When popping `stack`, `queue`, `deque`, check for `size() > 0` first
28. For binary searching, l and r are just idx, don't forget to use the value that point to! (360)
29. Convert to graph! (399)
30. Odd/even checking 
31. Sorted or not?
32. DFS next step, besides bound check, don't forget to check if it's allow to be walked
33. `fabs()` may be required when doing floating point diffing

# Compilation

1. `PROBLEM=...`
2. ```bash
clang-format -style=LLVM -i $PROBLEM.cpp && astyle --style=linux $PROBLEM.cpp && rm $PROBLEM.cpp.orig && time g++ -Wall -Wextra -Wshadow -O2 -std=c++14 -DLOCAL $PROBLEM.cpp && time ./a.out
```

# Random notes

* check for total problems solved `ls *.cpp | wc -l`
* `vector<string> inp{"Hello world"};`
* `next(it, steps=1)`;

# Snippets

Some random setup code

## TreeNode code

```c++
struct TreeNode {
    int val;
    TreeNode *left;
    TreeNode *right;
    TreeNode(int x) : val(x), left(NULL), right(NULL) {}
};
```

## Singly linked list

```c++
struct ListNode {
    int val;
    ListNode *next;
    ListNode(int x) : val(x), next(NULL) {}
};
```

## sstream

```c++
string item;
stringstream ss;
ss.str(input);

while(!getline(ss, item, ',')) {

}
```

## Set struct overloading

Overload `bool operator(const ... & others) const`

## Tuple

1. `tuple<type, type, ...>`
2. `make_tuple(var, var)`
3. `get<index> tupleName`
4. 
```c++
int a;
int b;
tie(a, b) = someReturnedTuple

## 2D vector init

```c++
dp = vector<vector<int>>(n, vector<int>(m, 0));
```

## Two pointers

```c++
int l = 0, sum = 0;
int ans = 0;
for (int r = 0; r < n; r++) { // [l, r)
    sum += nums[r];
    if (sum == k)
        ans++;

    while (l < r && sum > k) {
        sum -= nums[l];
        l++;

        if (sum == k)
            ans++;
    }
}
```

# Conversion

string version of `atoi()` is `stoi()`

# Questions that I messed up

* Simply good one: 240 (581 talked about it, now finally understands it), 418 (observation), 766 (implementation), 670 (greedy), 266, 400, 835
* Good but hard greedy: 316
* Two pointer: 683 (nlogn is easy though), 239 (deque), 340, 76 (hard), 259 (goodness!), 360
    * Not two pointer 560
* Iterator: 341, 26 (implement unique)
* Trie
    * (easy) 421, 820
    * (design) 208
    * (tedious) 425
* Heavy implementation skill: 388 (stack), 166, 315, 10, 336 (don't be afraid to enumerate), 681 (100 lines 1 AC!, but time conversion can be done in a more elegant way), 218 (skyline), 351 (enumeration), 288 (tricky case), 544
* Good DP: 10, 312 (cutting stick, but in a different approach), 96(1D), 309(state machine approach, wow!), 818 (hard)
* Math: 172 (I can't believe how bad my math is), 829
* Tree: 124 (wow, path! 3 cases), 687, 298, 834 (very good subtree observation problem)
* Geometry: 149
* Easy DP: 221 (first time coming up with a DP solution!), 85 (based on max rect in histogram), 361, 801 (spaceship)
* Good observation: 11, 828, 484 
* Recursion: 114, 140, 298 (good one)
* Pointer: 237 (never thought of it!), 328
* Recursion `O(2^N)`, with memoization `O(N^2)` because you kept all possible pairs of `(start, end)` in DP!
* Do it from the front or back, coding complexity differs: 482
* Basic DP: 72 (edit distance)
* To graph: 753, 399 (very good one)
* DS: 308 (2d bit)
* UFDS: 737, 305, 839
* Design problems: 271
* BFS: 317 (where to start?/read sample code), 286, 409 (GG good one)
* KMP: 616
* Queue: 329 (topological sort)
* Combination DP: 276
* Class inheritance: 284
* DFS: 417, 294
* String: 676
* Classic:
    * Dynamic median query: 295, 480
* Lot's of cases: 816
* Rectangle: 836

# Procedure

* Ask for spec
* Generate basic testcases, and add more while coding
