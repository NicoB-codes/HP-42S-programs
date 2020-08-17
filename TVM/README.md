# TVM

Time Value of Money for HP-42S.

Compound interest calculations with advanced features:

* Possibility of having different values for “installment periods per year” `P/Y` and “compounding periods per year” `C/Y`
* Calculation of the amortization table with adjustable periods
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

## Usage

### Launching the program

Starts the program by launching `TVM`.

### Storing numbers in the financial registers
To store a value in a financial register, enter the number on the screen, then press the corresponding key: `[N]`, `[I% Y]`, `[PV]`, `[PMT]`, or `[FV]`.

### Recalling numbers in the financial registers
To display a value stored in a financial register, press `[RCL]` and then the corresponding key.

### Clearing the financial registers
Each financial function uses numbers stored in multiple financial registers. Before starting a new financial calculation, it is recommended to clear all financial records by pressing `[↓]` then `[CLEAR]`.

