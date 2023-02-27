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
Now we'll put it together with the week 7 lab exercise.
### Steps Required:
1. Log into ieng6
2. Clone your fork of the repository from your Github account
3. Run the tests, demonstrating that they fail
4. Edit the code file to fix the failing test
5. Run the tests, demonstrating that they now succeed
6. Commit and push the resulting change to your Github account

### Log into ieng6
Open a new Bash window and enter `ssh <username>@<domain>` then press `<Enter>`.
<img width="508" alt="Screenshot 2023-02-26 at 5 31 26 PM" src="https://user-images.githubusercontent.com/122574417/221452018-21e38a64-ec7b-4568-bdf5-e2c1f4129bc2.png">

## Clone your fork of the repository




