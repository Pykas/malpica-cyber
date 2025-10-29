# Linux Fundamentals #2 Tryhackme

In part 2, we'll be ditching the in-browser functionality and help you get started in what is a fundamental skill in being able to login to and control the terminals of remote machines. Not only this, but the room will also have you:

Unlocking the potential of your first few commands by introducing you to using flags and arguments
Advancing your knowledge of the filesystem to perform some more useful commands such as copying and moving files
Discovering how access to files and folders is managed and how we can determine our access.

Running your first few scripts and executables!

## How to login in a Linux remote machine

ssh = Secure shell
Allow us to execute commands on another device remotely
The data sent is encrypted

Exemple of connection: ss "User@ipdestino"
Then it ask for the password, once we put it it is done, we can execute commands in the remote computer/servercd

If i type a command + --help i will have all the commands for it

## Copy, create, delete and move files

Touch or mkdir to create folders and files

rm = remove files and folders
rm - r "foldername" 

Copying and Moving Files and Folders (cp, mv)

Copying and moving files is an important functionality on a Linux machine. Starting with cp, this command takes two arguments:

1. the name of the existing file

2. the name we wish to assign to the new file when copying

CP = To copy files and the content of the files

MV = To rename a folder or a document

Exemple
```
tryhackme@linux2:~$ mv note2 note3
tryhackme@linux2:~$ ls           
folder1 note note3
```
Using ls -lh to see all the permisions on the folders
```
tryhackme@linux2:~$ ls -lh
-rw-r--r-- 1 cmnatic cmnatic 0 Feb 19 10:37 file1
-rw-r--r-- 8 cmnatic cmnatic 0 Feb 19 10:37 file2
```
4th line is the owner of file and the manager

## Changing user in a Linux machine

Switching between users on a Linux install is easy work thanks to the su command. Unless you are the root user (or using root permissions through sudo), then you are required to know two things to facilitate this transition of user accounts:

The user we wish to switch to
The user's password
The su command takes a couple of switches that may be of relevance to you. For example, executing a command once you log in or specifying a specific shell to use. I encourage you to read the man page for su to find out more. However, I will cover the -l or --login switch.

Simply, by providing the -l switch to su, we start a shell that is much more similar to the actual user logging into the system - we inherit a lot more properties of the new user, i.e., environment variables and the likes. 

## Linux filesystem: quick reference

/etc — system configuration directory (network, services, user config). Not a command; it’s a path.
/etc — system configuration directory (network, services, user config). Not a command; it’s a path.

Important files:

/etc/sudoers — who can use sudo (edit only with sudo visudo).

/etc/passwd — user accounts (public info; passwords moved out).

/etc/shadow — password hashes (SHA-512); readable only by root.

/var — variable data (logs, caches, databases). Common: /var/log, /var/tmp.

/root — home directory for the root user. Only root can read/write by default.

/tmp — temporary directory, world-writable. Cleared on reboot on many systems; useful for transient files.

Why /etc alone does nothing

Typing a path like /etc in the shell is not a command. Use commands to interact with paths (e.g., ls, cd, cat, less).
