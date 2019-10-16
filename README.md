# BrainFuck!

This week we're going to be looking at Interpreters and to do this we're going to start with a simple language that everyone has likely heard of, [BrainFuck!](https://en.wikipedia.org/wiki/Brainfuck)

## BrainFuck 101

In the off-chance you haven't heard of it, BrainFuck is a Turing complete esoteric programming language with only 8 instructions, all of which are single characters.

Instruction | Meaning
------------|--------
`>` | Pointer ++
`<` | Pointer --
`+` | Value ++
`-` | Value --
`.` | Write Char
`,` | Read Char
`[` | Start While()
`]` | End While()

Instructions inside square brackets will only be processed if the current value in the array is zero when the initial square bracket is reached, otherwise the program will jump to the closing square bracket.  Equally if the second square bracket is reached when the current value is not zero it will jump back to the initial square bracket.

Note: Any character that is not listed above is considered a comment and therefore not interpreted.

Because of this seemingly limited instruction set and the due to the fact BrainFuck programs don't give any indication of their state they can look a little .. random.

```BrainFuck
++++++++++              # Set cell 0 to 10
[                       # This loop will run 10 times
    >+                  # Set cell 1 to 1
    >+++                # Set cell 2 to 3
    >+++++++            # Set cell 3 to 7
    >++++++++++         # Set cell 4 to 10
    <<<<-               # Move to cell 0, reduce by 1
]
>>>++.                  # Move to cell 3, add 2, print
>+.                     # Move to cell 4, add 1, print
+++++++..               # Add 7, print, print
+++.                    # Add 3, print
<<++.                   # Move to cell 2, add 2, print
>+++++++++++++++.       # Move to cell 3, add 15, print
>.                      # Move to cell 4, print
+++.                    # Add 3, print
------.                 # Reduce by 6, print
--------.               # Reduce by 8, print
<<+.                    # Move to cell 2, add 1, print
<.                      # Move to cell 1, print
```

Before moving on; feel free to gain an understanding of BrainFuck, [this](https://copy.sh/brainfuck/) is an online interpreter with some examples you can play with.

## Bad explaining 102

This code will take a number from one cell and add it to the cell next to it.

```BrainFuck
[
    ->+<
]
```

The basis of this code is of course the square brackets, which form a loop, put simply it subtracts one from the left number and adds one to the right number until the left is equal to zero at which point the loop is skipped.

Imagine if you will the left hand number is a 3 and the right hand number is a 5:

```
Initial state: 3 - 5
```

The first time the loop is reached the pointer will not be looking at a zero so it will enter the loop.  From here it will subtract one from the left hand side leaving 2 - 5, move right and add one to the right hand side leaving 2 - 6.  It will then reach once again go back to the left side and because the number here is not a zero, it's a 2, the loop will return to the start.

```
New state: 2 - 6
```

From here the loop will run again:

```
New state: 1 - 7
```

Finally the loop will begin by looking at a 1, which it will then subtract one from leaving zero, and add one to the right hand side, leaving 8 and once again travel back to the left hand side.  As the pointer is now looking at a zero the loop will not restart.

```
Final state: 0 - 8
```

Last time I checked 3 + 5 was 8 so I declare this loop a success!

## Interpreters 103

Generally speaking an Interpreter.. Interprets stuff.. no kidding :D

They can do this task in one of a few ways:

The most simple way to accomplish this task is to read in the code and execute it immediately, if you were around in the 80's or are lucky enough to have a computer from this era this is how [BASIC](https://en.wikipedia.org/wiki/BASIC) works.

A slightly more advanced way to carry out this process is to parse, tokenise and then execute the tokens, which are usually just simplified instructions, this is how both [Python](http://www.bash.org/?400459) and [Ruby](https://en.wikipedia.org/wiki/Ruby_(programming_language)) work.

Finally the strangest way to interpret would be to use a runtime compiler and then execute this code?  Strange right.. I'm pretty sure this is how [Pascal](https://en.wikipedia.org/wiki/Pascal_(programming_language)) works but I need a Pascal expert to confirm this for me.

## Writing your own interpreter

Writing a simple BF interpreter is much like writing a file reader and a string or character parser, it doesn't need to be any more difficult.

```
# open file and read contents

for char in file
    # Do stuff
```

For BrainFuck, and this session, the entire interpreter need consist of no more than a cascading `if` block, other languages however may require more complex control flow.

```
if char +
    pointer + 1
else if char -
    pointer - 1
```

These examples are intentionally ambiguous, feel free to use whatever language you choose.

#### But why would I want to write my own interpreter?

Because why not?

Writing an interpreter can teach you a lot about how a language processes instructions..
They can be extremely fun to build and if you plan on writing your own programming language one day you'll probably need one!

## Your challenges, should you choose to accept them!

 * Using this knowledge of BrainFuck and in a language of your choice, write a BrainFuck Interpreter that can process any BrainFuck code you choose to throw at it!

 I personally suggest working on each of the instructions in pairs, `<>`, `+-`, `.,` and `[]` respectively as this will greatly decrease the complexity of the task.

 * For a secondary challenge try and get your interpreter under a Kilobyte in size

 An easy trick here is to use single character variable and method names.. this is cheating so please don't do this!

 * And if you're feeling a particular kind of crazy .. make it "tweet-able", 140 characters is hard [but possible](http://www.danielvik.com/2016/02/tweetable-brainfuck-interpreter-in-c.html), thankfully Twitter made it 280 characters last year so this is much easier now!