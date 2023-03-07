# regex-tutorial

This is a breakdown of the regular expression for matching a URL.


## Summary

A regex, which is short for regular expression, is a sequence of characters that defines a specific search pattern. When included in code or search algorithms, regular expressions can be used to find certain patterns of characters within a string, or to find and replace a character or sequence of characters within a string. They are also frequently used to validate input.

The following regular expression is a pattern used for matching URLs:<br>
![image](https://user-images.githubusercontent.com/114010089/223305516-ad8b332f-afeb-4428-8bb0-b6f56dfa1531.png)<br><br>

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

![image](https://user-images.githubusercontent.com/114010089/223305623-7dc04d09-9ee5-43c5-a2ad-42ae792b91d8.png)<br>

This will match one or more characters that are either digits, lowercase letters, periods or hyphens. 
### Flags
A flag is an optional perameter that modifies its search behavior. By using i, g, or m flags at the end of the URL, we can capture multiple links that are line broken:<br>
/^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/gm<br>

  www.webaddress.com<br>
  www.webaddress.com
### Grouping and Capturing
The following expression has four different groups:<br><li>
(https?://) - Matches the optional http portion.<li>
([\da-z.-]+) - Captures a domain name with any characters followed by a ".".<li> 
([a-z.]{2,6}) - Matches two to six characters either being lowercase letters or periods. This captures the top-level domain. An example would be: "com", "edu", "gov".<li>
([/\w .-]) - Matches an optional path that starts with a "/" and can contain any combination of word characters, spaces, periods, hyphens, and forward slashes.
### Bracket Expressions
Bracket expressions represent a range of charactes we want to match within a set of square brackets '([])'. Here is the bracket expression within this regex:<br>
 [\da-z\.-] and ([a-z\.]{2,6} and [\/\w \.-]<br>

 This is used to identify which part of the expression can be any or all characters. The reference above is looking for any digit, any a-z, "." or "_".

 ### Greedy and Lazy Match
In regular expressions, a greedy quanitfier ('+' and 'asteric ') will match as many characters as possible while still allowing the match to succeed. A lazy quantifier adds a '?' to the end and will match as few characters as possible.<br>
Example: \w+?, \w*?
### Boundaries
Boundary markers like ^ or a dollar sign allows you to anchor the expression pattern to the beginning and end of the line respectively. This means that when you want to match a literal ^ or $ , you need to escape these special characters with a backslash.
## Author

https://github.com/MatthewC86

https://github.com/MatthewC86/regex-tutorial
