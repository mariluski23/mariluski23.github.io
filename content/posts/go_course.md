---
date: "2024-12-15T11:35:56+01:00"
draft: false
title: "Go course for begginers in backend - Part 1/3"
summary: "Go course for begginers in backend - Part 1/3"
tags: ["go", "golang", "golang-course", "golang-tutorial", "tutorial"]
---

Go (Golang) is a very _nice_ programming to learn for beginners.

## What is Go?

Go is a programming language developed by Google in 2009.
The syntax is similar to [The C programming language](<https://en.wikipedia.org/wiki/C_(programming_language)>).

## Why Go?

- Its **blazing fast**.
- Its **simple**, **easy to learn** and **minimal** syntax make it a good choice for beginners.

## Getting started

First, we need the following tools:

- [Go](https://go.dev/doc/install)
- A code editor (I use [VSCode](https://code.visualstudio.com/))

## Making a new project

Let's create a new project:

Just go to a terminal, in your project folder and run:

```bash
go mod init my-project
touch main.go
```

Or in Windows:

```pwsh
go mod init my-project
type nul > main.go
```

This will create a go _project_ (formally; a _module_) called `my-project` and make a `main.go` file.

Now, let's open the `main.go` file and write some code:

## Making a simple Hello World program

The first thing we are going to do is to print `Hello World` to the terminal.

Before we do that, we need to specify the _**`package`**_ name.

> **NOTE**: A _**`package`**_ is a collection of Go files that share information.
> It is a way to organize your code.

The first package to run is the **`main`** package.

To declare a package, we use the `package` keyword followed by the name of the package.
So, we'll add the following line to the top of our `main.go` file:

```go
package main
```

Ok, now, we need to add more boilerplate code to the `main.go` file.

Now, we need to import the `fmt` package.

> **WARNING**: When you **import** a package, you are using an external package.

To import a package, we use the `import` keyword followed by the name of the package in
quotes (double or single).

So, we'll add the following line bellow the `package main` line:

```go
import "fmt"
```

Now, the last thing we need to do is to add the `main` function.

A function is a block of code can be wrote once and executed multiple times.
Even tough, the `main` function is the entry point of our program and is executed only once.

To declare a function, we use the `func` keyword followed by the name of the function,
parenthesis and curly brackets (`{}`) to delimit the code block used by the function.

So (finally), we'll add the following line bellow the `import "fmt"` line:

```go
func main() {
}
```

Now, all full:

```go
package main

import "fmt"

func main() {
}
```

Ok, now, after we've added the boilerplate code, we can write actual code.

Let's use the `fmt` package to print `Hello World` to the terminal.
`fmt` comes with the `Println` function that prints a string to the terminal and
adds a new line at the end.

By the way, here the syntax of the `Println` function:

```go
fmt.Println("<text in double/single quotes>")
```

So, we'll add the following line bellow the `func main()` line:

```go
fmt.Println("Hello World")
```

Now, here the full code:

```go
package main

import "fmt"

func main() {
    fmt.Println("Hello, World!")
}
```

### Line-by-line explanation

1. We declare the `main` _package_ with the `package` keyword followed by the name of the package.
   Remember, the main package is the entry point of our program.

2. A blank line, it helps our code to be more readable.

3. We import the `fmt` _package_ with the `import` keyword followed by the name of the package in
   quotes (double or single); `fmt` lets us do things with the terminal.

4. Another blank line, again, it helps our code to be more readable.

5. We declare the `main` _function_ with the `func` keyword followed by the name of the function,
   parenthesis and curly brackets (`{}`) to delimit the code block used by the function.
   Remember, the `main` function is the entry point of our program and is executed only once.

6. We use the `fmt` _package_ to print `Hello World` to the terminal with the `Println` function.

7. We close the `main` _function_ with the `}` curly bracket.

### Running the program

To run the program, we need to [**_compile_**](<https://en.wikipedia.org/wiki/Compile_(computing)>) it.

Luckily, Go has a built-in tool to compile our code.

To compile a Go program, we use the `go run` command followed by the name of the file.
So, we'll run the following command in the terminal:

```bash
$ go run main.go # NOTE: Don't copy the $ sign
Hello, World!
```

Nice! Now, we have a working Go program.

## Variables

Variables are used to store _variable_ data (Use [Constants](#constants) for _constant_ data).

Variables are declared with the `var` keyword followed by the name of the variable and,
optionally, the [data type](#data-types) of the variable.

> **PRO TIP**: Use `camelCase` (first letter is lowercase,
> and the initial letter of each word is uppercase) for variable names so we can separate words.
> For example: `myVariableName`

So, delete all the code inside the `main` function and add the following line:

```go
var temperature = 24.3
```

### Accessing variables

To access a variable, we simply use its name as a number, text, or whatever the
variable is used for.

For example, to print the value of the `temperature` variable, we can use the `Println` function:

```go
package main

import "fmt"

func main() {
    var temperature = 24.3
    fmt.Println(temperature)
}
```

This will print `24.3` to the terminal (as the variable's value is 24.3).

### Data types

Go has a few data types; data types define what a variable can store.

Go has every data type you would expect:

---

| Data type | Description                  | Use cases                           |
| --------- | ---------------------------- | ----------------------------------- |
| `bool`    | True or false values         | Comparisons, on or off switche, etc |
| `int`     | Whole numbers                | Ages, years, etc.                   |
| `float`   | Numbers with decimals        | Temperatures, weights, etc.         |
| `string`  | Text                         | Names, addresses, etc.              |
| `rune`    | Single **unicode** character | Emojis, letters, etc.               |

---

> **NOTE**: [Unicode](https://en.wikipedia.org/wiki/Unicode) is a standard that defines
> the characters that can be used in a computer.
> There are others (like ASCII) but Unicode is the most common and complete.
> Characters are represented by a number, called a _**code point**_, so we can use
> `int`s to store `rune`s and vice versa.

## Constants

Constants are used to store _constant_ data.
These have similarities with [Variables](#variables), but they are declared with the `const` keyword.

For example, we can make a constant called `PI` with the value `3.141592653`.

```go
const PI = 3.141592653
```

> **TIP**: Use `SCREAMING_SNAKE_CASE` for constants (all uppercase, separated by underscores).
