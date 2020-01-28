---
layout: post
title: "Variables and Types"
date: 2019-01-15 23:00:00 Wednesday
author: semih
comments: true
categories: [java]
tags: [java, datatypes]
---
Although Java is object oriented, not all types are object. There are primitive types as well. Here is a list of all primitive types in Java:

<div class="datatable-begin"></div>

Data Type    | Description                           | Size | Example Literals | Range
------- | ------------------------------------- | -------- | ----------- | -----------
byte		| twos complement integer  | 8 bits   | (none) | -2^7...2^7 -1
short		| twos complement integer  | 16 bits  | (none) | -2^15...2^15 -1
int			| twos complement integer  | 32 bits  | -2, -1, 0, 1, 2 | -2^31...2^31 -1
long		| twos complement integer  | 64 bits  | -2L, -1L, 0L, 1L, 2L | -2^63...2^63-1
float  	| IEEE 754 floating point  | 32 bits  | 1.23e100f, -1.23e-100f, .3f, 3.14F | 
double 	| IEEE 754 floating point  | 64 bits  | 1.23456e300d, -1.23456e-300d, 1e1d | 
boolean   | true or false            | 1 bit    | true, false | 0...1
char 		| Unicode character        | 16 bits  | 'a', '\u0041', '\101', '\\', '\'', '\n', 'ß' | '\u0000'...'\uffff' or 0...65,535 inclusive

<div class="datatable-end"></div>



<br/>
Hope to see you in the next article...