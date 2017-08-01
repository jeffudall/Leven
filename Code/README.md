# Leven - Levenshtein Automaton ANML Creation Program

The Levenshtein Automaton ANML Creation Program, *leven*, is a C++ progam that can generate Levenshtein automata giving a pattern string, *p*, and Levenshtein edit distance, *d*.

The *leven* executable creates a customized ANML file, named *leven.anml*, based on the command-line arguments provided in this format:  
>*leven \<OPTION> \<string/file name/rand width> \<edit dist> \<rand DNA or alphanum> \<random iterations>*

## Parameter Descriptions

### \<OPTION>
This parameter specifies what mode you would like to use, **string**, **file**, or **random**. (See above fore explaination of the different modes.)

### \<string/file name/rand width>
This parameter specifies either the string characters in **String mode**, the file name in **File mode**, or the width of the random string(s) to generate in **Random mode**.

### \<edit dist>
This parameter specifies the Levenshtein distance used when making the automata. The edit distance is the number of edits that a matching string can have and still count as a match. An *edit* is either an **insertion**, **substitution**, or **deletion**. 

For instance, if the pattern string is "*wahoo*" and the edit distance is *d=2* then words such as "*wah*" "*wahooes* "*hoos*" "*wallhoo*" etc would all match because they are each only two edits away from "*wahoo*".

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
*leven s \<pattern string> \<edit dist>*  
Example:  
>**leven s wahoo 2**

This will make a Levenshtein automaton with p="wahoo" with edit distance of d=2.  
This uses 5 STEs, one for each character, like this:    
>**[(w)(a)(h)(o)(o)]**

### **File mode**  
The arguments for file mode are in this format:  
*leven f \<pattern file name> \<edit dist>*  
Example:  
>**leven f pattern.txt 3**  

This will make a Levenshtein automaton for each line of chars in file, each with edit distance d=3.  
If your *pattern.txt* file is:  
>Bob  
>Jones  
>Karen  
>Mary

You will get four Levenshtein automata of various sizes, one for each line of text, like this:  
>**(B)(o)(b)  
>(J)(o)(n)(e)(s)  
>(K)(a)(r)(e)(n)  
>(M)(a)(r)(y)**
  
### **Random mode**  
The arguments for random mode are in this format:  
*leven r \<width> \<edit dist> \<DNA or alphanum> \<iterations>*   
**DNA Example**:  
>**leven r 5 2 DNA 5** 

This will make five random Levenshtein automata, each 5 DNA chars long, with a edit distance of d=2 like this:  
>**(A)(T)(G)(G)(C)  
>(G)(T)(A)(G)(A)  
>(T)(C)(A)(G)(G)  
>(C)(G)(A)(T)(C)  
>(T)(G)(A)(A)(C)  
>(G)(G)(C)(A)(T)**

**Alpha-num Example**:
>**leven r 5 2 alphanum 2**  

This will make two random Levenshtein automata, each five alpha-numeric chars long, with a edit distance of d=2  
>**(6)(h)(l)(8)(p)  
>(o)(N)(i)(d)(M)**
