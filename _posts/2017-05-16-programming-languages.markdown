---
layout: post
title: "计算机程序设计：语言篇"
date: "2017-05-16 12:51:53 +0800"
---

<!-- TOC -->

- [1. Data types, operators and expressions](#1-data-types-operators-and-expressions)
    - [1.1. Overview](#11-overview)
        - [1.1.1. Type list](#111-type-list)
        - [1.1.2. Show Type Info](#112-show-type-info)
        - [1.1.3. Variable Declaration](#113-variable-declaration)
    - [1.2. Boolean](#12-boolean)
        - [1.2.1. Variable Declaration](#121-variable-declaration)
        - [1.2.2. Logical Operators](#122-logical-operators)
    - [1.3. Number](#13-number)
        - [1.3.1. Constants](#131-constants)
        - [1.3.2. Variable Declaration](#132-variable-declaration)
        - [1.3.3. Arithmetic Operators](#133-arithmetic-operators)
        - [1.3.4. Assignment Operators](#134-assignment-operators)
        - [1.3.5. Comparison Operators](#135-comparison-operators)
        - [1.3.6. Bitwise Operators](#136-bitwise-operators)
    - [1.4. String](#14-string)
        - [1.4.1. Variable Declaration](#141-variable-declaration)
        - [1.4.2. Assignment Operators](#142-assignment-operators)
        - [1.4.3. Comparison Operators](#143-comparison-operators)
    - [1.5. Pointer and Reference](#15-pointer-and-reference)
    - [1.6. Array and List](#16-array-and-list)
        - [1.6.1. Definition](#161-definition)
        - [1.6.2. Add element](#162-add-element)
        - [1.6.3. Delete element](#163-delete-element)
        - [1.6.4. Search element](#164-search-element)
        - [1.6.5. Sort](#165-sort)
    - [1.7. Tuple](#17-tuple)
    - [1.8. Directory/Hash/Associative array](#18-directoryhashassociative-array)
        - [1.8.1. Definition](#181-definition)
        - [1.8.2. CRUD](#182-crud)
    - [1.9. Date and Time](#19-date-and-time)
        - [1.9.1. Format](#191-format)
        - [1.9.2. Operation](#192-operation)
    - [1.10. Preprocessing](#110-preprocessing)
- [2. Control statements](#2-control-statements)
    - [2.1. if](#21-if)
    - [2.2. switch](#22-switch)
    - [2.3. while](#23-while)
    - [2.4. for](#24-for)
    - [2.5. break and continue](#25-break-and-continue)
    - [2.6. exception](#26-exception)
- [3. Function](#3-function)
    - [3.1. Definition](#31-definition)
        - [3.1.1. Variable arguments](#311-variable-arguments)
        - [3.1.2. Local and Global (Scope)](#312-local-and-global-scope)
        - [3.1.3. Return Value](#313-return-value)
    - [3.2. Overload and Default Arguments](#32-overload-and-default-arguments)
    - [3.3. Recursive](#33-recursive)
    - [3.4. Callback](#34-callback)
    - [3.5. Lambda](#35-lambda)
- [4. Class and Object](#4-class-and-object)
    - [4.1. Definition (property and method)](#41-definition-property-and-method)
    - [4.2. Class/Object Memeber](#42-classobject-memeber)
        - [4.2.1. this/self](#421-thisself)
        - [4.2.2. *Case Study*](#422-case-study)
    - [4.3. Encapsulation (private/protected/public)](#43-encapsulation-privateprotectedpublic)
    - [4.4. Constructor and Destructor](#44-constructor-and-destructor)
        - [4.4.1. GC](#441-gc)
        - [4.4.2. finalize](#442-finalize)
- [5. Inheritance and Polymorphism](#5-inheritance-and-polymorphism)
    - [5.1. Inherit](#51-inherit)
        - [5.1.3. super](#513-super)
        - [5.1.4. protected, default](#514-protected-default)
        - [5.1.5. final](#515-final)
    - [5.2. Polymorphism](#52-polymorphism)
        - [5.2.1. Override](#521-override)
        - [5.2.2. virtual](#522-virtual)
    - [5.3. Abstract Class](#53-abstract-class)
    - [5.4. Interface](#54-interface)
        - [5.4.1. Implements](#541-implements)
        - [5.4.2. Extends](#542-extends)
        - [5.4.3. Multiple implements/extends](#543-multiple-implementsextends)
- [6. Generic/Template Class](#6-generictemplate-class)
    - [6.1. <?>](#61-)
- [7. Collection](#7-collection)
    - [7.1. Set](#71-set)
    - [7.2. List](#72-list)
    - [7.3. Map](#73-map)
    - [7.4. Vector](#74-vector)
- [8. String and Regular Expression](#8-string-and-regular-expression)
    - [8.1. Basic operations](#81-basic-operations)
        - [8.1.1. Format](#811-format)
        - [8.1.2. Compare](#812-compare)
        - [8.1.3. Sub string](#813-sub-string)
        - [8.1.4. Search and substitution](#814-search-and-substitution)
        - [8.1.5. Split and join](#815-split-and-join)
        - [8.1.6. String-Number Conversion](#816-string-number-conversion)
    - [8.2. regular expressions](#82-regular-expressions)
- [9. Modular Programming](#9-modular-programming)
    - [9.1. Header](#91-header)
    - [9.2. Static](#92-static)
    - [9.3. Statically-linked libs](#93-statically-linked-libs)
    - [9.4. Dynamically-linked libs](#94-dynamically-linked-libs)
    - [9.5. Package](#95-package)
        - [9.5.1. Create (jar)](#951-create-jar)
- [10. Reflection](#10-reflection)
    - [10.1. Class](#101-class)
        - [10.1.2. Get Name](#1012-get-name)
        - [10.1.3. from Name](#1013-from-name)
    - [10.2. Properties/Fields](#102-propertiesfields)
        - [10.2.1. Get Fields](#1021-get-fields)
        - [10.2.2. Access Fields](#1022-access-fields)
    - [10.3. Methods](#103-methods)
        - [10.3.1. Get Methods](#1031-get-methods)
        - [10.3.2. Invoke Methods](#1032-invoke-methods)
- [11. Annotations/Decorators](#11-annotationsdecorators)
    - [11.1. Built-in Annotations](#111-built-in-annotations)
- [12. Others](#12-others)
    - [12.1. Reserved/Key words](#121-reservedkey-words)
        - [12.1.3. Java](#1213-java)
        - [12.1.4. JavaScript](#1214-javascript)
        - [12.1.5. Python](#1215-python)
    - [12.2. Comments and docstring](#122-comments-and-docstring)
    - [12.3. Versions and Features](#123-versions-and-features)

<!-- /TOC -->

# 1. Data types, operators and expressions

## 1.1. Overview

typeof

instanceof

typedef

### 1.1.1. Type list


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

### 1.1.2. Show Type Info

Java: getClass()

JavaScript: typeof()

Python: type()

TypeScript: ?

### 1.1.3. Variable Declaration

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

## 1.2. Boolean

### 1.2.1. Variable Declaration
constants: true/false

TypeScript:
```typescript
let done: boolean = true;
```

### 1.2.2. Logical Operators

```javascript
==, ===
&&, ||, !
```

## 1.3. Number

### 1.3.1. Constants

0b11, 011/0o11, 0x11

2e3 (JS/TS/Python)

Math.PI

complex

enum

### 1.3.2. Variable Declaration


### 1.3.3. Arithmetic Operators

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

### 1.3.4. Assignment Operators

C/C++/Java/JavaScript/TypeScript:
```c
=
+=
-=
*=
/=
%=
```

### 1.3.5. Comparison Operators

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

### 1.3.6. Bitwise Operators

```c
&
|
~
^
<<
>>
>>>
```

## 1.4. String

Unicode

### 1.4.1. Variable Declaration

JavaScript:

```javascript
let s1 = "123";
```

TypeScript:
```typescript
let s1: string = "123";
```

### 1.4.2. Assignment Operators

Java/JavaScript/TypeScript:
```c
=
+=
```

### 1.4.3. Comparison Operators


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

## 1.5. Pointer and Reference

## 1.6. Array and List

Use random

### 1.6.1. Definition

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

### 1.6.2. Add element

### 1.6.3. Delete element

### 1.6.4. Search element

### 1.6.5. Sort

## 1.7. Tuple

## 1.8. Directory/Hash/Associative array

### 1.8.1. Definition

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

### 1.8.2. CRUD

## 1.9. Date and Time

### 1.9.1. Format

### 1.9.2. Operation

## 1.10. Preprocessing

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

### 5.1.4. protected, default

### 5.1.5. final

## 5.2. Polymorphism

### 5.2.1. Override

### 5.2.2. virtual

## 5.3. Abstract Class

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

## 5.4. Interface

### 5.4.1. Implements

### 5.4.2. Extends

### 5.4.3. Multiple implements/extends

# 6. Generic/Template Class

## 6.1. <?>

# 7. Collection

## 7.1. Set

## 7.2. List

## 7.3. Map

## 7.4. Vector

# 8. String and Regular Expression

## 8.1. Basic operations

### 8.1.1. Format

Python 3.x:

```python
key = 'abc'
value = 123
content = f'{key} = {value}'

print(content)
```

### 8.1.2. Compare

### 8.1.3. Sub string

### 8.1.4. Search and substitution

### 8.1.5. Split and join

### 8.1.6. String-Number Conversion

<!--StringBuffer, StringBuilder-->

## 8.2. regular expressions

# 9. Modular Programming

## 9.1. Header

## 9.2. Static

## 9.3. Statically-linked libs

## 9.4. Dynamically-linked libs

## 9.5. Package

### 9.5.1. Create (jar)

# 10. Reflection

## 10.1. Class

### 10.1.2. Get Name

Java: getName

Python:

```python
class Demo:
    foo = 123

demo = Demo()
print(type(demo).__name__)
```

### 10.1.3. from Name

Java: forName

Python:

```python

```

## 10.2. Properties/Fields

### 10.2.1. Get Fields

Java:
getFields
getDeclaredFields

### 10.2.2. Access Fields

Java:
Field.get()/set()

Python:

```python
class Demo:
    foo = 123

f = getattr(Demo, 'foo')
print(f)
```

## 10.3. Methods

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

### 10.3.1. Get Methods

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

### 10.3.2. Invoke Methods
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

# 11. Annotations/Decorators

## 11.1. Built-in Annotations

Java:

@Deprecated
@Override
@SuppressWarnings

# 12. Others

## 12.1. Reserved/Key words

### 12.1.3. Java

### 12.1.4. JavaScript

### 12.1.5. Python

## 12.2. Comments and docstring

## 12.3. Versions and Features

