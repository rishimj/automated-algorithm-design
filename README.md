# Genetic Programming with DEAP

## Overview

This repository contains implementations of two classical problems in genetic programming using the DEAP library:

1. **One Max Problem** - A simple genetic algorithm problem where the objective is to find a bit string of all `1s` for a given length.
2. **N Queens Problem** - A genetic programming approach to solve the problem of placing `n` queens on an `n x n` chessboard such that no two queens attack each other.

## Requirements

- Python 3.x
- [DEAP library](https://deap.readthedocs.io/)
- Jupyter Notebook (optional, for interactive exploration)

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/genetic-programming-deap.git
   cd genetic-programming-deap
   ```
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

## One Max Problem

The One Max Problem aims to optimize a bit string such that all bits are `1`.

### Implementation Details

- **Fitness Function**: Evaluates the fitness of an individual as the sum of its bits.
- **Genetic Operators**:
  - **Crossover**: Two-point crossover.
  - **Mutation**: Bit-flip mutation with a 5% probability.
  - **Selection**: Tournament selection with a size of 3.
- **Algorithm**: Evolves a population of 300 individuals over 40 generations.

### Usage

Run the `OneMaxProblem.ipynb` notebook to see the full implementation and results.

### Sample Output

```plaintext
-- Generation 0 --
  Min 42.0
  Max 68.0
  Avg 54.19
  Std 4.46
...
-- End of (successful) evolution --
Best individual is [1, 1, 1, ..., 1], (100.0,)
```

## N Queens Problem

The N Queens Problem places `n` queens on an `n x n` chessboard such that no two queens attack each other.

### Implementation Details

- **Fitness Function**: Evaluates fitness by counting conflicts along diagonals.
- **Genetic Operators**:
  - **Crossover**: Partially matched crossover (PMX).
  - **Mutation**: Index shuffling with a probability of `2/n`.
  - **Selection**: Tournament selection with a size of 3.
- **Algorithm**: Evolves a population of 300 individuals over 100 generations.

### Usage

Run the `NQueensProblem.ipynb` notebook to see the implementation and results. The default value for `n` is 20, but it can be modified.

### Sample Output

```plaintext
-- Generation 0 --
  Min 5.0
  Max 15.0
  Avg 9.36
  Std 1.78
...
-- End of (successful) evolution --
Best individual is [8, 10, 3, ..., 15], (0.0,)
```

## How It Works

Both problems leverage the DEAP framework, which provides tools for evolutionary algorithms. Key components include:

- **Creator Module**: Defines custom classes for individuals and fitness functions.
- **Toolbox Module**: Registers functions for initialization, evaluation, crossover, mutation, and selection.
- **Algorithm**: Implements an evolutionary loop with fitness evaluation, genetic operations, and population replacement.

### DEAP Library Overview

DEAP (Distributed Evolutionary Algorithms in Python) simplifies the implementation of evolutionary algorithms. For detailed documentation, visit the [DEAP official documentation](https://deap.readthedocs.io/).

## Notebooks

- [One Max Problem](notebooks/OneMaxProblem.ipynb)
- [N Queens Problem](notebooks/NQueensProblem.ipynb)

## References

- [DEAP GitHub Repository](https://github.com/DEAP/deap)
- [One Max Problem Example](https://github.com/DEAP/notebooks/blob/master/OneMax.ipynb)
- [N Queens Problem Example](https://github.com/DEAP/deap/blob/master/examples/ga/nqueens.py)

## Contributing

Contributions are welcome! Please fork the repository, create a branch, and submit a pull request.

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.
