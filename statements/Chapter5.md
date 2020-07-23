# Chapter 5 Statements

Almost everything done in a program seems to be a statement just different kinds of it so I
really don't know how to define it, lets just say they are the constituent units of a program

## 1. Simple statements

Most statements in C flavored languages end with ;. You can even define a null statement 
where the statement has no body and just has a single semi-colon delimiter.Extra semi-colons
don't make much of a difference to the problem unless you use if after conditional or
iterative statements which can screw up the entire logic.

## 2. Compound statements

A sequence of statements and declaration wrapped in braces, form a compound statement or 
a block. Names defined within a block are visible only within it and blocks nested in it.

## 3. Conditional statements

C++ has two statements for conditional execution the if and switch statements.
* The dangling else in C++ is matched to the lexically closest preceding unmatched if.
* In the switch case the case has to be integral expressions.
* Without breaks the cases trickle down

