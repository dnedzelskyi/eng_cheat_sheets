[Home](../index.md) > Java > [Arrays](./java_arrays.md)

# Java | Arrays

## Basics

```java
// Crete array of 8 int elements.
// numbers = [0, 0, 0, 0, 0, 0, 0, 0]
int[] numbers = new int[8];

// Create array of 5 Strings.
// labels = [null, null, null, null, null]
var labels = new String[5];

// Create and initialize at once.
// flags = [true, true, false]
// letters = [A, B, C]
boolean[] flags = {true, true, false};
var letters = new char[]{'A', 'B', 'C'};

// Assign value.
// [0, 5, 0, 0, 7, 0, 0, 0]
numbers[4] = 7;
numbers[1] = 5;

// Read value by index
// sum = 12
int sum = numbers[1] + numbers[4];
```

## Iterate

```java
// Iterate by index.
// labels = [I0, I1, I2, I3, I4]
for (int i = 0; i < labels.length; i++) {
    labels[i] = "I" + i;
}

// Iterate by values
// word = "ABC"
StringBuilder sb = new StringBuilder();
for (char letter : letters) {
    sb.append(letter);
}
String word = sb.toString();

// Iterate using while loop
// numbers = [1, 1, 1, 1, 7, 0, 0, 0]
int i = 0;
while (numbers[i] < 7) {
    numbers[i] = 1;
    i++;
}

// Iterate using do-while
// flags = [true, true, false]
// latestFlagValue = false
boolean latestFlagValue;
int k = 0;
do {
    latestFlagValue = flags[k];
    k++;
} while (k < flags.length);
```

## Big-O

| Operation       | Time Complexity        |
| --------------- | ---------------------- |
| Access by Index | O(1)                   |
| Insertion S-M-E | O(n)-O(n)-O(1)         |
| Deletion S-M-E  | O(n)-O(n)-O(1)         |
| Linear Search   | O(n)                   |
| Binary Search   | O(log n)               |
| Sorting         | O(n^2) or O(n\*log(n)) |
| Resize          | O(n)                   |
