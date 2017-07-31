# Levenshtein

A Levenshtein automoton contains a pattern string (p) and a Levenshtein edit distance (d). Any input string that matches pattern string within the edit distance will report a match. A pattern string is used to populate the Levenshtein automaton STE's with characters. The edit distance is the number of edits - insert, substitute, or delete - that are allowed in any matchine string.

**Example:** 
>Let's say a given string pattern could is word "wahoo" and the Levenshtein edit distance is two. A Levenshtein automaton with this pattern and edit distance would look like Figure 1 below. The first number in each state's name is the column number, from zero to the number of characters; for "wahoo" this would be 0-5. The second number is number of edits, from 0 to the edit distance; for d=2 it would be 0-2.

<p align="center">
<img src="https://raw.githubusercontent.com/jeffudall/Levenshtein/master/Images/Levenshtein-automaton-sm.jpg" width="647" height="300" alt="state_wahoo_d2"> 
Figure 1 - Levenshtein automaton with string pattern s="wahoo" and edit distance of d=2. 
</p>

>Starting at the first state, 0.0 we feed in the first character of an input string. If the first character is "w" this would move the state to the right, to 1.0, indicating one character match step and zero edits. If it was a blank space this would move to the state right above, to 0.1, indicating it zero successful character steps and one deletion edit. If it was any other character it would move above and to the right, to 1.1, indicating one character step with one insertion or substitution edit. It would then continue on to examine the second character at the active state, either 1.0, 0.1, or 1.1, and move to the next state depending on if it gets a match(right), deletion(up), or insert/substitution(up and right). 

>If it reaches any of the states to the far right (any 5.X states) this indicates the input string (p) matches the given pattern string within the given edit distance (d). However, if it reaches the top level of the automaton (any of the X.2 states) and encounters a futher edit this will terminate it's movement through the Levenshtein automata, thus preventing a positive match.

## Automata Processor

In order to make a Levenshtein automaton using Micron's Automata Processor (AP) we must c


The Levenshtein program will accept a string or file of strings as input patterns. It will also create automatons with random patterns of DNA characters or alpha-numeric characters. When giving an input pattern and a distance 


## References

[1] Roy, Indranil, and Srinivas Aluru. "Finding motifs in biological sequences using the micron automata processor." Parallel and Distributed Processing Symposium, 2014 IEEE 28th International. IEEE, 2014.
