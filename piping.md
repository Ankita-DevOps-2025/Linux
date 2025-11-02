# Pipe

# What is a Pipe?
- Pipes are used to redirect a stream from one program to another program.
- Essentially, the output of one command is redirected to the input of another.

# Pipe Syntax
- We use the | symbol (vertical bar) to separate two commands.
- The output of the first command is passed/redirected to the second command as its input.
 $ command1 | command2

eg -> ps -ef | grep httpd

# CASES
1. find no. of files present in directory 
= ls -l | wc -l
2. there are 2 file names.txt country.txt , combine both file content usinf cat and sort it
= cat names.txt country.txt | sort
3. find unique records from file names.txt
= cat names.txt | sort | uniq
4. how to see only 30-37 line in file of 100 lines 
= cat data.txt | head -37 | tail -7
5. netstat | more/less

# TEE COMMAND
TEE read standard input and copies it both to standard output and into a file.
We can see the information going through pipeline.

eg -> 
ls | tee test.txt
ls | tee test.txt | wc -l

# XARGS
it convert the stdinput into command line argument

eg ->
ls | xargs echo "hi"
 
there is file file.txt which has file2 file1 file3 file4 file5 in it as list , now you need to create the file of that list 
-> cat file.txt | xargs touch  

