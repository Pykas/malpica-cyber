
##Linux fundamentals

The first Linux release was in 1991, almost every technology thing now uses linux (Cars, consoles, pcs, android, etc)

#Commands that i learned
ls = listing of files in the dossier i can use the commande with the name of a folder to se what is inside the folder without entering the folder
cd = change directory or to navigate exemple: cd folder
cat to read the docs that i want exemple cat note.txt
"Cat" is short for concatenating & is a fantastic way for us to output the contents of files (not just text files!).

pwd = To know in which file i am for exemple /home/user/documents

find The find command is fantastic in the sense that it can be used both very simply or rather complex depending upon what it is you want to do exactly. However, let's stick to the fundamentals first.
Exemple to find a document instead of navigating or going all into it we can just type the command find + -name + document.txt

If we dont know the name we can just go with find -name *.txt . Where "Find" has been able to find every .txt file and has then given us the location of each one:

Grep 
The grep command allows us to search the contents of files for specific values that we are looking for.
For exemple, we can hace more than 240 entries of one kind of file and a lot of text that we can't naviagte quickly with the commande cat
We can use grep + one value and he will find it very quickly ex: grep "81.143.211.90" access.log
# Search for an IP in an access log:
grep "81.143.211.90" /var/log/nginx/access.log

# Search recursively in a folder:
grep -R "ERROR" /var/log/myapp/


& = Run a command and continue tyoping commands
&& = Run various commands one after the other but only if all of them are excuted correctly
> To write and replace 
>> To add some text instead, it doesn't replace

How i used it
I used ls to read the directory, then i used echo >> folder to create a folder
I checked that it is well created with ls
I used the command rm folder && ls to erase it and then check if it was tryle erased

