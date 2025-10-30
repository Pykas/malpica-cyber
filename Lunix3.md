## What i did in this class

Launching a Linux machine
Login in with the credentials and IP address 

```
ssh tryhackme@#IP
Yes
Password
```
### Terminal text editors
nano VIM

#### Nano
It is easy to get started with Nano! To create or edit a file using nano, we simply use nano filename -- replacing "filename" with the name of the file you wish to edit.
Used to modify text in the terminal
If the document don't exist, it will create it

```
nano #file
```
Vim is better but more complex

### Downloading and transfering files
wget is to dowload directly from the web, from a known website

```
wget archivo.com/desgarga/loco.zip
```

SCP is between 2 computers with ssh
Exemple
```
scp important.txt ubuntu@192.168.1.30:/home/ubuntu/transferred.txt
```

### How to start a webserver
```
python3 -m  http.server
```
The server will give you Ip and in which port it is running

From there, you can dowload files from it if they are available
For exemple
```
wget http://10.10.127.76:8000/myfile
```

To see proceses we use the ps command
If we add some more like aux, we can see the totality of the program
Top is another way to see them

## Managing Processes

You can send signals that terminate processes; there are a variety of types of signals that correlate to exactly how "cleanly" the process is dealt with by the kernel. To kill a command, we can use the appropriately named kill command and the associated PID that we wish to kill. i.e., to kill PID 1337, we'd use kill 1337.

Below are some of the signals that we can send to a process when it is killed:

SIGTERM - Kill the process, but allow it to do some cleanup tasks beforehand
SIGKILL - Kill the process - doesn't do any cleanup after the fact
SIGSTOP - Stop/suspend a process

How to get services to start on boot

```
systemctl [option] [service]
systemctl start apache2

```
We can do four options with systemctl:

Start
Stop
Enable
Disable

The commands are exaactly like the words

## 🕒 Introduction to Cron and Crontab (Linux)

Cron is a built-in Linux service used to run tasks automatically at specific times or intervals — for example, running commands, creating backups, or launching apps after boot.

🔹 What is a Crontab?

A crontab (short for cron table) is a special file that lists commands for the cron process to execute on a schedule.
Each line in the crontab represents one scheduled task.

🔹 Crontab Format

Every line follows this structure:

MIN  HOUR  DOM  MON  DOW  CMD

Field	Meaning
MIN	Minute (0–59)
HOUR	Hour (0–23)
DOM	Day of the month (1–31)
MON	Month (1–12)
DOW	Day of the week (0–6, Sunday = 0)
CMD	The command to execute

The * (asterisk) means “every” or “any value”.

🔹 Example
0 */12 * * * cp -R /home/cmnatic/Documents /var/backups/


This means:

Run the command every 12 hours, at minute 0, to copy the “Documents” folder into “/var/backups/”.

🔹 Managing Crontabs

View / Edit your crontab

crontab -e


This opens the crontab in an editor (like Nano). Add your scheduled lines there.

List existing jobs

crontab -l


Cron will automatically execute your commands according to the schedule — as long as your system is running.

🔹 Helpful Tools

If you’re unsure about the syntax, try:

Crontab Generator

Cron Guru

Summary

cron → the background service that runs tasks.

crontab → the configuration file where tasks are defined.

* → means “every possible value”.

crontab -e → open and edit your scheduled jobs.
