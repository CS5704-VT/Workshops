# Debugging

**Debugging** is the process of finding and removing errors from code. These include _syntax errors_ where a programming language is misused (usually caught by the compiler), _logic errors_ where the code is syntactically correct but there is incorrect output, and _runtime errors_ when the program stops during execution. Research shows debugging is one of the most time-consuming activities for developers and one of the most expensive processes of software engineering[^1].

Tips for debugging:
- Do not make random or extensive changes to the program! Instead, examine the code to figure out what went wrong.
- Think before you change anything
- Figure out why it went wrong
- Always address the first compiler error listed before addressing the other errors.
- Always recompile after making changes to code because fixing one error will often fix other errors as well.

Many useful tools are available to help software engineers debug their code. 

## Debugging Tools

To improve debugging for software engineers, a variety oftools have been developed to support debugging activities. Most IDEs, such as [VS Code](https://code.visualstudio.com/docs/editor/debugging) and [Eclipse](https://www.eclipse.org/community/eclipse_newsletter/2017/june/article1.php), include built-in debuggers to help users find and fix errors in their code. Debuggers are useful for helping programming find bugs more effectively and efficiently compared to searching a code base manually. In the following activity, you will have the opportunity to practice working with several examples of debugging tools:


## 📒 Online Exercise: Debugging Tools

Click below to access the workshop activities in Docable. There will be a brief tutorial for using gdb and valgrind. GDB and valgrind support a variety of programming languages (Ada, Assembly, C, C++, Fortran, Go, Rust,...), however this assignment primarily focuses on C. 

**C Overview**
You do not need in-depth knowledge of the C programming language to complete this activity, but will need to know how to compile and run programs to test your ability using tools and comprehending debugging messages. The following example is how to compile a C program in a source code file called file.c to create a program executable named file. After compiling the program, use `./file` to run the code. 

```c
gcc -Wall -std=c99 -g file.c -o file
./file
```

### To receive credit, complete the two tutorials below. Then answer the Debugging activity questions and add your responses to the [Homework 5 submission](https://canvas.vt.edu/courses/145256/assignments/1384322) on Canvas.

<a href="https://devops.docable.cloud/dcbrown/v/6214036d5872b78ccff4fea3">
<img src="resources/imgs/gdb-preview.png">
</a>

<a href="https://devops.docable.cloud/dcbrown/v/62223149362731820848f3af">
<img src="resources/imgs/valgrind-preview.png">
</a>

### Activity Questions

<a href="https://devops.docable.cloud/dcbrown/v/62228104362731820848f3f6">
<img src="resources/imgs/debug.jpg" width="375" height="300" />
</a>

### 📝 Upload your reponses on Canvas. Due: Friday, March 11 at 11:59pm

> [^1] [An Exploratory Study of Debugging Episodes](https://arxiv.org/pdf/2105.02162.pdf)

> * The content of the GDB workshop is primarily based on a `C and Software Tools` course exercise by [Dr. David Sturgill](https://www.csc.ncsu.edu/people/dbsturgi).
> * The content of the valgrind workshop is primarily based on a `The Valgrind Quick Start Guide` at [CMU](https://www.cs.cmu.edu/afs/cs.cmu.edu/project/cmt-40/Nice/RuleRefinement/bin/valgrind-3.2.0/docs/html/index.html).
