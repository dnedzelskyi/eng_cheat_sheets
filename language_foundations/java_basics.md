[Home](../index.md) > Java > [Basics](./java_basics.md)

# Java | Basics

## Primitive Types.

1. **`byte`** signed 8-bit integer value.
1. **`short`** signed 16-bit integer value.
1. **`int`** signed 32-bit integer value.
1. **`long`** signed 64-bit integer value.
1. **`float`** single-precision 32-bit floating-point value.
1. **`double`** double-precision 64-bit floating-point value.
1. **`char`** single 16-bit Unicode character.
1. **`boolean`** boolean value, which can be either true or false.

## Variables.

```java
// Local variable
int bufferSize = 74;

// Local constant
final String APP_NAME = "Engineering Cheat Sheets";

// Instance constant, variable.
public class User {
  final String[] GENDER_OPTIONS = {"Male", "Female"};

  String name;
  int age;
}

// Class constant and variable.
public class Scheduler {
  private static final EXECUTION_INTERVAL = 500;

  static boolean isRunning;
}
```

## Decision-making statements.

```java
// if-then
if (isLoaded || length > 0) {
  ...
}

// if-then-else
if (score < 40) {
    ...
} else if (65 < score && score < 70) {
    ...
} else {
    ...
}

// Switch
switch (grade) {
    case 'A':
        ...
        break;
    case 'B', 'C':
        ...
        break;
    ...
    default:
        ...
        break;
}

// Switch expressions
String message = switch (grade) {
    case 'A', 'B' -> "Amazing";
    case 'C' -> "Good";
    default -> {
        System.out.println("Oh NO !!!");
        yield "Bad";
    }
};

```

## Loop statements.

```java
// for loop
for (int i = 0; i < arr.length; i++) {
  ...
}

// while loop
while (i < arr.length) {
  ...
}

// do-while loop
do {
  ...
} while (keepRunning);
```
