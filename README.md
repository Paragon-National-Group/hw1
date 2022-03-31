# HW1
This is the first programming assignment of the computer science track for Paragon National Group. The questions will cover the topics learned in the first lecture, which entailed print statements, various data types, variables, basic operations, and conditionals.

Carefully read over the specifications of each function that is given in the header description.

_Due Date: Apr 4th 2022 11:59pm_

# Installing Python
As mentioned during the lecture, we will only be using Python for this curriculum. Thus, having Python installed on your computer is essential. If you have not yet done so, then go to https://www.python.org/download/releases/3.0/ to download the latest version (Python 3.10.4).

To check whether you have the latest version for Python, run this command from the terminal:
```
$ python --version
```
The output should be Python 3.10.4. If it outputted a different version of python, it is fine, but it is recommended to update to the latest version.

# Git: Generating a SSH Key
The purpose of Git is to manage a project, or a set of files, as they change over time. Git stores this information in a data structure called a repository. A git repository contains, among other things, the following: A set of commit objects. A set of references to commit objects, called heads. We will be using GitHub Classrooms to manage the submission of assignments in the course. You'll need a github account to proceed.

We're first going to connect github to your login terminal. This involves creating a public and private key pair. This key pair helps to encrypt information that ensures data is protected during transmission. Private Key and public key are a part of encryption that encodes the information. Essentially, we create this key pair and keep the private key on our server and hand off the public key to Github.

To create an SSH key, run the following command from the terminal:
```
$ ssh-keygen
```
You will see the following prompt:
```
Generating public/private rsa key pair.
Enter file in which to save the key (/home/username/.ssh/id_rsa):
```

Press Enter (this will select the default file path shown in the prompt: ```/home/username/.ssh/id_rsa```)

Next, you will see this prompt:
```
Enter passphrase (empty for no passphrase):
```

Just press Enter here. You will be asked to confirm (just press Enter again):
```
Enter same passphrase again:
```

If all goes well, you should see something like this:
```
Your identification has been saved in /home/username/.ssh/id_rsa
Your public key has been saved in /home/username/.ssh/id_rsa.pub
The key fingerprint is:
SHA256:cBUUs2FeMCIrBlTyv/PGpBtNz0v235zvLykpoWIOS9I username@machine
The key's randomart image is:
+---[RSA 3072]----+
| .+.. . ..@+.    |
|   +   o = *     |
|    + o . o      |
|   . o o         |
|      . S        |
|   .   +.o.      |
|  . E ++..=. . . |
|   o o+++o.oo oo.|
|    .oo+. ...o.+O|
+----[SHA256]-----+
```

This means your key was created correctly.

**Note**

If, after pressing Enter to the prompt ```Enter file in which to save the key (/home/username/.ssh/id_rsa):```, you see the following message:
```
/home/username/.ssh/id_rsa already exists.
Overwrite (y/n)?
```
This means there is already an SSH key in your home directory. You should proceed as follows:

1. If you are already familiar with SSH keys, and know for certain that you’d like to use your existing SSH key, type “n” and skip ahead to the “Git: Uploading your SSH Key to GitHub” section below.

2. If you do not know why you have an SSH key in your directory, it’s possible it was created for you if you’ve taken a Computer Science course in the past. Type “n” and then run the following commands to create a backup of your existing key:

```
mv ~/.ssh/id_rsa ~/.ssh/id_rsa.bak
mv ~/.ssh/id_rsa.pub ~/.ssh/id_rsa.pub.bak
```

Then, re-run the ssh-keygen command, press Enter when prompted for the file name, and follow the rest of the instructions in this section.

# Git: Uploading your SSH Key to GitHub
Now, we need to instruct GitHub to accept our SSH key. To do this, log into https://github.com/ and go to your Settings page (by clicking on the top-right account icon, and then selecting “Settings” in the drop-down menu. Then, click on “SSH and GPG keys”.

Now, click on the green “New SSH key” button. This will take you to a page where you can upload your SSH key. You will be asked for two values: a “Title” and the key itself. The title can be anything you want, but we suggest something like “CS SSH Key”.

The value of the key is contained in the ```.ssh/id_rsa.pub``` file in your home directory. To print out the contents of that file, we can just use the ```cat``` command:
```
$ cat ~/.ssh/id_rsa.pub
```

This will print a few lines of output starting with ```ssh-rsa``` and ending in something like ```username@machine```. Copy the whole output to the clipboard; you can do this by clicking and dragging the mouse from the first character to the last character, and then pressing ```Ctrl-Shift-C```.

Then, paste the key into the “Key” field on the GitHub page. Then click on the green “Add SSH Key” button.

To verify that you correctly uploaded the key, try running the following command:
```
ssh -T git@github.com
```

You may see a message like this:
```
The authenticity of host 'github.com (...)' can't be established.
RSA key fingerprint is SHA256:nThbg6kXUpJWGl7E1IGOCspRomTxdCARLviKw6E5SY8.
Are you sure you want to continue connecting (yes/no)?
```

You can safely enter “yes” here. You should then see a message like this:
```
Hi username! You've successfully authenticated, but GitHub does
not provide shell access.
```

This means your SSH key is properly set up (don’t worry about the “does not provide shell access”; that is normal).

If you are unable to set up your SSH key, please make sure to ask for help. You will not be able to complete the rest of the homework until you’ve set up your SSH key.

# GitHub Classroom
Now, that we have everything ready, it is time to begin your first assignment. Each assignment will have a unique link. https://classroom.github.com/a/1Y1ksrPf is the link for this assignment. Once you "accept" the assignment, a pre-populated repository will be created for you with the assignment details. Once the repository is created, you will get a link that looks something like this:
```
https://github.com/Paragon-National-Group/hw1-john-hahn
```
You will need to clone this repository to your computer by running this line of code from the terminal (replace 'john-hahn' with your own name):
```
$ git clone git@github.com:Paragon-National-Group/hw1-john-hahn.git
```
Now you're ready to start the homework.

# Tasks
A skeleton is provided for each task, and your job is to fill it out. The parts where you need to fill it out is marked as "TODO".

**print_welcome_message**

This is the first task, which introduces the notion of print statements. This function prints out a sentence saying "Welcome to the start of the PNG CS track".

**split_change**

This is the second task, which introduces the notion of basic operations using integers. This function takes the number of cents as an argument and prints the best combination of quarters, dimes, nickels, and pennies in descending order of importance (i.e. 25 cents can be split into 25 pennies, but quarters is more important, thus it would be split into 1 quarter). Assume that the argument given is non-negative.

**concatenate_strings**

This is the third task, which uses basic operations again and introduces the notion of variables. This function takes two strings as arguments and returns the concatenated string. Assume that the strings provided do not have trailing or leading whitespaces. This means you have to add the whitespace in between the two strings yourself. The code MUST utilize variables.

**number_of_heads**

This is the last task, which introduces conditionals. This function takes five strings (the strings can only either be 'H', 'h', 'T', or 't') as arguments and returns the number of heads as an integer. Assume that no other strings can be inputted other than those four types.

# Submitting the Code
To submit your code, simply run the following steps:

```
git add hw1.py
```

```
git commit -m 'Submitted hw1'
```

```
git push
```

After committing the latest changes to your Github repository, submit your code through Gradescope.
