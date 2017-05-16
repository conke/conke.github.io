---
layout: post
title: "计算机程序设计：语言篇"
date: "2017-05-16 12:51:53 +0800"
---

<!-- TOC depthFrom:1 depthTo:6 withLinks:1 updateOnSave:1 orderedList:0 -->

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
	- [1.7. Preprocessing](#17-preprocessing)
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
		- [2.7.1. try … throw … catch … finally](#271-try-throw-catch-finally)
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
	- [4.1. Class](#41-class)
		- [4.1.3. property and method](#413-property-and-method)
		- [4.1.4. Default, Private, public](#414-default-private-public)
	- [4.2. this and super](#42-this-and-super)
		- [4.2.1. this for constructor](#421-this-for-constructor)
	- [4.3. Overload](#43-overload)
	- [4.4. constructor](#44-constructor)
	- [4.5. destructor and GC](#45-destructor-and-gc)
		- [4.5.1. finalize](#451-finalize)
	- [4.6. static](#46-static)
	- [4.7. final](#47-final)
- [5. Inheritance and Polymorphism](#5-inheritance-and-polymorphism)
	- [5.1. Inherit](#51-inherit)
		- [5.1.1. super](#511-super)
		- [5.1.2. protected, default](#512-protected-default)
	- [5.2. Polymorphism](#52-polymorphism)
		- [5.2.1. Override](#521-override)
		- [5.2.2. virtual](#522-virtual)
	- [5.3. abstract class](#53-abstract-class)
	- [5.4. Interface](#54-interface)
		- [5.4.1. Implements](#541-implements)
		- [5.4.2. Extends](#542-extends)
		- [5.4.3. Multiple implements/extends](#543-multiple-implementsextends)
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
		- [8.1.4. Compare](#814-compare)
		- [8.1.5. Sub string](#815-sub-string)
		- [8.1.6. Search and substitution](#816-search-and-substitution)
		- [8.1.7. Split and join](#817-split-and-join)
	- [8.2. StringBuffer](#82-stringbuffer)
	- [8.3. StringBuilder](#83-stringbuilder)
	- [8.4. regular expressions](#84-regular-expressions)
- [9. Modular Programming](#9-modular-programming)
	- [9.1. Header](#91-header)
	- [9.2. Static](#92-static)
	- [9.3. Statically-linked libs](#93-statically-linked-libs)
	- [9.4. Dynamically-linked libs](#94-dynamically-linked-libs)
	- [9.5. Package](#95-package)
		- [9.5.1. Create (jar)](#951-create-jar)
- [10. Reflection](#10-reflection)
	- [10.1. Class](#101-class)
		- [10.1.2. forName](#1012-forname)
		- [10.1.3. getName](#1013-getname)
	- [10.2. Field](#102-field)
		- [10.2.1. getFields](#1021-getfields)
		- [10.2.2. getDeclaredFields](#1022-getdeclaredfields)
		- [10.2.3. Field.get()/set()](#1023-fieldgetset)
	- [10.3. Method](#103-method)
		- [10.3.1. getMethods()](#1031-getmethods)
		- [10.3.2. getDeclaredMethods()](#1032-getdeclaredmethods)
		- [10.3.3. invoke](#1033-invoke)
- [11. Annotation](#11-annotation)
	- [11.1. Built in: over, dep, warn](#111-built-in-over-dep-warn)
- [12. Others](#12-others)
	- [12.1. Comments and docstring](#121-comments-and-docstring)

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

## 1.7. Preprocessing

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

## 4.1. Class

### 4.1.3. property and method

### 4.1.4. Default, Private, public

## 4.2. this and super

### 4.2.1. this for constructor

## 4.3. Overload

## 4.4. constructor

## 4.5. destructor and GC

### 4.5.1. finalize

## 4.6. static

## 4.7. final

# 5. Inheritance and Polymorphism

## 5.1. Inherit

### 5.1.1. super

### 5.1.2. protected, default

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

## 12.1. Comments and docstring
