# Leven - Levenshtein Automaton ANML Creation Program

The Levenshtein Automaton ANML Creation Program, *Leven*, is a C++ progam that can generate Levenshtein automata giving a pattern string, *p*, and Levenshtein edit distance, *d*.


    cout <<"\n  USAGE:  "
	<< argv << " [OPTION] [string/file/width] [lev dist] [rand DNA or alphanum] [rand iterations]"<< endl;

    cout <<"\n  For STRING:\t"<< argv <<" s [pattern string] [lev dist]"<< endl;
    cout <<"     example:\t"<< argv <<" s wahoo 2 "<< endl;
    cout <<"\t\t"<< "This will make a lev automaton w 5 STEs"<< endl;
    cout <<"\t\t"<< "(w)(a)(h)(o)(o) - with lev dist of 2"<< endl;

    cout <<"\n    For FILE:\t"<< argv <<" f [pattern file name] [lev dist]"<< endl;
    cout <<"     example:\t"<< argv <<" f pattern.txt 3"<< endl;
    cout <<"\t\t"<< "This will make a lev automaton for each group of chars in file"<< endl;
    cout <<"\t\t"<< "New line indicates a new automaton"<< endl;

    cout <<"\n  For RANDOM:\t"<< argv <<" r [width] [lev dist] [DNA or alphanum] [iterations]"<< endl;
    cout <<"     example:\t"<< argv <<" r 5 2 DNA 15"<< endl;
    cout <<"\t\t"<< "This will make 15 random lev automata"<< endl;
    cout <<"\t\t"<< "each 5 DNA chars long with a lev dist of 2"<< endl;
    cout <<"     example:\t"<< argv <<" r 5 2 alphanum 2"<< endl;
    cout <<"\t\t"<< "This will make 2 random lev automata"<< endl;
    cout <<"\t\t"<< "each 5 alpha-numeric chars long with a lev dist of 2"<< endl;
