# WHAT-IS-LINKED-LIST

**Linked List**

**Introduction**

A linked list is a linear data structure where each element is a separate object, known as a node. Each node contains two components: the data field (information field) and the address field (next field). The nodes are linked together through the address field, which contains the address of the next node.

**Types of Linked Lists**

There are three types of linked lists:

1. **Singly Linked List**: Each node in the linked list stores the address of only one node, allowing only forward movement.
2. **Doubly Linked List**: Each node in the linked list stores the addresses of both the next node and the previous node, allowing bidirectional movement.
3. **Circular Linked List**: The last node in the linked list points to the first node, allowing direct movement from the last node to the first node and vice versa.

**Node Structure**

A node in a linked list consists of:

1. **Information Field**: Holds the actual data of the node.
2. **Address Field**: Holds the address of the next node in the linked list.

**Example**

```python
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

# Create a linked list with three nodes
head = Node(3)
head.next = Node(1)
head.next.next = Node(7)

# Print the linked list
current = head
while current:
    print(current.data)
    current = current.next
```

**Operations on Linked Lists**

1. **Insertion**: Adding a new node to the linked list.
2. **Deletion**: Removing a node from the linked list.
3. **Traversal**: Iterating through the linked list to access its nodes.

**Advantages of Linked Lists**

1. **Efficient Use of Memory**: Linked lists can be more memory-efficient than arrays, as they only allocate memory for the actual data.
2. **Dynamic Size**: Linked lists can grow or shrink dynamically as nodes are added or removed.

**Disadvantages of Linked Lists**

1. **Slower Access Time**: Linked lists can be slower to access than arrays, as the program needs to traverse the linked list to access a specific node.
2. **More Complex Implementation**: Linked lists require more complex implementation than arrays, as the program needs to manage the nodes and their connections.

**Conclusion**

Linked lists are a fundamental data structure in computer science, offering efficient use of memory and dynamic size. However, they can be slower to access and require more complex implementation than arrays. Understanding linked lists is essential for building efficient and scalable software systems.

---

# IMPLEMENTATION-OF-LINKED-LIST

- Introduction:
  - The session discusses the implementation of a linked list using dynamic and static memory allocation.

- Dynamic Memory Allocation:
  - Memory allocation is done at the time of creating a node.
  - Memory is allocated only when a node is created, making it space efficient.
  - No limit on the number of nodes or elements in the linked list.
  - Example: Defining a node using a struct and reserving memory for each node using malloc function.

- Static Memory Allocation:
  - Memory is allotted before creating the linked list, often using an array.
  - Space for the linked list needs to be reserved beforehand.
  - Example: Using an array to reserve space for the linked list and store elements within the array.

- Comparison:
  - Dynamic memory allocation is space efficient and has no limit on the number of nodes.
  - Static memory allocation is space inefficient and limited by the size of the array.

- Implementation Using Array:
  - Example: Defining a node structure with information and next fields.
  - Creating a two-dimensional array to represent the linked list.
  - Storing node information and addresses in the array.

- Summary:
  - Dynamic memory allocation is the preferred method for implementing a linked list due to its space efficiency and flexibility.
  - Static memory allocation using an array is limited by the array size and is not recommended for linked list implementation.

---

# OPERATIONS-ON-LINKED-LIST-I

**Introduction to Singly Linked List**

A singly linked list is a data structure where each node represents a single element in the list. Each node contains a value and a reference (i.e., a "link") to the next node in the list. This allows for efficient insertion and deletion of nodes at arbitrary positions in the list.

**Properties of Singly Linked List**

* Only forward pass is allowed; no backward movement is possible.
* The address of the first node must be stored, as losing this address makes it impossible to access any elements in the list.
* Before visiting a node, all preceding nodes must be visited, making singly linked lists sequential data structures that do not support random access.

**Operations on Linked List**

