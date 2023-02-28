# Lab 4 - Improving CLI/Bash Workflow Efficiency with Shortcuts
In this week's lab, we explored some essential bash shortcuts that can help improve productivity and efficiency while working in the command line interface.

### Useful shortcuts
1. Bash history: Use the up and down arrow keys to navigate through recently used commands.
2. `<Ctrl+R>`: Allows for searching for specified commands within the previously used commands.
3. Using `<Tab>`: The Tab key can be used to auto-complete the possible options when typing only the first few letters of a command and its options.

### Useful Key Combinations
1. `<Ctrl+A>`: Move the cursor to the beginning of the line.
2. `<Ctrl+E>`: Move the cursor to the end of the line.
3. `<Ctrl+U>`: Delete all characters before the cursor.
4. `<Ctrl+K>`: Delete all characters after the cursor.
5. `<Ctrl+W>`: Delete the word before the cursor.
6. `<Ctrl+L>`: Clear the terminal screen.
7. `<Alt|Option+Left>` and `<Alt|Option+Right>`: Moves cursor one word at a time instead of each character at a time.

### Generating SSH Keys
For password-secured remote machines that are accessed often, generating an SSH key will help speed up the workflow.
1. In your local bash instance, run `ssh-keygen` and then continue pressing `<Enter>` until the imageart appears.
2. Note the path in which the public key file (.pub) is saved.
3. Login to the remote machine and run `mkdir .ssh` in the terminal.
4. Logout of the remote machine.
5. Now on the local machine, use the `scp` command to copy the public key to the remote machine as a file called `authorized-keys`:
6. `scp <path to your public SSH key> <username>@<domain>:~/.ssh/authorized_keys`
7. You will be prompted for a password for the last time if performed correctly!

### Generating SSH Key for GitHub
This will outline how to add an SSH key to GitHub for cloning and pushing using the CLI.
1. Login to the local or remote machine you'd like to use with GitHub.
2. Run `ssh-keygen` and press enter until the "randomart" image appears.
3. Copy the path to the `.pub` public key file.
4. Run `cat <path to ssh key .pub file>.
5. Login to your GitHub account and navigate to the Settings page.
6. Within the Access section of the sidebar, select the SSH and GPG keys menu.
7. Click on `New/Add SSH Key` and enter a title for the machine being used.
8. Select the `Key Type` to be an Authentication Key.
9. Paste the key output from the `cat` command used earlier into the `Key` field.
10. Confirm GitHub account access if prompted.
11. In the terminal, run `ssh-keyscan -t rsa github.com >> ~/.ssh/known_hosts` to add the machine as a recognized host.
12. Check the terminal connection with `ssh -T git@github.com`

## CSE Labs Done Faster
Here is how I utilized some of these shortcuts with the week 7 lab exercise.
### Steps Required:
1. Log into ieng6
2. Clone your fork of the repository from your Github account
3. Run the tests, demonstrating that they fail
4. Edit the code file to fix the failing test
5. Run the tests, demonstrating that they now succeed
6. Commit and push the resulting change to your Github account

### 1. Log into ieng6
Opened a new Bash window and pressed `<up>` in my terminal since the last thing I used bash for was logging in to ieng6:
`ssh <username>@<domain>` then press `<Enter>`.

<img width="508" alt="Screenshot 2023-02-26 at 5 31 26 PM" src="https://user-images.githubusercontent.com/122574417/221452018-21e38a64-ec7b-4568-bdf5-e2c1f4129bc2.png">


### 2. Clone your fork of the repository
Since I had already cloned my fork of the repository previously, I pressed `<Ctrl+R>` to search and then typed `git c<Enter>` to auto-complete the full command: `git clone git@github.com:bretdubois/lab7.git`

<img width="587" alt="Screenshot 2023-02-27 at 6 03 30 PM" src="https://user-images.githubusercontent.com/122574417/221734144-a4031d40-a9ca-4722-b0fa-82b660a2f0c2.png">


### 3. Run the tests, demonstrating that they fail
I navigated to lab7 with `cd lab7` and `ls` to show the files it contains.
Using `<Ctrl+R>` I searched `javac -cp` and pressed `<up><enter>` to select `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java`
Then I used `<Ctrl+R>` to reverse search again by typing `java<Space>` and then pressing `<Enter>`.
The full command is `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests`

<img width="941" alt="Screenshot 2023-02-27 at 7 15 35 PM" src="https://user-images.githubusercontent.com/122574417/221744528-f8fa1c4b-af41-4ada-aaef-c92ad10bdeab.png">


### 4. Edit the code file to fix the failing test
To edit the code file, I pressed `nano L<Tab>.java<Enter>`.
Then, I used `<Ctrl+W>` to search `< 0<Enter>` then `<right>=`.
Finally, I did `<Ctrl+W>return result<Enter><up><up><right><right><right><right><right><right><right><delete>2`.

<img width="931" alt="Screenshot 2023-02-27 at 6 37 25 PM" src="https://user-images.githubusercontent.com/122574417/221739070-6b17fd4f-3074-437f-9e99-83c3753dd267.png">

Then `<Ctrl+O><Enter><Ctrl+X>` to save and exit.

### 5. Rerun the tests, demonstrating that they now succeed
To run the JUnit tests again, I first compiled `ListExamples.java` with `javac L<Tab>.j<Tab>`.
Then I pressed `<up><up><up><Enter>` to navigate through my previous bash history and select the appropriate command: `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests`

<img width="945" alt="Screenshot 2023-02-27 at 6 39 35 PM" src="https://user-images.githubusercontent.com/122574417/221739387-be8d703f-65a8-4a72-a75e-2a85c44747aa.png">

### 6. Commit and push the resulting changes to your GitHub account
To commit and push the resulting changes, I entered:
`git init` and added with `git add L<Tab>.j<Tab>`
Then `git commit -m "Fixed failing JUnit tests"`
And finally `git push origin main`
<img width="778" alt="Screenshot 2023-02-27 at 6 55 25 PM" src="https://user-images.githubusercontent.com/122574417/221742848-53fb9d20-84b0-4a65-bdff-1ce23f83cb99.png">







