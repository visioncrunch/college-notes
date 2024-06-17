# Stack Data Structure Notes

## Overview

- Stack is a linear, homogeneous data structure following Last-In-First-Out (LIFO) or First-In-Last-Out (FILO) access methods.
- Elements are ordered linearly and must be of the same data type.
- Key operations:
    - **PUSH:** Inserts an element into the stack.
    - **POP:** Removes the most recently inserted element from the stack.

## Stack Analogy

Imagine a stack of books. You can only add or remove books from the top of the stack. The last book you add is the first one you can remove.

## Basic Terminologies

- **TOP:** Refers to the most recently inserted element or the element at the top of the stack. A variable `TOP` is often maintained to keep track of this element.
- **PUSH:** Inserts a new element into the stack.
    
    ```
    // Code snippet for PUSH operation (array implementation)
    stack[++top] = new_element; 
    ```
    
- **POP:** Removes the element pointed to by `TOP`.
    
    ```
    // Code snippet for POP operation (array implementation)
    removed_element = stack[top--]; 
    ```
    
- **Size:** Represents the number of elements currently in the stack.
- **Stack Overflow/Full:** Occurs when there is no more space to insert a new element into the stack.
- **Stack Underflow/Empty:** Occurs when trying to remove an element from an empty stack.

## Stack Implementation

Stack can be implemented using either an array or a linked list.

## Applications of Stack

Stacks are used in various applications, including:

- Function calls and recursion
- Undo/redo functionality in software
- Expression evaluation
- Backtracking algorithms
- Memory management

## Additional Notes

- The lecture did not provide code snippets for implementing a stack using a linked list. You can find examples online.
- The lecture also did not cover all possible operations on a stack, such as `peek` (to view the top element without removing it).

Let me know if you'd like more details on any of these topics.

# Stack Implementation Using Arrays

## Assumptions

- **Array Size:** The maximum size of the stack is represented by `MAX`.
- **Static Data Structure:** The size of the array cannot be changed during runtime.
- **Initial State:** The stack is initially empty.
- **TOP Variable:** The `TOP` variable points to the index of the top element in the stack.
- **Lower Bound:** The lower bound of the array is zero (assumed in C programming language).
- **Initial TOP Value:** When the stack is empty, `TOP` is initialized to -1.

## PUSH Operation

### Algorithm

1. Check if the stack is full (`TOP < MAX - 1`).
2. If the stack is not full:
    - Increment `TOP` by one.
    - Store the new element at the location pointed to by `TOP`.
    - Return 1 (success).
3. If the stack is full:
    - Return 0 or -1 (failure).

### C Implementation

C

```
int push(int element) {
    if (top < MAX - 1) {
        storage[++top] = element;
        return 1; // Success
    } else {
        return 0; // Stack overflow
    }
}
```

### Time and Space Complexity

- **Time Complexity:** O(1) (constant time) - Insertion is done at the end of the array.
- **Space Complexity:** O(1) (constant space) - Only a constant amount of additional space is used for variables.

## Notes

- The implementation assumes global variables for `storage` (array), `TOP`, and `MAX`.
- Insertion is done at the last position to reduce time complexity (avoiding shifting elements).
- You can implement insertion at the beginning of the array, but it will increase the time complexity to O(n).
- This code snippet focuses only on the `push` operation. You'll need to implement other stack operations (`pop`, `peek`, etc.) to complete the stack implementation using an array.

# Stack Implementation Using Arrays (Continued)

## POP Operation

### Algorithm

1. Check if the stack is empty (`TOP > -1`).
2. If the stack is not empty:
    - Store the top element (`storage[TOP]`) in a temporary variable (`OUT`).
    - Decrement `TOP` by one.
    - Return `OUT`.
3. If the stack is empty:
    - Return an error code (e.g., -1) to indicate stack underflow.

### C Implementation

C

