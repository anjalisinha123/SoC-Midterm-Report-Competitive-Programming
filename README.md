# SoC-Midterm-Report-Competitive-Programming
Week 1 Progress Summary: Problem Solving & Algorithms
Overview
This week focused on foundational problem-solving patterns, including string manipulation, 
two-pointer sliding windows, greedy approximations, and Kadane’s algorithm. A total of 10 
problems were successfully implemented in C++.
Problem Summaries
1. Beautiful Year
Core Concept: Brute Force / Digit Extraction
Approach: The program increments the starting year n by 1 and checks subsequent years 
sequentially. For each year, it extracts all four individual digits and uses a conditional 
statement to verify if all digits are mutually distinct. It prints the first year that satisfies 
this condition and terminates. 
2. Books
Core Concept: Two-Pointer Approach / Sliding Window
Approach: Designed to find the maximum number of books that can be read within a time 
limit t. It maintains a variable window defined by left and right pointers. The right pointer 
expands the window by adding books to the sum. If sum exceeds t, the left pointer 
contracts the window from the left until the condition is re-satisfied. The maximum 
window size is tracked throughout. 
3. Flipping Game
Core Concept: Kadane’s Algorithm / Dynamic Programming
Approach: To maximize the number of 1s after exactly one subarray flip, the problem is 
transformed into finding the maximum subarray sum. Elements are mapped such that 0 
becomes +1 (potential gain) and 1 becomes -1 (potential loss). Kadane's algorithm is then 
executed on this modified array to find the optimal segment to flip. 
4. George and Accommodation
Core Concept: Basic Conditional Filtering
Approach: Iterates through n rooms, reading the current number of occupants a and the 
total capacity b. It increments a counter whenever a room has at least 2 free spaces 
remaining (b - a > 1) to accommodate George and his friend. 
5. Lucky Sum of Digits
Core Concept: Greedy Search / Digit Construction
Approach: Finds the lexicographically smallest number consisting only of digits 4 and 7 
that sums exactly to n. The loop dynamically prioritizes subtracting 7 when divisible , 
then 4 when divisible , and falls back to a combined step if needed. It then prints the 
constructed sequence of 4s followed by 7s. 
6. Petya and Strings
Core Concept: String Comparison & Normalization
Approach: Normalizes two strings by converting all uppercase characters to lowercase 
via ASCII shifts (+32). After checking that the lengths match , it performs a lexicographical 
comparison using standard operators to output 0 if equal, 1 if the first is greater, and -1 if 
the second is greater. 
7. Queue at the School
Core Concept: Simulation
Approach: Simulates a queue shuffle over t time steps. In each step, it passes through the 
string and swaps adjacent characters whenever a boy (B) is directly in front of a girl (G). 
The loop index is incremented an extra time upon a swap to prevent a single student from 
moving forward multiple positions in a single time step. 
8. Regular Bracket Sequence
Core Concept: Combinatorics / Validation logic
Approach: Evaluates whether counts of specific bracket pairs (((, )(, (), ))) can form a valid 
bracket sequence. It verifies that the count of open-pair blocks matches the close-pair 
blocks , and handles the edge case where independent middle pairs ()() exist without any 
outer enclosing brackets. 
9. Stones on the Table
Core Concept: String Traversal / Neighbor Checking
Approach: Solves the problem of finding the minimum number of stones to remove so 
that no two adjacent stones have the same color. It checks the string linearly from index 
0 to n-2 and increments a removal counter whenever s[i] == s[i+1]. 
10. Translation
Core Concept: Two-Pointer String Reversal
Approach: Validates if string t is the reverse of string s. It manually reverses string s in
place by swapping symmetric characters from both ends up to the middle of the string 
(s.size()/2). Finally, it performs a direct string equality check against

Week 2 Progress Summary: Advanced Greedy & Data Structures
Overview
This week shifted focus toward optimization problems involving two-pointer greedy schemes, 
prefix sum look-aheads, coordinate sorting, and frequency/index map lookups using 
associative containers. A total of 6 problems were successfully implemented in C++.
Problem Summaries
1. Basketball Together
Core Concept: Two-Pointer Greedy Strategy 
Approach: To maximize the number of winning teams, the available players are sorted by 
their power. Using a two-pointer approach, the algorithm greedily picks the strongest 
unassigned player to act as the team leader. It calculates the exact number of additional 
players required to make this leader's total team power cross the threshold $D$. The 
required numbers are then sacrificed from the weakest available players at the left 
pointer. 
2. Collecting Game
Core Concept: Prefix Sums & Multi-Pointer Look-Ahead 
Approach: Tracks how many elements a starting element can absorb by pairing values 
with their original indices and sorting them. It constructs a prefix sum array to keep track 
of the cumulative score accumulated up to any element. The algorithm employs a trailing 
pointer j that scans forward as far as possible, expanding the cascade whenever the 
current cumulative prefix sum is large enough to absorb the next element. 
3. Ian and Array Sorting
Core Concept: Parity & Ripple-Effect Invariance 
Approach: Analyzes whether an array can be made non-decreasing by applying 
operations that increase or decrease an adjacent pair of elements simultaneously. If the 
array size $n$ is odd, it is always valid. For even $n$, the code executes a continuous, 
greedy forward pass ("ripple pass"). It forces elements into non-decreasing order step
by-step and updates the subsequent adjacent element, checking if the final two elements 
satisfy the non-decreasing condition at the end. 
4. Points and Minimum Distance
Core Concept: Coordinate Sorting & Greedy Path Optimization 
Approach: Minimizes the total Manhattan distance required to connect $n$ geometric 
points along a straight path using $2n$ line segments. The code sorts the entire array of 
coordinates. It then splits the sorted array cleanly down the middle, pairing the first half 
(representing $x$-coordinates) directly with the second half (representing $y$
coordinates) to yield the minimum possible path perimeter. 
5. Train and Queries
Core Concept: Position Hashing / Map Index Lookup 
Approach: Optimizes route-validation queries by checking if a train can travel from 
station $A$ to station $B$ along a single path. Instead of traversing the array linearly for 
each query, the code uses two std::map containers to cache the absolute first_occ and 
last_occ indices of every station as they are read. Validating a path is reduced to an 
$O(1)$ lookup check to see if the earliest occurrence of $A$ is smaller than the latest 
occurrence of $B$. 
6. Yarik and Musical Notes
Core Concept: Combinatorics & Frequency Maps 
Approach: Solves for pairs $(i, j)$ satisfying the equation $a_i^{a_j} = a_j^{a_i}$. 
Mathematically, this condition is only met when $a_i = a_j$, or in the single unique edge 
case where the values are $1$ and $2$ (since $1^2 \neq 2^1$ is false, but $2^1$ vs $1^2$ 
holds up under the original problem's log property transformations). The program 
populates a frequency map, calculates matching identical pairs using the combination 
formula $\frac{count \times (count - 1)}{2}$, and adds cross-products for counts of $1$ 
and $2$
