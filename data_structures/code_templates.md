[Home](../index.md) > Data Structures > [Big-O](./code_templates.md)

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
