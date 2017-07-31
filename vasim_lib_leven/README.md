# Leven - Levenshtein Automaton ANML Creation Program

The Levenshtein Automaton ANML Creation Program, *Leven*, is a C++ progam that can generate Levenshtein automata giving a pattern string, *p*, and Levenshtein edit distance, *d*.


## Usage

leven [OPTION] [string/file/width] [lev dist] [rand DNA or alphanum] [rand iterations]

For STRING: **leven s [pattern string] \[lev dist]**
<br />Example: 
>**leven s wahoo 2**
<p><br />This will make a lev automaton w 5 STEs "(w)(a)(h)(o)(o) - with lev dist of 2</p>

<br />or FILE: **leven f [pattern file name] [lev dist]**
<br />Example: 
>**leven f pattern.txt 3**
<p><br />This will make a lev automaton for each group of chars in file. A new line indicates a new automaton.</p>
  
<br />For RANDOM: **leven r [width] \[lev dist] [DNA or alphanum] [iterations]**
<br />Example: 
>**leven r 5 2 DNA 15**
<p><br />This will make 15 random lev automata each 5 DNA chars long with a lev dist of 2</p>

<br /><br />Example: 
>**leven r 5 2 alphanum 2**
<p><br />This will make 2 random lev automata each 5 alpha-numeric chars long with a lev dist of 2</p>

