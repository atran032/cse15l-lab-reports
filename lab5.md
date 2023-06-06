# Lab Report 5
## The Problem
Hello! I have a problem using a bash script which runs an algorithm. I am using remote access to the UCSD lab. I am running Windows 11 on a laptop and using `ssh` via the VSCode terminal.

<img width="341" alt="image" src="https://github.com/atran032/cse15l-lab-reports/assets/130080125/ad5dd446-d862-4def-af2b-362cc9e2499b">

The expected output of `bash algorithm.sh 3 4 2` is "The result of 3 + 4 - 2 is 5." However, there is a syntax error in my code and the output is incomplete. It is detailed in the image.

<img width="258" alt="image" src="https://github.com/atran032/cse15l-lab-reports/assets/130080125/dde2aee0-21e6-4937-b805-8d9814c591cc">

This is the bash script in question. The purpose is to return the first and second numbers added, minus the third number. All of this was written using vim in the home directory of ieng6.

## The Response
Hi there! The bug you're having seems to be inside the bash script, rather than the input. Line 10 indicates this with `algorithm.sh: line 10: syntax error near unexpected token `('`
