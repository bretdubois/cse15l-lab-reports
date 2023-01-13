# Lab 1 Report
## Configuring Course-Specific Remote Access

**Steps Required**
1. Installing VScode
2. Connect to Remote Server
3. Trying Some Commands

## Part I - Installing VScode
1. Follow the instructions to download and install VScode on your machine.
* [Official website for download](https://code.visualstudio.com/download)

2. Open Visual Studio Code and you should see the logo in the background with various menus/options.

## Part II - Remotely Connecting via SSH
1. If you're using Windows, install 'git' first: [Git](https://gitforwindows.org)
2. Obtain your course-specific username from [here](https://sdacs.ucsd.edu/~icc/index.php). **NEVER share your account information with anyone.**
3. Open the terminal in VSCode by going to **View > Terminal**.
4. In the new terminal, enter the command 'ssh [username]@ieng6.ucsd.edu' and press enter. Replace [username] with your ieng6 account username.

You're now ready to run commands on the remote computer using your course-specific account!

## Part III - Trying Some Commands
1. Once connected to the ieng6 server, you can run basic Linux commands such as 'ls', 'cd', and 'cat'.
2. Enter the command 'ls' to list files in the current directory.
3. Enter the command 'cd [directory]', using the name of the directory you want to navigate to instead of [directory].
4. Enter the command 'cat [file]', using the name of the file you want to view intstead of [file].

Try entering:
'cd /home/linux/ieng6/cs15lwi23/public'
'cat hello.txt'

This changes the directory to the 'public' folder and opens the 'hello.txt' file.
