# Regex Tutorial

Regex, or regular expressions, are a special kind of expression that is used to match a pattern of characters. This tutorial will link to sections describing the most common regex types

## Summary

This tutorial links to sections describing the most common regex types and give examples of that code.

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

Anchors define the position where the pattern should be matched. They can be used to specify the start or the end of the pattern. The caret (^) is used to start and the ($) is used to end. (/b) looks for matching words and (?=) looks ahead.

Pattern pattern = Pattern.compile("^\\w+\\d+$");

This uses the (^) to start, the (\b) looks for matching words, and the ($) to end.

The w+ means one or more characters - it will match any character a-z and numbers 0-9.

### Quantifiers

Quantifiers specify how many times a character can appear in a pattern. The most common ones are: * (0 or more), + (1 or more), and ? (0 or one). You can also put them together: {1,3}.

 ^\w{1,3}$ 

 This will match any string of 1-3 letters or numbers.

### OR Operator

The OR operator (||) compares 2 values and returns a boolean. The lines technically mean "or", so 1 or 2 values can be true for the boolean to be true.

if (x == 1 || y == 2) {
  //then...something happens in this code
}

### Character Classes

Character classes are used in regex to categorize for easier reading. For example, \d stands for any digit, \w stands for any word character, and \s stands for any whitespace.

\b\w+\b

The \b characters are anchoring and represent a boundary, and the \w+ part matches one or more word characters. The end \b anchors the end.

### Flags

Flags are used as modifiers with regular expressions. They go on the end of a regex and can be used to change the behavior. Some common flags are "i" (ignore case) or "g" (global). They are used to make it more specific or to specify a particular behavior.

/^A.*X$/g

This will match any string of characters that starts with A and ends with X.

### Grouping and Capturing

Grouping lets a pattern be organized and then stored in a variable to use later. The pattern is broken into smaller groups and can then be taken out when matched. Capturing lets the rest of the pattern be put back together in different ways.

(\d+)\s+(\w+)

This matches any 2 groups of characters - the first one a number and the second one a word. 

### Bracket Expressions

Bracket expressions use square brackets [] and use symbols to match a text sequence.

\d[a-zA-Z]

This will match any string that has a number followed by a letter.

### Greedy and Lazy Match

Greedy match looks for the longest possible matches to the pattern and lazy match looks for the shortest possible matches to the pattern.

Greedy match:

const pattern = /(.*){3}/;
const text = 'abcdefghijklmnop';
const matches = text.match(pattern);
console.log(matches[0]); // abcdefghijklmno

This return the longest possible match, which is the whole thing.

Lazy match:

const pattern = /(.*?){3}/;
const text = 'abcdefghijklmnop';
const matches = text.match(pattern);
console.log(matches[0]); // abc

This returns the shortest possible match, the first 3 letters: abc

### Boundaries

Boundaries are used to indentify words or text in a specific location. Usually the beginning or end of a string. Could be words that start with a specific letter or phrase, or end that way.

const regex = /\w+/g; 
let string = "Hello World"; 
let matches = string.match(regex); 
console.log(matches); // ["Hello", "World"]

This looks for sequences that begin with the string "hello world"

### Back-references

 A back reference is indicated by a backslash (\) followed by a number or an abbreviation. They refer to a previously captured group.

 ([a-z])\1

 This will find a pattern of a lowercase letter followed by an uppercase letter.

### Look-ahead and Look-behind

Look-ahead and look-behind are used to check what comes before or after a specified character or sequence. 

Look-ahead:

'hello(?=\sworld)'

This will match the word “hello” if it is followed by the word “world”

Look-behind:

'(?<=hello\s)world'

This will match the word "world" if it preceded by the word "hello"

## Author

Chelsea Pederson is a web-development student at the University of Minnesota. To see all current and past projects, visit:

https://github.com/Chelsea-Marie
