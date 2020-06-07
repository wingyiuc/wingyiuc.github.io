---
layout: post
title: "10 Excel Skills You Should Know "
date: 2020-06-07

---

Before learning how to use Python or R for trading strategies backtesting, there is some elementary skill you should know - Excel. This post would teach you 10 typical and useful Excel skills that would help you build your Excel model smoothly:

## 1. Navigating around the worksheet with keyboard

| What to do                                  | Keys                         |
| ------------------------------------------- | ---------------------------- |
| Jumping to the edge of your data region     | `CTRL`+ `← → ↑ ↓`            |
| Selecting the whole row/column/grid of data | `CTRL` + `SHIFT` + `← → ↑ ↓` |
| Jumping to another sheet                    | `CTRL` + `PGUP`/`PGDN`       |

## 2. Editing your sheet

| What to do                        | Keys                 |
| --------------------------------- | -------------------- |
| Add new row/column                | `CTRL`+ `SHIFT`+ `=` |
| Delete row/column                 | `CTRL` + `-`         |
| Hiding a column                   | `CTRL` + `0`         |
| Hiding a row                      | `CTRL` + `9`         |
| Editing the formula in cell       | `F2`                 |
| Lock cell (in your formula)       | `F4`                 |
| Recalculating everything in sheet | `F9`                 |
| Shortcut key to *Home*            | `ALT` + `H`          |

## 3. Copying and Pasting

| What to do                   | Keys                                                         |
| ---------------------------- | ------------------------------------------------------------ |
| Paste options                | Press `CTRL` once after pasting to see the available paste options |
| Copy formula down the column | Move your mouse to the lower right corner of the cell until you see a cross **+** ; double click and you will see the cell is copied and pasted down the whole column |

## 4. Concatenate

The `=CONCAT` function is very useful for putting strings in two cells together. 

|      | Column A | Column B    | Outcome            | Formula            |
| ---- | -------- | ----------- | ------------------ | ------------------ |
| 1    | apple    | gmail.com   | apple@gmail.com    | =CONCAT(A1,"@",B1) |
| 2    | banana   | outlook.com | banana@outlook.com | =CONCAT(A2,"@",B2) |

## 5. Left/ Right/ Mid for getting substring

To get a substring from a string, use `LEFT` / `RIGHT` / `MID`. The first argument is the cell that contains the string. The second argument is the number of characters you want to get.

In case you want to get the string before '@', use `FIND` to count the character position. 

To get the length of string, use `LEN` and put the corresponding cell in its argument.

|      | Column A           | Outcome | Formula                  |
| ---- | ------------------ | ------- | ------------------------ |
| 1    | apple@gmail.com    | apple   | =LEFT(A1,FIND("@",A1)-1) |
| 2    | banana@outlook.com | banana  | =LEFT(A2,FIND("@",A2)-1) |

|      | Column A           | Outcome     | Formula                         |
| ---- | ------------------ | ----------- | ------------------------------- |
| 1    | apple@gmail.com    | gmail.com   | =RIGHT(A1,LEN(A1)-FIND("@",A1)) |
| 2    | banana@outlook.com | outlook.com | =RIGHT(A2,LEN(A2)-FIND("@",A2)) |

## 6. Substitute string

To change a part of the string, use `SUBSTITUTE`. The first argument takes the cell, second argument takes the substring you would like to replace and third argument takes the string you would like to replace with. 

|      | Column A  | Outcome | Formula                   |
| ---- | --------- | ------- | ------------------------- |
| 1    | pineapple | apple   | =SUBSTITUTE(A1,"pine","") |

## 7. Find if cell contains substring

To check if the cell contains certain substring, use `SEARCH`. It would return *#VALUE!* if it cannot find the text. So wrap the formula with `ISNUMBER`, which return *TRUE* if it can find the text; *FALSE* if it cannot. 

|      | Column A  | Outcome | Formula                       |
| ---- | --------- | ------- | ----------------------------- |
| 1    | apple     | TRUE    | =ISNUMBER(SEARCH("apple",A1)) |
| 2    | pineapple | TRUE    | =ISNUMBER(SEARCH("apple",A2)) |
| 3    | banana    | FALSE   | =ISNUMBER(SEARCH("apple",A3)) |

## 8. Conditional formatting

Conditional formatting is a very useful tool that automatically highlights cells according to some predefined rules. Shortcut: `ALT` + `h`, then press `l`.

## 9. VLOOKUP & OFFSET MATCH

If you have two columns that are in pair and you would like to find the value given the key, you may use `VLOOKUP`. The first argument takes your lookup value, second argument takes the table array and third argument takes the column number. 

|      | Column A | Column B |                      |
| ---- | -------- | -------- | -------------------- |
| 1    | apple    | 10       |                      |
| 2    | banana   | 20       |                      |
| 3    | orange   | 30       |                      |
|      |          |          |                      |
|      | apple    | 10       | =VLOOKUP(A5,A1:B3,2) |

However, `VLOOKUP` always refer to the right of the table, so it does not work if it is the case:

|      | Column A | Column B |      |                      |
| ---- | -------- | -------- | ---- | -------------------- |
| 1    | 10       | apple    |      |                      |
| 2    | 20       | banana   |      |                      |
| 3    | 30       | orange   |      |                      |
|      |          |          |      |                      |
|      |          | apple    | #N/A | =VLOOKUP(B6,A1:B3,1) |

In this case, you need to use `OFFSET` and `MATCH` .

| 1    | Price (A) | Item (B) |      |                                  |
| ---- | --------- | -------- | ---- | -------------------------------- |
| 2    | 10        | apple    |      |                                  |
| 3    | 20        | banana   |      |                                  |
| 4    | 30        | orange   |      |                                  |
|      |           |          |      |                                  |
|      |           | apple    | 10   | =OFFSET(B1,MATCH(B6,B2:B4,0),-1) |

## 10. IF, SUMIF, COUNTIF

If-else logic is the basic element of programming and it is essential in constructing Excel backtesting. Here's a simple illustration of how to use `COUNTIF`.

| 1    | Item (A)          | Price (B) |                       |
| ---- | ----------------- | --------- | --------------------- |
| 2    | apple             | 10        |                       |
| 3    | banana            | 20        |                       |
| 4    | orange            | 30        |                       |
|      |                   |           |                       |
|      | Count if item >15 | 2         | =COUNTIF(B2:B4,">15") |





These are the basic Excel skills that most of us would know. In the next tutorial, I will show how to construct trading strategy backtesting with Excel and plottin the profit & loss graph like this: 
![image](https://user-images.githubusercontent.com/46639292/83962683-0644eb80-a8d2-11ea-9ce5-f20da399efa0.png)

