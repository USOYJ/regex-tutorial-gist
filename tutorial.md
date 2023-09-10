# Matching an Email: – /^([a-z0-9_.-]+)@([\da-z.-]+).([a-z.]{2,6})$/ by Oyindamola Jongbo

This is a comprehensive tutorial on matching email using regular expressions (regex).In this tutorial, we will be exploring a specific regular expression that can be used to match valid email addresses. We will break down each component of the regular expression and explain what it does.

<br>

# Summary
The regular expression (Regex) we will be discussing is `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/` This regex pattern can be used to validate email addresses. It uses different components like character classes, quantifiers, and anchors to define a specific search pattern. 

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

### Anchors
Anchors are used to match a position in the text rather than a character. In our email regex, the ^ anchor is used at the beginning of the pattern to match the start of the line, and the $ anchor is used at the end to match the end of the line. This ensures that the email address is matched in its entirety and not just as part of a larger string. Anchors are used to specify the position of the match within the text:
* ^ (caret): Matches the start of a line
* $ (dollar sign): Matches the end of a line.


### Quantifiers
 Quantifiers specify how many times a character or group should be matched. Some common quantifiers include:
* * (asterisk): Zero or more occurrences.
* + (plus): One or more occurrences.
* ? (question mark): Zero or one occurrence.
* {n}: Exactly n occurrences.
* {n,}: At least n occurrences.
* {n,m}: Between n and m occurrences.


### OR Operator
In regular expressions (regex), the | (pipe) character serves as the OR operator. It allows you to create patterns that match one of several alternatives. Here's how it works:
When you use the | operator in a regex pattern, it separates multiple subpatterns or alternatives, and the regex engine will match any one of those alternatives. The pattern will match if it finds any of the specified alternatives in the text being searched.
For example, suppose you want to find either "apple" or "banana" in a text using regex:
/apple|banana/

In regular expressions (regex), the | (pipe) character serves as the OR operator. It allows you to create patterns that match one of several alternatives. Here's how it works:

When you use the | operator in a regex pattern, it separates multiple subpatterns or alternatives, and the regex engine will match any one of those alternatives. The pattern will match if it finds any of the specified alternatives in the text being searched.

For example, suppose you want to find either "apple" or "banana" in a text using regex:
/apple|banana/
In this pattern, apple and banana are the two alternatives separated by |. When applied to a text, it will match either "apple" or "banana" if either of them exists in the text;
/apple|banana/ will match "apple" or "banana."


### Character Classes
Character classes allow you to match a single character from a set of characters. They are defined using square brackets []. For example, [aeiou] matches any vowel.


### Flags
Flags are special parameters that you can add to the end of a regex pattern to modify how the pattern is matched or processed. Each flag has a specific purpose and can change the behavior of the regex engine when applying the pattern to a text. Flags are typically represented as single characters after the closing delimiter of the regex pattern (usually a forward slash / or another character).
Here are some common regex flags:
* 		Case Insensitive (i): The i flag makes the pattern match text case-insensitively. It allows the regex to match both uppercase and lowercase letters interchangeably. For example:
    * /apple/i will match "apple," "Apple," "APPLE," etc.
* 		Global (g): The g flag tells the regex engine to find all matches in the input text rather than stopping after the first match. For example:
    * /abc/g will find all occurrences of "abc" in the text.
* 		Multiline (m): The m flag changes the behavior of anchors ^ and $. When m is used, ^ matches the start of a line, and $ matches the end of a line within a multiline text. Without m, they match the start and end of the entire text. For example:
    * /^abc/m will match "abc" at the start of each line in multiline text.
* 		Single Line (s or dotall): The s (or dotall) flag makes the . (dot) metacharacter match any character, including newline characters (\n). Without this flag, the dot matches any character except a newline. For example:
    * /a.b/s will match "a\nb" because it treats \n as a valid character.
* 		Unicode (u): The u flag is used to enable full Unicode matching, allowing you to work with Unicode characters and properties in your regex patterns.
* 		Sticky (y): The y flag makes the regex engine perform a sticky match, meaning it will only search from the index where the previous match ended. This can be useful for sequential matching.
* 		Dot All (s): Similar to the single-line flag, s makes the dot . match any character, including newline characters.
* 		Extended (x): The x flag allows you to add whitespace and comments within your regex pattern for better readability and organization. It ignores spaces and comments, treating them as if they were not there.
* 		Unicode Case (ui): The ui flag is used to perform case-insensitive matching based on Unicode character properties.
These flags give you fine-grained control over how your regex pattern behaves when matching text. Depending on your requirements, you can use one or more of these flags to tailor your regex pattern's behavior to your specific needs.



### Grouping and Capturing
Parentheses () are used for grouping parts of a pattern and capturing matched portions of the text for later use.

These components, when combined in various ways, allow you to create complex patterns for searching and manipulating text. Regular expressions are a powerful tool for text processing tasks but can also be complex and challenging to master due to their flexibility.

### Bracket Expressions
Bracket expressions, also known as character classes, are a feature in regular expressions (regex) that allow you to define a set of characters you want to match at a specific position in a string. They are enclosed in square brackets [ ] and are used to create patterns that can match any one character from the set.
Here's how to use bracket expressions in regular expressions:
* 		Basic Bracket Expression: To create a basic bracket expression, enclose a set of characters inside square brackets. For example:
    * [abc]: Matches either 'a', 'b', or 'c'.



