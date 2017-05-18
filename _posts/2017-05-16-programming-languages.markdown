---
layout: post
title: "计算机程序设计：语言篇"
date: "2017-05-16 12:51:53 +0800"
---

<!-- TOC -->

- [1. Data types, operators and expressions](#1-data-types-operators-and-expressions)
    - [1.1. Overview](#11-overview)
    - [1.2. Boolean](#12-boolean)
    - [1.3. Number](#13-number)
    - [1.4. String](#14-string)
    - [1.5. Pointer and Reference](#15-pointer-and-reference)
    - [1.6. Array and List](#16-array-and-list)
    - [1.7. Directory/Hash/Associative array](#17-directoryhashassociative-array)
    - [1.8. Date and Time](#18-date-and-time)
    - [1.9. Preprocessing](#19-preprocessing)
- [2. Control statements](#2-control-statements)
    - [2.1. if](#21-if)
    - [2.2. switch](#22-switch)
    - [2.3. while](#23-while)
    - [2.4. for](#24-for)
    - [2.5. break and continue](#25-break-and-continue)
    - [2.6. exception](#26-exception)
- [3. Function](#3-function)
    - [3.1. Definition](#31-definition)
    - [3.2. Overload and Default Arguments](#32-overload-and-default-arguments)
    - [3.3. Recursive](#33-recursive)
    - [3.4. Callback](#34-callback)
    - [3.5. Lambda](#35-lambda)
- [4. Class and Object](#4-class-and-object)
    - [4.1. Definition (property and method)](#41-definition-property-and-method)
    - [4.2. Class/Object Memeber](#42-classobject-memeber)
    - [4.3. Encapsulation (private/protected/public)](#43-encapsulation-privateprotectedpublic)
    - [4.4. Constructor and Destructor](#44-constructor-and-destructor)
- [5. Inheritance and Polymorphism](#5-inheritance-and-polymorphism)
    - [5.1. Inherit](#51-inherit)
    - [5.2. Polymorphism](#52-polymorphism)
    - [5.3. abstract class](#53-abstract-class)
    - [5.4. Interface](#54-interface)
- [6. Generic/Template Class](#6-generictemplate-class)
    - [6.1. <?>](#61-)
- [7. Collection](#7-collection)
    - [7.1. Java collection](#71-java-collection)
    - [7.2. Set](#72-set)
    - [7.3. List](#73-list)
    - [7.4. Map](#74-map)
    - [7.5. Vector](#75-vector)
- [8. String and Regular Expression](#8-string-and-regular-expression)
    - [8.1. Basic operations](#81-basic-operations)
    - [8.2. StringBuffer](#82-stringbuffer)
    - [8.3. StringBuilder](#83-stringbuilder)
    - [8.4. regular expressions](#84-regular-expressions)
- [9. Modular Programming](#9-modular-programming)
    - [9.1. Header](#91-header)
    - [9.2. Static](#92-static)
    - [9.3. Statically-linked libs](#93-statically-linked-libs)
    - [9.4. Dynamically-linked libs](#94-dynamically-linked-libs)
    - [9.5. Package](#95-package)
- [10. Reflection](#10-reflection)
    - [10.1. Class](#101-class)
    - [10.2. Field](#102-field)
    - [10.3. Method](#103-method)
- [11. Annotation](#11-annotation)
    - [11.1. Built in: over, dep, warn](#111-built-in-over-dep-warn)
- [12. Others](#12-others)
    - [12.1. Reserved/Key words](#121-reservedkey-words)
    - [12.2. Comments and docstring](#122-comments-and-docstring)
    - [12.3. Versions and Features](#123-versions-and-features)

<!-- /TOC -->

# 1. Data types, operators and expressions

## 1.1. Overview

### 1.1.1. Type list

print the type

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

### 1.1.2. Show Type Info

Java: getClass()

JavaScript: typeof()

Python: type()

### 1.1.3. typeof

### 1.1.4. typedef

## 1.2. Boolean

### 1.2.1. Definition

### 1.2.2. And/Or/Not

## 1.3. Number

### 1.3.1. Definition

### 1.3.2. Constants

### 1.3.3. Operators and Expressions

Bitwise Operation

## 1.4. String

Unicode

## 1.5. Pointer and Reference

## 1.6. Array and List

### 1.6.1. Definition
Use random

### 1.6.2. CRUD

## 1.7. Directory/Hash/Associative array

### 1.7.1. Definition

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

### 1.7.2. CRUD

## 1.8. Date and Time

### 1.8.1. Format

### 1.8.2. Operation

## 1.9. Preprocessing

# 2. Control statements

## 2.1. if

JavaScript:

```javascript
===
```

Python:

elif, <>, in

## 2.2. switch

Java: case String

JavaScript: 'case' means '==='

Python: not support

<!--## 2.3. goto-->

## 2.3. while

practice: Insert, Merge

## 2.4. for

## 2.5. break and continue

## 2.6. exception

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

# 3. Function

## 3.1. Definition

Python: pass

### 3.1.1. Variable arguments

### 3.1.2. Local and Global (Scope)

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

### 3.1.3. Return Value

object copy or reference?

## 3.2. Overload and Default Arguments

Lang | Overload | Default Arguments
-----|----------|------------------
C++ | Y | Y
Java | Y | N
JavaScript | N | Y
Python | N | Y

## 3.3. Recursive

## 3.4. Callback

## 3.5. Lambda

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

# 4. Class and Object

## 4.1. Definition (property and method)

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

## 4.2. Class/Object Memeber

### 4.2.1. this/self

### 4.2.2. *Case Study*

<!--this for constructor-->
Java:

```java
public class Demo {
    static int x = 11;
    // int x = 22; // error: variable x is already defined
```

JavaScript:


Python:

```python
x = 11 # static/class property

class Demo:
    x = 22

    def __init__(self): # object method
        self.x = 33 # object property
        print(x)

	# add @staticmethod for python 2.x
    def foo(): # static/class method
        print(x)
        print(Demo.x)

demo = Demo()
print(demo.x)
Demo.foo()
```

comment line 7 and check output again

## 4.3. Encapsulation (private/protected/public)

Java: +default


Python: none

__ as private in convention


## 4.4. Constructor and Destructor

Python:

```python
__init__()

__del__()

```

### 4.4.1. GC

### 4.4.2. finalize

# 5. Inheritance and Polymorphism

## 5.1. Inherit

### 5.1.3. super

### 5.1.4. protected, default

### 5.1.5. final

## 5.2. Polymorphism

### 5.2.1. Override

### 5.2.2. virtual

## 5.3. abstract class

## 5.4. Interface

### 5.4.1. Implements

### 5.4.2. Extends

### 5.4.3. Multiple implements/extends

# 6. Generic/Template Class

## 6.1. <?>

# 7. Collection

## 7.1. Java collection

## 7.2. Set

## 7.3. List

## 7.4. Map

## 7.5. Vector

# 8. String and Regular Expression

## 8.1. Basic operations

### 8.1.4. Compare

### 8.1.5. Sub string

### 8.1.6. Search and substitution

### 8.1.7. Split and join

## 8.2. StringBuffer

## 8.3. StringBuilder

## 8.4. regular expressions

# 9. Modular Programming

## 9.1. Header

## 9.2. Static

## 9.3. Statically-linked libs

## 9.4. Dynamically-linked libs

## 9.5. Package

### 9.5.1. Create (jar)

# 10. Reflection

## 10.1. Class

### 10.1.2. forName

### 10.1.3. getName

## 10.2. Field

### 10.2.1. getFields

### 10.2.2. getDeclaredFields

### 10.2.3. Field.get()/set()

## 10.3. Method

### 10.3.1. getMethods()

### 10.3.2. getDeclaredMethods()

### 10.3.3. invoke

# 11. Annotation

## 11.1. Built in: over, dep, warn

# 12. Others


## 12.1. Reserved/Key words

### 12.1.4. Java

### 12.1.5. JavaScript

### 12.1.6. Python

## 12.2. Comments and docstring

## 12.3. Versions and Features

