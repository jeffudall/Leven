# Levenshtein

A Levenshtein automoton contains a pattern string (p) and a Levenshtein edit distance (d). Any input string that matches pattern string within the edit distance will report a match. A pattern string is used to populate the Levenshtein automaton STE's with characters. The edit distance is the number of edits - insert, substitute, or delete - that are allowed in any matchine string.

>*For example:* A given string pattern could be the word "wahoo" and have an edit distance of two. A Levenshtein automaton with this pattern and edit distance would be Figure 1 below. The first number in each state's name is the column number, from zero to the number of characters; for "wahoo" this would be 0-5. The second number is number of edits, from 0 to the edit distance; for d=2 it would be 0-2.

> > <img src="https://raw.githubusercontent.com/jeffudall/Levenshtein/master/Images/Levenshtein-automaton-sm.jpg" width="647" height="300">

>Starting at the first state, 0.0 we feed in the first character of an input string. If the first character is "w" this would move the state to the right, to 1.0, indicating one character match step and zero edits. If it was a blank space this would move to the state right above, to 0.1, indicating it zero successful character steps and one deletion edit. If it was any other character it would move above and to the right, to 1.1, indicating one character step with one insertion or substitution edit. It would then continue on to examine the second character at the active state, either 1.0, 0.1, or 1.1, and move to the next state depending on if it gets a match(right), deletion(up), or insert/substitution(up and right). 

>If it reaches any of the states to the far right (any 5.X states) this indicates the input string (p) matches the given pattern string within the given edit distance (d). However, if it reaches the top level of the automaton (any of the X.2 states) and encounters a futher edit this will terminate it's movement through the Levenshtein automata, thus preventing a positive match.




The Levenshtein program will accept a string or file of strings as input patterns. It will also create automatons with random patterns of DNA characters or alpha-numeric characters. When giving an input pattern and a distance 