* Create a linked list: creates an empty linked list by declaring a pointer variable to store the address of the first node.
* Insert a new element: has multiple functions for inserting elements at different positions in the list (e.g., at the beginning, end, or arbitrary position).
* Delete a node: has multiple functions for deleting nodes at different positions in the list (e.g., the first, last, or arbitrary node).
* Traverse the linked list: visits each node in the list, often used to print or process the elements in the list.

**Traversing a Linked List**

* The traversal operation visits each node in the linked list, starting from the first node and moving to the next node until the last node.
* The algorithm uses a pointer variable to store the address of the current node and moves to the next node by assigning the address of the next node to the pointer variable.
* The loop continues until the pointer variable is not equal to null, at which point the last node has been visited and the algorithm terminates.

**Time and Space Complexity of Traversal**

* Time complexity: O(n), where n is the number of nodes in the linked list.
* Space complexity: O(n), as the algorithm requires memory to store the linked list.

**Search Operation**

* The search operation finds an element in the linked list by scanning the list starting from the first node until the element is found or the last node is reached.
* The algorithm uses a function that takes the address of the first node and checks if the element is present in each node until the element is found or the last node is reached.

**Time Complexity of Search Operation**

* Best case: O(1), when the element is found in the first node.
* Average case: O(n), as the algorithm scans all nodes in the list with equal probability.
* Worst case: O(n), when the element is found in the last node.

**Conclusion**

In conclusion, singly linked lists are data structures that allow efficient insertion and deletion of elements at arbitrary positions. The traversal operation visits each node in the list, and the search operation finds an element in the list. Understanding the time and space complexity of these operations is crucial for efficient implementation and optimization.

---

# OPERATIONS-ON-LINKED-LIST-II-INSERT

**Insertion Operation in a Single Linked List**

**Introduction**

A linked list is a data structure where each element, called a node, is a separate object. Each node has two parts: the data (information) and the link to the next node. Insertion operations are essential in a linked list, allowing new nodes to be added to the list. This note discusses the insertion operation in a single linked list.

**Insertion at the First Position**

Inserting a new node at the first position involves three steps:

1. **Create a new node**: Allocate memory for a new node using `malloc` and store the new value in the node.
2. **Connect the new node**: Store the address of the first node in the existing linked list in the `next` field of the new node.
3. **Update the head pointer**: Assign the address of the new node to the `head` pointer.

**Example Code (Python)**
```python
def insert_at_first(head, new_node):
    new_node.next = head
    head = new_node
    return head
```
**Time Complexity:** O(1)
**Space Complexity:** O(1)

**Insertion at the Last Position**

Inserting a new node at the last position involves three steps:

1. **Create a new node**: Allocate memory for a new node using `malloc` and store the new value in the node.
2. **Scan the linked list**: Traverse the linked list to find the last node.
3. **Connect the new node**: Store the address of the new node in the `next` field of the last node.

**Example Code (Python)**
```python
def insert_at_last(head, new_node):
    current = head
    while current.next is not None:
        current = current.next
    current.next = new_node
    return head
```
**Time Complexity:** O(n)
**Space Complexity:** O(1)

**Insertion at Any Position**

Inserting a new node at any position involves three steps:

1. **Create a new node**: Allocate memory for a new node using `malloc` and store the new value in the node.
2. **Scan the linked list**: Traverse the linked list to find the node before the insertion position.
3. **Connect the new node**: Store the address of the new node in the `next` field of the node before the insertion position.

**Example Code (Python)**
```python
def insert_at_position(head, new_node, position):
    current = head
    for _ in range(position - 1):
        current = current.next
    new_node.next = current.next
    current.next = new_node
    return head
```
**Time Complexity:** O(n)
**Space Complexity:** O(1)

**Conclusion**

This note has discussed the insertion operation in a single linked list, including insertion at the first position, last position, and any position. The time and space complexities for each operation have been analyzed. The examples provided illustrate the insertion operations using Python code snippets.

---

