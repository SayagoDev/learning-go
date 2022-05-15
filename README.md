# Go <!-- omit in toc -->

## Table of Contents <!-- omit in toc -->

- [Data Types](#data-types)
- [Strings & Runes](#strings--runes)
- [Go CLI Tool](#go-cli-tool)
- [Variables](#variables)
- [Functions](#functions)

## Data Types

- All data in programs consiste of binary numbers (0 or 1)
- A _**data type**_ is a way that the program can interpret the binary numbers
- Numbers, letters, and words are all different types
- Go is a statically typed language
  - Data types must be provided by the programmer
- Go uses _**type inference**_ to determine what type of data it is working with
  - Data types only need to be provided in specific circumstances
  - Can always specify the type if desired

**Primitive Data Types:**

- All primitive data types in Go are numeric
- Type indicated in code is a convention
  - It's possible that the data is invalid for the given type
    - Only applies when working with user input or manually manipulating the binary data

**Type Aliases:**

- Possible to create type aliases
- Same in every way to another type, just a different name
- Useful for providing indication of what kind of data is being utilized

```go
type UserId int
type Direction byte
type Speed float64
type Velocity Speed
```

**Type Conversions:**

Converting between types can be done with parentheses

```go
type UserId int
type Speed float64

UserId(5)
Speed(88.3)
```

## Strings & Runes

**Text Encoding:**

- Textual data in Go uses UTF-8 **encoding**
- Encoding is a way to represent thousands of different symbols using **code pages**
- Code pages are tables which use the first few bytes of data ot determine which page
  to use
  - Each symbol in the code page is called a **code point**

**Runes:**

- Text is represented using the **rune** type
  - Similar to **char** in many other programming languages
- **Rune** is an alias for int32 (32-bit integer)
  - Always a number: will print numeric value unless proper formatting is specified
- A rune can represent any symbol
  - Letters, numbers, emojis, etc.

**Strings:**

- A **string** is the data type for storing multiple runes
- Strings are just an array of **bytes** and a string length
  - There is no null termination with a Go **string**
- When iterating a string, iteration occurs over **bytes**
  - Bytes are **not** symbols
  - Special iteration required to retrieve runes/symbols

Runes: 'a', 'R', '7', '\n', \`ß\`, \`©\`
Strings: "Amount is €22\n"
Raw Literal: \`Let's code in "Golang!"\n\`

## Go CLI Tool

- Go toolchain provides the **go** command line utility
- This tools is used to:
  - Update dependencies
  - Build & test projects
  - Manage artifacts
  - Format source code

**Everyday Go Commands:**

- **build:** builds the project & emits an executable binary
  - **build -race:** checks for concurrency problems
- **run:** runs the projects directly; no output executable
- **mod:** manages modules & dependencies
  - **mod tidy:** updates dependencies
- **test:** runs the project's test suite
- **fmt:** formats all source code files (usually automated with IDE)

## Variables

**Single Creation:**

```go
var example = 3

var example int = 3

var example int
example = 3
```

**Compound Creation:**

```go
var a, b, c = 1, 2, "sample"
```

**Block Creation:**

```go
var (
  a int = 1
  b int = 2
  c = "sample"
)
```

**Create & Assign:**

```go
example := 3

a, b := 1, "sample"
```

**Naming:**

- Go variable naming convention is camelCase:

```go
myLongVariableName := "hi"
```

**Constants:**

- Constants can be created using the **const** keyword
- Useful when declaring some value that needs to be utilized
  throughout some or all fo the program

```go
const MaxSpeed = 30
const MinPurchasePrice = 7.50
const AppAuthor = "Bob"
```

## Functions

- Most basic building block of Go programs
- Allows functionality to be isolated, which makes programs easier to:
  - Test, debug, extend, modify, read, write, document
- Functions are simple: they take data as input and return data as output
  - Input and output data is optional

**Creating Functions:**

```go
func name(param1 type, param2 type) type {
  // body
}

// Example Function
func sum(lhs, rhs int) int {
  return lhs + rhs
}

// Multiple Return Values
func multiReturn() (int, int, int) {
  return 1, 2, 3
}

a, b, _ := multiReturn()
```