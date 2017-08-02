# Leven - Levenshtein Automaton ANML Creation Program

The Levenshtein Automaton ANML Creation Program, *leven*, is a C++ progam that can generate Levenshtein automata giving a pattern string, *p*, and Levenshtein edit distance, *d*.

The *leven* executable creates a customized ANML file, named *leven.anml*, based on the command-line parameters this format:  
`leven <MODE> <string/file name/rand width> <edit dist> <rand DNA or alphanum> <random iterations>`

## Parameter Descriptions

### \<MODE>
This parameter specifies what mode you would like to use, '`s`' for **String**, '`f`' for **File**, or '`r`' for **Random**. (See below for more detailed  explaination of the different modes.)

### \<string/file name/rand width>
This parameter specifies either the string characters in **String mode**, the file name in **File mode**, or the width of the random string(s) to generate in **Random mode**.

### \<edit dist>
This parameter specifies the Levenshtein distance used when making the automata. The edit distance is the number of edits that a matching string can have and still count as a match. An *edit* is either an **insertion**, **substitution**, or **deletion**. This number **MUST** be smaller than the pattern string width. (If the pattern string width is equal to or smaller than the edit distance the resulting Levenshtein automaton will match **EVERY** input string, thus making it compltely useless.

If the pattern string is "*wahoo*" and the edit distance is *d=2* then words such as "*wah*" "*wahooes* "*hoos*" "*wallhoo*" etc would all match because they are each only two edits away from "*wahoo*". Other strings like "*wa*" "*oohs*" "*ah*" "oops" will not report a match. Neither will any string report a match that doesn't contain at least three characters from "*wahoo*" in the same order. For instance "*oohaw*" will not report as a match, but "*hoo*" will.

### \<rand DNA or alphanum>
This parameter only applies to **Random mode**, and specifies which random type to use - either **DNA** or **Alphanum**. String mode and File mode do not use this parameter.

>#### DNA type
>This **Random mode** type will make random pattern string(s) using the the four DNA nucleobases **A**(adenine), **T**(thymine), **G**(guanine), or **C**(cytosine).

>#### Alhpanum type
>This **Random mode** type will make random pattern string(s) using alpha-numeric characters consisting of 0-9 and A-Z (upper case and lower case) characters. 

### \<random iterations>
This parameter only applies to **Random mode**, and specifies how many iterations of Levenshtein automata the resulting ANML file will contain. 


## **Usage**

The program has three modes - **string**, **file**, and **random**. 

### **String mode**  
the arguments are in this format:  
`leven s <pattern string> <edit dist>` 

Example:  
>**leven s wahoo 2**

>This will make a Levenshtein automaton with p="wahoo" with edit distance of d=2.  
>This uses 5 STEs, one for each character, like this:    
>>**[(w)(a)(h)(o)(o)]**

<p align="center">
<img src="https://raw.githubusercontent.com/jeffudall/Levenshtein/master/Images/string%20wahoo%20d2%20test%20edit.png" width="605" height="130" alt="string_example_wahoo_d2">  
</p>

### **File mode**  
The **File mode** allows you to import a file with multiple pattern strings to be made into Levenshtein automata. The new line character delimiter separating each string. No spaces are allowed.  
The arguments for **File mode** are in this format:  
`leven f <pattern file name> <edit dist>`  

**Example**:  
>**leven f pattern.txt 2**  

>This will make a Levenshtein automaton for each line of chars in file, each with edit distance d=3.  
>If your `pattern.txt` file is:  
>>Bob  
>>Jones  
>>Karen  
>>Mary

>You will get four Levenshtein automata of various sizes, one for each line of text, like this:  
>>**(B)(o)(b)  
>>(J)(o)(n)(e)(s)  
>>(K)(a)(r)(e)(n)  
>>(M)(a)(r)(y)**

<p align="center">
<img src="https://raw.githubusercontent.com/jeffudall/Levenshtein/master/Images/file%20input%20test%20edit.png" width="605" height="180" alt="file_example">  
</p>

### **Random mode**  
The arguments for random mode are in this format:  
`leven r <width> <edit dist> <DNA or alphanum> <iterations>`  

**DNA Example**:  
>**leven r 5 2 DNA 5** 

>This will make five random Levenshtein automata, each five DNA chars long, with a edit distance of d=2 like this:  
>>**(G)(G)(A)(G)(A)   
>>(T)(C)(A)(G)(G)  
>>(C)(G)(A)(A)(C)  
>>(A)(G)(A)(A)(C)  
>>(G)(G)(C)(G)(G)**

<p align="center">
<img src="https://raw.githubusercontent.com/jeffudall/Levenshtein/master/Images/rand%20DNA%20test%20edit.png" width="605" height="170" alt="rand_dna">  
</p>

**Alpha-num Example**:
>**leven r 5 2 alphanum 5**  

>This will make five random Levenshtein automata, each five alpha-numeric chars long, with a edit distance of d=2  
>>**(5)(j)(p)(t)(N)  
>>(l)(b)(W)(e)(r)  
>>(9)(n)(V)(w)(5)  
>>(4)(d)(B)(q)(q)  
>>(0)(j)(g)(t)(e)**

<p align="center">
<img src="https://raw.githubusercontent.com/jeffudall/Levenshtein/master/Images/rand%20alphanum%20test%20edit.png" width="605" height="175" alt="rand_alphanum">  
</p>
