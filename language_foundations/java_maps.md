[Home](../index.md) > Java > [Maps](./java_maps.md)

# Java | Maps

**Map** - represents a collection of key-value pairs where each key uniquely associated with a value. Allows quickly retrieve values based on their corresponding keys. The order of elements in Map is not guaranteed.

## Basics

```java
// Create. Out: {}
Map<String, Integer> userAge = new HashMap<>();

// Create + Init. Out: {80=B, 50=C, 20=D, 100=A}
Map<Integer, Character> scoreGrade = new HashMap<>(Map.of(
        100, 'A',
        80, 'B',
        50, 'C',
        20, 'D'
));

// Add pair. Out: {Eva=31, Cole=16, Alice=16, John=49, Mary=22}
userAge.put("Alice", 16);
userAge.putIfAbsent("John", 49);
userAge.putAll(Map.of(
        "Mary", 22,
        "Cole", 16,
        "Eva", 31
));

// Get value by key. Out: Cole - 16, 15 - !
userAge.get("Cole");
scoreGrade.getOrDefault(15, '!');

// Replace. Out: {Eva=31, Cole=25, Alice=19, John=49, Mary=22}
userAge.put("Alice", 19);
userAge.replace("Cole", 25);

// Remove. Out: {80=B, 50=C, 100=A}
scoreGrade.remove(20);
scoreGrade.remove(50, 'D');

// Check key or value. Out: Eva - true, D - false
userAge.containsKey("Eva");
scoreGrade.containsValue('D');

// Size. Out: userAge - 5, scoreGrade - 3
userAge.size();
scoreGrade.size();
```

## Iterate

```java
// Iterate key and value #1.
for (Map.Entry<String, Integer> item : userAge.entrySet()) {
    var key = item.getKey()
    var value = item.getValue())
}

// Iterate key and value #2.
userAge.forEach((key, value) ->  {
    System.out.printf("Name: %s Age: %d%n}", key, value);
});

// Iterate by key.
for (var score : scoreGrade.keySet()) {
    Character grade = scoreGrade.get(score);
    System.out.printf("Grade: %c Score: %d%n", grade, score);
}
```

## References

- Wikipedia > [Associative array](https://en.wikipedia.org/wiki/Associative_array)
- Wikipedia > [Hash table](https://en.wikipedia.org/wiki/Hash_table)
- Oracle. Java Docs > [java.util.Map](https://docs.oracle.com/javase/8/docs/api/java/util/Map.html)
