[Home](../index.md) > Java > [Sets](./java_sets.md)

# Java | Sets

**Set** - is an unordered collection of unique elements.

## Basics

```java
// Create. Out: [].
Set<Integer> uniqueNumbers = new HashSet<>();

// Create with initial values. Out: [apricot, cherry, lemon].
Set<String> fruits = new HashSet<>(Arrays.asList(
  "apple",
  "apricot",
  "lemon"
));

// Get size. Out: 0, 3
uniqueNumbers.size();
fruits.size();

// Add element. Out: [11, 4]
uniqueNumbers.add(4);
uniqueNumbers.add(11);

// Check existence. Out: true, false
fruits.contains("apple");
uniqueNumbers.contains(21);

// Delete element: Out: [apricot, cherry]
fruits.remove("lemon")
```

## References

- Wikipedia > [Set (Abstract Data Type)](<https://en.wikipedia.org/wiki/Set_(abstract_data_type)>)
- Oracle. Java Docs > [java.util.Set](https://docs.oracle.com/javase/8/docs/api/java/util/Set.html)
