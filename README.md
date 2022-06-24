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

The board defines a **7** x **7** cell matrix upon which the pieces must all be arranged.

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

## First Strategy

After thinking about this A LOT, here's my first approach:

### Rules

1. Preorder the list of pieces to try in order.

1. Find the first piece that fits in the top-left cell of the board.

1. Find the first piece that fits to occupy the next cell to the right without violating the board's boundary.

1. Repeat this process for the remainder of the first row so that:

    1. All the cells in the first row are filled.

    1. There are no piece overlaps.

    1. None of the pieces violate the board's boundary.

1. Repeat for the remaining rows.

1. When you cannot find a piece to play, backup to the previous piece and see if any of the following work:

    1. Can the previous piece be repositioned successfully?  If so continue:

    1. If not, select the next available piece type and see if you can replace the current piece with it.  If so, continue.  If not, repeat this process for the "previous previous" piece.

1. The currently played pieces are on a stack.  When you get stuck, you back up the stack to a piece position or type that you haven't tried yet in that stack position and try that.

1. When the stack contains all the pieces and no cells are left unoccupied, then the game is solved.

*I get the idea above, but it needs polishing.*

## Keep in Mind

### Each stack position defines a piece type and its orientation.

So we need to define the notion of how orientation is used.

* Should we just associate and enumeration with each possible position for the piece type?

    1. The "T's", "L's" and "Z's" each have 4 possible positions.  So when we need to update a type, before we do we have to step through the existing candidate through each of its positions first.

    1. It might be useful to associate position inforamation with determining how to fit a piece into the desired cell given the cell's surrounding pieces.  This only has to work with the desired cell and any adjacent cells in the row underneath.
