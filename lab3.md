# Lab 3
## Researching Commands

The **grep** command is used to search text files and find lines which contain a given string. Here, we'll be exploring some of the interesting things you can do with **grep** and some ways you might use them. I give special thanks to ChatGPT for helping me find all four of the following.

First, the *or* operator can be used by typing a vertical bar between two strings. It must be formatted starting with a backslash with backslashes following every string. Surround all strings with a parenthesis and vertical bars in between, like so:
    
    $ grep "\(word1\|word2\)" file.txt
    
The or operator returns all lines which contain either the first string or the second.

    $ grep "\(accident\|driver\)" government/Alcohol_Problems/Session3-PDF.txt
        the medical conditions, accidents, and injuries that cause visits
        and accidents" to a 65% reduction in "accidental and violent
        ...
        alcohol health worker in an accident and emergency
        drinking, riding with a drinking driver, and drinking and driving.
    
It can also be used more than twice, in case you need to look for more than a pair of words.

    $ grep "\(serotonin\|ligand\|receptor\)" biomed/1471-2091-3-15.txt
        Sequence homology between the serotonin type 3 receptor
        receptor (nAChR), the GABA
        A receptor and the glycine receptor
        this superfamily of ligand gated ion channels [ 1 2 3 ] .
        ...
            
The or operator is practical for it's ability to search for related terms. For example, you may want to find lines containing "code" or "program." In such situations, **grep** and a vertical bar should be used.

Second, you can use the **-v** option to display only lines which do not contain a given string. 

    $ grep -v "word" file.txt
    
By putting **-v** after **grep**, you filter out any occurrence of that string.

    $ grep -v "\(Stutter\|stutter\)" plos/journal.pbio.0020046.txt
        centuries; earliest descriptions probably date back to the Biblical Moses' “slowness of
        in all cultures and ethnic groups (Andrews et al. 1983; Zimmermann et al. 1983), although
        prevalence might differ. Insofar as many of the steps in how we produce language normally
        genetic and neurobiological approaches are now giving us clues to causes and better
        treatments.
        ...
        
<!-- -->
        
        $ grep -v "t" biomed/1471-2105-3-24.txt
            disease.
            molecular basis of disease.
            10,243 SNPs by examining publicly available EST (Expressed
            polymorphisms [ 16 17 ] .
            conserved regions [ 18 ] . An analysis of homologous
            genes [ 21 ] .
            ...
            
The filter option allows you to omit particular words or phrases that may be irrelevant to your search. For example, you may be looking at a text file for research but, to make things for efficient, you filter out some terms.

Next, you can use the before and after options to show any amount of lines above and below the matching line.

    $ grep -B # -A # "word" file.txt
    
**-B** stands for "before" and **-A** stands for "after." The numbers indicate the amount of lines you want to display for each option. You can use one or the other or both at the same time.

    $ grep -B 1 -A 2 "Air Force" 911report/chapter-10.txt
            After the attacks had occurred, while crisis managers were still sorting out a number
                of unnerving false alarms, Air Force One flew to Barksdale Air Force Base in
                Louisiana. One of these alarms was of a reported threat against Air Force One
                itself, a threat eventually run down to a misunderstood communication in the hectic
                White House Situation Room that morning.
                ...
                
<!-- -->

    $ grep -B 2 "death" biomed/1468-6708-3-4.txt
      
        Introduction
        With the exception of counting deaths from all causes, a
--
        schedule and drop out of the study without further
        measurements. Possible reasons for patients dropping out of
        the study (the so-called 'withdrawals') include death,
        ...
        
The before and after options can be used to get a bit of context surrounding a particular line. Let's say you're doing research on a phrase but seeing the individual line wouldn't be helpful. Instead of manually searching for the context in the file, you can have some extra lines displayed with these options.

Instead of looking at just one file, grep can also perform some recursive searching with the **-r** and **include** options.

    $ grep -r --include="*.txt" "word" directory/
    
**-r** makes **grep** search recursively in the given directory, while **include** checks the files to see if they contain a matching extension. The "*\.txt"