# OPERATIONS-ON-LINKED-LIST-III-DELETE

**Deleting Nodes in a Linked List**

**Introduction**

Deleting nodes in a linked list is a crucial operation in many applications. In this session, we will discuss three different scenarios for deleting nodes: deleting the first node, deleting the last node, and deleting a node at any position.

**Deleting the First Node**

Deleting the first node in a linked list is a simple operation. We need to update the head pointer to point to the next node. Here is a Python code snippet to illustrate this:

```
def delete_first_node(head):
    if head is None:
        return None
    head = head.next
    return head
```

The time complexity of this algorithm is O(1) because we are visiting only one node. The space complexity is O(1) because we are not using any additional space.

**Deleting the Last Node**

Deleting the last node in a linked list requires us to traverse the list to find the node before the last node. Here is a Python code snippet to illustrate this:

```
def delete_last_node(head):
    if head is None:
        return None
    current = head
    while current.next:
        previous = current
        current = current.next
    previous.next = None
    return head
```

The time complexity of this algorithm is O(n) because we need to traverse the entire list. The space complexity is O(1) because we are not using any additional space.

**Deleting a Node at Any Position**

Deleting a node at any position in a linked list requires us to traverse the list to find the node before the position and update the next pointer of the previous node. Here is a Python code snippet to illustrate this:

```
def delete_node_at_position(head, position):
    if head is None:
        return None
    current = head
    previous = None
    for _ in range(position - 1):
        previous = current
        current = current.next
    previous.next = current.next
    return head
```

The time complexity of this algorithm is O(n) because we need to traverse the entire list. The space complexity is O(1) because we are not using any additional space.

**Conclusion**

In this session, we have discussed three different scenarios for deleting nodes in a linked list: deleting the first node, deleting the last node, and deleting a node at any position. We have also provided Python code snippets to illustrate each scenario. The time and space complexities of each algorithm have been discussed.

---

# DOUBLY-LINKED-LIST

Here are the comprehensive notes based on the provided transcript:

**Introduction**

A doubly linked list is a linear data structure where each node maintains a reference to the previous node in addition to the next node. This allows for traversal in both forward and backward directions.

**Properties of a Doubly Linked List**

* A doubly linked list is a linear data structure, meaning nodes are arranged in a sequence.
* It is also a sequential data structure, requiring that before visiting a node, all nodes preceding it must be visited.
* Unlike singly linked lists, doubly linked lists can be traversed in both forward and backward directions.

**Implementation of a Doubly Linked List**

* Nodes in a doubly linked list maintain two pointers: one pointing to the next node (next field) and another pointing to the previous node (previous field).
* The head and tail pointers are used to traverse the list in both forward and backward directions.
* Dynamic memory allocation is more efficient for implementing doubly linked lists.

**Example of Creating a Node in a Doubly Linked List**

* A node in a doubly linked list is defined using a structure with three members: information field, next field, and previous field.
* The head and tail pointers are used to traverse the list in both forward and backward directions.
* Creating a node involves assigning values to the information field and previous field, and linking the node to the previous node.

**Example of Creating a Toy Doubly Linked List**

* The example demonstrates creating a doubly linked list with three nodes, assigning values to the information field, and linking the nodes to each other.
* The head and tail pointers are used to traverse the list in both forward and backward directions.

**Summary**

In conclusion, a doubly linked list is a linear data structure that allows for traversal in both forward and backward directions. It is implemented using nodes that maintain two pointers, one pointing to the next node and another pointing to the previous node. Dynamic memory allocation is more efficient for implementing doubly linked lists. The example demonstrates creating a doubly linked list with three nodes and traversing the list in both forward and backward directions.

---

# INSERTION-OPERATION-IN-DOUBLY-LINKED-LIST-PART-I

