[Home](../index.md) > Java > [Basics](./java_basics.md)

# Java | Basics

## Primitive Types.

1. **`byte`** - Represents a signed 8-bit integer value.
1. **`short`** - Represents a signed 16-bit integer value.
1. **`int`** - Represents a signed 32-bit integer value.
1. **`long`** - Represents a signed 64-bit integer value.
1. **`float`** - Represents a single-precision 32-bit floating-point value.
1. **`double`** - Represents a double-precision 64-bit floating-point value.
1. **`char`** - Represents a single 16-bit Unicode character.
1. **`boolean`** - Represents a boolean value, which can be either true or false.

## Variables.
```java

// Local variable
int bufferSize = 74;

// Local constant
final String APP_NAME = 'Engineering Cheat Sheets';

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
