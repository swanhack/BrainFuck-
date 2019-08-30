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

Instructions inside square brackets will only be processed if when the initial square bracket is reached the current value in the array is zero, otherwise the program will jump to the closing square bracket.  Equally if the second square bracket is reached when the current value is not zero it will jump back to the initial square bracket.

Because of this seemingly limited instruction set and the due to the fact BrainFuck programs don't give any indication of their state they can look a little .. random.

```Brainfuck
++++++++++[>+>+++>+++++++>++++++++++<<<<-]>>>++.>+.+++++++..+++.<<++.>+++++++++++++++.>.+++.------.--------.<<+.<.
```

Before moving on feel free to gain an understanding of BrainFuck, [this](https://copy.sh/brainfuck/) is an online interpreter with some examples you can play with.

## Interpreters 101

```
TODO: This
```

## Your challenges, should you choose to accept them!

 * Using this knowledge of BrainFuck and Interpreters and in a language of your choice, write a BrainFuck Interpreter that can process any BrainFuck code you choose to throw at it!

 I personally suggest working on each of the instructions in pairs, `<>`, `+-`, `.,` and `[]` respectively as this will greatly decrease the complexity of the task.

 * For a secondary challenge try and get your interpreter under a Kilobyte in size

 An easy trick here is to use single character variable and method names.. this is cheating!

 * And if you're feeling a particular kind of crazy .. make it "tweet-able", 140 characters is hard [but possible](http://www.danielvik.com/2016/02/tweetable-brainfuck-interpreter-in-c.html), thankfully Twitter made it 280 characters last year so this is much easier now!

```
TODO: Also This
```