```
int pop() {
    if (top > -1) {
        int out = storage[top--];
        return out;
    } else {
        return -1; // Stack underflow
    }
}
```

### Time and Space Complexity

- **Time Complexity:** O(1) (constant time) - Removal is done directly from the top of the array.
- **Space Complexity:** O(1) (constant space) - Only a constant amount of additional space is used for variables.

## Other Stack Operations

- **topOfStack:** Returns the top element without removing it. Time complexity: O(1), Space complexity: O(1).
- **isEmpty:** Returns `true` (or 1) if the stack is empty, `false` (or 0) otherwise. Time complexity: O(1), Space complexity: O(1).
- **isFull:** Returns `true` (or 1) if the stack is full, `false` (or 0) otherwise. Time complexity: O(1), Space complexity: O(1).
- **display:** Prints all elements of the stack. Time complexity: O(n) (linear time), Space complexity: O(1).

## Complete C Program

The lecture provided a complete C program incorporating all these operations. Please refer to the lecture video for the code.

## Stack ADT (Abstract Data Type)

The lecture also demonstrated implementing a Stack ADT using C++, encapsulating the stack operations and data within a class. This promotes better code organization and separation of concerns.

## Key Points

- **Array Limitations:** The size of the stack is limited by the size of the underlying array.
- **Insertion Position:** Inserting at the last position (`push`) and removing from the last position (`pop`) are more efficient (O(1)) than inserting/removing at the beginning (O(n)).
- **ADT Advantages:** Using an ADT provides a cleaner interface for interacting with the stack and hides implementation details from the client code.

# Stack Implementation Using Linked Lists

## Assumptions

- **Linked List Type:** Singly linked list (though doubly or circular could be used).
- **PUSH Operation:** Inserts a new node at the beginning of the list (insert at first).
- **POP Operation:** Deletes the first node of the list (delete at first).
- **Head Pointer:** Global variable to simplify implementation.
- **Headed List:** A dummy node acts as the head node, with elements inserted after it.

## Headed Linked List Implementation

### Create Empty Stack

- Create a dummy node (`head`).
- Set `head->data` to 0 (initial number of elements).
- Set `head->next` to NULL (empty list).

### PUSH Operation

1. Create a new node (`ptr`).
2. Assign the value to `ptr->data`.
3. Set `ptr->next = head->next` (connect to previous first node).
4. Set `head->next = ptr` (make the new node the first node).
5. Increment `head->data` (update node count).

### POP Operation

1. Check if the list is empty (`head->next == NULL`).
2. If not empty:
    - Store the address of the first node (`head->next`) in `ptr`.
    - Set `head->next = head->next->next` (remove first node).
    - Decrement `head->data`.
    - Store the data from `ptr` in a variable (`x`).
    - Free the node (`ptr`).
    - Return `x`.
3. If empty:
    - Return an error code (e.g., -1).

### Other Operations

- **isEmpty:** Returns `true` (or 1) if the list is empty, `false` (or 0) otherwise.
- **size:** Returns `head->data` (number of nodes in the list).
- **display:** Traverses the list and prints each node's data.

### Time and Space Complexity

- **PUSH and POP:** O(1) time and space complexity.
- **isEmpty and size:** O(1) time and space complexity.
- **display:** O(n) time complexity, O(1) space complexity.

## Non-Headed Linked List Implementation

The implementation for a non-headed linked list would be similar, but without the dummy node. The `head` pointer would directly point to the first element of the stack.

## Key Points

- **Headed List Advantages:** Simplifies operations like checking for an empty stack and tracking the size.
- **Insert/Delete at First:** Choosing to insert and delete at the beginning allows for O(1) time complexity due to direct access to the head node.
- **Full Operation Not Applicable:** With dynamic memory allocation, a stack using a linked list won't overflow unless memory runs out.

Refer to the uploaded code for a complete implementation and feel free to experiment with it!

# Stack Implementation Using Non-Headed Linked Lists

## Assumptions

