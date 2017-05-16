---
layout: post
title: "计算机程序设计：语言"
date: "2017-04-30 04:51:53 +0800"
---

<!-- TOC -->

- [1. Data types, operators and expressions](#1-data-types-operators-and-expressions)
    - [1.1. Primitive types](#11-primitive-types)
        - [1.1.1. Type list](#111-type-list)
        - [1.1.2. Operators and expressions](#112-operators-and-expressions)
        - [1.1.3. typeof](#113-typeof)
        - [1.1.4. typedef](#114-typedef)
    - [1.2. Pointer](#12-pointer)
    - [1.3. Array and List](#13-array-and-list)
        - [1.3.1. Use random](#131-use-random)
    - [1.4. Directory/Hash/Map/Associative array](#14-directoryhashmapassociative-array)
    - [1.5. String](#15-string)
    - [1.6. Date and Time](#16-date-and-time)
    - [1.7. Preprocessing (C/C++)](#17-preprocessing-cc)
- [2. Control statements](#2-control-statements)
    - [2.1. if](#21-if)
    - [2.2. switch](#22-switch)
    - [2.3. goto](#23-goto)
    - [2.4. while](#24-while)
        - [2.4.1. break and continue](#241-break-and-continue)
        - [2.4.2. practice: Insert](#242-practice-insert)
        - [2.4.3. practice: Merge](#243-practice-merge)
    - [2.5. for](#25-for)
    - [2.6. for each](#26-for-each)
    - [2.7. exception](#27-exception)
        - [2.7.1. try … throw … catch … finally](#271-try--throw--catch--finally)
        - [2.7.2. throws](#272-throws)
- [3. Function](#3-function)
    - [3.1. Arguments pass: swap()](#31-arguments-pass-swap)
        - [3.1.3. by value](#313-by-value)
        - [3.1.4. By address](#314-by-address)
    - [3.2. Function pointer](#32-function-pointer)
    - [3.3. Lambda](#33-lambda)
    - [3.4. Callback](#34-callback)
    - [3.5. Recursive](#35-recursive)
    - [3.6. arguments parsing](#36-arguments-parsing)
        - [3.6.1. Argv[]](#361-argv)
        - [3.6.2. getopt()](#362-getopt)
- [4. Class and Object](#4-class-and-object)
    - [4.1. Structure (C/C++)](#41-structure-cc)
    - [4.2. Class and encapsulation](#42-class-and-encapsulation)
        - [4.2.3. Default, Private, public](#423-default-private-public)
    - [4.3. this and super](#43-this-and-super)
        - [4.3.1. this for constructor](#431-this-for-constructor)
    - [4.4. Overload](#44-overload)
    - [4.5. constructor](#45-constructor)
    - [4.6. destructor and GC](#46-destructor-and-gc)
        - [4.6.1. finalize](#461-finalize)
    - [4.7. static](#47-static)
    - [4.8. final](#48-final)
    - [4.9. Generic/Template Class](#49-generictemplate-class)
        - [4.9.1. <?>](#491-)
- [5. Inheritance and Polymorphism](#5-inheritance-and-polymorphism)
    - [5.1. Inherit](#51-inherit)
        - [5.1.2. super](#512-super)
        - [5.1.3. protected, default](#513-protected-default)
    - [5.2. Polymorphism](#52-polymorphism)
        - [5.2.1. Override](#521-override)
        - [5.2.2. virtual](#522-virtual)
    - [5.3. abstract class](#53-abstract-class)
    - [5.4. Interface](#54-interface)
        - [5.4.1. Implements](#541-implements)
        - [5.4.2. Extends](#542-extends)
        - [5.4.3. Multiple implements/extends](#543-multiple-implementsextends)
- [6. Collection](#6-collection)
    - [6.1. Java collection](#61-java-collection)
    - [6.2. Set](#62-set)
    - [6.3. List](#63-list)
    - [6.4. Map](#64-map)
    - [6.5. Vector](#65-vector)
- [7. String and Regular Expression](#7-string-and-regular-expression)
    - [7.1. Basic operations](#71-basic-operations)
        - [7.1.4. Compare](#714-compare)
        - [7.1.5. Sub string](#715-sub-string)
        - [7.1.6. Search and substitution](#716-search-and-substitution)
        - [7.1.7. Split and join](#717-split-and-join)
    - [7.2. StringBuffer](#72-stringbuffer)
    - [7.3. StringBuilder](#73-stringbuilder)
    - [7.4. regular expressions](#74-regular-expressions)
- [8. Modular Programming](#8-modular-programming)
    - [8.1. Header](#81-header)
    - [8.2. Static](#82-static)
    - [8.3. Statically-linked libs](#83-statically-linked-libs)
    - [8.4. Dynamically-linked libs](#84-dynamically-linked-libs)
    - [8.5. Package](#85-package)
        - [8.5.1. Create (jar)](#851-create-jar)
    - [8.6.](#86)
- [9. Reflection](#9-reflection)
    - [9.1. Class](#91-class)
        - [9.1.1. forName](#911-forname)
        - [9.1.2. getName](#912-getname)
    - [9.2. Field](#92-field)
        - [9.2.1. getFields](#921-getfields)
        - [9.2.2. getDeclaredFields](#922-getdeclaredfields)
        - [9.2.3. Field.get()/set()](#923-fieldgetset)
    - [9.3. Method](#93-method)
        - [9.3.1. getMethods()](#931-getmethods)
        - [9.3.2. getDeclaredMethods()](#932-getdeclaredmethods)
        - [9.3.3. invoke](#933-invoke)
- [10. Annotation](#10-annotation)
    - [10.1. Built in: over, dep, warn](#101-built-in-over-dep-warn)
- [11. Others](#11-others)
    - [11.1. Comments and docstring](#111-comments-and-docstring)

<!-- /TOC -->

# 1. Data types, operators and expressions

## 1.1. Primitive types

### 1.1.1. Type list

### 1.1.2. Operators and expressions

### 1.1.3. typeof

### 1.1.4. typedef

## 1.2. Pointer

## 1.3. Array and List

### 1.3.1. Use random

## 1.4. Directory/Hash/Map/Associative array

## 1.5. String

## 1.6. Date and Time

## 1.7. Preprocessing (C/C++)

# 2. Control statements

## 2.1. if

## 2.2. switch

## 2.3. goto

## 2.4. while

### 2.4.1. break and continue

### 2.4.2. practice: Insert

### 2.4.3. practice: Merge

## 2.5. for

## 2.6. for each

## 2.7. exception

### 2.7.1. try … throw … catch … finally

### 2.7.2. throws

# 3. Function

## 3.1. Arguments pass: swap()

### 3.1.3. by value

### 3.1.4. By address

## 3.2. Function pointer

## 3.3. Lambda

## 3.4. Callback

## 3.5. Recursive

## 3.6. arguments parsing

### 3.6.1. Argv[]

### 3.6.2. getopt()

# 4. Class and Object

## 4.1. Structure (C/C++)

## 4.2. Class and encapsulation

### 4.2.3. Default, Private, public

## 4.3. this and super

### 4.3.1. this for constructor

## 4.4. Overload

## 4.5. constructor

## 4.6. destructor and GC

### 4.6.1. finalize

## 4.7. static

## 4.8. final

## 4.9. Generic/Template Class

### 4.9.1. <?>

# 5. Inheritance and Polymorphism

## 5.1. Inherit

### 5.1.2. super

### 5.1.3. protected, default

## 5.2. Polymorphism

### 5.2.1. Override

### 5.2.2. virtual

## 5.3. abstract class

## 5.4. Interface

### 5.4.1. Implements

### 5.4.2. Extends

### 5.4.3. Multiple implements/extends

# 6. Collection

## 6.1. Java collection

## 6.2. Set

## 6.3. List

## 6.4. Map

## 6.5. Vector

# 7. String and Regular Expression

## 7.1. Basic operations

### 7.1.4. Compare

### 7.1.5. Sub string

### 7.1.6. Search and substitution

### 7.1.7. Split and join

## 7.2. StringBuffer

## 7.3. StringBuilder

## 7.4. regular expressions

# 8. Modular Programming

## 8.1. Header

## 8.2. Static

## 8.3. Statically-linked libs

## 8.4. Dynamically-linked libs

## 8.5. Package

### 8.5.1. Create (jar)

## 8.6. #

# 9. Reflection

## 9.1. Class

### 9.1.1. forName

### 9.1.2. getName

## 9.2. Field

### 9.2.1. getFields

### 9.2.2. getDeclaredFields

### 9.2.3. Field.get()/set()

## 9.3. Method

### 9.3.1. getMethods()

### 9.3.2. getDeclaredMethods()

### 9.3.3. invoke

# 10. Annotation

## 10.1. Built in: over, dep, warn

# 11. Others

## 11.1. Comments and docstring

