# TVM

Time value of money for HP-42S.

Compound interest calculations with advanced features:

* Adjustable values for “installment periods per year” `P/Y` and also “compounding periods per year” `C/Y`
* Amortization table with adjustable period of calculation
* Ability to solve the 2 solutions for `I%Y` (in the rare cases where this happens)

## Warning

In order to run properly, `TVM` automatically modifies some settings of the HP-42S. If you don’t want this behavior, don’t use it or change the programs accordingly before launching `TVM` or `CLFIN`.

When the program is started, `TVM` updates these settings:

* `REALRES` disables complex results in calculations
* `FIX 02` sets the number of displayed decimals to 2

`CLFIN` updates this settings:

* `SIZE 100` sets the number of available registers to 100
* Variables `N`, `I%Y`, `PV`, `PMT`, `FV`, `P/Y` and `C/Y` are moved to the beggining of the list of variables

When the program is closed, `TVM` restores these settings:

* `CPXRES` enables complex results in calculations
* `ALL` sets the display mode to `ALL`

## First use

Before the very first use, you must initialize the registers by launching the program `CLFIN` (see warning above).

## Basic usage

### Launching the program

Starts the program by launching `TVM`. You should see this screen:

<img src="./screenshots/screen1.png" width="200">

### Setting parameters

The configuration menu can be accessed by pressing `[↓]`:

<img src="./screenshots/screen2.png" width="200">

Here you can set:

* `[P/Y]`: number of installment periods per year (default 12)
* `[C/Y]`: number of compounding periods per year (default 12)
* `[BEG]`: switch between payment at end or beginning of period (default END)
* `[C]`: switch between ”simple interest” and compound interest” for the odd period when `N` is not an integer

The last menu item resets the financial registers:

* `[CLEAR]`: clears the financial registers and resets `P/Y` and `C/Y` to 12 periods per year

### Storing numbers in the financial registers
To store a value in a financial register, enter the number on the screen, then press the corresponding key:

* `[N]`: number of periods
* `[I%Y]`: annual interest rate
* `[PV]`: present value
* `[PMT]`: periodic payment amount
* `[FV]`: final value

Once 4 values ​​have been set, you can calculate the last one by pressing it directly.

### Recalling numbers in the financial registers
To display a value stored in a financial register, press `[RCL]` and then the corresponding key.

### Clearing the financial registers
Before starting a new financial calculation, it is recommended to clear all financial registers by pressing `[↓]` then `[CLEAR]`.

## Example

### Prêt immobilier

How much can you borrow to buy a house on a 20-year 2.5% interest loan (monthly compounding), if you can make payments of $1000 at the end of each month?

Press:

[`v`] [`CLEAR`] [`^`] `20` [`ENTER`] `12` [`×`] [`N`] `2.5` [`I%Y`] `1000` [`+/–`] [`PMT`] [`PV`]

Solution: you can borrow $188,713.82

How much interest are you going to pay?

Press:

`0` [`N`] [`AMOR`]

You are asked how many periods you want to amortize:

<img src="./screenshots/screen8.png" width="200">

`240` [`R/S`]

<img src="./screenshots/screen17.png" width="200">

Solution: after 240 months, you will have paid $51,286.18 in interest

From this screen, if you want to calculate the monthly amortization table, press:

[`EXIT`] [`PV`]    *(you need to recalculate the present value)*

`0` [`N`] [`AMOR`] `1` [`R/S`]

<img src="./screenshots/screen18.png" width="200">

Continue to display the rest of the table by pressing [`R/S`]

<img src="./screenshots/screen19.png" width="200">

...etc...

You can find a lot more examples in the user manual of the HP-12C.

## Requirements

Sub-routines (included in `tvm.raw`):
* `SOLVi`: solver for `I%Y`
* `CLFIN`: resets the financial registers
* `RND2`: rounds the value in `Y` to the step in `X`