# Use regular expressions in Visual Studio.
Information is from Microsoft Learn websites:
[Regular Expression Language - Quick Reference](https://learn.microsoft.com/en-us/dotnet/standard/base-types/regular-expression-language-quick-reference) 
and 
[Use regular expressions in Visual Studio](https://learn.microsoft.com/en-us/visualstudio/ide/using-regular-expressions-in-visual-studio), 
# ازاي ده هيفيدني؟

A regular expression is a pattern that the regular expression engine attempts to match in input text. A pattern consists of one or more character literals, operators, or constructs. For a brief introduction, see .NET Regular Expressions.

Each section in this quick reference lists a particular category of characters, operators, and constructs that you can use to define regular expressions.

# For Example (this table is from Microsoft website: [Use regular expressions in Visual Studio](https://learn.microsoft.com/en-us/visualstudio/ide/using-regular-expressions-in-visual-studio)),

<details>
<summary> MS VS Code Regular Expressions Table</summary>

Purpose|Expression|Example
| ------------- | ------------- | ------------- |
Match any single character (except a line break). For more information, see Any character.|.|a.o matches "aro" in "around" and "abo" in "about" but not "acro" in "across"
Match zero or more occurrences of the preceding expression (match as many characters as possible). For more information, see Match zero or more times.|*|a*r matches "r" in "rack", "ar" in "ark", and "aar" in "aardvark"
Match any character zero or more times.|.*|c.*e matches "cke" in "racket", "comme" in "comment", and "code" in "code"
Match one or more occurrences of the preceding expression (match as many characters as possible). For more information, see Match one or more times.|+|e+d matches "eed" in "feeder" and "ed" in "faded"
Match any character one or more times.|.+|e.+e matches "eede" in "feeder" but finds no matches in "feed"
Match zero or more occurrences of the preceding expression (match as few characters as possible). For more information, see Match zero or more times (lazy match).|*?|\w*?d matches "fad" and "ed" in "faded" but not the entire word "faded" due to the lazy match
Match one or more occurrences of the preceding expression (match as few characters as possible). For more information, see Match one or more times (lazy match).|+?|e\w+? matches "ee" in "asleep" and "ed" in "faded" but finds no matches in "fade"
Anchor the match string to the beginning of a line or string|^|^car matches the word "car" only when it appears at the beginning of a line
Anchor the match string to the end of a line|\r?$|car\r?$ matches "car" only when it appears at the end of a line
Anchor the match string to the end of the file|$|car$ matches "car" only when it appears at the end of the file
Match any single character in a set|[abc]|b[abc] matches "ba", "bb", and "bc"
Match any character in a range of characters|[a-f]|be[n-t] matches "bet" in "between", "ben" in "beneath", and "bes" in "beside", but finds no matches in "below"
Capture and implicitly number the expression contained within parenthesis|()|([a-z])X\1 matches "aXa" and "bXb", but not "aXb". "\1" refers to the first expression group "[a-z]". For more information, see Capture groups and replacement patterns.
Invalidate a match|(?!abc)|real(?!ity) matches "real" in "realty" and "really" but not in "reality." It also finds the second "real" (but not the first "real") in "realityreal".
Match any character that isn't in a given set of characters. For more information, see Negative character group.|[^abc]|be[^n-t] matches "bef" in "before", "beh" in "behind", and "bel" in "below", but finds no matches in "beneath"
Match either the expression before or the one after the symbol|||(sponge|mud) bath matches "sponge bath" and "mud bath"
Escape the character following the backslash|\|\^ matches the character ^
Specify the number of occurrences of the preceding character or group. For more information, see Match exactly n times.|{n}, where 'n' is the number of occurrences|x(ab){2}x matches "xababx"
x(ab){2,3}x matches "xababx" and "xabababx" but not "xababababx"
Match text in a Unicode category. For more information about Unicode character classes, see Unicode Standard 15.0 Character Properties.|\p{X}, where "X" is the Unicode number.|\p{Lu} matches "T" and "D" in "Thomas Doe"
Match a word boundary|\b (Outside a character class \b specifies a word boundary, and inside a character class \b specifies a backspace.)|\bin matches "in" in "inside" but finds no matches in "pinto"
Match a line break (that is, a carriage return followed by a new line)|\r?\n|End\r?\nBegin matches "End" and "Begin" only when "End" is the last string in a line and "Begin" is the first string in the next line
Match any word character|\w|a\wd matches "add" and "a1d" but not "a d"
Match any whitespace character|\s|Public\sInterface matches the phrase "Public Interface"
Match any decimal digit character|\d|\d matches "4" and "0" in "wd40"

</details>