- The operations that can be performed on a doubly linked list are similar to those of a singly linked list, including create, insert, delete, search, and traversal functions.
- Three possible scenarios for insert function: insert at first, insert at last, insert at any position.
- Three possible scenarios for delete function: delete the first node, delete the last node, delete a node at any position.
- Other operations include search and traversal of the list.
- Time and space complexity are discussed for each operation.
- Detailed explanation and example of how to insert a node as the first node in a doubly linked list.
- Detailed explanation and example of how to insert a node as the last node in a doubly linked list.
- Time complexity for inserting a node at the first location is order of one or theta of one.
- Time complexity for inserting a node at the last location is also order of one.
- Space complexity for all operations is order of n.

Summary:
- Doubly linked lists have similar operations as singly linked lists, including create, insert, delete, search, and traversal functions.
- Inserting a node as the first or last node can be done in constant time, while the space complexity remains order of n.
- The use of pointer variables such as head and tail can help reduce time complexity for insert operations.

---

# INSERTION-OPERATION-IN-DOUBLY-LINKED-LIST-PART-II

**Inserting a Node at Any Position in a Linked List**

**Introduction**

In a linked list, inserting a node at any position can be challenging when we don't have the address of the first node and the last node. In this scenario, we need to traverse the list from the first node or the last node to find the position where we want to insert the new node.

**Scanning the List**

There are three possible cases when inserting a node at any position:

1. **Case 1: Scanning from the First Node**
If the position is less than or equal to half the number of nodes in the list, we can scan the list from the first node.
2. **Case 2: Scanning from the Last Node**
If the position is greater than or equal to half the number of nodes in the list, we can scan the list from the last node backward.
3. **Case 3: Simultaneous Scanning**
In this case, we can scan the list simultaneously from the first node forward and the last node backward to find the position where we want to insert the new node.

**Algorithm**

The algorithm for inserting a node at any position in a linked list involves the following steps:

1. Create a new node and assign it to a pointer variable.
2. Initialize two pointers, `head_current` and `tail_current`, to scan the list simultaneously from the first node forward and the last node backward.
3. Count the number of nodes scanned and update the `head_current` and `tail_current` pointers accordingly.
4. When the position is found, establish the required connections between the new node and the existing nodes.

**Code Snippet**
```python
def insert_node(head, tail, position, value):
    # Create a new node
    new_node = Node(value)
    
    # Initialize pointers
    head_current = head
    tail_current = tail
    
    # Simultaneously scan the list from the first node forward and the last node backward
    while True:
        # Update pointers
        head_current = head_current.next
        tail_current = tail_current.previous
        
        # Count the number of nodes scanned
        count += 1
        
        # Check if the position is reached
        if count == position:
            # Establish connections
            if position <= len(head):
                new_node.next = head_current.next
                head_current.next = new_node
            else:
                new_node.previous = tail_current.previous
                tail_current.previous = new_node
            break
    
    return head
```
**Time Complexity**

The time complexity of this algorithm is O(n), where n is the number of nodes in the list. This is because we need to scan the list at most up to the middle nodes.

**Space Complexity**

The space complexity of this algorithm is O(1), as we only use a few extra variables to store the pointers and the count of nodes scanned.

---

# DELETE-OPERATION-IN-DOUBLY-LINKED-LIST

**Deleting a Node in a Doubly Linked List**

Deleting a node in a doubly linked list involves three possible scenarios: deleting the first node, deleting the last node, and deleting a node at any position.

**Deleting the First Node**

Deleting the first node involves updating the head pointer to point to the second node and updating the previous field of the second node to null. This can be done in constant time, with a time complexity of O(1) and a space complexity of O(n).

**Deleting the Last Node**

Deleting the last node involves assigning null to the next field of the last node. This can be done in constant time, with a time complexity of O(1) and a space complexity of O(n).

**Deleting a Node at Any Position**

Deleting a node at any position involves scanning the list simultaneously from the first node forward and the last node backward. This can be done using two pointer variables, one for scanning forward and another for scanning backward. The node to be deleted is found by scanning the list, and then the necessary connections are updated to delete the node. This can be done in time complexity of O(n/2) and a space complexity of O(n).

