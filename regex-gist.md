# REGEX Tutorial

In this tutorial I will explain regular expressions or **"REGEX"**, a powerful search tool that'll allow you to search for items within a set of code. Please follow along as I explain all the functions within **REGEX**.

## Summary

Regular expressions or **REGEX** is a powerful toolthat is extremely useful in extracting information from any text. **REGEX** works by searching one or more matches of a specific search pattern. In this tutorial I'll dicuss the different types of unicode to search for email addresses within a specific set of code or text.

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

### Anchors **^ and $**
Anchors signify the beginning and end of your search criteria pattern. Basically the anchors tell the machine where your search criteria begins and ends.
* **^The**        matches any string that starts with The.
* **end$**        matches a string that ends with end.
* **^The end$**   exact string match (starts and ends with "The end").

**In the case of an email search you can see how this search parameter bigins with ^ and ends with $.**

    /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

### Quantifiers **+ * ? and {}**
* **abc***        matches a string that has ab followed by zero or more c.
* **abc+**        matches a string that has ab followed by one or more c.
* **abc?**        matches a string that has ab followed by zero or one c.
* **abc{2}**      matches a string that has ab followed by 2 c.
* **abc{2,}**     matches a string that has ab followed by 2 or more c.
* **abc{2,5}**    matches a string that has ab followed by 2 up to 5 c.
* **a(bc)***      matches a string that has a followed by zero or more copies of the sequence bc.
* **a(bc){2,5}**  matches a string that has a followed by 2 up to 5 copies of the sequence bc.

**You can see that there are 2 + in the code.**

    /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

**The first one is the first part of the email address. The second one appears after the @ sign and before the period. Meaning there is more than one input that is part of the string to be searched.**

    /^([a-z0-9_\.-]+)   @([\da-z\.-]+)  \.([a-z\.]{2,6})$/

### Grouping Constructs **()**
* **a(bc)**          parentheses create a capturing group with value bc.
* **a(?:bc)**      using ?: we disable the capturing group.
* **a(?<foo>bc)**    using ?<foo> we put a name to the group.

**In the case of the email address we have 3 subexpressions.**

    /^    ([a-z0-9_\.-]+)   @     ([\da-z\.-]+)    \.    ([a-z\.]{2,6})   $/


### Bracket Expressions **[]**
* **[abc]**            matches a string that has either an a or a b or a c -> is the same as a|b|c.
* **[a-c]**            same as previous.
* **[a-fA-F0-9]**      a string that represents a single hexadecimal digit, case insensitively.
* **[0-9]%**           a string that has a character from 0 to 9 before a % sign.
* **[^a-zA-Z]**        a string that has not a letter from a to z or from A to Z. In this case the ^ is used as negation of the expression.

**[a-z0-9_.-] any letters a-z or numbers 0-9, including underscores, periods and hyphens. [\da-z.-] Any letters a-z, includes periods and hyphens [a-z.] Letters a-z followed by a period.**

    /^([a-z0-9_\.-]+)@([\da-z\.-]+) \.([a-z\.]{2,6})$/

### Character Classes **\d \w \s and .**
* **\d**         matches a single character that is a digit.
* **\w**         matches a word character (alphanumeric character plus underscore).
* **\s**         matches a whitespace character (includes tabs and line breaks).
* **.**          matches any character.

### The OR Operator **| or []**
* **a(b|c)**     matches a string that has a followed by b or c (and captures b or c).
* **a[bc]**      same as previous, but without capturing b or c.

### Flags
* **g** (global) does not return after the first match, restarting the subsequent searches from the end of the previous match
* **m** (multi-line) when enabled ^ and $ will match the start and end of a line, instead of the whole string
* **i** (insensitive) makes the whole expression case-insensitive (for instance /aBc/i would match AbC)

### Character Escapes
* **\\\\** single backslash
* **\A** start of a string
* **\b** word boundary. The zero-length string between \w and \W or \W and \w.
* **\B** not at a word boundary
* **\c**X ASCII control character
* **\d** single digit [0-9]
* **\D** single character that is NOT a digit [^0-9]
* **\E** stop processing escaped characters
* **\l** match a single lowercase letter [a-z]
* **\L** single character that is not lowercase [^a-z]
* **\Q** ignore escaped characters until \E is found
* **\r** carriage return
* **\s** single whitespace character
* **\S** single character that is NOT white space
* **\u** single uppercase character [A-Z]
* **\U** single character that is not uppercase [^A-Z]
* **\w** word character [a-zA-Z0-9_]
* **\W** single character that is NOT a word character [^a-zA-Z0-9_]
* **\x00-\xFF** hexadecimal character
* **\x{0000}-\x{FFFF}** Unicode code point
* **\Z** end of a string before the line break

## Author

Hello, I'm Chris Whalen and I'm and unsigned junior developer free agent! I'm a soon to be graduate of University of Denver's Coding Bootcamp. I'm beyond excited to enter the world of development while learning even more along the way. 
* Chris Whalen, Github: **[CobaltFrostfish](https://github.com/CobaltFrostfish)**