[Home](../index.md) > Java > [Lists](./java_lists.md)

# Java | Lists

**List** - represents an ordered, dynamically sized collection of elements, where each element can be accessed by an index. It can be of any data type, including objects or primitive data types. It can contain duplicate elements.

## Basics

```Java
// Create. Out: []
final List<String> names = new ArrayList<>();

// Create + Init. Out: numbers = [1, 2, 3], grades = [A, B, C]
List<Integer> numbers = new ArrayList<>(List.of(1, 2, 3));
List<Character> grades = new ArrayList<>(Arrays.asList('A', 'B', 'C'));

// Add elements. Out: [Sam, Jane, John, Emily]
names.add("Sam");
names.add("Jane");
names.add("John");
names.add("Emily");

// Get size. Out: 4
names.size();

// Insert at index. Out: [Sam, Mery, Jane, John, Emily]
names.add(1, "Mery");

// Update by index. Out: [Sam, Mery, Jane, John, Eva]
names.set(4, "Eva");

// Retrieve by index. Out: "Sam"
names.get(0);

// Remove first by element. Out: [Sam, Mery, John, Eva]
names.remove("Jane");

// Remove by index. Out: [Sam, Mery, Eva]
names.remove(2);

// Find first index by element. Out: 'Eva' = 2, 'John' = -1
names.indexOf("Eva");
names.indexOf("John");
```

## Iterate

```java
// Loop with an index.
for (int i = 0; i < list.size(); i++) {
    String element = list.get(i);
    System.out.println(element);
}

// for-each loop
for (String element : list) {
    System.out.println(element);
}

// Iterator.
Iterator<String> iterator = list.iterator();
while (iterator.hasNext()) {
    String element = iterator.next();
    System.out.println(element);
}

// Using streams
list.stream().forEach(element -> System.out.println(element));

// ListIterator (allows to move forward and backward)
ListIterator<String> iterator = list.listIterator();

while (iterator.hasNext()) {
    String element = iterator.next();
    System.out.println(element);
}

while (iterator.hasPrevious()) {
    String element = iterator.previous();
    System.out.println(element);
}
```

## References

- Wikipedia > [List (abstract data type)](<https://en.wikipedia.org/wiki/List_(abstract_data_type)>)
- Wikipedia > [Linked list](https://en.wikipedia.org/wiki/Linked_list)
- Oracle. Java Docs > [java.util.List](https://docs.oracle.com/javase/8/docs/api/java/util/List.html)
