---
layout: post
title: "10 Excel Skills You Should Know "
date: 2020-06-07
---
Before learning how to use Python or R for trading strategies backtesting, there is some elementary skill you should know - Excel. This post would teach you 10 typical and useful Excel skills that would help you build your Excel model smoothly:

### 1. Navigating around the worksheet with keyboard

| What to do                                  | Keys                         |
| ------------------------------------------- | ---------------------------- |
| Jumping to the edge of your data region     | `CTRL`+ `← → ↑ ↓`            |
| Selecting the whole row/column/grid of data | `CTRL` + `SHIFT` + `← → ↑ ↓` |
| Jumping to another sheet                    | `CTRL` + `PGUP`/`PGDN`       |

### 2. Editing your sheet

| What to do                        | Keys                 |
| --------------------------------- | -------------------- |
| Add new row/column                | `CTRL`+ `SHIFT`+ `=` |
| Delete row/column                 | `CTRL` + `-`         |
| Hiding a column                   | `CTRL` + `0`         |
| Hiding a row                      | `CTRL` + `9`         |
| Editing the formula in cell       | `F2`                 |
| Recalculating everything in sheet | `F9`                 |
| Shortcut key to *Home*            | `ALT` + `H`          |

### 3. Copying and Pasting

| What to do                   | Keys                                                         |
| ---------------------------- | ------------------------------------------------------------ |
| Paste options                | Press `CTRL` once after pasting to see the available paste options |
| Copy formula down the column | Move your mouse to the lower right corner of the cell until you see a cross **+** ; double click and you will see the cell is copied and pasted down the whole column |

### 4. Concatenate

The `=CONCAT` function is very useful for putting strings in two cells together. 

|      | Column A | Column B    | Outcome            | Formula            |
| ---- | -------- | ----------- | ------------------ | ------------------ |
| 1    | apple    | gmail.com   | apple@gmail.com    | =CONCAT(A1,"@",B1) |
| 2    | banana   | outlook.com | banana@outlook.com | =CONCAT(A2,"@",B2) |