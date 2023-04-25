# Lab Report 1
![server](https://user-images.githubusercontent.com/130080125/230830067-2c4f8dbf-1908-4225-b602-a637340358f2.gif)

So you want to remotely access a server? Then you've come to the right place! Remote access allows you to run commands on computers other than your own. This can be done in 3 easy steps.
## Installing VSCode
Visual Studio Code is Microsoft's own app for editing code and running commands. It can be installed from [VSCode](https://code.visualstudio.com/) by following the provided instructions. If you already have VSCode installed as well as Git for Windows, you can skip this step.

<img width="947" alt="image" src="https://user-images.githubusercontent.com/130080125/230801635-0adf6903-efd0-44a9-a300-3dbaff5a9ce0.png">

Upon opening VSCode, you should be greeted with a welcome page helping you navigate folders and open files. From here, we proceed to our next step.

<img width="960" alt="image" src="https://user-images.githubusercontent.com/130080125/230801516-0a597c47-32d2-4483-adf4-d42392e21dcb.png">

To use remote access, you also need to install [Git for Windows](https://gitforwindows.org/). Follow the instructions on the installer and you're all set. 

<img width="946" alt="image" src="https://user-images.githubusercontent.com/130080125/230801805-fc73febb-f122-4ed6-8c42-586a84ebe909.png">

## Remotely Connecting
In order to access the server, you need to know your account name and password. You can find it at [Education Technology Services](https://sdacs.ucsd.edu/~icc/index.php) using the account lookup feature. 
<img width="947" alt="image" src="https://user-images.githubusercontent.com/130080125/230801311-d7e8e9d6-7342-46c0-92f9-b1be73a02b9b.png">
Enter your username and student ID and proceed. Under **Additional Accounts**, look for the account starting with *cs15lsp23*. Remember the final two letters, which make your account unique. You must also have a password set using the indicated using the indicated tool.

<img width="911" alt="image" src="https://user-images.githubusercontent.com/130080125/230801423-8d6b0a3e-39ed-4f9a-8c87-bd1dc5bacf22.png">

Your username and password will be used to achieve remote access. Return to VSCode and click *Terminal* at the top, then *New Terminal*. Type **ssh cs15lsp23zz@ieng6.edu** where **zz** is replaced by your unique letters and hit enter. If it's your first time connecting it will ask you to verify that you want to proceed, which you should respond *yes*. 

<img width="281" alt="image" src="https://user-images.githubusercontent.com/130080125/230802063-794ba64b-5c68-4a7f-ab7f-a97c14a498ba.png">

Lastly, it will prompt you for your password. Though you can't see it, type it and press enter. Congratulations! You're logged into a server.

<img width="384" alt="image" src="https://user-images.githubusercontent.com/130080125/230802116-195c5443-25ad-420c-8497-93c67a410873.png">

## Running Commands
While on the server, you can use a variety of commands to view and manipulate your directory. Enter *pwd* to view your current directory or *ls* to view files contained within it. You can also use the *cat* command to print a Hello message!

<img width="581" alt="image" src="https://user-images.githubusercontent.com/130080125/230831621-633948f4-e1b5-482d-b637-02d4d772b29b.png">

The commands *ls -lat* and *ls -a* also print some rather cryptic information. Lastly, to close the server, type *exit*. Congrats! Now you know how to remotely access a server and run some commands in it.
