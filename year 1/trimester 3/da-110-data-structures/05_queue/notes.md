# QUEUE-DATA-STRUCTURE-AND-ITS-OPERATIONS

- Queue Data Structure
  - Linear and homogeneous data structure
  - First-in-first-out (FIFO) or last-in-last-out (LILO)
  - Elements are of the same data type

- Operations on Queue Data Structure
  - Enqueue: Inserting an element into the queue
  - Dequeue: Removing an element from the queue
  - Two pointers: Head (front) and Tail (rear)

- Implementation of Queues
  - Using Array
    - Python example:
      ```
      class Queue:
          def __init__(self):
              self.items = []

          def enqueue(self, item):
              self.items.append(item)

          def dequeue(self):
              return self.items.pop(0)
      ```

  - Using Linked List
    - Python example:
      ```
      class Node:
          def __init__(self, data):
              self.data = data
              self.next = None

      class Queue:
          def __init__(self):
              self.front = None
              self.rear = None

          def enqueue(self, item):
              new_node = Node(item)
              if self.rear is None:
                  self.front = self.rear = new_node
              else:
                  self.rear.next = new_node
                  self.rear = new_node

          def dequeue(self):
              if self.front is None:
                  return "Queue is Empty"
              temp = self.front
              self.front = temp.next
              if self.front is None:
                  self.rear = None
              return temp.data
      ```

- Application of Queue Data Structure
  - Examples: ATM queue, ticket counter queue, bank counter queue
  - First-in-first-out (FIFO) principle

- Common Operations on Queue
  - Enqueue: Insertion from the tail
  - Dequeue: Removal from the head
  - Supporting operations: isEmpty, isFull, front element, rear element

- Summary
  - Queue data structure is linear and follows FIFO or LILO principle.
  - It can be implemented using arrays or linked lists.
  - Common operations include enqueue, dequeue, and supporting operations.
  - Examples of queue applications include real-life scenarios like ATM and ticket counter queues.

---

# SCENARIO-1

- The transcript provides an in-depth discussion on implementing a queue data structure using an array data structure.
- It highlights the different types of queues such as circular queue, double-ended queue, monotonic queue, and priority queue, each with its own unique characteristics and applications.

Main Topics:
1. Implementing a Queue Using Array Data Structure
2. Scenario 1: Enqueue and Dequeue Operations
3. Limitations of Scenario 1
4. Proposed Implementation for Scenario 1
5. Summary and Conclusion

Implementing a Queue Using Array Data Structure:
- Queue data structure is commonly implemented using two data structures: array and linked list.
- The discussion focuses on implementing a queue using an array data structure, highlighting the key characteristics and operations involved.

Scenario 1: Enqueue and Dequeue Operations:
- The scenario outlines the process of performing enqueue and dequeue operations in a queue implemented using an array data structure.
- It defines the initial state of the queue, updates the tail pointer for enqueue operations, and updates the head pointer for dequeue operations.
- The limitations of this scenario are also discussed, such as the restriction on the maximum number of enqueue operations and the inability to perform further enqueue operations when the tail reaches the last index of the array.

Limitations of Scenario 1:
- The limitations of the first scenario are emphasized, including the restriction on the number of enqueue operations based on the allocated space and the inability to perform further enqueue operations when the tail reaches the last index of the array.

Proposed Implementation for Scenario 1:
- A proposed implementation for the first scenario is outlined, including the use of global variables, empty and isFull functions, and the logic for enqueue and dequeue operations.

Summary and Conclusion:
- The discussion provides a comprehensive overview of implementing a queue using an array data structure, highlighting the key considerations, operations, and limitations.
- It emphasizes the importance of defining the characteristics of the queue before implementation and acknowledges the limitations of the proposed scenario.
- Overall, the transcript offers valuable insights into the implementation of queue data structures and sets the stage for further exploration of different types of queues and their applications.

---

# SCENARIO-II

**Scenario 2: Limiting the Number of Enqueue Operations by Max**

**Introduction**

Scenario 2 addresses the problem of limiting the number of enqueue operations by max. The assumption is made that the first element will always be at the first index of the array, regardless of how many dequeue operations are performed.

**Initial State of the Queue**

The initial state of the queue is defined as follows: head is equal to minus one and tail is also equal to minus one. This represents an empty queue.

**Enqueue Operation**

When an enqueue operation is performed, the tail is incremented by one, just like in Scenario 1. This updates the tail pointer to point to the new element.

