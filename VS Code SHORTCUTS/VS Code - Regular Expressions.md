# Use regular expressions in Visual Studio.
Information is from Microsoft Learn websites:
[Regular Expression Language - Quick Reference](https://learn.microsoft.com/en-us/dotnet/standard/base-types/regular-expression-language-quick-reference) 
and 
[Use regular expressions in Visual Studio](https://learn.microsoft.com/en-us/visualstudio/ide/using-regular-expressions-in-visual-studio), 
# ازاي ده هيفيدني؟

A regular expression is a pattern that the regular expression engine attempts to match in input text. A pattern consists of one or more character literals, operators, or constructs. For a brief introduction, see .NET Regular Expressions.

Each section in this quick reference lists a particular category of characters, operators, and constructs that you can use to define regular expressions.

# For Example (this table is from Microsoft website: [Use regular expressions in Visual Studio](https://learn.microsoft.com/en-us/visualstudio/ide/using-regular-expressions-in-visual-studio)),

<div class="has-inner-focus"><table aria-label="Table 1" class="table table-sm margin-top-none">
<thead>
<tr>
<th>Purpose</th>
<th>Expression</th>
<th>Example</th>
</tr>
</thead>
<tbody>
<tr>
<td>Match any single character (except a line break). For more information, see <a href="/en-us/dotnet/standard/base-types/character-classes-in-regular-expressions#any-character-" data-linktype="absolute-path">Any character</a>.</td>
<td>.</td>
<td><code>a.o</code> matches "aro" in "around" and "abo" in "about" but not "acro" in "across"</td>
</tr>
<tr>
<td>Match zero or more occurrences of the preceding expression (match as many characters as possible). For more information, see <a href="/en-us/dotnet/standard/base-types/quantifiers-in-regular-expressions#match-zero-or-more-times-" data-linktype="absolute-path">Match zero or more times</a>.</td>
<td>*</td>
<td><code>a*r</code> matches "r" in "rack", "ar" in "ark", and "aar" in "aardvark"</td>
</tr>
<tr>
<td>Match any character zero or more times.</td>
<td>.*</td>
<td><code>c.*e</code> matches "cke" in "racket", "comme" in "comment", and "code" in "code"</td>
</tr>
<tr>
<td>Match one or more occurrences of the preceding expression (match as many characters as possible). For more information, see <a href="/en-us/dotnet/standard/base-types/quantifiers-in-regular-expressions#match-one-or-more-times-" data-linktype="absolute-path">Match one or more times</a>.</td>
<td>+</td>
<td><code>e+d</code> matches "eed" in "feeder" and "ed" in "faded"</td>
</tr>
<tr>
<td>Match any character one or more times.</td>
<td>.+</td>
<td><code>e.+e</code> matches "eede" in "feeder" but finds no matches in "feed"</td>
</tr>
<tr>
<td>Match zero or more occurrences of the preceding expression (match as few characters as possible). For more information, see <a href="/en-us/dotnet/standard/base-types/quantifiers-in-regular-expressions#match-zero-or-more-times-lazy-match-" data-linktype="absolute-path">Match zero or more times (lazy match)</a>.</td>
<td>*?</td>
<td><code>\w*?d</code> matches "fad" and "ed" in "faded" but not the entire word "faded" due to the lazy match</td>
</tr>
<tr>
<td>Match one or more occurrences of the preceding expression (match as few characters as possible). For more information, see <a href="/en-us/dotnet/standard/base-types/quantifiers-in-regular-expressions#match-one-or-more-times-lazy-match-" data-linktype="absolute-path">Match one or more times (lazy match)</a>.</td>
<td>+?</td>
<td><code>e\w+?</code> matches "ee" in "asleep" and "ed" in "faded" but finds no matches in "fade"</td>
</tr>
<tr>
<td>Anchor the match string to the <a href="/en-us/dotnet/standard/base-types/anchors-in-regular-expressions#start-of-string-or-line-" data-linktype="absolute-path">beginning of a line or string</a></td>
<td>^</td>
<td><code>^car</code> matches the word "car" only when it appears at the beginning of a line</td>
</tr>
<tr>
<td>Anchor the match string to the <a href="/en-us/dotnet/standard/base-types/anchors-in-regular-expressions#end-of-string-or-line-" data-linktype="absolute-path">end of a line</a></td>
<td>\r?$</td>
<td><code>car\r?$</code> matches "car" only when it appears at the end of a line</td>
</tr>
<tr>
<td>Anchor the match string to the end of the file</td>
<td>$</td>
<td><code>car$</code> matches "car" only when it appears at the end of the file</td>
</tr>
<tr>
<td>Match any single character in a set</td>
<td>[abc]</td>
<td><code>b[abc]</code> matches "ba", "bb", and "bc"</td>
</tr>
<tr>
<td>Match any character in a range of characters</td>
<td>[a-f]</td>
<td><code>be[n-t]</code> matches "bet" in "between", "ben" in "beneath", and "bes" in "beside", but finds no matches in "below"</td>
</tr>
<tr>
<td>Capture and implicitly number the expression contained within parenthesis</td>
<td>()</td>
<td><code>([a-z])X\1</code> matches "aXa" and "bXb", but not "aXb". "\1" refers to the first expression group "[a-z]". For more information, see <a href="#capture-groups-and-replacement-patterns" data-linktype="self-bookmark">Capture groups and replacement patterns</a>.</td>
</tr>
<tr>
<td>Invalidate a match</td>
<td>(?!abc)</td>
<td><code>real(?!ity)</code> matches "real" in "realty" and "really" but not in "reality." It also finds the second "real" (but not the first "real") in "realityreal".</td>
</tr>
<tr>
<td>Match any character that isn't in a given set of characters. For more information, see <a href="/en-us/dotnet/standard/base-types/character-classes-in-regular-expressions#negative-character-group-" data-linktype="absolute-path">Negative character group</a>.</td>
<td>[^abc]</td>
<td><code>be[^n-t]</code> matches "bef" in "before", "beh" in "behind", and "bel" in "below", but finds no matches in "beneath"</td>
</tr>
<tr>
<td>Match either the expression before or the one after the symbol</td>
<td>|</td>
<td><code>(sponge|mud) bath</code> matches "sponge bath" and "mud bath"</td>
</tr>
<tr>
<td><a href="/en-us/dotnet/standard/base-types/character-escapes-in-regular-expressions" data-linktype="absolute-path">Escape the character</a> following the backslash</td>
<td>\</td>
<td><code>\^</code> matches the character ^</td>
</tr>
<tr>
<td>Specify the number of occurrences of the preceding character or group. For more information, see <a href="/en-us/dotnet/standard/base-types/quantifiers-in-regular-expressions#match-exactly-n-times-n" data-linktype="absolute-path">Match exactly n times</a>.</td>
<td>{n}, where 'n' is the number of occurrences</td>
<td><code>x(ab){2}x</code> matches "xababx"<br><code>x(ab){2,3}x</code> matches "xababx" and "xabababx" but not "xababababx"</td>
</tr>
<tr>
<td><a href="/en-us/dotnet/standard/base-types/character-classes-in-regular-expressions#unicode-category-or-unicode-block-p" data-linktype="absolute-path">Match text in a Unicode category</a>. For more information about Unicode character classes, see <a href="https://www.unicode.org/versions/Unicode15.0.0/ch04.pdf#G39" data-linktype="external">Unicode Standard 15.0 Character Properties</a>.</td>
<td>\p{X}, where "X" is the Unicode number.</td>
<td><code>\p{Lu}</code> matches "T" and "D" in "Thomas Doe"</td>
</tr>
<tr>
<td><a href="/en-us/dotnet/standard/base-types/anchors-in-regular-expressions#word-boundary-b" data-linktype="absolute-path">Match a word boundary</a></td>
<td>\b (Outside a character class <code>\b</code> specifies a word boundary, and inside a character class <code>\b</code> specifies a backspace.)</td>
<td><code>\bin</code> matches "in" in "inside" but finds no matches in "pinto"</td>
</tr>
<tr>
<td>Match a line break (that is, a carriage return followed by a new line)</td>
<td>\r?\n</td>
<td><code>End\r?\nBegin</code> matches "End" and "Begin" only when "End" is the last string in a line and "Begin" is the first string in the next line</td>
</tr>
<tr>
<td>Match any <a href="/en-us/dotnet/standard/base-types/character-classes-in-regular-expressions#word-character-w" data-linktype="absolute-path">word character</a></td>
<td>\w</td>
<td><code>a\wd</code> matches "add" and "a1d" but not "a d"</td>
</tr>
<tr>
<td>Match any <a href="/en-us/dotnet/standard/base-types/character-classes-in-regular-expressions#whitespace-character-s" data-linktype="absolute-path">whitespace character</a></td>
<td>\s</td>
<td><code>Public\sInterface</code> matches the phrase "Public Interface"</td>
</tr>
<tr>
<td>Match any <a href="/en-us/dotnet/standard/base-types/character-classes-in-regular-expressions#decimal-digit-character-d" data-linktype="absolute-path">decimal digit character</a></td>
<td>\d</td>
<td><code>\d</code> matches "4" and "0" in "wd40"</td>
</tr>
</tbody>
</table></div>
