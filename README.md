# Regex Tutorial on Validating an Email Address
Week-17 Challenge: Computer Science for JavaScript Challenge: Regex Tutorial

![GITHUB](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)
![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)
![Lora Lainio](https://img.shields.io/badge/Lora-Lainio-4baaaa.svg)

## Table of Contents

- [Description](#description)
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
- [Screenshot](#screenshot)
- [License](#license)
- [Contact](#contact)

## Description
When working with HTML forms, it's beneficial to validate form input using regular expressions. Email validation, in particular, can be challenging due to the intricacies of the email specification. It's advisable to utilize built-in language or framework functions for email validation rather than creating your own solution. However, you can create a robust regular expression that effectively matches many common email formats using the concepts we've covered.

An important consideration is the use of plus addressing by many individuals for temporary purposes, such as "name+filter@gmail.com," which resolves to "name@gmail.com" but allows for filtering based on the additional information. Additionally, some domains consist of multiple components. For instance, registering a domain like "hellokitty.hk.com" enables emails in the format "ilove@hellokitty.hk.com," necessitating careful handling of the domain part during email matching.

Below are examples of common emails. In this exercise, attempt to extract the name from the email, excluding any filters (characters after a plus sign) and the domain (characters after the @ symbol).

For example, the following regular expression can be used to verify that user input is a valid email address:
This is the regex code that will be broken apart: `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

# Regex Components
### Anchors
The `^` anchor signifies a string that begins with the characters that follow it, while the `$` anchor signifies a string that ends with the characters that precede it.

The anchors used to contain the regular expression in the example are: `^` to start, and `$` to finish it.

### Quantifiers
Quantifiers set the limits of the string that a regex matches (or an individual section of the string). They frequently include the minimum and maximum number of characters that your regex is looking for.

Quantifiers are inherently greedy, meaning they match as many occurrences of particular patterns as possible. They include the following:

`*` —Matches the pattern zero or more times

`+` —Matches the pattern one or more times

`?` —Matches the pattern zero or one time

`{}` —Curly brackets can provide three different ways to set limits for a match:

`{ n }` —Matches the pattern exactly n number of times

`{ n, }` —Matches the pattern at least n number of times

`{ n, x }` —Matches the pattern from a minimum of n number of times to a maximum of x number of times


In this example, we used `+` to pattern one or more times. We also used `{2,6}` to specify the input should be a minimum of 2 characters to a maximum of 6 characters.

### OR Operator
An OR operator `(|)` means that the expression `[abc]` could be written as `(a|b|c)`.

In the example, email does not have an Operator included.

### Character Classes
A character class in a regex defines a set of characters, any one of which can occur in an input string to fulfill a match.

Here are some of the other common character classes:

`.` —Matches any character except the newline character (\n)

`\d` —Matches any Arabic numeral digit. This class is equivalent to the bracket expression `[0-9]`.

`\w` —Matches any alphanumeric character from the basic Latin alphabet, including the underscore `(_)`. This class is equivalent to the bracket expression `[A-Za-z0-9_]`.

`\s` —Matches a single whitespace character, including tabs and line breaks

In the example, the character class `/d` is used to classify the use of any digit from 0 to 9.

### Flags
Flags are placed at the end of a regex, after the second slash, and they define additional functionality or limits for the regex. The most comment are:

`g` —Global search: the regex should be tested against all possible matches in a string.

`i` —Case-insensitive search: case should be ignored while attempting a match in a string

`m` —Multi-line search: a multi-line input string should be treated as multiple lines

In the example, there are no flags being used.


### Grouping and Capturing
To break these sections up, use grouping constructs. The primary way you group a section of a regex is by using parentheses `(())`. Each section within parentheses is known as a subexpression. Grouping constructs have two primary categories: capturing and non-capturing. Capturing groups capture the matched character sequences for possible re-use (including a numbered backreference) while non-capturing groups do not. A grouping construct can be made non-capturing by adding the characters `?:` at the beginning of an expression inside the parentheses.

In the example, there are 3 groups being captured:

#### Group 1
This represents the username of the e-mail account.
`[a-z0-9_\.-]+`

#### Group 2
This represents the domain name, or e-mail service being used.
`[\da-z\.-]+`

#### Group 3
This represents the domain extension (i.e .com or .net)
`[a-z\.]{2,6}`

### Bracket Expressions
Bracket expressions are anything inside a set of square brackets `([])`. These represent a range of characters that are meant to match.

In this example, there are 3 bracket expressions:

#### Group 1
This represents the case sensitive characters from a-z, numbers from 0-9, an underscore, periods and hyphens.
`[a-z0-9_\.-]`

#### Group 2
This represents the all digits, case sensitive characters from a-z, periods and hyphens.
`[\da-z\.-]`

#### Group 3
This represents the case sensitive characters from a-z and periods.
`[a-z\.]`

### Greedy and Lazy Match
Quantifiers can be made to be lazy by adding the `?` symbol after it, meaning it will match as few occurrences as possible.

However, because quantifiers are inherently greedy, in the example only greedy quantifiers are being used. It uses `+` and `{}` which allows the matches to expand as long as its needed to versus making the shortest matches like lazy quantifiers would.

### Boundaries
Boundaries make assertions about what can be matched to the left and right of the current position. Word boundaries are useful when you want to match a sequence of letters (or digits) on their own, or to ensure that they occur at the beginning or the end of a sequence of characters.

We do not use boundaries in this example.

### Back-references
Back-references are used to match the same text previously matched by a capturing group. This both helps in reusing previous parts of your pattern and in ensuring two pieces of a string match.

Back-references are not used in this example.

### Look-ahead and Look-behind
Look-ahead is the syntax is: `X(?=Y)`, and it means that it will look for `X`, but match only if followed by `Y`.
Look-behind is similar, but it looks behind. That is, it allows to match a pattern only if there’s something before it.
These are not used in this example.

## Screenshot
![](./images/90W7R.png)
![](./images/YI6KR.png)
![](./images/SrUwP.png)
![](./images/Zight%202024-6-4%20at%203.13.37%20PM.png)
![](./images/Zight%202024-6-4%20at%203.17.00%20PM.png)

## License

NOTICE: This application is covered under the MIT License

© 2024 edX Boot Camps LLC. Confidential and Proprietary. All Rights Reserved.

## Contact

Have additional questions? Click the links below to reach me through my GitHub account or Email address.

[Link to Github](https://github.com/L-Lainio)

<a href="mailto:lora.lainio.it@gmail.com">lora.lainio.it@gmail.com</a>

## Resources & Links

### Regexone
https://regexone.com/problem/matching_emails

### Wikipedia
https://en.wikipedia.org/wiki/Email_address#Syntax

### Stackoverflow
https://stackoverflow.com/questions/201323/how-can-i-validate-an-email-address-using-a-regular-expression

### Regular-Expression
https://www.regular-expressions.info/index.html


❤
[Link-to-github-gist-file](https://gist.github.com/L-Lainio/013bafa09a24542d178234e3db52dcda.js)
