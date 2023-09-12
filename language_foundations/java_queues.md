[Home](../index.md) > Java > [Lists](./java_queues.md)

# Java | Queues

## Basics

```java
// Create. Out: []
Queue<String> messageQueue = new LinkedList<>();

// Create + Init. Out: [600, -200]
Queue<Integer> transactionQueue = new LinkedList<>(List.of(600, -200));

// Add element. Out: [Hi., Call me., Ok, I'll call you in 5 min., Thanks.]
messageQueue.add("Hi.");
messageQueue.addAll(List.of("Call me.", "Ok, I'll call you in 5 min."));
messageQueue.offer("Thanks.");

// Get Size. Out: Message queue - 4, Transaction queue - 2
messageQueue.size();
transactionQueue.size();

// Retrieve, but not remove, the head. Out: 600, Hi.
transactionQueue.element();
messageQueue.peek();

// Retrieve and remove head. Out: 600, Hi.
transactionQueue.remove();
messageQueue.poll();

// Remove node by value. Out: true, [Ok, I'll call you in 5 min., Thanks.]
messageQueue.remove("Call me.");

// Clear. Out: []
messageQueue.clear();
```

## Iterate

```java
// loop with poll()
while (!queue.isEmpty()) {
    String element = queue.poll();
    System.out.println(element);
}

// for-each loop
for (String element : queue) {
    System.out.println(element);
}

// Temporary queue
Queue<String> tempQueue = new LinkedList<>(queue);
while (!tempQueue.isEmpty()) {
    String element = tempQueue.poll();
    System.out.println(element);
}

// Using streams.
Stream<String> stream = queue.stream();
stream.forEach(element -> System.out.println(element));
```

## References

- Wikipedia > [Queue (abstract data type)](<https://en.wikipedia.org/wiki/Queue_(abstract_data_type)>)
- Oracle. Java Docs > [java.util.Queue](https://docs.oracle.com/javase/8/docs/api/java/util/Queue.html)