**Code Snippet**

Here is a Python code snippet to demonstrate deleting a node at any position:
```
def delete_node_at_position(head, position):
    # Initialize head current and tail current pointers
    head_current = head
    tail_current = head

    # Initialize count to 1
    count = 1

    # Scan the list simultaneously from the first node forward and the last node backward
    while head_current and tail_current:
        # Move forward and backward pointers
        head_current = head_current.next
        tail_current = tail_current.previous

        # Increment count
        count += 1

        # Check if the position is reached
        if count == position:
            # Update necessary connections to delete the node
            head_current.next = head_current.next.next
            tail_current.next = tail_current.next.previous

            # Free the space consumed by the deleted node
            # (not shown in the code snippet)

            # Return the updated head
            return head_current

    # Return the original head if the position is out of range
    return head
```
**Summary**

In conclusion, deleting a node in a doubly linked list involves three possible scenarios: deleting the first node, deleting the last node, and deleting a node at any position. The time complexity of deleting the first node is O(1), the time complexity of deleting the last node is also O(1), and the time complexity of deleting a node at any position is O(n/2). The space complexity of all three scenarios is O(n).

---

# CIRCULAR-LINKED-LIST

**Circular Linked List**

A circular linked list is a type of linked list where the last node points to the first node, forming a circular connection. This allows for efficient insertion and deletion of nodes, as well as traversal of the list.

**Advantages**

* Any node in the list can be used as a starting point for traversal.
* Circular connections enable efficient insertion and deletion of nodes.
* Traversal can start from any node in the list.

**Implementation**

* Define a node structure with attributes for data and next node.
* Create a circular linked list by connecting the last node to the first node.
* Implement insertion and deletion operations by maintaining the circular connections.

**Insertion**

* Insert a new node by updating the next node attribute of the previous node and the previous node attribute of the new node.
* Update the circular connections to maintain the circular structure.

**Deletion**

* Delete a node by updating the next node attribute of the previous node and the previous node attribute of the current node.
* Update the circular connections to maintain the circular structure.

**Traversal**

* Start traversal from any node in the list.
* Use a while loop to traverse the list until the node points to the starting node again.

**Example Code**

```
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

def insert(node, data):
    new_node = Node(data)
    new_node.next = node.next
    node.next = new_node

def delete(node):
    node.next = node.next.next

def traverse(node):
    while node:
        print(node.data)
        node = node.next
        if node == node_start:
            break

# Example usage
node_start = Node(1)
node_start.next = Node(2)
node_start.next.next = Node(3)
insert(node_start, 4)
delete(node_start.next)
traverse(node_start)
```

**Summary**

Circular linked lists offer efficient insertion and deletion of nodes, as well as traversal starting from any node in the list. The implementation involves defining a node structure, creating a circular linked list, and implementing insertion, deletion, and traversal operations. The provided example code demonstrates the usage of circular linked lists in Python.

---

# HEADED-LINKED-LIST

- Introduction:
  - The speaker discusses the implementation of a linked list using a dedicated head node, which simplifies the process and allows for uniform treatment across different implementations.

- Single Linked List with Dedicated Head Node:
  - Creation of a dummy node called the header node.
  - The head pointer always points to the header node, which serves as the first node in the list.
  - Insertion of a new node as the first node without modifying the head pointer.
  - Creation of an empty linked list using the header node.

- Operations in Different Types of Linked Lists:
  - The concept of a dedicated head node can be applied to single linked lists, circular linked lists, and double linked lists.
  - Illustration of the implementation in each type of linked list, with a focus on the uniform treatment of the head node.

- Summary:
  - The use of a dedicated head node simplifies the implementation of linked lists and ensures uniform treatment across different types of linked lists.
  - The header node serves as the first node in the list and allows for consistent operations without modifying the head pointer.

---