- **Linked List Type:** Singly linked list (no dummy head node).
- **PUSH Operation:** Inserts a new node at the beginning (insert at first).
- **POP Operation:** Deletes the first node (delete at first).
- **Head Pointer:** Global variable pointing to the first node.
- **No Tail Pointer:** The address of the last node is not maintained.

## Non-Headed Linked List Implementation

### Create Empty Stack

- Simply declare the `head` pointer variable and initialize it to `NULL`.

### PUSH Operation

1. Create a new node (`ptr`).
2. Assign the value to `ptr->data`.
3. Set `ptr->next = head` (connect to the previous first node).
4. Update `head = ptr` (make the new node the first node).

### POP Operation

1. Check if the list is empty (`head != NULL`).
2. If not empty:
    - Store the address of the first node (`head`) in `temp`.
    - Update `head = head->next` (move head to the second node).
    - Store the data from `temp` in a variable (`x`).
    - Free the node (`temp`).
    - Return `x`.
3. If empty:
    - Return an error code (e.g., -1).

### Other Operations

- **isEmpty:** Returns `true` (or 1) if `head == NULL`, `false` (or 0) otherwise.
- **size:** Traverses the list to count the number of nodes.
- **display:** Traverses the list and prints each node's data.

### Time and Space Complexity

- **PUSH and POP:** O(1) time and space complexity.
- **isEmpty:** O(1) time and space complexity.
- **size:** O(n) time complexity, O(1) space complexity.
- **display:** O(n) time and space complexity.

## Implementation Differences (Compared to Headed List)

- **Creation:** No dummy head node is created in a non-headed list.
- **isEmpty:** Checks if `head` is `NULL` instead of checking `head->next`.
- **size:** Requires traversing the entire list to count nodes.
- **PUSH:** The `head` pointer is updated directly instead of `head->next`.

## Typo Corrections

- In the `pop` operation, the condition should be `head != NULL`, not `head->next != NULL`.
- The slide mentioning "headed" list should actually say "headless" or "non-headed".

## Conclusion

Both headed and non-headed linked list implementations offer efficient stack operations with O(1) time complexity for `push` and `pop`. The choice between them depends on whether you prefer the simplicity of a non-headed list or the additional benefits of a dummy head node for tracking size and simplifying the `isEmpty` check.

# Infix to Postfix Conversion Using Stack

## Overview

This session focuses on evaluating infix expressions using a two-step process:

1. Convert the infix expression to postfix notation using a stack.
2. Evaluate the postfix expression using another stack.

## Assumptions

- **Stack Usage:** A stack is used to store operators and intermediate results.
- **Operator Associativity:** The algorithm assumes left-to-right associativity for operators.
- **Operator Exclusions:** Unary operators (e.g., negation) and exponent operators are not included in this simplified version.

## Algorithm for Infix to Postfix Conversion

1. **Scan the infix expression** from left to right, extracting tokens one by one.
2. **For each token:**
    - **If it's an operand:** Append it to the postfix expression.
    - **If it's an operator:**
        - **If the stack is empty:** Push the operator onto the stack.
        - **If the stack is not empty:**
            - **Pop operators** from the stack while they have higher or equal precedence to the current operator and are not opening parentheses.
            - **Append the popped operators** to the postfix expression (except for opening parentheses).
            - **Push the current operator** onto the stack.
    - **If it's an opening parenthesis:** Push it onto the stack.
    - **If it's a closing parenthesis:**
        - **Pop operators** from the stack and append them to the postfix expression until an opening parenthesis is encountered.
        - **Discard the opening and closing parentheses.**
3. **After scanning:** Pop any remaining operators from the stack and append them to the postfix expression.

## Time and Space Complexity

- **Time Complexity:** O(n), where n is the number of tokens in the infix expression.
- **Space Complexity:** O(n), as the stack size can grow up to the number of operators.

## Example

