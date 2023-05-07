# Lab 3
## Researching Commands

The **grep** command is used to search text files and find lines which contain a given string. Here, we'll be exploring some of the interesting things you can do with **grep** and some ways you might use them. I give special thanks to ChatGPT for helping me find all of the following.

First, the *or* operator can be used by typing a vertical bar (|) between two strings. It must be formatted starting with a backslash (\\) with backslashes following every string. Surround all strings with a parenthesis and vertical bars in between, like so:
    
    $ grep "\(word1\|word2\)" file.txt
    
The *or* operator returns all lines which contain either the first string or the second.

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
            
The *or* operator is practical for it's ability to search for related terms. For example, you may want to find lines containing "code" or "program." In such situations, **grep** and **|** should be used.

Second, you can use the **-v** option to display only lines which do not contain a given string. 

    $ grep -v "word" file.txt
    
By putting **-v** after **grep**, you filter out any occurrence of that string.

    $ 
