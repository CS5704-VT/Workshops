# Getting Started

To successfully build software, you need a properly configured environment with a variety of tools. Unfortunately, creating consist work enviroments for a development team can be difficult and frustrating, especially in a classroom environment, due to various operating systems, personal configurations, coding editor preferences and setups, etc. Thus, for the majority of technical workshops for CS 5704 this semester we will be using Docable as a consistent virtual work environment built on Docker to create online notebooks for everyone to complete activities. Here is a brief tutorial on how to use this interactive tutorial system.

### Content

Docable notebooks contain items in cells. Cells are able to provide a wide variety of features, as we will see later, including embedded content to provide additional information to users like images, slides, or videos. Check out the demo presentation in the example cell below. To navigate, you may click on the slides themselves or use the menu at the bottom of the cell:

```|{type:'slides'}
https://docs.google.com/presentation/d/e/2PACX-1vSl94Tz9pRTwp1LTR6ImmHoHqd7kHiresyP-Ytq0HnPdjqdK38MtxMvr4agOykQPqDIQrixKtW27mlT/embed
```

### Quizzes

Workshops will often include short quizzes to assess your understanding of workshop content. Quizzes on Docable will consist of multiple choice questions that will notify you if your answers are correct or provide the right answer otherwise. Choose your response(s) in the quiz and click the gray check mark (✅) on the right of the cell to submit. Check out examples of quiz format below:

#### Single Choice Question

A *description* for the question will be here.
_Select Choice A for the correct answer below:_

```js|{type:'quiz', quiz_type:'singlechoice', quiz_answers:'0'}
- [ ] Choice A
- [ ] Choice B
- [ ] Choice C
```

#### Multiple Choice Question (Check all that apply)

Another *description* for a question. Try choosing _Choice 2_ and clicking the question mark on the right to see an example of an incorrect answer.
_Choices 2 **and** 3 are the correct answers below:_

```js|{type:'quiz', quiz_type:'multichoice', quiz_answers: '1,2'}
- [ ] Choice 1
- [ ] Choice 2
- [ ] Choice 3
```

> **Note:** When reviewing quiz feedback, the first option starts at position 0!

### Files

Docable allows users to edit and store _files_. Below is a sample text file. You may edit the contents of a file by clicking in the cell below and typing whatever you want. Try updating the `/tmp/docable.txt` file below. To create or update the file in the interactive tutorial environment, click on the pencil and paper icon (📝) on the right side of the cell (_Make sure not to forget this step, otherwise you may face problems later in tutorials!_). You should see a message that says SUCCESS: Created file successfully.

```bash|{type:'file',path:'/tmp/docable.txt'}

```

### Scripts

Similarly, Docable is able to provide simple _scripts_ for you to edit and run blocks of code. To edit, change the content within the cell. To run, click on the play button icon (▶️) on the right side of the cell. The platform supports scripting in JavaScript, Python, Ruby, and Java. Scripts will be indicated with a '[script:]' and the logo of the script's programming language the left side of the cell (i.e. the script below is in JavaScript). Modify the first line of the script below to print out `Hello Docable` on the first line and add a new line to print `Welcome to CS5704!`. Running the script should generate a success message with the output.

```js |{type:'script'}
console.log( "Hello World" );
```

Update the print statement below to print `"Hello Docable` (typo included). When this script is run, you should run into a compilation error due to invalid JavaScript syntax.

```js |{type:'script'}
console.log(  );
```

To further verify scripts, we are able to run some (very basic) checks on the output of your scripts to verify answers and provide feedback. For example, write a JS script below to prints out `no`:

```js|{type:'script', failed_when: "stdout.includes('no')", success_message:"Nice, you figured out this command successfully! :)", failure_message: "Sorry, that output is not what was expected :( You should actually print any other string that does not include the substring 'no'"}

```

### [Getting Started (cont.) ⏭️](Setup2.md)