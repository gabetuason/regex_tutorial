# Regex Tutorial Documentation: Matching an Email

Regex, short for regular expression, is a sequence of characters that specifies a search pattern. It's utilized in code or search algorithms to identify specific character patterns in a string, replace them or validate input. One of the main advantages of regular expressions is that it can simplify complex text processing tasks, making it possible to quickly and accurately extract information from large amounts of data. Regex is extensively used in web development, data analysis, and system administation, among other fields.

## Summary

In this tutorial, we will be primarily discussing Regex: Matching an Email, particularly viewing syntax, usages and examples. 

For starters, In matching an email address using regex, you can specify a pattern that consists of a sequence of characters before and after the "@" symbol, followed by a domain name and a top-level domain(TLD) (ex. domain123@email.com). Other TLDs include: `.org`, `.gov`, `.net`, `.co`, etc. The regular expression pattern as shown `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/` can be used to match most valid email addresses. This pattern specifies that the email address should start with one or more lowercase letters, numbers, underscore (), period (.), or hyphen (-), followed by the "@" symbol, then a sequence of one or more lowercase letters, numbers, or special characters such as period (.), underscore(), or hyphen (-) for the domain name, and finally, a top-level domain consisting of two to six letters or periods.


## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)
- [Boundaries](#boundaries)
- [Back-references](#back-references)
- [Look-ahead and Look-behind](#look-ahead-and-look-behind)

## Regex Components

As mentioned before, Regex can help in accurately validating whether an input string is a valid email address or not. We'll be using the following regex components to create a pattern for matching email addresses: `/^([a-z0-9_.-]+)@([\da-z.-]+).([a-z.]{2,6})$/`

To understand each component, we will describe each component with a description, that is accompanied by a code snippet and examples that fulfill the requirements.

### Anchors

In terms of the Anchors for the email matching string, anchors allow us to indicate the start and end of the search string. In the example of searching for an email address pattern, the symbols `^` and `$` act as anchors. The ^ symbol showcases the beginning of the search string for the email address pattern, while the $ symbol marks the end of the search string. Everything in between these two symbols serves as the characters we are searching for. In this case, the regex pattern ^([a-z0-9_.-]+)@([\da-z.-]+).([a-z.]{2,6}) uses these anchors to narrow down the search to a valid email address pattern.

Remember:
- `^` corresponds to the start pattern string
- `$` corresponds to the end pattern string 

### Quantifiers

In regular expressions, Quantifiers are applied to specify the number of occurrences of a character or a group of characters. It allows to match patterns that occur a certain number of times, or to specify a range of occurrences. In this case, The `+` quantifier means "one or more" and applies to the character class `[a-z0-9_.-]`, which matches one or more lowercase letters, digits, underscores, periods, or hyphens in the first section of the email address before the "@" symbol.

The `{2,6}` quantifier here means "between 2 and 6" and applies to the character class [a-z.], which matches 2 to 6 lowercase letters or periods in the top-level domain section of the email address (e.g., .com, .edu, .co.uk).

There are other quantifiers like 
- * (zero or more)
- ? (zero or one)
- {n} (exactly n)
- {n,m} (between n and m)
- {n,} (n or more)

### OR Operator

In our example for matching email, the regex pattern does not contain any OR operators.

For learning purposes, the OR operator is denoted by a vertical line character `|`. It is usually used to match either one pattern or another.
Example: `/(sedan|coupe|suv|pickup)/` This regex pattern will match any of the following car types: sedan, coupe, suv, or pickup.

### Character Classes

Character classes are used to define sets of characters that can be matched by the pattern.

For the character classes here, `[a-z0-9_.-]` is a character class that matches any lowercase letter, digit, period (.), underscore (_), or hyphen (-). In similarly fashion, the `[\da-z.-]` matches any digit, lowercase letter, period (.), or hyphen (-). [a-z\.] matches any lowercase letter or period (.), while {2,6} is a quantifier that specifies that the preceding character class (in this case, [a-z\.]) should match between 2 and 6 times.

### Flags

Flags is an optional parameter that you can use to modify behavior for searching.

Again, there are no flags specified for the given matching regex pattern (matching email) in our example. However, we can change how regular expressions behave in various ways. Like case-insensitive, global matching.

- `g` global matching
- `i` case-insensitive

- `/cars/g Makes sure all occurrences of cars match globally.`
- `/cars/i Matches all occurrences of cars regardless of case (e.g. Cars, CARS, cArs all match).`

There are more flag types, these are just the more common ones.

### Grouping and Capturing

Grouping and capturing in regular expressions are used to treat a set of characters as a single unit. In regular expressions, the grouping is denoted by the use of parentheses `( )`.

In the example of an email address pattern, we have three groups: the first group represents the user name, the second group represents the email domain name, and the third group represents the email extension. These groups are enclosed in parentheses to capture and group the characters together as a single unit.

- ([a-z0-9_\.-]+)
- ([\da-z\.-]+)
- ([a-z\.]{2,6})


### Bracket Expressions

Enclosed in square brackets, and the characters inside are the possible matches.

In the email regex pattern `/^([a-z0-9_.-]+)@([\da-z.-]+).([a-z.]{2,6})$/`, the following bracket expressions are used:

- [a-z0-9_.-]: Matches any lowercase letter, digit, underscore, period, or hyphen.
- [\da-z.-]: Matches any digit, lowercase letter, period, or hyphen.
- [a-z.]{2,6}: Matches any lowercase letter or period between 2 and 6 times in a row. This is used to match the TLD (top-level domain) of the email address.

### Greedy and Lazy Match

In the email address pattern example, the quantifiers `+` and `{2,6}` are greedy, which means they will match as many characters as possible while still allowing the overall pattern to match.

### Boundaries

The search pattern for matching an email has two boundaries: the beginning and end of the string. These are represented by the symbols `^` and `$` in the regular expression.
Again they defined by the anchor characters.

### Back-references

For the matching email example there isint really any back reference. However, essentially what it is its a previous capture group in a regular expression pattern. It allows you to match the same text that was previously matched by a capturing group. Uses `\1` and `\2`.

### Look-ahead and Look-behind

The regex concepts in regards to Look-ahead and Look-behind, let you match text only if it is followed by or preceded by certain text, without including that text in the match itself.

In more detail, in the context of an email pattern, you can use look-ahead to match only email addresses that are followed by a specific domain name, without including the domain name in the match. Similarly, you can use look-behind to match only email addresses that are preceded by a specific username format, without including the username in the match.

Example:
`/([a-z0-9_.-]+)@([\da-z.-]+)(?=\.gmail\.com)/`

In this pattern, `(?=\.gmail\.com)` is the look-ahead assertion, which specifies that the match should only occur if the preceding group (i.e., the email domain) is followed by the string ".gmail.com".

So, this pattern would match an email address like "example@gmail.com", but only return "example" and "gmail.com" as the captured groups, without including the ".gmail.com" portion in the match.

## Author
Gabriel Tuason, Jr. Web Developer

Check out my Git hub here at: https://github.com/gabetuason
