**Packages** are Go's way of organizing code.

Programs are written as one or more packages.
    | packages can be imported from the Go packages registry.

Packages should be focused on perform a single thing.
    | argument parsing.
    | drawing graphics.
    | handling HTTP.

Using Packages:
```go
    import "name"

    import (
        "name"
        "namespace/packageName"
    )
```
Can import everything using a dot (.)
    | No need to reference package name in code.
| Imports can be renamed.
```go
    import (
        . "name"
        pk "namespcae/packageName"
    )
```



**Modules** are a collection of packages.
Created by having a **go.mod** file in the root directory of your project.
    | can be managed by the GO CLI
Contains information about your project.
    | dependencies, Go version, package info.
All Go projects have a **go.mod** file.
> Example Module:
```go
    module example.com/practice
    go 1.17
    require (
        github.com/alexfint/go-arg v1.4.2
        github.com/fatih/color v1.13.0
    )
```




# Data Types

| Go is a statically typed language.
| Go uses **type inference** to determine what type of data it is working with.
`   `|| data types only need to be provided in specific circumstances.
`   `|| can always specify the type if desired.
| All primitive types in Go are numeric.
`   `|| signed integer type:   **int8**, **int16**, **int**, **int32**, **int64**
`   `|| unsigned integer type: **uint8**, **byte**, **uint16**, **uint**, **uint32**, **uint64**, **uintptr**
`   `|| others:  **float32**, **float64**, **complex64**, **complex128**, **bool**


# Type Aliases
> Example:
```go
    type UserId int32
    type Direction byte
    type Speed float64
    type Velocity Speed
```

# Type Conversions
> Example:
```go
    type UserId int32
    type Speed float64

    UserId(5)       // convert to UserId type.
    Speed(88.3)     // convert to Speed type.
```


# Strings & Runes

| Textual data in Go uses **UTF-8** encoding.
| Encoding is a way to represent thousands of different symbols using **code pages**.
| Code pages are tables which use the *first few bytes* of data to determine which page to use.
`   `|| each symbol in the code page is called a **code point**.
`   `|| e.g. **0**0 is 'A' but **1**0 is 'a', **0**1 is 'B' but **1**1 is 'b'.
| Text is represented using the **rune** type.
`   `|| similar to **char** in other programming languages.
| **rune** is an alias for **int32** actually.
`   `|| will print numeric value unless proper formatting is specified.
| A **rune** can represent any symbol.
`   `|| letters, numbers, emojis, etc.
| A **string** is the data type for storing multiple **rune**s.
| Strings are just an array of **byte**s and a string length.
`   `|| there's no null terminator with a Go **string**.
| When iterating over a **string**, iteration occurs over **byte**s.
`   `|| bytes are not symbols.
`   `|| special iteration required to retrieve runes/symbols.
> Example Creation:
```go
    'a' 'R' '7' '\n' 'Ω'            // runes
    "Amount is $22" "k"             // strings
    `Let's code in "Golang"!\n`     // raw literal
```


# Go CLI

| Go toolchain provides the go command line utility:
`   `|| update dependencies.
`   `|| build & test projects.
`   `|| manage artifacts.
`   `|| format source code.
| Everyday Go Commands:
`   `|| **build**: builds the project & emits an executable binary.
`       `|| **build -race**: checks for concurrency problems.
`   `|| **run**: runs the project directly, no output executable.
`   `|| **mode**: manages modules & dependencies.
`       `|| **mode tidy**: updates dependencies.
`   `|| **test**: runs the project's test suite.
`   `|| **fmt**: fromats all source files.




