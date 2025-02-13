---
layout: post
title: Prime Time All The Time
date: 2025-02-04 15:57 +0200
---

## Prime numbers
A prime number is a number divisable by 1 and itself. That's it! There's nothing more to it. There might be if you want it to be, but that's the basic of prime numbers. "How come people often talk about them", the simpleton asks. Fear not, allow the **intellectual** to answer.  

![Mr Bean Waiting](/assets/img/posts/mr-bean-waiting.gif)

It seems the **intellectual** did not respond. Allow me to take a stab at it.

But all of that yapping is simply to get to the actual content of the post. I want to see in how many programming languages can I write an `isPrime` function! With that knowledge, welcome to the abyss as we dive into all sorts of programming languages trying to discover a prime!

## Table Of Contents

| Language |
|----------|
| [General-Purpose Programming Languages](#general-purpose-programming-languages) |
| [Web Development Languages & Frameworks](#web-development-languages--frameworks) |
| [Mobile & UI Development](#mobile--ui-development) |
| [Scientific & Mathematical Computing](#scientific--mathematical-computing) |
| [Game Development & Graphics](#game-development--graphics) |
| [Embedded Systems & Low-Level Languages](#embedded-systems--low-level-languages) |
| [Scripting & Shell Languages](#scripting--shell-languages) |
| [Functional & Logical Programming](#functional--logical-programming) |
| [Database Query & Blockchain Languages](#database-query--blockchain-languages) |
| [High-Performance & Parallel Computing](#high-performance--parallel-computing) |

### General-Purpose

| Language |
|----------|
| [Java](#java) |
| [Groovy](#groovy) |
| [Kotlin](#kotlin) |
| [Go](#go) |
| [Python](#python) |
| [C](#c) |
| [C++](#c-1) |
| [C#](#c-2) |
| [Swift](#swift) |
| [Rust](#rust) |
| [Dart](#dart) |
| [Ruby](#ruby) |
| [Vala](#vala) |
| [Julia](#julia) |
| [Nim](#nim) |
| [Perl](#perl) |
| [PHP](#php) |
| [Scala](#scala) |

---

#### Java
```java
boolean isPrime(int n) {
    if (n < 2) return false;
    for (int i = 2; i * i <= n; i++) {
        if (n % i == 0) return false;
    }
    return true;
}
```

#### Groovy
```groovy
boolean isPrime(int n) {
    if (n < 2) return false
    for (int i = 2; i * i <= n; i++) {
        if (n % i == 0) return false
    }
    return true
}
```

#### Kotlin
```kotlin
fun isPrime(n: Int): Boolean {
    if (n < 2) return false

    var i = 2
    while (i * i <= n) {
        if (n % i == 0) return false
        i++
    }

    return true
}
```

#### Go
```go
func isPrime(n int) bool {
    if n < 2 {
        return false
    }

    for i := 2; i*i <= n; i++ {
        if n%i == 0 {
            return false
        }
    }

    return true
}
```

#### Python
_To do..._

#### C
_To do..._

#### C++
_To do..._

#### C#
_To do..._

#### Swift
_To do..._

#### Rust
_To do..._

#### Dart
_To do..._

#### Ruby
_To do..._

#### Vala
_To do..._

#### Julia
_To do..._

#### Nim
_To do..._

#### Perl
_To do..._

#### PHP
_To do..._

#### Scala
_To do..._


### Web Development & Frameworks

| Language |
|----------|
| [JavaScript](#javascript) |
| [TypeScript](#typescript) |
| [HTML/CSS](#htmlcss) |
| [Razor](#razor) |
| [ASP.NET](#aspnet) |
| [Svelte](#svelte) |
| [Hack](#hack) |

---

#### JavaScript
_To do..._

#### TypeScript
_To do..._

#### HTML/CSS
_To do..._

#### Razor
_To do..._

#### ASP.NET
_To do..._

#### Svelte
_To do..._

#### Hack
_To do..._


### Mobile & UI Development

| Language |
|----------|
| [Flutter](#flutter) |
| [React Native](#react-native) |
| [Xamarin](#xamarin) |
| [Objective-C](#objective-c) |

---

#### Flutter
_To do..._

#### React Native
_To do..._

#### Xamarin
_To do..._

#### Objective-C
_To do..._


### Scientific & Mathematical Computing

| Language |
|----------|
| [R](#r) |
| [MATLAB](#matlab) |
| [SAS](#sas) |
| [Octave](#octave) |
| [Wolfram](#wolfram) |
| [Stan](#stan) |
| [JAX](#jax) |
| [Maple](#maple) |
| [Maxima](#maxima) |
| [SageMath](#sagemath) |
| [J](#j) |

---

#### R
_To do..._

#### MATLAB
_To do..._

#### SAS
_To do..._

#### Octave
_To do..._

#### Wolfram
_To do..._

#### Stan
_To do..._

#### JAX
_To do..._

#### Maple
_To do..._

#### Maxima
_To do..._

#### SageMath
_To do..._

#### J
_To do..._


### Game Development & Graphics

| Language |
|----------|
| [UnityScript](#unityscript) |
| [UnrealScript](#unrealscript) |
| [GDScript](#gdscript) |
| [Haxe](#haxe) |
| [Löve2D](#löve2d) |
| [GameMaker](#gamemaker) |
| [Cocos2d](#cocos2d) |

---

#### UnityScript
_To do..._

#### UnrealScript
_To do..._

#### GDScript
_To do..._

#### Haxe
_To do..._

#### Löve2D
_To do..._

#### GameMaker
_To do..._

#### Cocos2d
_To do..._


### Embedded Systems & Low-Level

| Language |
|----------|
| [Assembly](#assembly) |
| [Embedded C](#embedded-c) |
| [Ada](#ada) |
| [Forth](#forth) |
| [MicroPython](#micropython) |
| [NXC](#nxc) |
| [VHDL](#vhdl) |
| [Verilog](#verilog) |
| [PIC Assembly Language](#pic-assembly-language) |
| [Zig](#zig) |

---

#### Assembly
_To do..._

#### Embedded C
_To do..._

#### Ada
_To do..._

#### Forth
_To do..._

#### MicroPython
_To do..._

#### NXC
_To do..._

#### VHDL
_To do..._

#### Verilog
_To do..._

#### PIC Assembly Language
_To do..._

#### Zig
_To do..._


### Scripting & Shell

| Language |
|----------|
| [Lua](#lua) |
| [Tcl](#tcl) |
| [PowerShell](#powershell) |
| [Bash](#bash) |
| [AWK](#awk) |
| [Fish Shell](#fish-shell) |
| [BeanShell](#beanshell) |

---

#### Lua
_To do..._

#### Tcl or Tool Command Language
_To do..._

#### PowerShell
_To do..._

#### Bash
_To do..._

#### AWK
_To do..._

#### Fish Shell
_To do..._

#### BeanShell
_To do..._

### Functional & Logical Programming

| Language |
|----------|
| [Haskell](#haskell) |
| [F#](#f) |
| [OCaml](#ocaml) |
| [Elm](#elm) |
| [Idris](#idris) |
| [PureScript](#purescript) |
| [Scheme](#scheme) |
| [Lisp](#lisp) |
| [Agda](#agda) |
| [Clojure](#clojure) |
| [Racket](#racket) |
| [Elixir](#elixir) |

---

#### Haskell
_To do..._

#### F#
_To do..._

#### OCaml
_To do..._

#### Elm
_To do..._

#### Idris
_To do..._

#### PureScript
_To do..._

#### Scheme
_To do..._

#### Lisp
_To do..._

#### Agda
_To do..._

#### Clojure
_To do..._

#### Racket
_To do..._

#### Elixir
_To do..._

### Database Query & Blockchain

| Language |
|----------|
| [SQL](#sql) |
| [PL/SQL](#pl/sql) |
| [T-SQL](#t-sql) |
| [GraphQL](#graphql) |
| [Cypher](#cypher) |
| [SPARQL](#sparql) |
| [Datalog](#datalog) |
| [Solidity](#solidity) |
| [Vyper](#vyper) |
| [Michelson for Tezos Blockchain](#michelson-for-tezos-blockchain) |
| [Simplicity](#simplicity) |
| [Move for Diem Blockchain](#move-for-diem-blockchain) |
| [Hoon](#hoon) |
| [Clarity on Stacks blockchain](#clarity-on-stacks-blockchain) |

---

#### SQL
_To do..._

#### PL/SQL
_To do..._

#### T-SQL
_To do..._

#### GraphQL
_To do..._

#### Cypher
_To do..._

#### SPARQL
_To do..._

#### Datalog
_To do..._

#### Solidity
_To do..._

#### Vyper
_To do..._

#### Michelson for Tezos Blockchain
_To do..._

#### Simplicity
_To do..._

#### Move for Diem Blockchain
_To do..._

#### Hoon
_To do..._

#### Clarity on Stacks blockchain
_To do..._


### Performance & Parallel Computing

| Language |
|----------|
| [FORTRAN](#fortran) |
| [OpenCL](#opencl) |
| [CUDA C/C++](#cuda-cc) |
| [Chapel](#chapel) |
| [Futhark](#futhark) |
| [Pony](#pony) |
| [Crystal](#crystal) |
| [Red](#red) |
| [Q](#q) |

#### FORTRAN
_To do..._

#### OpenCL
_To do..._

#### CUDA C/C++
_To do..._

#### Chapel
_To do..._

#### Futhark
_To do..._

#### Pony
_To do..._

#### Crystal
_To do..._

#### Red
_To do..._

#### Q
_To do..._