Let's consider the infix expression: `A + B - C * (D / E + F) * G`

The following table shows the step-by-step conversion process:

|Token|Postfix Expression|Stack|Action|
|---|---|---|---|
|A|A||Append operand|
|+|A|+|Push operator|
|B|AB|+|Append operand|
|-|AB|-|Push operator (higher precedence)|
|C|ABC|-|Append operand|
|*|ABC|*|Push operator|
|(|ABC|*(|Push opening parenthesis|
|D|ABCD|*(|Append operand|
|/|ABCD|*/(|Push operator|
|E|ABCDE|*/(|Append operand|
|+|ABCDE|+/(|Push operator|
|F|ABCDEF|+/(|Append operand|
|)|ABCDE+F|*|Pop until '(' and discard|
|*|ABCDE+F*|*|Push operator (equal precedence)|
|G|ABCDE+F*G|*|Append operand|
||ABCDE+F_G_-/++||Pop remaining operators|

The resulting postfix expression is: `ABCDE+F*G*-/++`

## Exercise

Modify the algorithm to support right-to-left associativity for exponent and unary operators.

# Postfix Expression Evaluation Using Stack

## Overview

This session covers the algorithm to evaluate postfix expressions using a stack. The approach is simpler than evaluating infix expressions directly.

## Assumptions

- **Stack Usage:** A stack is used to store operands and intermediate results.
- **Operator Associativity:** Left-to-right associativity is assumed for operators.

## Algorithm for Postfix Evaluation

1. **Scan the postfix expression** from left to right, extracting tokens one by one.
2. **For each token:**
    - **If it's an operand:** Push it onto the stack.
    - **If it's an operator:**
        - **Pop two operands** from the stack (second operand first, then the first operand).
        - **Apply the operator** to the popped operands.
        - **Push the result** back onto the stack.
3. **After scanning:** The single remaining element in the stack is the result of the expression.

## Time and Space Complexity

- **Time Complexity:** O(n), where n is the number of tokens in the postfix expression.
- **Space Complexity:** O(n), as the stack size is determined by the number of operands.

## Example

Let's consider the postfix expression: `2 5 + 3 6 * 2 9 / - 3 / -`

The following table shows the step-by-step evaluation process:

|Token|Stack|Action|
|---|---|---|
|2|2|Push operand|
|5|2, 5|Push operand|
|+|7|Pop 5, 2; Apply '+'; Push 7|
|3|7, 3|Push operand|
|6|7, 3, 6|Push operand|
|*|7, 18|Pop 6, 3; Apply '*'; Push 18|
|2|7, 18, 2|Push operand|
|9|7, 18, 2, 9|Push operand|
|/|7, 18, 2|Pop 9, 2; Apply '/'; Push 2|
|-|7, 16|Pop 2, 18; Apply '-'; Push 16|
|3|7, 16, 3|Push operand|
|/|7, 5|Pop 3, 16; Apply '/'; Push 5|
|-|1|Pop 5, 7; Apply '-'; Push 1|

The final result in the stack (1) is the value of the postfix expression.

## Key Points

- **Operand Order:** Ensure the correct order of operands when popping from the stack for operations (second operand first).
- **Operator Implementation:** Implement the application of operators (+, -, *, /, etc.) based on your specific programming language and data types.

Let me know if you'd like a code example for implementing this algorithm!

# Infix to Prefix Conversion Using Stack

## Overview

This session covers an algorithm to convert an infix expression to its prefix form by leveraging the infix-to-postfix conversion algorithm with modifications.

## Concept

1. Reverse the infix expression, swapping opening and closing parentheses.
2. Apply a modified infix-to-postfix algorithm to the reversed expression.
3. Reverse the resulting postfix expression to obtain the prefix expression.

## Modifications to Infix-to-Postfix Algorithm

- In step 5, instead of popping operators with **higher or equal** precedence, pop only those with **strictly higher** precedence than the current operator.
- In step 2, when the current token is an opening parenthesis, push it onto the stack if the stack is empty or the top element is also an opening parenthesis. Otherwise, push the current token onto the stack.

## Example

Let's consider the infix expression: `A * B + C / D`

1. **Reverse and swap parentheses:** `D / C + B * A`
2. **Apply modified infix-to-postfix algorithm:**
    - This step is the same as the previous infix-to-postfix conversion, with the modification mentioned above. The resulting postfix expression will be: `DC/BA*+`
3. **Reverse the postfix expression:** `+A*BC/D`

The final result is the prefix expression: `+A*BC/D`

## Algorithm Steps (with Modifications Highlighted)

1. Scan the reversed infix expression from left to right.
2. For each token:
    - If it's an operand, append it to the postfix expression.
    - If it's an operator:
        - If the stack is empty, push the operator onto the stack.
        - If the top of the stack is an opening parenthesis, push the operator onto the stack.
        - If the top of the stack is an operator with **strictly higher** precedence, pop it from the stack and append it to the postfix expression. Then push the current operator onto the stack.
        - Otherwise, push the current operator onto the stack.
    - If it's an opening parenthesis, push it onto the stack.
    - If it's a closing parenthesis, pop operators from the stack and append them to the postfix expression until an opening parenthesis is encountered. Discard both parentheses.
3. After scanning, pop any remaining operators from the stack and append them to the postfix expression.
4. Reverse the resulting postfix expression to obtain the prefix expression.

## Time and Space Complexity

- **Time Complexity:** O(n), where n is the number of tokens in the infix expression.
- **Space Complexity:** O(n), as the stack size can grow up to the number of operators.

## Key Points

- This algorithm leverages the existing infix-to-postfix algorithm with minor modifications.
- Reversing the expression and swapping parentheses are crucial steps.
- The modified precedence rule ensures correct operator placement in the prefix expression.

# Applications of Stack Data Structure: Delimiter Matching and Pattern Counting

## Delimiter Matching

- **Purpose:** Verifies if opening and closing delimiters (parentheses, brackets, etc.) in a string are correctly matched.
- **Relevance:** Essential for syntax checking in programming languages, JSON, XML, and other structured data formats.
- **Algorithm:**
    1. Initialize an empty stack.
    2. Scan the string from left to right.
    3. If an opening delimiter is found, push it onto the stack.
    4. If a closing delimiter is found:
        - If the stack is empty or the top element does not match the closing delimiter, then the delimiters are not matched.
        - If the top element matches the closing delimiter, pop it from the stack.
    5. Repeat until the entire string is scanned.
    6. If the stack is empty, the delimiters are matched; otherwise, they are not matched.

## Pattern Counting

- **Purpose:** Determines if a string belongs to a specific language based on patterns of characters.
    
- **Examples:**
    
    - Language L1: a^n b^n (equal number of 'a's followed by equal number of 'b's)
    - Language L2: a^i b^j a^k (any number of 'a's followed by any number of 'b's, followed by any number of 'a's)
    - Language L3: a^m b^m a^n b^n (equal number of 'a's followed by equal number of 'b's, repeated)
- **Algorithm (for L1):**
    
    1. Initialize an empty stack.
    2. Scan the string from left to right.
    3. If the character is 'a', push it onto the stack.
    4. If the character is 'b':
        - If the stack is empty, the string is not in L1.
        - Otherwise, pop an 'a' from the stack.
    5. Repeat until the entire string is scanned.
    6. If the stack is empty, the string is in L1; otherwise, it is not.
- **Algorithm (for L2 and L3):** Similar approaches can be applied, with specific push/pop rules for each language.
    

## Key Points

- Stacks are well-suited for problems involving nested structures or matching pairs.
- The algorithms presented here are simplified examples. More complex patterns might require adjustments to the push/pop rules.
- Delimiter matching and pattern counting have applications in compiler design, text processing, and more.

