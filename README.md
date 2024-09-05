# Calc Action

**Calc Action** is a simple GitHub Action for performing basic arithmetic operations: addition and subtraction. This action allows you to perform calculations directly within your GitHub Actions workflows.

## Table of Contents

- [Usage](#usage)
- [Inputs](#inputs)
- [Outputs](#outputs)
- [Example Workflow](#example-workflow)
- [License](#license)

## Usage

The Calc Action can be used in your GitHub Actions workflows to perform arithmetic operations. This action supports addition and subtraction operations.

## Inputs

The action accepts the following inputs:

- `x`: The first number for the arithmetic operations. (Required, Default: `0`)
- `y`: The second number for the arithmetic operations. (Required, Default: `0`)

## Outputs

The action produces the following outputs:

- `plus`: The result of the addition operation (`x + y`).
- `minus`: The result of the subtraction operation (`x - y`).

## Example Workflow

Here is an example of how to use the Calc Action in a GitHub Actions workflow:

```yaml
name: Example Workflow

on: [push]

jobs:
  calculate:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout code
        uses: actions/checkout@v3

      - name: Perform calculations
        id: calc
        uses: s570908/calc-action@v1.0.0
        with:
          x: 10
          y: 5

      - name: Display results
        run: |
          echo "Addition result: ${{ steps.calc.outputs.plus }}"
          echo "Subtraction result: ${{ steps.calc.outputs.minus }}"