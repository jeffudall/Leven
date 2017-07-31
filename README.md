# Levenshtein

A Levenshtein automoton contains a pattern string (p) and a Levenshtein edit distance (d). Any input string that matches pattern string within the edit distance will report a match. A pattern string is used to populate the Levenshtein automaton STE's with characters. The edit distance is the number of edits - insert, substitute, or delete - that are allowed in any matchine string.

*For example:* A given string could be the word "wahoo". This would be used to populate the 


 <img src="https://raw.githubusercontent.com/jeffudall/Levenshtein/master/Images/Levenshtein-automaton.jpg" alt="Lev automaton p=whaoo d=2">


The Levenshtein program will accept a string or file of strings as input patterns. It will also create automatons with random patterns of DNA characters or alpha-numeric characters. When giving an input pattern and a distance 
