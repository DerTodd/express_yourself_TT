# express_yourself_TT

So, you have seached the internet and finally found the end of it.  You should feel a sense of accomplishment.  Few have achieved such a lofty goal, but I warn you I'd wait a little longer, take a break, maybe a brief nap and then search some more.  New things are constantly added! However, if you are desperate and want to finish the internet as it currently stands, keep reading.



## Summary

Let's face it, we live in a lazy world where saying Federal Express is too much to ask.  We need to save that sweet time by shortening it to FedEX.  Relish the amount of time you just saved.  Now, let's repeat that process.  Think "Regular Expression."  Well, that is just too long and might not sound like you know enough jargon. So, lets just say "regex." I'll let your goosebumps subside before I continue this sweet, sweet essay.

Why you are still reading, I cannot fully comprehend, but we will press on together.  I just hope you are getting paid to read this because your mind is about to be blown.  We will write regular expression expressions.  I think we can see why we needed to shorten the first part.  It's like going to The Country's Best Yogurt yogurt, but I digress.

A regexex is simply a way to search.  The expression can make sure that words are spelled correctly or meet the input validation for a certain field that a user, ummm, inputs data in.

You want to make sure that is an email address! Bam, this is the tool for you!

        Example :  Regular expression for an email address :
        ^([a-zA-Z0-9_\-\.]+)@([a-zA-Z0-9_\-\.]+)\.(edu{3})$
        ^
The caret indicates that the match will start at the beginning of the expression
        ([a-zA-Z0-9_\-\.]+)
The brackets establish the characher set.  It can contain any letter from a-z as well as A-Z.  It can have any digit, and can have underscores as well as dashes or periods.  The plus says that it has to have atleast one of the tokens. The parentheses groups these together
        @
Matches the @ symbol
        ([a-zA-Z0-9_\-\.]+)
The brackets establish the characher set.  It can contain any letter from a-z as well as A-Z.  It can have any digit, and can have underscores as well as dashes or periods.  The plus says that it has to have atleast one of the tokens. The parentheses groups these together
        \.
The period is Escaped out and loses it's magic.  It is simply saying that there has to be a period.
        (edu{3})
Group that sets the last three characters as an exact match of an edu account.  The curly brackets state that it must match 3 of the proceeding characters. The parentheses groups these together
        $
End of the match.

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
Regular Expressions are made up of Special Charaters, Anchors, Assertions, Groups, Brackets, Quantifiers... Basically all the stuff in the TOC! More of what they actually are follows!

### Anchors
Anchors are used to match the beginning with a caret, the end with a dollar sign, or any word boundary with the backslash and b
^([a-zA-Z0-9_\-\.]+)@([a-zA-Z0-9_\-\.]+)\.(edu{3})$
The email is checked from the first caret to the ending $.  

### Quantifiers
They tell us what to match or how many of each are required
Question Mark- matches zero or one of the proceding
Asterisk- matches zero or more
Plus- matches one of more
These create an exact numberical match, a min, or a range placed between braces
{3}- exactly 3
{3,}- A minimum of 3
{3,5}- A minimum of 3 but a maximum of 5
^([a-zA-Z0-9_\-\.]+)@([a-zA-Z0-9_\-\.]+)\.(edu{3})$
(edu{3})
While looking at the email, we check and confirm that the address is an edu account.  The last 3 letters have to match "edu."

### Grouping Constructs
() Set up a capturing group of tokens
Square brackets set up a grouping or range of tokens
[a-zA-Z] range can contain any letter of any case
Parentheses create a sequence
([a-zA-Z0-9_\-\.]+) the group can contain any of the characters as well as the requirement add by the plus to the group that it must have at least one token
^([a-zA-Z0-9_\-\.]+)@([a-zA-Z0-9_\-\.]+)\.(edu{3})$
For the email, there is a minimum length of one character before the @ sign.  
a-z allows for any lower case letter
A-Z allows for any upper case letter
0-9 allows for any number
_ for underscores
 \- We have to escape out the plus sign and the dash so they can be used as characters in the email address.
. for the period

### Bracket Expressions
brackets allow for matching anything within them.  [mt]ile would allow for the words mile or tile.  For a number match 5[45] would allow for 54 or 55.  
If a caret is added, it negates the matches [^t] don't allow t
[.] The dot also loses its metacharacter abilities when it is in serch function 
If you need the caret of the - in the bracket, include these at the end [a-z^-]
^([a-zA-Z0-9_\-\.]+)@([a-zA-Z0-9_\-\.]+)\.(edu{3})$
For the email, we have three brackets that allow for the matching of the above criteria. 
([This allows for a unique name]) @ ([a domain ])and finally the .(edu )

### Character Classes
These are all preceded by a "/" and they are used to match any one of a set of charactes.  They can match letters, digits, and elements in a string including spaces and symbols.
/b:  This is used to match anything that surrounds words.  It can include the following -,.";:
/d:  d is for digits. It matches any digit
/D:  The big D and I don't mean Dallas does the opposit of the small d.  It will match any chacater that isn't a digit.
/s:  s is for spaces.  It will match whitespaces left by the spacebar and tab.
/S:  The opposite of the small s matches anything that isn't whitespace.
/w:  w is for word to your mother.  It matches any character that could be in a word 
/W:  The big W is the opposite of the small w.  It will match anything that isn't something that would be found in a word.  
Character classes are also character sets inside of brackets.  
[ae]allows for matching of either an a or e
[^ae] negates characters so it won't match either a or e
[a-e] aimilar to [a-z] would allow for matches in the range

### The OR Operator
The OR operator is the straight line.  It is an alternation checks to make sure the expression before or after it matches. It doesn't always produce the desired results.  It is usually used with strings to give the or option.
he(llo|lp) would match either help or hello
|
^([a-zA-Z0-9_\-\.]+)@([a-zA-Z0-9_\-\.]+)\.(edu{3})$
The email does not contain an OR operator

### Flags
Flags are used to change regular expression search behaviors. They can be grouped toghther in any order 
If you add the flag of i to the end, the search will not be case sensitive.
If you add the flag of g to the end, the results will show all the occurances for the seach and not just the first one. 
^([a-zA-Z0-9_\-\.]+)@([a-zA-Z0-9_\-\.]+)\.(edu{3})$
The email does not contain any flags 

### Character Escapes
So how can one search for a character that has the special powers of a bracket, caret, plus symbol or asterisk!  Well, they have thought of it all.  You just need to slap the ESCAPE symbol infront.  Backslash is the kyptonite of the magical characters.  All their powers are removed!
Need to search for mathmatical expressions \+ \- 
^([a-zA-Z0-9_\-\.]+)@([a-zA-Z0-9_\-\.]+)\.(edu{3})$
The email escapes out the dash so it can be recognized simply as a character instead of a metacharacter

## Author

Todd is a very tired individual who writes these things to amuse himself!  Maybe it causes others to laugh along the way.
https://github.com/DerTodd/

some resources for better information!
wikipidea, geeks for geeks, liquid Web, codeguage, and keycdn were used as references
Test your regexex at 
https://regexr.com

