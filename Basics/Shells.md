# Shells

A shell is a computing environment where commands can be interpreted, evaluated, and their output displayed. We have already seen a few examples of shells and Unix commands in the introductory tutorial and with REPL programming environments. Shell commands can be difficult to learn, however a good shell provides access to a rich set of commands and allows simple programming of commands, which can be useful for creating powerful scripts and tools to improve your productivity as a software engineer. This tutorial provides a brief overview of bash shells. 

## Shell Basics

Bash (Bourne Again Shell) is a Unix shell command language that replaced the preceding Bourne shell in 1989. It has been the most popular interactive shell and is used as the default shell for most Linux distributions. If you would like to know more information about shells and learn additional commands, check out this thorough tutorial through [Software Carpentry](https://swcarpentry.github.io/shell-novice/index.html) for shell novices, [Command Line Fu](https://www.commandlinefu.com/commands/browse) or the [Unix Workbench](https://seankross.com/the-unix-workbench/) book. To access shells on your own:

* Linux: you already have a shell!
* Mac: you can run the Terminal in Applications and pin to your Dock.
* Windows: You access a shell in several ways. You can right click on the Windows Icon in the Task Bar and open a terminal window. You can also type in the name of the shell program in the search bar (e.g., Cmd/Powershell). To get bash on Windows, you will need to install an emulated shell with bash, such as Bash for Git or Windows Linux Subsystem (WSL).
> Tip: IDES, such as VS Code provide easy access to a terminal (View ⇨ Terminal).

### Commands

99% of the reason you use shells is to run useful commands.

##### Essential commands.

* **`ls`**: list content of a directory.
* **`cd`**: change directories to a new path.
* **`mkdir`**: make a new directory.
* **`pwd`**: output current directory
* **`cp`**: copy files
* **`rm`**: remove files
* **`touch`**: make a new empty file/update status
* **`echo`**: print out standard output
* **`cat`**: output the contents of a file
* **`head`**: output the first lines of a file
* **`tail`**: output the last lines of a file
* **`grep`**: search files for a key phrase
* **`wget`**: retrieve file from the web
* **`cut`**: extract output of a file (columns)
* **`awk`** and **`sed`**: Magic commands for extracting, searching, and transforming content

##### Combining commands

Command can run sequentially or conditionally:

```bash
command1 ; command2
(command1 ; command2) # in a sub-shell
command1 || command2  # do command2 only if command1 fails
command1 && command2  # do command2 only if command1 succeeds
```

Try running this command that combines these shell commands.

```bash|{type: 'command'}
mkdir test ; ls test
```

```bash|{type: 'command'}
touch shells-test.txt && cat shells-test.txt && cp shells-test.txt test/ && ls test
```

Now, try using the `||` operator. 

```bash|{type: 'command', }
cat shells-test.txt || echo "backup plan"
```

See what happens in this case.

```bash|{type: 'command', failed_when: "!stdout.includes('backup plan')"}
cat filedoesnotexist.txt || echo "backup plan"
```

```bash|{type: 'command', failed_when: "!stdout.includes('backup plan')"}
cat filedoesnotexist.txt && echo "backup plan"
```

##### Command I/O

The UNIX shell commands push data from sources through filters along pipes. Normally, each command runs as a process and reads and writes data the following way:

* **Standard input (stdin)**: get information from keyboard.
* **Standard output (stdout)**: write information as output to console.
* **Standard error (stderr)**: write error information as output to console.

Pipes and redirects change stdin and stdout from default sources. For example, we can change the stdin of a process to be piped from the output of another process. Or rather than printing to the console, we can get a process to write to a file.

```bash
command              # default standard in and standard out
command < inputFile  # redirect of inputFile contents to command as standard in
command > outputFile # redirect command output to outputFile as standard out
command >> outputFile # append the command output to the existing outputFile
command1 | command2  # pipes output of command1 as standard in to command2
```

Try the following scripts below to see some brief examples:

```bash|{type: 'command'}
pwd > path.txt && cat path.txt
```

```bash|{type: 'command'}
ls >> path.txt && cat path.txt
```

```bash|{type: 'command'}
echo "Hello World" > shells-test.txt && cat shells-test.txt
```

```bash|{type: 'command'}
grep "o" < shells-test.txt 
```

```bash|{type: 'command'}
echo "testing" | grep "o"
```

## Advanced: Shell Programming

Once you have a set of commands or steps you perform frequently enough, you might find it useful to put into a bash script, including:

* Data collection scripts for mining data; data processing and cleaning scripts.
* Set up a local server, vms or containers, or anything else needed to test or run a complex application.
* Provision and deploy an application on a remote server.

While you do these all in the context of a interactive shell, some of the following are particular useful for writing multiple lines of scripts. Bash scripts are usually created with a `#!/bin/bash` header at the top of the file and a `.sh` file extension. For example, modify the file below to print out "Hello World":

```bash|{type:'file',path:'hello.sh'}
#!/bin/bash

echo ""

# Don't forget to save me on the right!
```

To execute a bash script, you can run:
```bash|{type:'command'}
bash hello.sh
```
or change the mode of the file to be an executable using `chmod` and run with `./`:
```bash|{type:'command'}
chmod a+x hello.sh ; ./hello.sh
```

Here are some other useful shell programming concepts:

```bash
# This is a Bash comment.

# If statement
if command; then
   commands
fi

# Error handling
[ -z "$var" ] && echo "var is undefined" || echo "var is defined"

# While loop
while command; do
  commands
done

# For loop
for (( i=10; i>0; i-- ))
do
    # Prints numbers counting down from 10
    echo "$i"
done

# Input/Output
read name # Get user input
echo "Hello $name!"
echo $1 # First command-line argument
echo $2 # Second command-line argument...

# Variables (storing values, results of commands, and referencing)
e=100
e=$(command)
$e
echo "result is: $e"

a=2                   # Integer.
let "a += 1"
echo "a = $a "           # a = 3
echo $a      
```
> ⚠️ Warning: In bash there are no types (everything is a character string) and spacing matters!
## 📝 Activity

> **Automated Test Case Generation**
> 
> You work for a company that provides a simple calculator that calculates the area of a circle (`3.14 * r^2`) with a given radius. The product is almost ready to ship, however there are no test case input or expected output files for the unit tests! Write a bash script to automatically generate 10 test case input and output files based on the following criteria:
> - The input files `test_n.txt`, where _n_ is the given test case number, will have the test input value of _n_ in the text file (i.e. `test_1.txt` will only contain a `1`, `test_2.txt` -> `2`, etc.). 
> - The corresponding expected output `expected_n.txt` should contain the area of a circle with the given radius _n_ (i.e. `expected_1.txt` -> `3.14`). 
> 
> You may test your bash script in the file and terminal below. There are no requirements for rounding your answers and this program will not be graded on correctness, but on effort. When you are finished, save your bash script _locally_ in a file called `workshop.sh`. This will be submitted later.

```bash|{type:'file',path:'workshop.sh'}

```

```|{type:'terminal'}
```

### [**Version Control with Git** ⏭️ ](Git.md)
