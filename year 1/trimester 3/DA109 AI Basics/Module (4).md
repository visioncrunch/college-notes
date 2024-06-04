Module 4 of DA 109 focuses on problem-solving using uninformed strategies in AI.

**Basic Concepts for Searching a Solution**

- **Search:** The process of finding an action sequence that leads from the initial state to the goal state.
- **Search Algorithm:** A systematic method to explore a problem space by generating and evaluating different action sequences.
- **Search Tree:** A hierarchical representation of the exploration process, where nodes represent states and branches represent actions.
- **Problem Space:** The set of all possible states and actions in a problem.
- **Root Node:** The initial state in the search tree.
- **Leaf Node:** A node with no children in the search tree.
- **Frontier:** The set of all leaf nodes available for expansion.

**Example: Route Planning from Arad to Bucharest**

- This classic example demonstrates how search algorithms work.
- The goal is to find the shortest path from Arad to Bucharest.
- A search tree is created, where cities are nodes and road segments are edges.

**Tree Search vs. Graph Search**

|Feature|Tree Search|Graph Search|
|---|---|---|
|Repeated States|Not considered|Considered|
|Memory Usage|Less|More|
|Completeness|May not be complete|Typically complete|
|Efficiency|More efficient|Less efficient|

**Data Structures for Search Algorithms** Search algorithms need data structures to keep track of the search tree. Each node in the tree includes:

- State
- Parent
- Action
- Path Cost

This lecture lays the foundation for understanding uninformed search strategies in AI. Future lectures will delve deeper into specific algorithms and their applications.

The lecture focuses on the distinction between informed and uninformed search strategies in AI, categorized by domain-specific and non-domain specific knowledge.

**Domain-Specific Knowledge:**

- **Definition:** Information, rules, and patterns specific to a particular problem domain or application area.
- **Informed Strategies:** Use domain-specific knowledge to guide the search process.
- **Pros:** Efficiency, accuracy, customization, interpretability, resource efficiency.
- **Cons:** Limited scope, dependency, data availability, generalization, expertise requirement.
- **Examples:** Medical diagnosis systems, automated trading algorithms, chatbots for customer support.

**Non-Domain Specific Knowledge:**

- **Definition:** Information, principles, and strategies applicable across multiple problem domains or application areas (general knowledge).
- **Uninformed Strategies:** Do not use domain-specific knowledge, exploring the search space systematically.
- **Pros:** Versatility, flexibility, scalability, data availability, innovation.
- **Cons:** Accuracy, interpretability, resource intensity, overfitting, lack of customization.
- **Examples:** Image recognition systems, Natural Language Processing (NLP) techniques, autonomous vehicles.

**Summary:**

- Domain-specific knowledge enhances AI systems in efficiency and accuracy within specific domains but may limit their scope and adaptability.
- Non-domain specific knowledge offers versatility and flexibility across domains but may sacrifice accuracy and customization for specific tasks.
- Choosing the right strategy depends on the specific problem, available data, and desired outcomes.

This lecture highlights the trade-offs between informed and uninformed search strategies and emphasizes the importance of considering both domain-specific and general knowledge in AI development.

Breadth-First Search (BFS) is a simple yet powerful uninformed search strategy used in AI to traverse graphs or trees systematically.

**Algorithm:**

1. Start at the root node.
2. Expand the root node, adding its successors to the back of a queue (FIFO).
3. Dequeue the front node and expand it, adding its successors to the back of the queue.
4. Repeat until the goal node is found or the queue is empty.

**Visualization (Binary Tree Example):**

```
    A
   / \
  B   C
 / \ / \
D  E F  G
```

The order of node expansion in BFS is A, B, C, D, E, F, G.

**Complexity Analysis:**

- **Time Complexity:** O(b^d) (where b is the branching factor and d is the depth of the solution)
- **Space Complexity:** O(b^d)

**Advantages:**

- **Completeness:** Guaranteed to find a solution if one exists.
- **Optimality:** Finds the shortest path in unweighted graphs or mazes.
- **Simplicity:** Easy to understand and implement.

**Limitations:**

- **Memory Consumption:** Can consume a lot of memory for large or deep graphs.
- **Time Complexity:** Can be slow if the solution is far from the root node.
- **Inefficiency in Large Graphs:** May not be the most efficient for very large graphs.

**Conclusion:** BFS is a fundamental search algorithm with strengths in completeness and optimality, but it is limited by memory consumption and time complexity, especially for large or deep graphs.

Understanding the strengths and weaknesses of BFS is crucial for selecting the appropriate search algorithm for a given problem.

Depth-First Search (DFS) is another uninformed search strategy used in AI, focusing on exploring one branch as deeply as possible before backtracking.

**Algorithm:**

