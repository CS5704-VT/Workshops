<!-- 
targets:
    - type: docker
      name: t1
      image: node:12-buster
    - type: docker
      name: t2
      image: node:12-buster
 -->



> We will revisit this ^ later...

### Shells

Shell _commands_ can also be edited and run directly in Docable. We will primarily be using Bash shells for this course. In the editor below, type `ls` and run the command to see a list of files used in this workshop.

```bash|{type:'command', shell:'bash'}

```

We also have basic functionality to validate the output of of commands. For example, modify the script in the cell below to print out `goodbye world`:
```bash|{type:'command', failed_when: "stdout.includes('goodbye')", success_message:"Great job 👍", failure_message: "Incorrect output: try 'hello world' instead..."}
echo ""
```

### Variables

Environment variables can also be set and run for bash commands in Docable. Remember the text boxes at the top? The command below will run successfully if you have correctly assigned the variables. Try assigning a string value to `foo` and running the first command:

```bash|{type:'command', variables: 'foo'}
echo "{{foo}} world"
```

If the variables are not set, you should get an error that the values have not been provided. Try running the this command without setting `bar` above:

```bash|{type:'command', variables: 'bar'}
echo "hello {{bar}}"
```

### Terminals

Additionally, Docable also provides full interactive _terminals_ for more extensive tutorial activities. These terminals are also connected to the shell commands and files generated throughout this tutorial. For example, run the command below to write “Hello World!” in /tmp/hello.txt:


```|{type:'command'}
echo "Hello World!" > /tmp/hello.txt
```

Then in the terminal below, type `cat /tmp/hello.txt` to check the result of command cell above:

```|{type:'terminal'}
```

Docable also provides several types of terminals including bash, zsh, and Windows as well as Read-Eval-Print Loop (REPL) programming language shells for JavaScript (node), Python, Ruby (irb), and Java (JShell).

### Multiple Targets

When working on tutorials, be careful to observe which commands are run in which _target terminal_. For example, running the command in the cell below will to create a the file `hello_world` in the `\tmp` directory of terminal **t2**:

    ```bash|{type:'command', target: 't2'}
    touch /tmp/hello_world
    ```

If a `target` is not specified for a command cell in a multi-target notebook, you can assume the original target will be used by default:

```bash|{type:'command'}
ls -al /tmp/hello_world
```

Now you can run the two Docable cells above ☝. First execute the cell with **t2** target to create a temp file. Then execute the second cell which uses the **t1** target to confirm this file does not exist.

You can also use this `target` property in terminal cells. 

Here is a rendered terminal for **t1** target:

```bash|{type:'repl', target: 't1', 'background-color': '#00345c'}
```

and another one for t2 target:

```bash|{type:'repl', target: 't2', 'background-color': '#013d17'}
```

Run the command `ls \tmp` in each to see that the `/tmp/hello_world` file is available in **t2** but not in **t1** to show that these are two separate environments. Feel free to play around with these two terminals to confirm they are connected to different targets.

## Final Thoughts on Workshops

* To receive credit, you will most likely have to submit screenshots or save a pdf of completed notebooks (most browsers have a `Print > Save As PDF` option in the print menu). Each workshop will have specific instructions on what to turn in (📝).
* If you run into any issues with a notebook, please contact the instructor.
* The academic integrity policy applies to all workshops. Do not work with another student unless otherwise specified.
* Remember, anything covered in workshops (including the following notebooks) are eligible content to be on the exam!

### [Programming Languages ⏭️](Coding.md)