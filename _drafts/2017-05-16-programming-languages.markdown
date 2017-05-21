---
layout: post
title: "计算机程序设计：语言篇"
date: "2017-05-16 12:51:53 +0800"
---

<!-- TOC -->

- [Data types, operators and expressions](#data-types-operators-and-expressions)
    - [Overview](#overview)
        - [Type list](#type-list)
        - [Show Type Info](#show-type-info)
        - [Variable Declaration](#variable-declaration)
    - [Boolean](#boolean)
        - [Variable Declaration](#variable-declaration-1)
        - [Logical Operators](#logical-operators)
    - [Number](#number)
        - [Constants](#constants)
        - [Variable Declaration](#variable-declaration-2)
        - [Arithmetic Operators](#arithmetic-operators)
        - [Assignment Operators](#assignment-operators)
        - [Comparison Operators](#comparison-operators)
        - [Bitwise Operators](#bitwise-operators)
    - [String](#string)
        - [Variable Declaration](#variable-declaration-3)
        - [Assignment Operators](#assignment-operators-1)
        - [Comparison Operators](#comparison-operators-1)
    - [Pointer and Reference](#pointer-and-reference)
    - [Array and List](#array-and-list)
        - [Definition](#definition)
        - [Access/Traversal](#accesstraversal)
        - [Add element](#add-element)
        - [Delete element](#delete-element)
        - [Search element](#search-element)
    - [Tuple](#tuple)
    - [Directory/Hash/Associative array](#directoryhashassociative-array)
        - [Definition](#definition-1)
        - [CRUD](#crud)
    - [Date and Time](#date-and-time)
        - [Format](#format)
        - [Operation](#operation)
    - [Preprocessing](#preprocessing)
- [Control statements](#control-statements)
    - [if](#if)
    - [switch](#switch)
    - [while](#while)
    - [for](#for)
    - [break and continue](#break-and-continue)
    - [exception](#exception)
- [Function](#function)
    - [Definition](#definition-2)
        - [Variable arguments](#variable-arguments)
        - [Local and Global (Scope)](#local-and-global-scope)
        - [Return Value](#return-value)
    - [Overload and Default Arguments](#overload-and-default-arguments)
    - [Recursive](#recursive)
    - [Callback](#callback)
    - [Lambda](#lambda)
- [Class and Object](#class-and-object)
    - [Definition (property and method)](#definition-property-and-method)
    - [Class/Object Memeber](#classobject-memeber)
        - [this/self](#thisself)
        - [*Case Study*](#case-study)
    - [Encapsulation (private/protected/public)](#encapsulation-privateprotectedpublic)
    - [Constructor and Destructor](#constructor-and-destructor)
        - [GC](#gc)
        - [finalize](#finalize)
- [Inheritance and Polymorphism](#inheritance-and-polymorphism)
    - [Inherit](#inherit)
        - [super](#super)
        - [protected, default](#protected-default)
        - [final](#final)
    - [Polymorphism](#polymorphism)
        - [Override](#override)
        - [virtual](#virtual)
    - [Abstract Class](#abstract-class)
    - [Interface](#interface)
        - [Implements](#implements)
        - [Extends](#extends)
        - [Multiple implements/extends](#multiple-implementsextends)
- [Generic/Template Class](#generictemplate-class)
    - [<?>](#)
- [Collection](#collection)
    - [Set](#set)
    - [List](#list)
    - [Map](#map)
    - [Vector](#vector)
- [String and Regular Expression](#string-and-regular-expression)
    - [Basic operations](#basic-operations)
        - [Format](#format-1)
        - [Compare](#compare)
        - [Sub string](#sub-string)
        - [Search and substitution](#search-and-substitution)
        - [Split and join](#split-and-join)
        - [String-Number Conversion](#string-number-conversion)
    - [regular expressions](#regular-expressions)
- [Modular Programming](#modular-programming)
    - [Header](#header)
    - [Static](#static)
    - [Statically-linked libs](#statically-linked-libs)
    - [Dynamically-linked libs](#dynamically-linked-libs)
    - [Package](#package)
        - [Create (jar)](#create-jar)
- [Reflection](#reflection)
    - [Class](#class)
        - [Get Name](#get-name)
        - [from Name](#from-name)
    - [Properties/Fields](#propertiesfields)
        - [Get Fields](#get-fields)
        - [Access Fields](#access-fields)
    - [Methods](#methods)
        - [Get Methods](#get-methods)
        - [Invoke Methods](#invoke-methods)
- [Annotations/Decorators](#annotationsdecorators)
    - [Built-in Annotations](#built-in-annotations)
- [Others](#others)
    - [Reserved/Key words](#reservedkey-words)
        - [Java](#java)
        - [JavaScript](#javascript)
        - [Python](#python)
    - [Comments and docstring](#comments-and-docstring)
    - [Versions and Features](#versions-and-features)

<!-- /TOC -->

# Data types, operators and expressions

## Overview

typeof

instanceof

typedef

### Type list


JavaScript:
1. boolean
2. number
3. string
4. function
5. object
6. undefined

TypeScript:
1. boolean
2. number
3. string
4. Array
5. tuple
6. enum
7. any
8. void


<!--
string

int  int8  int16  int32  int64
uint uint8 uint16 uint32 uint64 uintptr

byte // alias for uint8

rune // alias for int32
     // represents a Unicode code point

float32 float64

complex64 complex128
-->

<!--
Type   bool  byte  char  int16  uint16  int32  uint32  int64  uint64  float32  float64  complex64  complex128   pointer
Go    bool  byte  char  int16  uint16  int32  uint32  int64  uint64  float32  float64  complex64  complex128   pointer
Java   boolean  
JavaScript
Python
-->

### Show Type Info

Java: getClass()

JavaScript: typeof()

Python: type()

TypeScript: ?

### Variable Declaration

JavaScript:

```javascript
"use strict";

var a = 1;
let b = 2;
const c = 3;
```

TypeScript:

```typescript
var a: number = 1;
let b: number = 2;
const c: number = 3;
```

## Boolean

### Variable Declaration
constants: true/false

TypeScript:
```typescript
let done: boolean = true;
```

### Logical Operators

```javascript
==, ===
&&, ||, !
```

## Number

### Constants

0b11, 011/0o11, 0x11

2e3 (JS/TS/Python)

Math.PI

complex

enum

### Variable Declaration


### Arithmetic Operators

C/C++/Java/JavaScript/TypeScript:
```c
+
-
*
/
%
++
--
```

### Assignment Operators

C/C++/Java/JavaScript/TypeScript:
```c
=
+=
-=
*=
/=
%=
```

### Comparison Operators

```c
==
=== // JavaScript only
!=
!== // JavaScript only
>
<
>=
<=
?:
```

### Bitwise Operators

```c
&
|
~
^
<<
>>
>>>
```

## String

Unicode

### Variable Declaration

JavaScript:

```javascript
let s1 = "123";
```

TypeScript:
```typescript
let s1: string = "123";
```

### Assignment Operators

Java/JavaScript/TypeScript:
```c
=
+=
```

### Comparison Operators


```c
==
=== // JavaScript only, not recommended
!=
!== // JavaScript only, not recommended
>
<
>=
<=
```

## Pointer and Reference

## Array and List

Use random

### Definition

JavaScript:

```javascript
let ar = [11, 33, 22, 'abc'];
```

TypeScript:

```typescript
let ar: Array<any> = [11, 33, 22, 'abc'];
```

Python:

```python
ar = [11, 33, 22, 'abc']
```

### Access/Traversal

Basic:

```basic

```

C/C++:

```c

```

C#:

```C#

```

Erlang:

```erlang

```

Go:

```go

```

Groovy:

```groovy

```

Haskell:

```haskell

```

Java:

```java

```

JavaScript:

```javascript
//method 1:
for(let i = 0; i < list.length; i++) {
    console.log(list[i]);
}
//method 2:
for(let i in list) {
    console.log(list[i]);
}
//method 3:
for(let x of list) {
    console.log(x);
}
```

Kotlin:

```kotlin

```

Lua:

```lua

```

PHP:

```php

```

Matlab:

```matlab

```

Perl:

```perl

```

PowerShell:

```powershell

```

Python:

```python

```

R:

```r

```

Ruby:

```ruby

```

Rust:

```rust

```

Scala:

```scala

```

Swift:

```swift

```

TypeScript:

```typescript
//method 1:
for(let i = 0; i < list.length; i++) {
    console.log(list[i]);
}
//method 2:
for(let i in list) {
    console.log(list[i]);
}
//method 3:
for(let x of list) {
    console.log(x);
}
```

VB Script:

```vbs

```


### Add element

Basic:

```basic

```

C/C++:

```c

```

C#:

```C#

```

Erlang:

```erlang

```

Go:

```go

```

Groovy:

```groovy

```

Haskell:

```haskell

```

Java:

```java

```

JavaScript:

```javascript

```

Kotlin:

```kotlin

```

Lua:

```lua

```

PHP:

```php

```

Matlab:

```matlab

```

Perl:

```perl

```

PowerShell:

```powershell

```

Python:

```python

```

R:

```r

```

Ruby:

```ruby

```

Rust:

```rust

```

Scala:

```scala

```

Swift:

```swift

```

TypeScript:

```typescript

```

VB Script:

```vbs

```


### Delete element

Basic:

```basic

```

C/C++:

```c

```

C#:

```C#

```

Erlang:

```erlang

```

Go:

```go

```

Groovy:

```groovy

```

Haskell:

```haskell

```

Java:

```java

```

JavaScript:

```javascript

```

Kotlin:

```kotlin

```

Lua:

```lua

```

PHP:

```php

```

Matlab:

```matlab

```

Perl:

```perl

```

PowerShell:

```powershell

```

Python:

```python

```

R:

```r

```

Ruby:

```ruby

```

Rust:

```rust

```

Scala:

```scala

```

Swift:

```swift

```

TypeScript:

```typescript

```

VB Script:

```vbs

```


### Search element


Basic:

```basic

```

C/C++:

```c

```

C#:

```C#

```

Erlang:

```erlang

```

Go:

```go

```

Groovy:

```groovy

```

Haskell:

```haskell

```

Java:

```java

```

JavaScript:

```javascript

```

Kotlin:

```kotlin

```

Lua:

```lua

```

PHP:

```php

```

Matlab:

```matlab

```

Perl:

```perl

```

PowerShell:

```powershell

```

Python:

```python

```

R:

```r

```

Ruby:

```ruby

```

Rust:

```rust

```

Scala:

```scala

```

Swift:

```swift

```

TypeScript:

```typescript

```

VB Script:

```vbs

```


## Tuple

Basic:

```basic

```

C/C++:

```c

```

C#:

```C#

```

Erlang:

```erlang

```

Go:

```go

```

Groovy:

```groovy

```

Haskell:

```haskell

```

Java:

```java

```

JavaScript:

```javascript

```

Kotlin:

```kotlin

```

Lua:

```lua

```

PHP:

```php

```

Matlab:

```matlab

```

Perl:

```perl

```

PowerShell:

```powershell

```

Python:

```python

```

R:

```r

```

Ruby:

```ruby

```

Rust:

```rust

```

Scala:

```scala

```

Swift:

```swift

```

TypeScript:

```typescript

```

VB Script:

```vbs

```

## Directory/Hash/Associative array

### Definition

Java

```java
Map m = new XMap<Type1, Type2>();
```

JavaScript:

```javascript
var m = {key1:value1, key2:value2, ...};
```

types of values may be different.

reference:

m[key] or m.key

Python

```python
m = {}
```

builtin map() function

Interation

dictionary view:

```python
m = {'aa': 11, 'bb': 22}
keys = m.keys()

print(keys, m)
del m['aa']
print(keys, m)
```


Basic:

```basic

```

C/C++:

```c

```

C#:

```C#

```

Erlang:

```erlang

```

Go:

```go

```

Groovy:

```groovy

```

Haskell:

```haskell

```

Java:

```java

```

JavaScript:

```javascript

```

Kotlin:

```kotlin

```

Lua:

```lua

```

PHP:

```php

```

Matlab:

```matlab

```

Perl:

```perl

```

PowerShell:

```powershell

```

Python:

```python

```

R:

```r

```

Ruby:

```ruby

```

Rust:

```rust

```

Scala:

```scala

```

Swift:

```swift

```

TypeScript:

```typescript

```

VB Script:

```vbs

```

### CRUD


Basic:

```basic

```

C/C++:

```c

```

C#:

```C#

```

Erlang:

```erlang

```

Go:

```go

```

Groovy:

```groovy

```

Haskell:

```haskell

```

Java:

```java

```

JavaScript:

```javascript

```

Kotlin:

```kotlin

```

Lua:

```lua

```

PHP:

```php

```

Matlab:

```matlab

```

Perl:

```perl

```

PowerShell:

```powershell

```

Python:

```python

```

R:

```r

```

Ruby:

```ruby

```

Rust:

```rust

```

Scala:

```scala

```

Swift:

```swift

```

TypeScript:

```typescript

```

VB Script:

```vbs

```


## Date and Time

### Format

Basic:

```basic

```

C/C++:

```c

```

C#:

```C#

```

Erlang:

```erlang

```

Go:

```go

```

Groovy:

```groovy

```

Haskell:

```haskell

```

Java:

```java

```

JavaScript:

```javascript

```

Kotlin:

```kotlin

```

Lua:

```lua

```

PHP:

```php

```

Matlab:

```matlab

```

Perl:

```perl

```

PowerShell:

```powershell

```

Python:

```python

```

R:

```r

```

Ruby:

```ruby

```

Rust:

```rust

```

Scala:

```scala

```

Swift:

```swift

```

TypeScript:

```typescript

```

VB Script:

```vbs

```


### Operation

Basic:

```basic

```

C/C++:

```c

```

C#:

```C#

```

Erlang:

```erlang

```

Go:

```go

```

Groovy:

```groovy

```

Haskell:

```haskell

```

Java:

```java

```

JavaScript:

```javascript

```

Kotlin:

```kotlin

```

Lua:

```lua

```

PHP:

```php

```

Matlab:

```matlab

```

Perl:

```perl

```

PowerShell:

```powershell

```

Python:

```python

```

R:

```r

```

Ruby:

```ruby

```

Rust:

```rust

```

Scala:

```scala

```

Swift:

```swift

```

TypeScript:

```typescript

```

VB Script:

```vbs

```


## Preprocessing

# Control statements

## if

JavaScript:

```javascript
===
```

Python:

elif, <>, in

## switch

Java: case String

JavaScript: 'case' means '==='

Python: not support

<!--## 2.3. goto-->

## while

practice: Insert, Merge

## for

## break and continue

## exception

C++/Java/JavaScript in common:

```java
try {
	throw
} catch () {

} catch () {

} finally {

}
```

Java: throws

Python:

```python
try:
	...
	raise xxx
	...
except ExceptionType, Argument:
	...
except ExceptionType1[, ExceptionType2, ...]:
	...
else:
	...
```

# Function

## Definition

Python:

```python
def foo(x):
    return 2 * x
```

or with type checking:

```python
def foo(x: int) -> int:
    return 2 * x
```

pass

### Variable arguments

### Local and Global (Scope)

JavaScript:

```javascript
var a = 11, b = 11;

function foo() {
    var a;
    a = 22;
    b = 22;
}

foo();
console.log(a, b);
```

### Return Value

object copy or reference?

## Overload and Default Arguments

Lang | Overload | Default Arguments
-----|----------|------------------
C++ | Y | Y
Java | Y | N
JavaScript | N | Y
Python | N | Y

## Recursive

## Callback

## Lambda

JavaScript:

```javascript
f = (x) => x * x;
console.log(f(3));

f = (x) => { y = x * x; return y; }
console.log(f(3));
```

Python:

```python
f = lambda x:  x * x
print(f(3))
```

# Class and Object

## Definition (property and method)

Java: (skipped)

JavaScript:

```javascript
function Demo() {
    console.log('init')
    this.a = 11;
    this.foo = function (x) { // or use lambda ('=>')
        console.log(x + this.a)
    }
}

var demo = new Demo()
demo.foo(22)
```

anonymous class

```javascript
var demo = {
    a: 11,
    foo: function (x) { // or use lambda ('=>')
         console.log(x + this.a)
    }
}

// var demo = new Demo()
demo.foo(22)
```

Python:

```python

```

## Class/Object Memeber

### this/self

### *Case Study*

<!--this for constructor-->
Java:

```java
public class Demo {
    static int x = 11;
    // int x = 22; // error: variable x is already defined
}
```

JavaScript:


Python:

```python
x = 11 # static/class property

class Demo():
    x = 22

    # object/instance method
    def __init__(self):
        self.x = 33 # object property
        print(x)

    # static method
	# add @staticmethod for python 2.x
    def foo():
        print(x)
        print(Demo.x)

demo = Demo()
print(demo.x)
Demo.foo()
```

or:

```python
# class method
@classmethod
def foo(cls):
    print(x)
    print(cls.x)
```


comment line 7 and check output again

## Encapsulation (private/protected/public)

Java: +default


Python: none

__ as private in convention


## Constructor and Destructor

Python:

```python
__init__()

__del__()

```

### GC

### finalize

# Inheritance and Polymorphism

## Inherit

### super

Pyton:

```python
class A:
    def foo(self):
        print('A', type(self))

class B(A):
    def foo(self):
        print('B', type(self))

class C(B):
    def foo(self):
        super().foo() # super(B, self).foo()
        super(C, self).foo()

c = C()
c.foo()
```

### protected, default

### final

## Polymorphism

### Override

### virtual

## Abstract Class

Java:

```java
public class Demo {
    public abstract void foo();
}
```

Python 2.x:

```python
from abc import ABCMeta, abstractmethod

class Demo(object):
    __metaclass__ = ABCMeta

    @abstractmethod
    def foo(self):
        pass
```

Python 3.x:

```python
from abc import ABCMeta, abstractmethod

class Demo(metaclass=ABCMeta):
    @abstractmethod
    def foo(self):
        pass
```

## Interface

### Implements

### Extends

### Multiple implements/extends

# Generic/Template Class

## <?>

# Collection

## Set

## List

## Map

## Vector

# String and Regular Expression

## Basic operations

### Format

Python 3.x:

```python
key = 'abc'
value = 123
content = f'{key} = {value}'

print(content)
```

### Compare

### Sub string

### Search and substitution

### Split and join

### String-Number Conversion

<!--StringBuffer, StringBuilder-->

## regular expressions

# Modular Programming

## Header

## Static

## Statically-linked libs

## Dynamically-linked libs

## Package

### Create (jar)

# Reflection

## Class

### Get Name

Java: getName

Python:

```python
class Demo:
    foo = 123

demo = Demo()
print(type(demo).__name__)
```

### from Name

Java: forName

Python:

```python

```

## Properties/Fields

### Get Fields

Java:
getFields
getDeclaredFields

### Access Fields

Java:
Field.get()/set()

Python:

```python
class Demo:
    foo = 123

f = getattr(Demo, 'foo')
print(f)
```

## Methods

```java
public class Demo {
    public static void foo() {
        System.out.println("foo()");
    }

    public static void main(String[] args) throws NoSuchMethodException, InvocationTargetException, IllegalAccessException {
        Method fooMethod = Demo.class.getMethod("foo", new Class[]{});
        fooMethod.invoke(Demo.class);
    }
}
```

### Get Methods

Java:
getMethods()
getDeclaredMethods()

```java
public class Demo {
    public static void foo() {
        System.out.println("foo()");
    }

    public static void main(String[] args) throws NoSuchMethodException, InvocationTargetException, IllegalAccessException {
        Demo demo = new Demo();
        Class<Demo> demoClass = Demo.class;
        Method method = demoClass.getMethod("foo", new Class[]{});
        method.invoke(demo);
    }
}
```

### Invoke Methods
Java:
invoke()

Python:

```python
class Demo:
    def foo(x):
        return x * x

f = getattr(Demo, 'foo')
print(f(3))
```

# Annotations/Decorators

## Built-in Annotations

Java:

@Deprecated
@Override
@SuppressWarnings

# Others

## Reserved/Key words

### Java

### JavaScript

### Python

## Comments and docstring

## Versions and Features

