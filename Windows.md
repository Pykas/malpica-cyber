# Windows

This course reminds me how to use Windows in a more administrative ways

We go throught the user names, how to use the OS in a more admin point of viwe
Permissions, remote control, accounts, etc

To view accounts we con go through run and text lusrmgr.msc, is the most efficient way to see the acocunts, their groups and descriptions, also to modify them
Use Wireshark to improve the managing of the account in the computer and more security

Task manager can be accesed by pressing CTRL+SHIFT+ESC

## Windows command line
```
set

ver = To know the exact Windwos version running

systeminfo = To know our computer and all its specs

```
First, you can pipe it through more if the output is too long. Then, you can view it page after page by pressing the space bar button. To demonstrate this, try running driverquery and compare it with running driverquery | more. In the latter, you can display the output page by page and you can exit it using CTRL + C.

help - Provides help information for a specific command
cls - Clears the Command Prompt screen.

More common and useful commands in CMD

```
IPconfig = To know the ip of the computer, you can add /all for more information
tracert and ping = To check the network availability
nslookup = To lookup the comain fo the computer where it is attached
netstat = Show networks connections and listening ports
   -a displays all established connections and listening ports
   -b shows the program associated with each listening port and established connection
   -o reveals the process ID (PID) associated with the connection
   -n uses a numerical form for addresses and port number
netstat -abon
```

Ports are in the Local Adress part, when we use the netstat command
Exemple : 0.0.0.0:125 here (125) will be the port listening

```
cd works thje same as in Linux
dir will be the equivalent of ls
mkdir + name to create folder
move + name to move the file
copy + name to create the file
type + filename to open files in TXT in Powershell or CMD
tasklist = to see the task manager in the terminal
tasklist /FI(Filter) "#name of the process "imagename eq #Process = to s the specific PID of those
taskkill /PID #TargetPID to end processes
chkdsk: checks the file system and disk volumes for errors and bad sectors.
driverquery: displays a list of installed device drivers.
sfc /scannow: scans system files for corruption and repairs them if possible.
shutdown /s to turn off
shutdown /r to restart
shutdown /a to cancel any shutdown
```
## Windows Powershell

Powershell to say something is the "new" equivalent of cmd, with more commands and better automatization, very useful in company environement
PowerShell is a cross-platform task automation solution made up of a command-line shell, a scripting language, and a configuration management framework.”
Powershell is also called object-programming

Searching for Commands in PowerShell

To list all cmdlets that start with a specific word or verb, use:
```
Get-Command -Name <pattern>*
Example:
Get-Command -Name Remove*
```
→ Lists all commands whose names begin with “Remove” (e.g., Remove-Item, Remove-Module, etc.)
💡 The asterisk () acts as a wildcard to match any remaining characters.*

```
Echo can be written as write-output
```

🧩 1. Cmdlet Syntax (Verb–Noun)
Verb-Noun -Parameter Value


Examples

Get-Content -Path C:\file.txt     # Reads file content
Set-Location C:\Users             # Changes current directory

🔍 2. Discovering Commands

List all available commands:

Get-Command


Filter by command type:

Get-Command -CommandType Function


Search commands by name pattern:

Get-Command -Name Remove*


Search by verb:

Get-Command -Verb Get

🧠 3. Learn About Commands

Display documentation and usage examples:

Get-Help Get-Date
Get-Help Get-Date -Examples

⚡ 4. Aliases (Shortcuts)

Show all command aliases:

Get-Alias


Examples

Alias	Cmdlet Equivalent
dir	Get-ChildItem
cd	Set-Location
cat	Get-Content
📦 5. Modules and Extra Cmdlets

Find and install new cmdlets from the PowerShell Gallery:

Find-Module -Name PowerShell*
Install-Module -Name PowerShellGet

🌐 6. Remote Execution

Run a command on another computer:

Invoke-Command -ComputerName Server01 -ScriptBlock { Get-Service }


Run a local script remotely:

Invoke-Command -FilePath C:\scripts\test.ps1 -ComputerName Server01


Use credentials if needed:

$cred = Get-Credential
Invoke-Command -ComputerName Server01 -Credential $cred -ScriptBlock { Get-Process }

💬 7. Interactive Remote Session

Connect interactively to a remote system:

Enter-PSSession -ComputerName Server01
Exit-PSSession

🧾 Summary Table
Category	Cmdlet	Purpose
Discover	Get-Command	Lists all commands
Learn	Get-Help	Shows documentation and examples
Aliases	Get-Alias	Displays shortcuts for cmdlets
Modules	Find-Module, Install-Module	Finds and installs new modules
Remote	Invoke-Command	Runs commands on remote computers
Interactive	Enter-PSSession	Starts an interactive remote session
