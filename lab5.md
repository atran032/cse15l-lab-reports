# Lab Report 5
## The Problem
Hello! I have a problem using a bash script which runs an algorithm. I am using remote access to the UCSD lab. I am running Windows 11 on a laptop and using `ssh` via the VSCode terminal.

<img width="341" alt="image" src="https://github.com/atran032/cse15l-lab-reports/assets/130080125/ad5dd446-d862-4def-af2b-362cc9e2499b">

The expected output of `bash algorithm.sh 3 4 2` is "The result of 3 + 4 - 2 is 5." However, there is a syntax error in my code and the output is incomplete. It is detailed in the image.

<img width="258" alt="image" src="https://github.com/atran032/cse15l-lab-reports/assets/130080125/dde2aee0-21e6-4937-b805-8d9814c591cc">

This is the bash script in question. The purpose is to return the first and second numbers added, minus the third number. All of this was written using vim in the home directory of ieng6.

## The Response
Hi there! The bug you're having seems to be inside the bash script, rather than the input. Line 10 indicates this with `algorithm.sh: line 10: syntax error near unexpected token ('` In your bash script, you are missing a `$` on line 10 after the equal sign, indicating that it is a variable. Inserting it should do the trick.

## The Bug
Thanks! That fixed the problem. THe bug was a syntax error caused by a missing `$` sign to assign a value to `output`. Therefore, when the last line ran, output had no value and it printed and empty string.

<img width="257" alt="image" src="https://github.com/atran032/cse15l-lab-reports/assets/130080125/d96aa490-06e7-4cb2-a961-22f262de0a5f">

Now it's producing the correct result.

<img width="303" alt="image" src="https://github.com/atran032/cse15l-lab-reports/assets/130080125/f5cd4270-4754-4bc0-b9c0-8837825a616c">

Overall, the only error was produced by a fault in the code, rather than anything having to do with input or directories. By looking at the error message, the location of the error, line 10 was deduced, along with it being near the `(`. Knowing the functionality of `$` in bash scripts helped resolve the issue and the code ended up working as intended.

## Reflection
I really enjoyed learning about bash scripts. I thought they were initially hard to pick up due to having a different set of syntax rules and functions. However, I saw their utility and look forward to using them more in the future. Additionally, I thought `vim` was enjoyable to use. Sure, it's not as good as using a UI like VSCode, but it's functional and has a lot more commands than I initially assumed.
