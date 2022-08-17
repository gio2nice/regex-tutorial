# Matching URL - Regex Tutorial

Matching a URL regular expression breakdown.

## Summary

Throughout this tutorial, I will break down the regular expression for matching a URL & explain each piece in detail. 
The regular expression: 

```
  /^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/
```

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Author] (#author)

## Regex Components

### Anchors
The anchors will have a beginning & closing anchor. The two characters we will be looking at are ^ (beginning) and the $ (closing). These signify when the start and the end of the string we are looking for will occur. 


### Quantifiers
We have two qualifiers in this regular expression which are the ? and * symbols.

The first question mark labels the "s" in "https" as optional. The reason why is because some links start with http:// or https://. We want the regular expression to be able to find both. The ? after the first grouping marks the entire first grouping as optional. Just like with the character "s" in the string, some URLs will just begin with "www." thus making the http:// or https:// outdated in some cases. We would still want to flag any URLs without the beginning http. The question mark before the ending anchor marks the final "/" in a URL. 

```
  ([\/\w \.-]*)*\/?$/
```

Here the * is seen twice near the end of this expression. The * is marking that the final grouping can happen any number of times and be followed by the same thing multiple times. The question mark only allows for zero or one of the preceding character or grouping. 

### Flags
 Often regular expressions are delimited by the '/'. We see this at the beginning and end of the expression, even after the anchors that i mentioned before. It is possible to identify search criteria outside of the flags to help mark the expression as global (g), multi-line (m), or insensitive (i). 

### Grouping and Capturing

```
  /^(https?:\/\/)? and ([\da-z\.-]+)\. and ([a-z\.]{2,6}) and ([\/\w \.-]*)*\/?$/
```

The expression is four significant groups, first one is the optional http portion. Second group is looking for any characters that would represent a domain name. The third group is commonly seen as ".com" and is limited to 2-6 characters. Last group is the directory or file path specification.
 
### Bracket Expressions
The bracket expressions identify which portions of the expressions can be any or all of the characters within each bracket. In the initial bracket expression, we can say that we are looking for any digit, or any character a-z, or any "." or "-". Similarly with the last two brackets, we are looking for any or all of those characters.

Expression:
```
  [\da-z\.-] and ([a-z\.]{2,6} and [\/\w \.-]
```

## Author

This Regex Tutorial on matching a URL breakdown was created by Robertson Giovanni Rojas. Github: 
