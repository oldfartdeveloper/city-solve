# README

## Purpose

I have a wooden puzzle that consists of a square base and buildings that are to be arranged on it.  All of the buildings only fit on it if they are arranged precisely; the object of the puzzle is to figure out what the arrangement needs to be.

Needless to say, I suck at this puzzle, and this is my attempt to write a computer program to solve it.

## Description of Puzzle Pieces

Here are the puzzle pieces grouped by piece shape:

![piece shapes](/images/puzzelImage.jpg)

Here are the same pieces with names added:

![piece parts](/images/puzzleParts.jpeg)

## Description of Puzzle Parts

The puzzle consists of the board and **12** pieces:

### Board

The board defines a **7** x **7** matrix upon which the pieces must all be arranged.

### Tee

A **tee** is shaped like a flattend "T" character and occupies 4 places in the matrix as follows:

![tee](/images/tee.png)

There are **3** of these.

### Ell

An **ell** looks like an "L":

![ell](/images/ell.png)

There are **3** of these.

### LEll

A **lell** looks like a reversed "L" (i.e. the 'foot' is facing *left*):

![lell](/images/rell.png)

There is only **1** of these.

### Left

A **left** looks like it zigzags *left* then straightens out:

![left](/images/left.png)

There are **2** of these.

### Rite

A **right** looks like it zigzags *right* then straightens out:

![rite](/images/right.png)

There are **2** of these.

### Plus

A **plus** has a center and 4 spokes:

![plus](/images/plus.png)
