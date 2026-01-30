# push_swap

push_swap is a 42 School algorithm project that sorts a stack of integers using a second stack and a limited set of operations. The goal is to output the minimum number of moves needed to sort the input.

## Overview

You receive integers in stack A and must sort them using only 11 allowed operations (swap, push, rotate, reverse rotate). Stack B is used as temporary storage. Output is the sequence of operations to sort stack A with the fewest moves possible.

## Composition

- **push_swap.c** — main logic and orchestration
- **source/** — sorting and stack manipulation
  - `create_stack.c`, `lst.c` — stack data structure
  - `ft_sort_three.c` — base case for 3 elements
  - `sort_big.c` — algorithm for larger inputs
  - `calculate_costs.c`, `calculate_moves.c` — cost-based decisions
  - `b_to_a.c` — moving elements back to A
  - `functions/` — r, rr, s, p operations
- **libft/** — custom C library (includes ft_printf)
- **bonus/** — checker program to validate solutions
  - `checker.c` — reads operations and verifies sorting
  - `get_next_line/` — for reading from stdin

## Features

- **11 operations** — sa, sb, ss, pa, pb, ra, rb, rr, rra, rrb, rrr
- **Two stacks** — A (input) and B (auxiliary)
- **Optimized algorithm** — aims for minimal move count
- **Checker bonus** — validates push_swap output

## Technology

- C (C99)
- libft (custom)
- Linked lists for stacks

## Setup

Build push_swap:

```bash
make
```

Build checker (bonus):

```bash
make -C bonus
```

Usage:

```bash
./push_swap 4 2 1 3 5
./push_swap 4 2 1 3 5 | wc -l
```

With checker:

```bash
./push_swap 4 2 1 3 5 | ./bonus/checker 4 2 1 3 5
```

## Makefile targets

| Target   | Description                  |
|----------|------------------------------|
| `all`    | Build `push_swap`            |
| `clean`  | Remove object files          |
| `fclean` | Remove objects and binary    |
| `re`     | Fclean then rebuild          |

## Notes

- Input: space-separated integers (can be quoted as a single argument)
- Output: one operation per line on stdout
- Scoring depends on keeping the number of moves low
- Subject: `push_swap_subject.pdf`
