[Home](../index.md) > Data Structures > [Big-O](./big_o.md)

# Data Structures | Big-O

## Lists and Arrays.

| Name     | Access            | Search | Insert              | Delete               |
| ------------------ | ----------------- | ------ | ------------------- | -------------------- |
| Dynamic Array      | O(1) - by index   | O(n)   | O(n) - O(n) - O(1)  | O(n) - O(n) - O(1)   |
| Linked List        | O(n)              | O(n)   | O(1) - O(n) - O(n)  | O(1) - O(n) - O(n)   |
| Doubly Linked List | O(n)              | O(n)   | O(1) - O(n) - O(1)  | O(1) - O(n) - O(1)   |
| Stack              | O(1) - only last  | ...    | O(1) - push on top  | O(1) - pop top       |
| Queue              | O(1) - only first | ...    | O(1) - enqueue back | O(1) - dequeue front |

## Min/Max Heap.
| Operation          | Time Complexity | Space Complexity |
|--------------------|-----------------|------------------|
| Create             | O(N)            | O(N)             |
| Insert element     | O(logN)         | O(1)             |
| Get top element    | O(1)            | O(1)             |
| Delete top element | O(logN)         | O(1)             |
| Get size           | O(1)            | O(1)             |
