# GAUSS

Normal distribution for HP-42S.

## Usage

### 1. Enter parameters of the normal distribution
* Type the value of the mean of the distribution and press `[µ]`:

<img src="./screenshots/screen2.png" width="200">

* Type the value of the standard deviation of the distribution and press `[SD]`:

<img src="./screenshots/screen1.png" width="200">

* Press `[R/S]` to go to the next screen:

<img src="./screenshots/screen3.png" width="200">

### 2. Calculate values for the cumulative probability function and its inverse

* For the cumulative probability function, type the value of the variable and press `[CPF]`.

* For the inverse of cumulative probability function, type the value of the probability and press `[ICPF]`.

Example:

`0.95` `[ICPF]`:

<img src="./screenshots/screen4.png" width="200">

Result:

<img src="./screenshots/screen5.png" width="200">

## Requirements

Sub-routines (included in `gauss.raw`):
* `ERF`
* `IERF`
* `GPF`
* `IGPF`

> `ERF` and `IERF` copyright © 2006-2007 by Jean-Marc Baillard.