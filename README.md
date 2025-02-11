# Equation Solver

## Overview

This project is an advanced equation solver implemented in Python, supporting both linear and quadratic equations. It leverages object-oriented programming principles such as encapsulation, abstraction, and subclass initialization. By using abstract base classes (`ABC`), it ensures that all equation types follow a structured implementation. The project also utilizes the `re` module to enhance equation formatting. Additionally, it was developed as part of the freeCodeCamp certification program, highlighting its educational value and adherence to industry standards. This solver provides not only solutions but also in-depth equation analysis, making it a valuable mathematical tool.

## Features

- **Encapsulation**: Data hiding is maintained through structured class attributes and methods.
- **Supports Linear & Quadratic Equations**: Implements `LinearEquation` and `QuadraticEquation` classes.
- **Abstract Base Class**: Uses an `Equation` class as a blueprint with abstract methods.
- **Automatic Subclass Validation**: Implements `__init_subclass__` to enforce required attributes.
- **Equation String Formatting**: Uses the `re` module for clean equation representation.
- **Solving & Analysis**: Computes equation solutions and provides additional insights such as slopes, intercepts, and concavity.

## Implementation Details

### `Equation` Class (Base Class)

- Implements an abstract base class (`ABC`) to enforce method definitions in subclasses.
- Stores equation coefficients in a dictionary where keys represent the power of `x`.
- Encapsulates equation logic by restricting direct modification of coefficients.
- Includes `__str__` for formatted equation output using `re.sub` to remove unnecessary coefficients.

### `__init_subclass__` Method

- Ensures that every subclass has `degree` and `type` attributes.
- Raises an error if these attributes are missing, preventing improper subclass definitions.
- This helps maintain consistency and avoid runtime errors.

### Regular Expressions (`re` Module)

- Used in the `__str__` method to remove unnecessary `1` coefficients (e.g., `1x` → `x`).
- Ensures a cleaner and more readable equation representation.

## Usage

### Solving a Linear Equation:

```python
lin_eq = LinearEquation(2, 3)
print(solver(lin_eq))
```

**Output:**

```
-----Linear Equation------

       2x +3 = 0        

--------Solutions--------

        x = -1.500      

---------Details---------

slope =             2.000  
y-intercept =       3.000
```

### Solving a Quadratic Equation:

```python
quadr_eq = QuadraticEquation(1, 2, 1)
print(solver(quadr_eq))
```

**Output:**

```
---Quadratic Equation---

     x**2 +2x +1 = 0    

-------Solutions-------

       x = -1.000      

--------Details--------

concavit =      upwards   
min =   (-1.000, 0.000)
```

## Dependencies

- Python 3.x
- Uses built-in modules (`abc`, `re`).

## Acknowledgments

This project was developed as an exploration of object-oriented programming and mathematical computation in Python and was also part of the freeCodeCamp certification program.