1. Start at the root node.
2. Push the root node onto a stack.
3. Pop a node from the stack and expand it, adding its successors to the top of the stack.
4. Repeat until the goal node is found or the stack is empty.

**Visualization (Binary Tree Example):**

```
    A
   / \
  B   C
 / \ / \
D  E F  G
```

The order of node expansion in DFS is A, B, D, E, C, F, G.

**Complexity Analysis:**

- **Time Complexity:** O(b^m) (where b is the branching factor and m is the maximum depth of the tree)
- **Space Complexity:** O(bm)

**Advantages:**

- **Memory Efficiency:** Uses less memory than BFS because it only stores nodes on the current path.
- **Path Finding in Large Graphs:** More practical for large graphs due to lower memory requirements.
- **Backtracking Capability:** Naturally supports backtracking, useful for puzzles and games.

**Limitations:**

- **Completeness:** Not guaranteed to find a solution if one exists, especially in infinite or deep search spaces.
- **Optimality:** Does not guarantee the shortest path to the goal.
- **Risk of Infinite Loops:** Can get stuck in loops if cycle detection is not implemented.

**Conclusion:** DFS is a valuable search algorithm for exploring deep paths efficiently, but it comes with the trade-offs of potential incompleteness and not always finding optimal solutions. Choosing between DFS and BFS depends on the problem's characteristics and the specific requirements of the search.

Depth-Limited Search (DLS) is a variant of Depth-First Search (DFS) designed to address the issue of infinite paths in search spaces by introducing a predetermined depth limit.

**Algorithm:**

1. Start at the root node.
2. Set a depth limit `l`.
3. Recursively explore nodes using DFS up to depth `l`.
4. If the current depth exceeds `l`, stop expanding and backtrack.
5. Repeat until the goal node is found or the depth limit is reached.

**Key Points:**

- **Depth Limit (l):** The maximum depth the algorithm will explore.
- **Completeness:** DLS is not complete if the goal node is deeper than the depth limit.
- **Optimality:** DLS is not optimal if the goal node is shallower than the depth limit.
- **Time Complexity:** O(b^l) (where b is the branching factor and l is the depth limit)
- **Space Complexity:** O(bl)

**Advantages:**

- **Memory Efficiency:** Uses less memory than BFS.
- **Avoids Infinite Loops:** Prevents getting stuck in infinite paths.
- **Suitable for Deep Trees:** Can be effective when the solution is expected to be deep within the search space.

**Disadvantages:**

- **Incompleteness:** May not find a solution if it exists beyond the depth limit.
- **Not Optimal:** May not find the shortest path to the goal.
- **Choosing the Depth Limit:** Requires prior knowledge about the problem or the search space.

**Example (Graph Search):**

```
    S
   / \
  A   B
 / \ / \
C  D E  F
     \
      G
```

Goal: Find path from S to G.

If the depth limit is 2, DLS will explore S, A, B, C, D, E, but not find G. If the depth limit is 3, DLS will explore S, A, B, C, D, E, F, G, and find the goal.

**Conclusion:** DLS is a useful modification of DFS that addresses its potential for infinite loops, making it applicable to search spaces with limited depth. However, choosing an appropriate depth limit is crucial for its effectiveness.

Iterative Deepening Depth-First Search (IDDFS) is a search algorithm that combines the space efficiency of Depth-First Search (DFS) with the completeness of Breadth-First Search (BFS).

**Algorithm:**

1. Set depth limit to 0.
2. Perform Depth-Limited Search (DLS) with the current depth limit.
3. If the goal is found, return the solution.
4. If DLS returns "cutoff" (depth limit reached), increment the depth limit and repeat step 2.
5. If DLS returns "failure" (no solution), terminate the search.

**Visualization (Binary Tree Example):**

```
    A
   / \
  B   C
 / \ / \
D  E F  G
 / \
H   I
   / \
  J   K
     / \
    L   M
```

Goal: Find path from A to L.

IDDFS will perform DLS with increasing depth limits:

- Depth 0: A (cutoff)
- Depth 1: A, B, C (cutoff)
- Depth 2: A, B, D, E, C, F, G (cutoff)
- Depth 3: A, B, D, E, C, F, G, H, I, J, K, L (goal found)

**Complexity Analysis:**

- **Time Complexity:** O(b^d) (same as BFS)
- **Space Complexity:** O(bd) (same as DFS)

**Advantages:**

- **Memory Efficiency:** Uses less memory than BFS.
- **Completeness:** Guaranteed to find a solution if one exists.
- **Optimality:** Finds the shortest path in a tree with non-decreasing path costs.

**Disadvantages:**

- **Repetition of Nodes:** Nodes are repeatedly explored at each depth level, increasing time complexity.

