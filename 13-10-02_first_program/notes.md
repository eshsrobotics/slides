# Your First Program

Typically the first program you write in any language is called a "Hello World"
program - a program that simply outputs `Hello World` to the terminal. We did
this last week, but let's do it one more time just for practice.

Create a new directory in `~/go/src/helloWorld`. You can do this in the
terminal by entering `mkdir ~/go/src/helloWorld`.

Use your text editor to type in exactly the following:

```go
package main

import "fmt"

// this is a comment

func main() {
  fmt.Println("Hello World")
}
```

Save it as `helloWorld.go` in `~/go/src/helloWorld/`.

Change directory to `~/go/src/helloWorld/`. You can run the program we just
wrote with `go run helloWorld.go`. If you get an error, you probably made
a typo when writing the program. Computers are stupid. They do exactly what you
tell them to do. If you make a mistake, they won't correct it. Go is no
exception. It has no tolerance for mistakes.

## Breaking It Down

Go programs are read top to bottom, left to right.

The first line says this:

    package main

This is known as a package declaration. Evey Go program must start with a
package declaration. Packages are Go's way of organizing and reusing code.

There are two types of Go programs: executables and libraries. Executables are
programs you run (they end in `.exe` on windows). Libraries are collections
of code that we package together so we can use them in other programs. We will
explore libraries in more detail later. For now, remember that you need a
package declaration at the top of every Go program you write.

The next line is a blank line. New lines, spaces, and tabs are all known as
whitespace (because you can't see them). Go doesn't care about whitespace, we
just use it to make the program easier to read.

Next we see `import "fmt"`. The `import` keyword is how we include code from
other packages to use in our program. The `fmt` package (short for format) has
code for formatting input and output. Given what we know about packages, what
do you think the `fmt` package's files would contain at the top of them?

Notice that `fmt` is surrounded by double quotes. This is called a string
literal. We'll go more in to detail with these later. For now, just remember
that every " must be followed by another ". Everything in between the two "
is part of the string.

The next line (starts with `//`) is a comment. Comments are ignored by Go and
help us, the programmer, understand what the code is doing. There are two
types of comments: those that start with `//`, where everything after `//` on
the same line is part of the comment, and those that start with `/*` (and end
with `*/`, where everything between the `*`s is part of the comment. The second
kind of comment can span multiple lines.

Next we see a function declaration. `func main()...`. Functions named blocks of
code and are the building blocks of a Go program. They have inputs, outputs,
and a series of steps called statements which are executed in order.  All
functions start with the keyword `func` followed by the name of the function
(`main` in this case), a list of zero or more parameters surrounded by
parenthesis, an optional return type, and a "body" which is surrounded by curly
braces. This function has no parameters, doesn't reutrn anything, and has only
one statement. The name `main` is special because it's the starting point of
program. When we run the program, `main` is the first function to be called.

The final piece of our program is the following line:

    fmt.Println("Hello World")

This statement is made of three components. First we access another function
inside of the `fmt` package called `Println` (that's the `fmt.Println` piece,
`Println` means Print Line). Then we create a new string that contains `Hello
World` and invoke (also known as call or execute) that function with the string
as the first and only argument.

At this point we've gone over a lot of new terminology and you may be feeling
a little overwhelmed. Sometimes it's helpful to deliberately read your program
out loud. One reading of the program may go like this:

Create a new executable program, which references the `fmt` library and
contains one function called main. That function takes no arguments, doesn't
return anything and does the following: Access the `Println` function contained
inside of the `fmt` package and invoke it using one argument – the string
`Hello World`.

The `Println` does the real work in this program. You can find out more about
it by typing the following in your terminal.

    godoc fmt Println

Among other things, you should see this:

    Println formats using the default formats for its operands and writes to
    standard output. Spaces are always added between operands and a newline is
    appended. It returns the number of bytes written and any write error
    encountered.

Go is a very well documented programming language, but the documentation may
be difficult to understand unless you're already familiar with programming
languages.

The above documentation tells you that the `Println` function will send
whatever you give to it to standard output - a name for the output of the
terminal you are working in. This function is what causes `Hello World` to be
displayed.

Next we'll go over how Go stores and represents things like `Hello World` by
learning about types.

## Problems

* What is whitespace?  
* What is a comment? What are the two ways of writing a comment?  
* Our program began with package main. What would the files in the fmt package
  begin with?  
* We used the Println function defined in the fmt package. If we wanted to use
  the Exit function from the os package what would we need to do?  
* Modify the program we wrote so that instead of printing Hello World it prints
  Hello, my name is followed by your name.
