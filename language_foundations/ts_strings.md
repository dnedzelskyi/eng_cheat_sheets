[Home](../index.md) > TypeScript > [Strings](./ts_strings.md)

# TypeScrip | Strings

## Basics

```typescript

```

## Other

_Check if alphanumeric._

```typescript
// Using RegEx.
function isAlphanumeric(char: string): boolean {
  const alphanumericRegex = /^[a-zA-Z0-9]$/;
  return alphanumericRegex.test(char);
}

// Using Unicode Character Codes.
function isAlphanumeric(char: string): boolean {
  const charCode = char.charCodeAt(0);

  // Check numbers, u-case letters, l-case letters
  return (
    (charCode >= 48 && charCode <= 57) ||
    (charCode >= 65 && charCode <= 90) ||
    (charCode >= 97 && charCode <= 122)
  );
}
```
