# Matching an Email, A Regex Tutorial

This tutorial is going to explain how to use normal expression (regex) to match emails using the expression /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/. This is extremely crucial for validation of emails using Node, SQL, or Mongo.

## Summary

A regular expression is a pattern describing a certain amount of text. It is matched against a subject string from left to right. Most characters stand for themselves, and match the corresponding characters in the subject text. The simplest form of regular expression is actual literal text.

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

The anchors that are used for this regex expression to match an email are ^. This indicates the begining of the string and $ to mark the ending of the string. Multi line is not setup, so the regex will stop at $.

### Quantifiers

The quantifiers for this regex are the + operator, which allows the program to add the email name, along with the email provider, followed by a .com. The other quantifier in this expression is the {2,6} which ensures the email ending is no shorter than 2, but no longer than 6 characters.

### Grouping Constructs

The grouping constructs in this regex are as follows:
1- ([a-z0-9_\.-]+) for email name
2- ([\da-z\.-]+) for email service
3- ([a-z\.]{2,6}) for email end, ie:.com

### Bracket Expressions

The bracket expressions used in this regex are as follows:

[a-z0-9_\.-] : which is used to match any letter a-z (case sensitive). also matches for characters 0-9, "_", "-", "."

[\da-z\.-] : matches a single digit from 0-9, characters a-z(case sensitive) "." and "-"

[a-z\.] : matches any character a-z (case sensitive) and character "."

### Character Classes

the one character class found in this expression is \d. This matches a single character that is a digit from 0-9. It only will match a single instance such as "3", but not 33 or 333.

### The OR Operator

The OR operator (|) is seen used within the regex expression for email validition in '[\da-z\.-]. Within this brack we are searching for either a digit, OR letters a-z, OR a "." , OR a"-"

### Flags

Regular expressions have six optional flags that allow for functionality as in global and case insensitive searching.

The six are the following: 

the three main flags are:

(i) - This flag indicates the search is case insensitive 
(g) - This flag will search for all matches, otherwise only first match will return 
(m) - This flag indicates multiline code (still governed by Anchors) 
 
There are three further flags
 
(s) - Enables 'dotall' mode, that allows a dot (.) to match a newline character \n
(u) - Enables full Unicode support. 
(y) - "Sticky" mode - searching at the exact position in the text. 

In this Regex

 /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/.

 There were no flags set for anything at this time.

### Character Escapes
The character escapes in this regex are shown by the "\", this is used to escape a character that will be interpreted potentially differently. Easiest example is the "." which is used in all 3 different brackets inside our regex.

If we were to not put "\.", the expression would have issues because just a single "." in regex will represent any character possible. So even though it is setup to only accept specific ones, if you were to leave just "." it would break the validation you are trying to achieve.

## Author

David Hruza
I am a 33 year almost done with my Bootcamp coding course, with aspirations to become a full stack developer. Please click the link to check out all my projects!
http://www.github.com/dhruza88

