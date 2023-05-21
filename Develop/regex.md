# Regex Tutorial 



## Summary

/^#?([a-f0-9]{6}|[a-f0-9]{3})$/

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Greedy and Lazy Match](#greedy-and-lazy-match)
- [Bracket Expressions](#bracket-expressions)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Boundaries](#boundaries)
- [Back-references](#back-references)
- [Look-ahead and Look-behind](#look-ahead-and-look-behind)
- [Sources](#sources)

## Regex Components

### Anchors

Anchors are regex components used to specify the position of a match within the text. The ^ character indicates a string begins with the following character. The $ anchor indicates the string ense with the character that precedes it. 

### Quantifiers

Quantifiers specify how many times a certain character or group should occur. In the context of hex values, you can use quantifiers to specify the length of the hex string.

/^#?([a-f0-9]{6}|[a-f0-9]{3})$/

The {6} and {3} act as quantifiers here

### Greedy and Lazy Match

Quantifiers are inherently greedy, meaning they match as many occurrences of particular patterns as possible, but uantifiers can be made lazy by adding the ? symbol after it, meaning it will match as few occurrences as possible.

### Bracket Expressions

Anything inside a set of square brackets ([]) represents a range of characters that we want to match.

/^#?([a-f0-9]{6}|[a-f0-9]{3})$/

In the Hex Value regex it first captures 6 hex digits then moves on to the next 3 

### OR Operator (|)

Bracket expression does not require the string to meet the pattern requirements in the regex, but adding the OR operator forces it to do so. 

Example: ^#([0-9A-Fa-f]{3}|[0-9A-Fa-f]{6})$

([0-9A-Fa-f]{3}|[0-9A-Fa-f]{6}) creates a capturing group with two alternatives separated by the OR operator |.

### Character Classes

A character class in a regex defines a set of characters, any one of which can occur in an input string to fulfill a match. Bracket expressions, including positive and negative character groups, are considered character classes.

### Flags

Flags are optional modifiers that can be added to a regular expression pattern to change its behavior. 

Here are the most common flags: 

g—Global search: the regex should be tested against all possible matches in a string.

i—Case-insensitive search: case should be ignored while attempting a match in a string

m—Multi-line search: a multi-line input string should be treated as multiple lines

Example: (i)^#[0-9A-F]{6}$ 

Making the regex for a Hex Value case insensitive might be useful since they are not case sensitive 

### Grouping and Capturing

Grouping and capturing allow you to create logical units within a regular expression and capture specific parts of the matched text. In the context of hex values, you can use capturing groups to extract individual components, such as the red, green, and blue values of a color.

Example: ^#([0-9A-F]{2})([0-9A-F]{2})([0-9A-F]{2})$

([0-9A-F]{2}) creates a capturing group that matches and captures two hex digits, representing a color component.
^#([0-9A-F]{2})([0-9A-F]{2})([0-9A-F]{2})$ matches a six-digit hex value starting with '#', capturing three color components.

### Boundaries

Boundaries are used to specify the positions in the text where a match should occur. For hex values, you can use word boundaries \b to ensure that the hex value is not part of a longer word.

Example: /\b([0-9A-Fa-f]{6})\b/g

### Back-references

Back-references allow you to refer back to previously captured groups within the regex pattern. 

Example: <^#?([a-f0-9]{6}|[a-f0-9]{3})$>

### Look-ahead and Look-behind

Look-ahead and look-behind assertions allow you to assert certain conditions without consuming characters. You can use look-ahead or look-behind to ensure that specific conditions are met without including them in the actual match.

## Author

This Git gist was created by Isaac Stofko. 

https://github.com/isaacsto

### Sources 

https://coding-boot-camp.github.io/full-stack/computer-science/regex-tutorial

https://www.regular-expressions.info/
