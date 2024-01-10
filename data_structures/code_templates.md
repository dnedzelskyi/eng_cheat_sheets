[Home](../index.md) > Data Structures > [Code Templates](./code_templates.md)

# Data Structures | Code Templates

## Partitioning by Pivot

```typescript
/**
 * List partitioning (weak sorting) by pivot value.
 *
 * @param {T} pivot - partition value.
 * @param {T[]} list - List of vales.
 * @param {number} start - start index of sub-array.
 * @param {number} end - end index of sub-array.
 *
 * @returns {number} partition index.
 */
function partition<T>(pivot: T, list: T[], start: number, end: number): number {
  let m = start;

  for (let i = start; i < end; i++) {
    // Compare to pivot and swap if needed.
    if (list[i] <= pivot) {
      [list[m], list[i]] = [list[i], list[m]];
      m = m + 1;
    }
  }

  return m;
}

/* :: Examples ::

Input array: [2,1,2,2,1,1]
Partition by 1:
Partitioned array: [1,1,1,2,2,2]
Pivot index: 3

Input array: [1,0,0,2,2,0,1,0]
Partition by 0:
Partitioned array: [0,0,0,0,2,1,1,2]
Pivot index: 4

*/
```

## Partitioning by multiple custom conditions.

```typescript
/**
 * List partitioning (weak sorting) by multiple conditions.
 *
 * @param {((val: T) => boolean)[]} conditions - partition conditions.
 * @param {T[]} list - list of vales.
 * @param {number} start - start index of sub- array.
 * @param {number} end - end index of sub-array.
 *
 * @returns {number[]} Partition indexes for each conditions.
 */
function partition<T>(
  conditions: ((val: T) => boolean)[],
  list: T[],
  start: number,
  end: number,
): number[] {
  if (!conditions.length) {
    return [];
  }

  // Create pointers for each condition.
  const pointers = new Array(conditions.length).fill(start);

  // Loop through all condition.
  for (let i = 0; i < conditions.length; i++) {
    // Start from where the last pointer stopped.
    const jStart = i > 0 ? pointers[i - 1] : start;
    pointers[i] = jStart;

    // Sort list according to condition.
    for (let j = jStart; j < end; j++) {
      const value = list[j];
      if (conditions[i](value)) {
        [list[j], list[pointers[i]]] = [list[pointers[i]], list[j]];
        pointers[i] = pointers[i] + 1;
      }
    }
  }

  // Return indexes for each partition.
  return pointers;

  /* :: Examples ::

Input array: [2,0,2,1,1,0]
Partition by 0, 1, and 2:
Partitioned array: [0,0,1,1,2,2]
Pivot index: 2,4,6

Input array: [2,0,2,0,3,1,1,0,3,2]
Partition by 3, 2, 1, and 0:
Partitioned array: [3,3,2,2,2,1,1,0,0,0]
Pivot index: 2,5,7,10

*/
}
```

## Heap methods.

### Comparison function

```typescript
/**
 * A function type representing a priority order comparison function.
 *
 * @template T - Heap value type.
 *
 * @param {T} firstNodeValue - The value of the first node.
 * @param {T} secondNodeValue - The value of the second node.
 * @returns {boolean} Returns 'true' if firstNodeValue > secondNodeValue, otherwise 'false'.
 */
type PriorityOrderFunction<T> = (
  firstNodeValue: T,
  secondNodeValue: T,
) => boolean;
```

### HeapifyDown

```typescript
/**
 * Push node down until it will be placed in the right position in the heap according to the priority order.
 *
 * @template T - Heap value type.
 *
 * @param {T} i - Node index.
 * @param {T[]} heap - Array representation of the heap.
 * @param {PriorityOrderFunction} priorityOrder - Heap priority order function.
 */
function heapifyDown<T>(
  i: number,
  heap: T[],
  priorityOrder: PriorityOrderFunction<T>,
) {
  const { length: size } = heap;

  if (i < 0 || i >= size) {
    throw Error(`Invalid argument exception.`);
  }

  let keepHeapify = size > 0;
  while (keepHeapify) {
    // Set left and right child node indexes.
    const [l, r] = [2 * i + 1, 2 * i + 2];

    // Choose a node that satisfies the heap priority order the most.
    let p = i;
    if (l < size && !priorityOrder(heap[p], heap[l])) {
      p = l;
    }
    if (r < size && !priorityOrder(heap[p], heap[r])) {
      p = r;
    }

    // Stop, once the initial node is placed in the right position.
    if (p === i) {
      keepHeapify = false;
      continue;
    }

    // Push node down and proceed heapify.
    [heap[p], heap[i]] = [heap[i], heap[p]];
    i = p;
  }
}
```

### HeapifyUp

```typescript
/**
 * Push node up until it will be placed in the right position in the heap according to the priority order.
 *
 * @template T - Heap value type.
 *
 * @param {T} i - Node index.
 * @param {T[]} heap - Array representation of the heap.
 * @param {PriorityOrderFunction} priorityOrder - Heap priority order function.
 */
function heapifyUp<T>(
  i: number,
  heap: T[],
  priorityOrder: PriorityOrderFunction<T>,
) {
  if (i < 0 || i >= heap.length) {
    throw Error(`Invalid argument exception.`);
  }

  // Set initial parent node index.
  let p = Math.floor((i - 1) / 2);

  // Bubble node up while priority order won't be satisfied.
  while (i > 0 && !priorityOrder(heap[p], heap[i])) {
    [heap[p], heap[i]] = [heap[i], heap[p]];
    i = p;
    p = Math.floor((i - 1) / 2);
  }
}
```

### Poll / Extract Top

```typescript
/**
 * Extracts top element from the heap.
 *
 * @template T - Heap value type.
 *
 * @param {T[]} heap - Array representation of the heap.
 * @param {PriorityOrderFunction} priorityOrder - Heap priority order function.
 * @returns {T}
 */
function poll<T>(
  heap: T[],
  priorityOrder: PriorityOrderFunction<T>,
): T | undefined {
  // Return undefined when heap is empty.
  if (heap.length === 0) {
    return undefined;
  }

  // Take top node value, replace it with last node value and adjust heap priority order.
  const [firstNode, lastNode] = [heap[0], heap.pop()];
  if (firstNode !== lastNode) {
    heap[0] = lastNode!;
    heapifyDown(0, heap, priorityOrder);
  }

  return firstNode;
}
```
