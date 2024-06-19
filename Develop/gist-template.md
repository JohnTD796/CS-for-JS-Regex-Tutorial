# CS for JS: Regex Tutorial

The purpose of this challenge is to famialrize myself with the syntax and formualtion of Regex code and understand how and when they are supposed to be utilized.

## Summary

^(?=.*[A-Z])(?=.*[a-z])(?=.*\d)(?=.*[@$!%*?&])[A-Za-z\d@$!%*?&]{8,}$

This regex is specifying that the the string should have:
    At least one capital letter, At least one lowercase letter, at least one number, at least one special character, and should be 8 characters long.

    '()' - Specifies a grouping of parameters.

    '?=.*' - Is a positive lookahead specifying that the there must be at least one uppercase letter somewhere in the string after thje current postion in the string.

    '[]' - Is character class/bracket expression denoting that the the string should match the charcters inside the brackets.
            [A-Z] being that the regex should be looking for characters that are capital letters.

    '\d' - This is a character class asserting that the string should contain a number.

    '{8,}' - This is a quantifier (denoted by the {}) specifying the minimum number of times a character/number/special character must appear to be valid. 
            ',' separates the min/max.
            Since there is no max, it  is saying that there muyst be at least 8 characters.

    '^' - Asserts that the parameters should be found at the start of the regex string.
            In this example it shows the start of the string.

    '$' - Asserts that the parameters should be found at the start of the regex string.
            In this example it shows the end of the string.

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

    Anchors are what specify whether the parameters match the beginning or the end of the line
    Such as  '^' and '$'

    '^' - the parameters should be found at the start of the regex string

    '$' - the parameters should be found at the end of the regex string

### Quantifiers

    Quantifiers are what determines the amount of characters that follow.
    Such as '*', '?', '+', '{n}'

    '*' - the preceeding element should match 0 or more of the specified parameters.
        'a*' matches '', 'a', 'aa', 'aaa', etc.
    
    '?' - the preceeding element should match 0 or 1 of the specified parameters.
        'a?' matches '', 'a', etc.

    '+' - the preceeding element should match at least 1 of the specified parameters
        'a+' matches 'a', 'aa', 'aaa', 'aaaa', etc.
    

    '{n}' - the preceeding element should contain the specified parameters a specific {n}umber of times.
        'a{3}' matches 'aaa'


### OR Operator

    The '|' operator specifies whether the parameter is one or the other
        [a-zA-Z0-9._%+-]+@(gmail\.com|yahoo\.com)
            in this context the '|' operator means that the email could be email@gmail.com or email@yahoo.com


### Character Classes

    Character classes are what specifies the parameters for the the characters that are to be accepted by the Regex

        '[]' - the characters should match what is inside of the brackets
            '[a-z]' - the characters should be anywhere from a-z (lowercase)
            '[A-Z]' - the characters should be anywhere from A-Z (uppercase)
            **** '-' - is indiccative of a range
            **** '[a-zA-Z0-9]' - matches any alphanumeric character

        '[^]' - the characters should NOT match what is inside of the brackets
            '[^0-9] - Matches any character that is not a number.

        '\d' - matches any number
        '\D' - matches any character that is not a number

### Flags

    Modifies how the pattern matching is executed.

    'i' - ignores case sensitivity

    'g' - finds all occurences

    'm' - Makes the boundary characters ^ and $ match the beginning and ending of every single line instead of the whole string

    's' - makes the '.' search for newlines

    'u' - enables search for unicode

    'y' - expression starts its search from the index indicated in the lastIndex property

        syntax - pattern/flag [/d]/g: would find all occurences of numbers


### Grouping and Capturing

    '()' - used to group parts of the pattern
        (abc)+ would search for 'abc', 'abcabc', 'abcabcabc', etc.
        
    Grouping parts of a pattern are captured by the regex engine.

    ^(?=.*[A-Z])(?=.*[a-z])(?=.*\d)(?=.*[@$!%*?&])[A-Za-z\d@$!%*?&]{8,}$
        in this example the string is being grouped together by each parameter that is being checked for. it is looking for at least one uppercase/lowercase letter, at least one digit and at least one special character in no particular order.
        

### Bracket Expressions

    Allow specific characters/ range of characters represented inside of '[]'

'[]' - the characters should match what is inside of the brackets.
            '[a-z]' - the characters should be anywhere from a-z (lowercase)
            '[A-Z]' - the characters should be anywhere from A-Z (uppercase)
            **** '-' - is indicative of a range
            **** '[a-zA-Z0-9]' - matches any alphanumeric character

'[^]' - the characters should NOT match what is inside of the brackets.
            '[^0-9] - Matches any character that is not a number.

### Greedy and Lazy Match

Greedy quantifiers match as much of the string as possible.
    denoted by adding  '*', '+', or '{}' after a character or group.
        matches 'n' or more.

Lazy quantifiers match as little of the string as possible.
    denoted by adding  '?' after a greedy quantifier.
        matches 'n' or 1.

### Boundaries

    Boundaries specify where exactly the parameters of the regex should be found.
        ^(?=.*[A-Z])(?=.*[a-z])(?=.*\d)(?=.*[@$!%*?&])[A-Za-z\d@$!%*?&]{8,}$
        doesnt specify where each character/number/special charatcer should be found.

        ^(?=[A-Z][a-z]\d[@$!%*?&])[A-Za-z\d@$!%*?&]{8,}$
        specifies that the first letter of the string has to be a capital letter followed by any lowercase characters, then a number must follow, and then a special character must follow.

### Back-references

Back references allow you to refer to a specific captured group.
    denoted by '\' followed by a number.

    example \b(\w+)\b.*\b\1\b matches any word and then searches for any duplicates of the first reference which would be the (\w+).

### Look-ahead and Look-behind

Look-ahead allows you to assert whether a certain pattern can be matched ahead of the the current position of the string
    (?=.*[A-Z]) asserts that the string contains at least one capital letter.

Look-behind allows you to assert whether a certain pattern can be matched behind the the current position of the string
    (?<=\$)\d+ asserts that the current position starts with a dollar sign in front of it.

## Author

GitHub Repository link: https://github.com/JohnTD796/CS-for-JS-Regex-Tutorial.git
