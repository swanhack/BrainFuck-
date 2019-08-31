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

Because of this seemingly limited instruction set and the due to the fact BrainFuck programs don't give any indication of their state they can look a little .. random.

```Brainfuck
++++++++++[>+>+++>+++++++>++++++++++<<<<-]>>>++.>+.+++++++..+++.<<++.>+++++++++++++++.>.+++.------.--------.<<+.<.
```

Before moving on feel free to gain an understanding of BrainFuck, [this](https://copy.sh/brainfuck/) is an online interpreter with some examples you can play with.

## Interpreters 101

Generally speaking an Interpreter.. Interprets stuff.. no kidding :D

They can do this task in one of a few ways:

The most simple way to accomplish this task is to read in the code and execute it immediately, if you were around in the 80's or are lucky enough to have a computer from this era this is how [BASIC](https://en.wikipedia.org/wiki/BASIC) works.

A slightly more advanced way to carry out this process is to parse, tokenise and then execute the tokens, which are usually just simplified instructions, this is how both [P]ython](https://en.wikipedia.org/wiki/Python_(programming_language)) and [Ruby](https://en.wikipedia.org/wiki/Ruby_(programming_language)) work.

Finally the strangest way to interpret would be to use a runtime compiler and then execute this code?  Strange right.. I'm pretty sure this is how [Pascal](https://en.wikipedia.org/wiki/Pascal_(programming_language)) works but I need a Pascal expert to confirm this for me.

## Writing your own interpreter

Writing a simple interpreter is much like writing a file reader and a string parser, it doesn't need to be any more difficult.

NEEDS MORE

#### But why would I want to write my own interpreter?

Because why not?

ALSO NEEDS MORE  

## Your challenges, should you choose to accept them!

 * Using this knowledge of BrainFuck and Interpreters and in a language of your choice, write a BrainFuck Interpreter that can process any BrainFuck code you choose to throw at it!

 I personally suggest working on each of the instructions in pairs, `<>`, `+-`, `.,` and `[]` respectively as this will greatly decrease the complexity of the task.

 * For a secondary challenge try and get your interpreter under a Kilobyte in size

 An easy trick here is to use single character variable and method names.. this is cheating!

 * And if you're feeling a particular kind of crazy .. make it "tweet-able", 140 characters is hard [but possible](http://www.danielvik.com/2016/02/tweetable-brainfuck-interpreter-in-c.html), thankfully Twitter made it 280 characters last year so this is much easier now!

```
TODO: Also This
```