### Greedy and Lazy Match
In regular expressions (regex), greedy and lazy matching refer to the way the regex engine attempts to match patterns in a string. These behaviors are controlled by quantifiers, such as `*`, `+`, `?`, and `{}`, which determine how many times a character or group should be matched.

1. **Greedy Matching:**
   
   By default, most quantifiers in regex are greedy, which means they try to match as much of the input string as possible while still allowing the overall pattern to match. In other words, they seek the longest possible match. Greedy quantifiers are denoted by adding `*`, `+`, or `?` directly after the character or group to be quantified.

   - `*` (asterisk): Matches zero or more occurrences greedily.
   - `+` (plus): Matches one or more occurrences greedily.
   - `?` (question mark): Matches zero or one occurrence greedily.
   
   For example, in the regex pattern `/a.*b/`, the `.*` quantifier matches as many characters as possible between 'a' and 'b' in the input string. It will find the longest sequence of characters that satisfies the pattern.

2. **Lazy (Non-Greedy or Reluctant) Matching:**
   
   In contrast to greedy matching, lazy (non-greedy or reluctant) matching attempts to find the shortest possible match that still allows the overall pattern to match. You can make a quantifier lazy by adding a `?` after it.

   - `*?`: Matches zero or more occurrences lazily.
   - `+?`: Matches one or more occurrences lazily.
   - `??`: Matches zero or one occurrence lazily.
   - `{n,m}?`: Matches between n and m occurrences lazily.

   For example, in the regex pattern `/a.*?b/`, the `.*?` quantifier matches as few characters as possible between 'a' and 'b' in the input string. It will find the shortest sequence of characters that satisfies the pattern.

Here's a practical example to illustrate the difference:

Consider the input string: `"afoobarbazb"`.

- The greedy pattern `/a.*b/` will match the entire string `"afoobarbazb"` because it seeks the longest sequence between 'a' and 'b', which is the entire string.

- The lazy pattern `/a.*?b/` will match `"afoo"` because it seeks the shortest sequence between 'a' and 'b', stopping at the first 'b' it encounters.

Choosing between greedy and lazy matching depends on your specific requirements. Use greedy matching when you want to find the longest possible match, and use lazy matching when you want to find the shortest possible match, particularly when dealing with repetitive patterns in text.

### Boundaries
In regular expressions (regex), boundaries are used to define specific positions within a string where a match should occur. Boundaries help ensure that a pattern matches only when it appears at a particular location in the text, such as the start or end of a word or line. Common regex boundaries include:

1. **Word Boundary (`\b`):**
   - `\b`: Matches a word boundary, which is a position where a word begins or ends. It ensures that the pattern is not part of a longer word.
   
   For example:
   - `\bword\b` matches the word "word" but not "password" or "words."

2. **Start of Line (`^`):**
   - `^`: Matches the start of a line or string. It ensures that the pattern appears at the beginning of a line.
   
   For example:
   - `^start` matches "start" at the start of a line but not "the start."

3. **End of Line (`$`):**
   - `$`: Matches the end of a line or string. It ensures that the pattern appears at the end of a line.
   
   For example:
   - `end$` matches "end" at the end of a line but not "endless."

4. **Start of String (`\A`):**
   - `\A`: Matches the start of a string (not just a line). It ensures that the pattern appears at the beginning of the entire input string.

5. **End of String (`\Z` or `\z`):**
   - `\Z`: Matches the end of a string (not just a line). It ensures that the pattern appears at the end of the entire input string.
   - `\z`: Similar to `\Z`, but it requires the pattern to match the very end of the string, excluding any trailing newline characters.

6. **Word Start (`\B`):**
   - `\B`: Matches a position that is not a word boundary. It ensures that the pattern is part of a longer word.
   
   For example:
   - `\Bword\B` matches "word" in "password" but not as a standalone word.

7. **Line Break (`\R`):**
   - `\R`: Matches any line break sequence, such as newline (`\n`), carriage return (`\r`), or a combination (`\r\n`). It's useful for matching line breaks in different environments.

Using boundaries in regex patterns can help you pinpoint specific locations within text where you want to find or manipulate content. They are especially useful when you need to work with words, lines, or positions within a string or document.

### Back-references
Back-references are a powerful feature in regex that allows you to work with and manipulate text based on previously captured portions of the pattern. They are especially useful for tasks like finding repeated content, reordering text, and performing text transformations.

Using Back-References:

Once you have capturing groups in your pattern, you can reference them using back-references in the same regex pattern or in a replacement string. Back-references are denoted by \ followed by the capturing group's number.

\1 refers to the first capturing group.
\2 refers to the second capturing group.
\3 refers to the third capturing group, and so on.


### Look-ahead and Look-behind
 **Lookahead and Lookbehind:**
   - Lookahead and lookbehind assertions (`(?=...)` and `(?<=...)`) allow you to specify conditions that must be satisfied before or after the main pattern without including those conditions in the match itself. These are advanced boundary constructs for more complex matching scenarios.

## Author
<p>I'm Oyindamola Jongbo,a student of Rugters coding bootcamp, for my github account. Click on this <a href="https://github.com/USOYJ/regex-tutorial-gist">link.</a></p>
