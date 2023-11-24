
# Quick Regex tutorial for matching a Hex Value

In this gist I will give a quick synopsis on how a certain regular expression is used to match a Hex value

## Summary

/^#?([a-f0-9]{6}|[a-f0-9]{3})$/

The regex (regular expression) above is one that is used to match Hex values, and we be the one in discussion in this gist.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)
- [Flags](#flags)
- [Character Escapes](#character-escapes)

## Regex Components

### Anchors

Anchors in the regex world make sure that the regex matches a string at a certain place: that place is at the beginning, or end of the string, or end of a line, or on a word, or non-word boundary.

/^#?([a-f0-9]{6}|[a-f0-9]{3})$/

Beginning anchor: ^
Ending anchor: $

Everything in-between those two anchors is what the regex will be searching for.

https://launchschool.com/books/regex/read/anchors

### Quantifiers

Quantifiers control the characters repitition in order to help define the flexibility of the match. It does this by specifying how many times a certain character or group of characters should appear within the input string.

Code Snipet: /^#?

In this case one quantifier is `?`, and it is used to show that something is optional. So the `#?` is dictating that `#` is optional to show up in the beginning of the expression.

Code Snipet: [a-f0-9]{6}
Code Snipet: [a-f0-9]{3}

There is also `{}` as a quantifier. The number within the `{}` tells us that the string before hand must be repeated that many times. If left empty the string would repeat as many occurances of the pattern as possible. If there was a `?` in the `{}` then the string would repeat as few times as possible. In our case the first string will be repeated 6 times and the secong string will be repeated 3 times.

https://medium.com/@NALSengineering/regular-expression-for-dummies-25e5c83c72f0#:~:text=In%20Regex%2C%20a%20%E2%80%9Cquantifier%E2%80%9D,the%20flexibility%20of%20a%20match.

### Grouping Constructs

Code Snipet: ([a-f0-9]{6}|[a-f0-9]{3})

Grouping constructs which are shown  by `()` keeps the regular expression between them, by doing so it treats many characters as on single unit as an array. In this case the expression that is being grouped is an bracket expression whose details are explained below.

https://learn.microsoft.com/en-us/dotnet/standard/base-types/grouping-constructs-in-regular-expressions

### Bracket Expressions

Code Snipet: [a-f0-9]

A bracket expression is a certain pattern of characters that is enclosed by `[]`. The hyphen is used to describe a set or range of available characters. In this case our bracket expression shows matching a string that has any lowercase letter `a` through `f` and any integer `0` through `9`.

https://pubs.opengroup.org/onlinepubs/9699919799/basedefs/V1_chap09.html#:~:text=A%20bracket%20expression%20is%20either,character%20classes%2C%20or%20range%20expressions.

### Character Classes

Code Snipet: [a-f0-9]

Character class is a set of characters that are enclosed within square brackets, and specifies that the characters will match only a single character. In this case our character class is made up of any lowercase letter a-f or any integer 0-9.

https://docs.oracle.com/javase/tutorial/essential/regex/char_classes.html#:~:text=In%20the%20context%20of%20regular,from%20a%20given%20input%20string.

### The OR Operator

Code Snipet: ([a-f0-9]{6}|[a-f0-9]{3})

The OR operator is shown by `|` which is saying it will match either the expression before or after the `|`. In this case the OR operator is telling us that the regex is looking for either a 6 character value or a 3 character value.

https://stackoverflow.com/questions/8020848/how-is-the-and-or-operator-represented-as-in-regular-expressions

### Flags

A flag is an optional parameter that changes the way that the regex will execute its search. In this case our flag will be `m` because our regex starts with a `^` and ends with a `$`. Which means it will be a multiline flag causing the string to be looked at as a sequence of multiple lines to match the beginning and the ending of each line.

https://www.codeguage.com/courses/regexp/flags

### Character Escapes

A character escape is a syntax that represents a character that might not easily be represented in its literal form.

https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Regular_expressions/Character_escape

## Author
Ranil Dissanayaka
https://github.com/RanilSD
