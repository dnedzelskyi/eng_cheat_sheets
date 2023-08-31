[Home](../index.md) > Java > [Strings](./java_strings.md)

# Java | Strings

## Basics

```Java
// Declaration
String sentence = " I love Java!!! ";
var jumbledSentence = "What'sUp?";

// Text blocks
String multiLineText = """
        Hi <Name>,

        <Add your message here>

        Thank you.
        """;

// Length
int textLength = multiLineText.length();

// Format
String errorMessage =  String.format("Error %d", errorId);
```

## Methods

```java
String text = " Time is running slow  ";

// Trim
// trimmed = "Time is running slow"
String trimmed = text.trim();

// Split
// words = ["Time", "is", "running", "slow"]
String[] words = trimmed.split("\\s+");
```

## StringBuilder

```java
// Basic usage.
var builder = new StringBuilder();
builder.append("Product list:");

builder.append(System.lineSeparator());

builder.append("- Bread\n");
builder.append(String.format("- Eggs (%d)%n", 12));
builder.append("- Milk");

System.out.println("Text length: " + builder.length());
System.out.println("Text:");
System.out.println(builder.toString());
// Output:
// Text length: 42
// Text:
// Product list:
// - Bread
// - Eggs (12)
// - Milk


// Useful methods
var builder = new StringBuilder("HelloWorld");

String reversed = builder.reverse().toString();
char letter = builder.charAt(2);
builder.insert(5, ' ');
```

## Formatting

```java
// %s: String
System.out.println(String.format("Name: %s", "John"));
// Name: John

// %d: Decimal Integer
System.out.println(String.format("Age: %d", 25));
// Age: 25

// %f: Floating-Point Number
System.out.println(String.format("GPA: %.2f", 3.75));
// GPA: 3.75

// %c: Character
System.out.println(String.format("First letter: %c", 'A'));
// First letter: A

// %b: Boolean
System.out.println(String.format("Is Java fun? %b", true));
// Is Java fun? true

// %x or %X: Hexadecimal
System.out.println(String.format("Hex value: %x", 255));
// Hex value: ff

// %o: Octal
System.out.println(String.format("Octal value: %o", 63));
// Octal value: 77

// %e or %E: Exponential
System.out.println(String.format("Scientific notation: %e", 123.6789));
// Scientific notation: 1.236789e+02

// %t: Date/Time
System.out.println(String.format("Date: %tD", new Date()));
// Date: 08/20/23

// %n: Newline
System.out.println(String.format("Line 1%nLine 2"));
// Line 1
// Line 2

// %%: Percent
System.out.println(String.format("Discount: 20%%"));
// Discount: 20%
```