**Conclusion:** IDDFS is a useful algorithm when the depth of the solution is unknown and memory is limited. It combines the strengths of both DFS and BFS, making it a versatile and efficient search strategy for many AI applications.

Bidirectional Search is an AI search algorithm that simultaneously searches from the initial state and the goal state, meeting in the middle to potentially reduce the search space and improve efficiency.

**Motivation:**

- Reduces complexity compared to searching in a single direction.
- The sum of the areas of two smaller circles is less than the area of one large circle centered on the start and goal.

**Implementation:**

- Replaces the goal test with a check to see if the frontiers of the two searches intersect.
- If the frontiers intersect, a solution is found.
- An additional search may be needed to ensure optimality.

**Complexity Analysis:**

- **Time Complexity:** O(b^(d/2)) (using BFS in both directions)
- **Space Complexity:** O(b^(d/2)) (the main weakness of bidirectional search)

**Advantages:**

- **Time Efficiency:** Potentially much faster than unidirectional search.
- **Memory Efficiency:** Can be more memory efficient than BFS if one search uses iterative deepening.
- **Suitable for:** Problems with well-defined start and goal states, and roughly equal search effort in both directions.

**Schematic View:**

```
Start --> ... --> Meeting Node <-- ... <-- Goal
```

**Example (Graph Search):**

```
    A
   / \
  B   C
 / \ / \
E  F G  H
```

Goal: Find path from A to G.

1. Forward search starts from A, explores B, E, F.
2. Backward search starts from G, explores F, H.
3. Both searches meet at F, forming the path A -> B -> F -> G.

**Advantages:**

- **Time Efficiency:** Significantly faster than unidirectional search in many cases.
- **Memory Efficiency:** Can be optimized using iterative deepening for one search direction.
- **Suitable for:** Problems with well-defined start and goal states and similar search effort in both directions.

**Disadvantages:**

- **Space Complexity:** Requires storing visited nodes for both search directions, which can be a limitation.
- **Implementation Complexity:** More complex to implement than unidirectional search.

**Conclusion:** Bidirectional Search offers potential advantages in time efficiency for certain search problems. However, its memory requirements and implementation complexity should be considered when choosing a search strategy.

The lecture covered uninformed search strategies, focusing on Uniform Cost Search (UCS), a method that considers the cost of each path.

**Uniform Cost Search (UCS):**

- **Goal:** Finds the least-cost path from the start node to the goal node.
- **Principle:** Expands nodes with the lowest path cost first, unlike BFS which prioritizes depth.
- **Implementation:** Uses a priority queue to maintain nodes ordered by path cost.
- **Optimality:** Guaranteed to find the optimal solution if path costs are non-negative.
- **Completeness:** Complete if the branching factor is finite and step costs are greater than epsilon.
- **Time and Space Complexity:** Can be higher than BFS, O(b^(C*/ε)), where C* is the optimal cost.
- **Advantages:** Finds optimal solutions in problems with varying action costs.
- **Disadvantages:** Memory intensive and can be slow due to exploration of many low-cost paths.

**Comparison of Uninformed Search Strategies:**

|Strategy|Completeness|Optimality|Time Complexity|Space Complexity|
|---|---|---|---|---|
|Breadth-first search (BFS)|Yes (if b is finite)|Yes (if step costs are equal)|O(b^d)|O(b^d)|
|Uniform-cost search (UCS)|Yes (if b is finite and step costs ≥ ε)|Yes (if step costs ≥ 0)|O(b^(C*/ε))|O(b^(C*/ε))|
|Depth-first search (DFS)|No|No|O(b^m)|O(bm)|
|Depth-limited search (DLS)|No (unless l ≥ d)|No|O(b^l)|O(bl)|
|Iterative deepening depth-first search (IDDFS)|Yes (if b is finite)|Yes (if path cost is non-decreasing with depth)|O(b^d)|O(bd)|
|Bidirectional search|Yes (if b is finite)|Yes (if both directions use BFS)|O(b^(d/2))|O(b^(d/2))|

**Key Terminology:**

- **Branching factor (b):** Maximum number of successors of any node.
- **Depth (d):** Depth of the shallowest goal node.
- **Maximum depth (m):** Maximum depth of the search tree.
- **Depth limit (l):** Maximum depth explored in DLS.
- __Optimal cost (C_):_* Cost of the optimal solution.
- **Epsilon (ε):** Minimum cost of any action.

**Summary of Module 4:** This module covered various uninformed search strategies and their characteristics, including completeness, optimality, time complexity, and space complexity. It emphasized the importance of choosing the right search strategy based on the problem's characteristics and the available resources.

**Next Steps:** Module 5 will delve into informed search strategies, which utilize problem-specific knowledge to guide the search process more efficiently.