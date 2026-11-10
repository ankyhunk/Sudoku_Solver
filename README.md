# Sudoku-Solver-Assignment

A Python program that solves Sudoku puzzles using **recursion and backtracking**. Assignment from the Jovian Data Science and Machine Learning Bootcamp.

A Sudoku is a 9×9 grid with some numbers (1–9) already filled in. Each row, each column and each of the nine 3×3 boxes must contain every number from 1 to 9 exactly once.

![Sudoku](https://user-images.githubusercontent.com/59883315/196273966-d3d93b51-89b2-4219-baa1-d39f763b98c4.png)

## How it works

The puzzle is a list of 9 lists, with `0` for empty cells. The notebook builds the solver step by step:

1. **Representation:** store the puzzle as a list of lists
2. **Helpers:** `get_row`, `get_col`, `get_box` and `first_empty_position`
3. **Validation:** `is_sudoku_valid` (no repeats in any row, column or box) and `is_sudoku_complete`, built on `is_section_valid` / `is_section_complete`
4. **Solver:** `solve_sudoku` finds the first empty cell, tries each number 1–9, and recurses. If a choice leads to a dead end, it backtracks and tries the next number.
5. **Bulk solving (optional):** parses 100 puzzles from a CSV (`parse_sudoku` turns an 81-character string into a grid), solves them all, and writes the results to `sudokus_solved.csv` with `write_results`

## Example

```python
puzzle1 = [[5, 3, 0, 0, 7, 0, 0, 0, 0],
           [6, 0, 0, 1, 9, 5, 0, 0, 0],
           ...]
solution = solve_sudoku(puzzle1)
is_sudoku_complete(solution)   # True
```

## How to run

No extra packages are needed for the solver itself:

```bash
jupyter notebook python_sudoku_solver_assignment.ipynb
```

The bulk-solving section downloads its 100 puzzles from a public URL. The `jovian` cells are only for submitting the assignment and can be skipped.

## Technologies

Python (standard library: `copy`, `urllib`), Jupyter Notebook
