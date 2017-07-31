# Leven - Levenshtein Automaton ANML Creation Program

The Levenshtein Automaton ANML Creation Program, Leven, is a C++ progam that can generate Levenshtein automata giving a pattern string, p, and Levenshtein edit distance, d.


## Usage

leven OPTION string/file/width lev dist rand DNA or alphanum rand iterations

For STRING: leven s pattern string lev dist
Example: 
leven s wahoo 2
This will make a lev automaton w 5 STEs "(w)(a)(h)(o)(o) - with lev dist of 2

For FILE: leven f pattern file name lev dist
Example: 
leven f pattern.txt 3
This will make a lev automaton for each group of chars in file. A new line indicates a new automaton.
  
For RANDOM: leven r width lev dist DNA or alphanum iterations
Example: 
leven r 5 2 DNA 15
This will make 15 random lev automata each 5 DNA chars long with a lev dist of 2

Example: 
leven r 5 2 alphanum 2
This will make 2 random lev automata each 5 alpha-numeric chars long with a lev dist of 2
