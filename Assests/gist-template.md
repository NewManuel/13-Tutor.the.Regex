# Understanding Regular Expressions (Regex)

Regular expressions, often abbreviated as regex, are powerful tools for pattern matching and text manipulation. They allow you to define patterns to search for in strings, making them invaluable for tasks such as data validation, parsing, and text processing. In this tutorial, we will break down the components of a specific regular expression, explaining each part and providing examples to illustrate their usage.

## Summary

The regex we will be dissecting is `/^[\w-]+(\.[\w-]+)*@([\w-]+\.)+[a-zA-Z]{2,7}$/`. This regex is commonly used to validate email addresses. Let's explore each component in detail.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)

## Regex Components

### Anchors

Anchors are used to specify the position of the match within the string. In our regex, `^` and `$` are anchors. The `^` asserts the start of the line, while the `$` asserts the end of the line.

```javascript
/^[\w-]+(\.[\w-]+)*@([\w-]+\.)+[a-zA-Z]{2,7}$/
```

- `^`: Asserts the start of the line.
- `$`: Asserts the end of the line.

Examples:
- `example@email.com` - Matches because it starts and ends with the specified pattern.
- `test@example.com` - Does not match because it does not start with the specified pattern.

### Quantifiers

Quantifiers specify how many times a character or group can appear. In our regex, `+`, `*`, `{2,7}` are quantifiers.

```javascript
/^[\w-]+(\.[\w-]+)*@([\w-]+\.)+[a-zA-Z]{2,7}$/
```

- `+`: Matches the preceding element one or more times.
- `*`: Matches the preceding element zero or more times.
- `{2,7}`: Matches the preceding element between 2 and 7 times.

Examples:
- `user@example.com` - Matches because there is at least one character before the `@`.
- `@example.com` - Does not match because there are no characters before the `@`.

### Grouping Constructs

Grouping constructs are used to group parts of the regex together. In our regex, `(\.[\w-]+)*` and `([\w-]+\.)+` are grouping constructs.

```javascript
/^[\w-]+(\.[\w-]+)*@([\w-]+\.)+[a-zA-Z]{2,7}$/
```

- `(\.[\w-]+)*`: Groups the domain's parts together and matches zero or more occurrences.
- `([\w-]+\.)+`: Groups the domain and matches one or more occurrences.

Examples:
- `user@example.com` - Matches because the domain contains at least one dot.
- `user@example` - Does not match because there is no dot in the domain.

### Bracket Expressions

Bracket expressions define a character class, allowing matches with any character within the brackets. In our regex, `[\w-]` and `[a-zA-Z]` are bracket expressions.

```javascript
/^[\w-]+(\.[\w-]+)*@([\w-]+\.)+[a-zA-Z]{2,7}$/
```

- `[\w-]`: Matches any word character (alphanumeric or underscore) or hyphen.
- `[a-zA-Z]`: Matches any alphabetic character.

Examples:
- `user123@example.com` - Matches because it contains alphanumeric characters in the username.
- `user@example.com` - Matches because it contains alphabetic characters in the domain.

### Character Classes

Character classes match a single character from a set of characters. In our regex, `[a-zA-Z]` is a character class.

```javascript
/^[\w-]+(\.[\w-]+)*@([\w-]+\.)+[a-zA-Z]{2,7}$/
```

- `[a-zA-Z]`: Matches any alphabetic character, both lowercase and uppercase.

Examples:
- `example@example.com` - Matches because it contains only alphabetic characters in the top-level domain.
- `example@123.com` - Does not match because the top-level domain contains numeric characters.

### The OR Operator

The OR operator, represented by `|`, allows for alternatives within the regex pattern. Our regex does not use the OR operator.

## Author

This tutorial was written by Emmanuel Nwabueze https://github.com/NewManuel.
* GitHub Gist List:  https://gist.github.com/NewManuel
