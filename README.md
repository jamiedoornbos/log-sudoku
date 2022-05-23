# Log Sudoku

```
./solve --help

usage: solve [-h] [--finish] [--delay SECONDS] [--moves N] [--step STEP] [--no-step STEP] PATH

DESCRIPTION

  Find the next move in solving a sudoku puzzle, keeping a log of all moves.

INPUT

  To start a new puzzle, save a file with at least 9 lines, and 9 columns in each line. Use a dot for
  a blank space and a digit for the cell value given in the puzzle provider. Refer to sample/01.txt as
  an example.

  To make one move, run with the solve program with the puzzle file name:

    ./solve path_to_puzzle_file

  To solve the puzzle completely and log all steps, use the --finish argument.

positional arguments:
  PATH             file of puzzle

optional arguments:
  -h, --help       show this help message and exit
  --finish         Run until done
  --delay SECONDS  Sleep between solving turns
  --moves N        Run through N moves
  --step STEP      Enable a step (for debugging) - if specified one or more times, only those steps will be used, otherwise all steps will be used
  --no-step STEP   Disable a step (for debugging) - if specified one or more times, all steps will be used except those given

STEPS

  For the --no-step and --step arguments, the available steps are

    one_allowed              Cells with one one digit allowed
    singular                 Groups where a digit is allowed by only one cell
    subgroup                 Subsets of allowed digits across the same number of cells, e.g. naked pairs
    cross_group_elimination  Allowed cells for a digit in one group are entirely in another
    cross_quads              Two digits allowed in four cells are not allowed in remaining cells
    cross_hexes              Similar to cross_quads, but with six cells and three digits
    fulcrum_pairs            Triplet of allowed digits across three cells
    pair_alternatives        Brute force attempt using each allowed digit in turn on a copy of the board
```