**Dequeue Operation**

When a dequeue operation is performed, the first element is removed, and all other elements in the queue move one position forward. This ensures that the first element is always at the first index of the array.

**Queue Full**

When the queue is full, the tail is equal to max minus one. This indicates that the queue is full and there is no more space available for new elements.

**Efficiency**

Scenario 2 is more memory-efficient than Scenario 1, as it does not waste space in the queue. However, it is less time-efficient, especially for dequeue operations.

**Time Complexity**

The time complexity of the enqueue operation is O(1) because it only requires updating the tail pointer. The time complexity of the dequeue operation is O(n) because it requires moving old elements in the queue one position forward.

**Implementation**

The scenario can be implemented using a program with three global variables: head pointer, tail pointer, and an array to store the queue elements. The program checks if the queue is empty (tail is equal to minus one) or full (tail is equal to max minus one). When an enqueue operation is performed, the tail pointer is updated, and the new element is stored. When a dequeue operation is performed, the old elements in the queue are moved one position forward.

**Summary**

Scenario 2 is a space-efficient solution for implementing a queue with a limited number of enqueue operations. It ensures that the first element is always at the first index of the array and does not waste space in the queue. However, it is less time-efficient, especially for dequeue operations.

---

# CIRCULAR-QUEUE

**Circular Queue Implementation**

**Introduction**

A circular queue is a data structure that uses a linear array to store elements. It has two pointers, the head and the tail, which indicate the position of the first and last elements in the queue. The queue is considered full when the tail pointer reaches the end of the array, and it is considered empty when the head and tail pointers are equal.

**Key Concepts**

* The circular queue uses a linear array to store elements.
* The head pointer points to the first element in the queue.
* The tail pointer points to the last element in the queue.
* The queue is considered full when the tail pointer reaches the end of the array.
* The queue is considered empty when the head and tail pointers are equal.

**Circular Queue Implementation**

The circular queue can be implemented using a linear array. The head and tail pointers are used to keep track of the position of the first and last elements in the queue.

**Example**

Here is an example of how to implement a circular queue using a linear array:
```
class CircularQueue:
    def __init__(self, max_size):
        self.max_size = max_size
        self.queue = [None] * max_size
        self.head = 0
        self.tail = 0
        self.num_elements = 0

    def enqueue(self, element):
        if self.num_elements == self.max_size:
            print("Queue is full")
            return
        self.queue[self.tail] = element
        self.tail = (self.tail + 1) % self.max_size
        self.num_elements += 1

    def dequeue(self):
        if self.num_elements == 0:
            print("Queue is empty")
            return
        element = self.queue[self.head]
        self.head = (self.head + 1) % self.max_size
        self.num_elements -= 1
        return element

    def is_full(self):
        return self.num_elements == self.max_size

    def is_empty(self):
        return self.num_elements == 0
```
**Example Usage**

Here is an example of how to use the circular queue:
```
queue = CircularQueue(5)
queue.enqueue(1)
queue.enqueue(2)
queue.enqueue(3)
print(queue.dequeue())  # Output: 1
print(queue.dequeue())  # Output: 2
print(queue.is_full())  # Output: True
print(queue.is_empty())  # Output: False
```
**Summary**

The circular queue is a data structure that uses a linear array to store elements. It has two pointers, the head and the tail, which indicate the position of the first and last elements in the queue. The queue is considered full when the tail pointer reaches the end of the array, and it is considered empty when the head and tail pointers are equal. The circular queue can be implemented using a linear array and can be used to implement a queue data structure.

---

# QUEUE-IMPLEMENTATION-USING-LINKED-LIST

- Introduction:
  - The session discusses the implementation of a queue using linked lists as compared to array data structures.
  - It highlights the ease of implementing a queue using linked lists and the different types of linked lists that can be used for this purpose.

- Implementing Queue Using Linked List:
  - Types of linked lists for implementing queue: singly linked list, doubly linked list, circular linked list.
  - Explanation of using a singly linked list for queue implementation.
  - Time complexity of enqueue and dequeue operations in different scenarios.
  - Use of doubly linked list and circular linked list for queue implementation.

- Time Complexity of Enqueue and Dequeue Operations:
  - Enqueue operation time complexity based on maintaining the address of the tail node.
  - Impact of maintaining the tail pointer on enqueue operation time complexity.
  - Enqueue and dequeue operations in different types of linked lists.

