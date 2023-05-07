# Lab 3
## Researching Commands

The **grep** command is used to search text files and find lines which contain a given string. Here, we'll be exploring some of the interesting things you can do with **grep** and some ways you might use them.

First, the *or* operator can be used by typing a vertical bar, **|**, between two strings. It must be formatted starting with a backslash, **\\**, with backslashes following every string. Surround all strings with a parenthesis and vertical bars in between, like so:
    
    $ grep "\(word1\|word2\)" file.txt
    
The *or* operator returns all lines which contain either the first string or the second.

    $ grep "\(alcohol\|drinking\)" government/Alcohol_Problems/Session3-PDF.txt
    the medical conditions, accidents, and injuries that cause visits
    and accidents" to a 65% reduction in "accidental and violent
    ...
    alcohol health worker in an accident and emergency
    drinking, riding with a drinking driver, and drinking and driving.
    
It can also be used more than twice, in case you need to look for more than a pair of words.
