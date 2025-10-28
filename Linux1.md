
# Linux Fundamentals 1 — Notes

A quick, practical summary of the first Linux fundamentals I learned.  
Linux is everywhere: servers, phones (Android), appliances, cars, consoles, IoT, etc.

---

## Basic navigation & file commands

### `pwd`
Show current working directory.
```bash
pwd
# Example output: /home/manuel/documents
```
## Find
The find command is fantastic in the sense that it can be used both very simply or rather complex depending upon what it is you want to do exactly. However, let's stick to the fundamentals first.
Exemple to find a document instead of navigating or going all into it we can just type the command find + -name + document.txt

If we dont know the name we can just go with find -name *.txt . Where "Find" has been able to find every .txt file and has then given us the location of each one:

## Grep 
The grep command allows us to search the contents of files for specific values that we are looking for.
For exemple, we can hace more than 240 entries of one kind of file and a lot of text that we can't naviagte quickly with the commande cat
We can use grep + one value and he will find it very quickly ex: grep "81.143.211.90" access.log
# Search for an IP in an access log:
grep "81.143.211.90" /var/log/nginx/access.log

# Search recursively in a folder:
grep -R "ERROR" /var/log/myapp/

## Search recursively in a folder:

```
grep -R "ERROR" /var/log/myapp/
```

##Redirections & operators

### & : put a command in background (shell job), or in some shells used with nohup.
Example to run and continue typing:

```some_command &   # runs in background```

### && : run second command only if first succeeds.

```mkdir test && cd test   # cd runs only if mkdir succeeded```


### (> : redirect output and overwrite file.

```echo "hello" > file.txt   # file.txt now contains "hello"```


### (>> : append output to file.

```echo "another line" >> file.txt```

## Useful filesystem commands
```
mkdir name : create directory
touch file : create empty file or update timestamp.

rm file : remove file

rm -r folder : remove folder recursively (dangerous — be careful).

cp src dst : copy file/directory (-r for recursive).

mv src dst : move/rename.
```
```
ls                       # list folder
mkdir myfolder           # create folder
ls                       # check folder created
rm -r myfolder && ls     # remove folder and list to verify```
```

Networking basics

ip a : show network interfaces and IP addresses.

ping 1.1.1.1 : check connectivity.

ss -tulpn or netstat -tulpn : show listening ports and which process owns them.

curl -I https://example.com : fetch HTTP headers (quick test endpoint).

tcpdump -i any port 80 -c 100 -w capture.pcap : capture traffic (requires sudo).