- Comparison with Array Data Structure:
  - Advantages of using linked lists for queue implementation.
  - Absence of conditions for queue full or empty in linked list implementation.
  - Assurance of queue full only when there is no space in RAM.

- Summary:
  - Linked lists, regardless of type, use insert as last node for enqueue operation and delete first node for dequeue operation.
  - Implementation of queue using linked lists is easier and does not require handling of queue full or empty conditions.
  - The choice of linked list type impacts the time complexity of enqueue and dequeue operations.

---

# DIFFERENT-TYPES-OF-QUEUES

- Introduction:
  - Different types of queues: queue, circular queue, double ended queue, priority queue.
  - Focus on double ended queue and priority queue.

- Double Ended Queue:
  - Allows enqueue and dequeue operations from both ends.
  - Basic operations: Push_Front, Push_Back, Pop_Front, Pop_Back, isEmpty, isFull, front element, back element.
  - Can be input restricted or output restricted.
  - Can be monotonic queue with elements in increasing or decreasing order.
  - Implementation example: visualization of inserting an element in a monotonic queue.

- Priority Queue:
  - Each element has an associated priority.
  - Enqueue in any order, dequeue based on priority.
  - Example: elements A, B, C with priorities 1, 2, 1 respectively.
  - Different ways of implementing priority queue, including using heap data structure.

- Summary:
  - Double ended queue allows operations from both ends, can be monotonic.
  - Priority queue assigns priorities to elements and dequeues based on priority.
  - Different implementations of priority queue, including using heap data structure.

---

# IMPLEMENT-STACK-USING-TWO-QUEUES

- Queue Data Structure Applications
  - System level and application level programs
  - Examples: process scheduling, memory management, queue management system, packet scheduling, job scheduling

- Simulating Stack using Queue Data Structures
  - Using two queues (Q_1 and Q_2)
  - Push operation simulation
    - Enqueue element into Q_2
    - Move elements from Q_1 to Q_2
    - Move elements from Q_2 to Q_1
    - Time complexity: O(n)
  - Pop operation simulation
    - Dequeue element from Q_1
    - Time complexity: O(1)
  - Algorithm summary for push and pop operations

- Example Illustration
  - Stack status: 6 (top), 3
  - Push operation: insert 5
    - Q_2: enqueue 5
    - Move elements from Q_1 to Q_2
    - Move elements from Q_2 to Q_1
  - Stack status after push operation
  - Pop operation: remove top element 5 from Q_1

- Summary
  - Queue data structure applications in various programs
  - Simulating stack using two queues
  - Push and pop operation simulations
  - Time complexity analysis for push and pop operations

- Conclusion
  - Queue data structures are versatile and can be used to simulate other data structures like stacks
  - Understanding the implementation and time complexity of operations is essential for efficient use of data structures.

---

# IMPLEMENTATION-OF-QUEUE-USING-TWO-STACKS

- Introduction:
  - The transcript discusses simulating a queue using two stacks, similar to simulating a stack using two queues.

- Simulating a Queue using Two Stacks:
  - Status of the queue: Two elements - 6 (front) and 3 (rear).
  - Oldest element maintained at the top of the stack to simulate dequeue operation.
  - Enqueue operation: Element 7 inserted and ordering maintained by moving elements between stacks.
    - Example: 
      ```python
      # Enqueue operation
      S1 = [6, 3]  # Stack 1
      S2 = []      # Stack 2
      # Move elements from S1 to S2
      # Push 7 to S2
      # Move elements from S2 to S1
      ```
  - Time complexity: Order of n due to the need for moving elements between stacks.

- Dequeue Operation:
  - Removing the first element from the queue, equivalent to a pop operation from Stack 1.
  - Simulated using the algorithm for moving elements between stacks.
  - Example:
    ```python
    # Dequeue operation
    S1 = [6, 3, 7]  # Stack 1
    S2 = []         # Stack 2
    # Move elements from S1 to S2
    # Pop operation from S1
    # Move elements from S2 to S1
    ```

- Time Complexity:
  - Enqueue and dequeue operations have a time complexity of order of n due to the need for moving elements between stacks.

- Summary:
  - The transcript explains the simulation of a queue using two stacks, with a focus on maintaining the order of elements and the time complexity of the operations.

By following these guidelines, the notes provide a comprehensive understanding of simulating a queue using two stacks, including examples and explanations of key points.

---

