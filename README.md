# regex-tutorial

This is a breakdown of the regular expression for matching a URL.


## Summary

A regex, which is short for regular expression, is a sequence of characters that defines a specific search pattern. When included in code or search algorithms, regular expressions can be used to find certain patterns of characters within a string, or to find and replace a character or sequence of characters within a string. They are also frequently used to validate input.

The following regular expression is a pattern used for matching URLs:<br>
/^(https?://)?([\da-z.-]+).([a-z.]{2,6})([/\w .-])/?$/<br><br>

Here's a breakdown of what each part of the regex does:<br><br>

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)
- [Boundaries](#boundaries)


## Regex Components

### Anchors
Anchors generally consist of 2 character within the expression. '^' Matches the beginning of a string and '/$/' matches the end of the string.

### Quantifiers
The first '?' considers the 's' in 'https' as optional, since some links contain http or https and would want the regex to find both. Here is a more cut and dry example:<br>

(https?://)? matches an optional "http://" or "https://" at the beginning of the URL.<br>

The \w grouping allows any alphanumeric characters.
### Character Classes
A character class is a set of characters enclosed within square brackets. It specifies the characters that will successfully match a single character from a given input string. Here we have:<br>

'([\da-z.-]+)'<br>

This will match one or more characters that are either digits, lowercase letters, periods or hyphens. 
### Flags
A flag is an optional perameter that modifies its search behavior. By using i, g, or m flags at the end of the URL, we can capture multiple links that are line broken:<br>
/^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/gm<br>

  www.webaddress.com<br>
  www.webaddress.com
