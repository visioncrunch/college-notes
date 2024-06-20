# LOGICAL-EXPRESSIONS

**Conditional Execution in R**

### Introduction
Today's topic covers conditional execution in R. We'll understand what conditional execution means, its syntax, and explore various types, including nested and hierarchical conditional execution. Additionally, we'll delve into vectorized if-else and the importance of sanity checks in code. Examples will illustrate these concepts.

### Learning Objectives
- Understand conditional execution.
- Learn the syntax for conditional execution in R.
- Explore nested and hierarchical conditional execution.
- Understand vectorized if-else.
- Learn the importance of sanity checks in coding.
- Practice with examples.

### Logical Expressions
Conditional execution in programming is based on logical expressions, which evaluate to either true or false. These expressions are used to make decisions in a program.

### Comparison Operators
Comparison operators are used to compare two values:
- `==`: Equal to
- `!=`: Not equal to
- `>`: Greater than
- `<`: Less than
- `>=`: Greater than or equal to
- `<=`: Less than or equal to

Example:
```R
x <- 5
y <- 10
x == y  # FALSE
x != y  # TRUE
x > y   # FALSE
x < y   # TRUE
x >= y  # FALSE
x <= y  # TRUE
```

### Logical Operators
Logical operators combine multiple logical expressions:
- `&`: AND
- `|`: OR
- `!`: NOT

Example:
```R
TRUE & FALSE  # FALSE
TRUE | FALSE  # TRUE
!TRUE         # FALSE
```

### Short Form vs Long Form Logical Operators
- **Short Form (`&`, `|`)**: Performs element-wise operations and returns a logical vector of the same length as the operands.
- **Long Form (`&&`, `||`)**: Evaluates only the first element of each vector and returns a single logical value.

Example:
```R
# Short form
c(TRUE, FALSE) & c(FALSE, TRUE)  # FALSE  TRUE

# Long form
TRUE && FALSE  # FALSE
TRUE || FALSE  # TRUE
```

### Match Operators
Match operators check for the presence of elements within vectors.

Example:
```R
x <- c(1, 2, 3)
1 %in% x   # TRUE
4 %in% x   # FALSE
```

### Conditional Execution
Conditional execution in R involves making decisions based on logical expressions.

#### If Statements
The basic structure of an if statement in R:
```R
if (condition) {
  # Code to execute if condition is TRUE
}
```

Example:
```R
x <- 5
if (x > 0) {
  print("Positive number")
}
```

#### If-Else Statements
An if-else statement executes one block of code if the condition is true and another block if the condition is false.
```R
if (condition) {
  # Code to execute if condition is TRUE
} else {
  # Code to execute if condition is FALSE
}
```

Example:
```R
x <- -5
if (x > 0) {
  print("Positive number")
} else {
  print("Negative number")
}
```

#### Nested If Statements
Nested if statements allow for multiple layers of conditions.
```R
if (condition1) {
  # Code if condition1 is TRUE
  if (condition2) {
    # Code if condition2 is TRUE
  }
}
```

Example:
```R
x <- 5
y <- 10
if (x > 0) {
  if (y > 0) {
    print("Both numbers are positive")
  }
}
```

### Vectorized If-Else
Vectorized if-else statements allow for conditional checks on entire vectors.
```R
result <- ifelse(condition, value_if_true, value_if_false)
```

Example:
```R
x <- c(-5, 0, 5)
result <- ifelse(x > 0, "Positive", "Non-positive")
print(result)  # "Non-positive" "Non-positive" "Positive"
```

### Sanity Checks
Sanity checks ensure that the data or conditions meet certain criteria before executing code, preventing errors and improving code reliability.

Example:
```R
x <- NA
if (!is.na(x) && x > 0) {
  print("Positive number")
} else {
  print("Not a positive number")
}
```

### Summary
Conditional execution is a fundamental concept in programming, allowing for decision-making based on logical expressions. R provides various tools and operators to perform these checks, including comparison operators, logical operators, and both short and long forms of these operators. Understanding and correctly applying these concepts enhances code efficiency and reliability.
# HANDLING-NA-AND-NULL-IN-LOGICAL-EXPRESSION

**Handling NA and NULL in Logical Expressions**

**Introduction**

In this section, we will discuss how to handle NA (Not Available) and NULL values in logical expressions. We will use the `is.na` and `is.null` functions to check if a value is NA or NULL.

**Checking for NA and NULL**

When working with logical expressions, it's common to encounter NA and NULL values. These values can cause errors in our code. To handle this, we can use the `is.na` and `is.null` functions to check if a value is NA or NULL.

**Example**

Let's consider an example to illustrate this. Suppose we have a variable `x` that can take on different values, including NA and NULL.

```python
x = NA
if x > 0:
    print("x is greater than zero")
else:
    print("x is not greater than zero")
```

In this example, the code will throw an error because `x` is NA, and the `if` statement is trying to compare it to a number. To fix this, we can use the `is.na` function to check if `x` is NA.

```python
if not is.na(x) and x > 0:
    print("x is greater than zero")
else:
    print("x is not greater than zero")
```

**Using Short Form Operators**

We can also use short form operators to simplify our code. For example, we can use the `&` operator to check if `x` is not NA and greater than zero.

```python
if !is.na(x) & x > 0:
    print("x is greater than zero")
else:
    print("x is not greater than zero")
```

**Handling NULL Values**

We can also use the `is.null` function to check if a value is NULL. For example, let's assume we have a variable `y` that can take on different values, including NULL.

```python
y = NULL
if not is.null(y) and y > 0:
    print("y is greater than zero")
else:
    print("y is not greater than zero")
```

**Matrix Operations**

We can also use the short form operators to check if a matrix is a certain size. For example, let's assume we have a matrix `x` with three rows and three columns.

```python
x = matrix(1:9, nrow=3, ncol=3)
if nrow(x) == 3 and ncol(x) == 3:
    print("x is a 3x3 matrix")
```

**Summary**

In this section, we learned how to handle NA and NULL values in logical expressions using the `is.na` and `is.null` functions. We also learned how to use short form operators to simplify our code. Additionally, we saw how to use these operators to check if a matrix is a certain size.

---

# SOME-FUNCTIONS-FOR-CONDITONAL-EXECUTION

**Conditional Execution in R**

**Introduction**

In this topic, we will explore some useful functions in R for conditional execution, specifically the `all()` and `any()` functions, as well as the `all.equal()` and `identical()` functions.

**The `all()` and `any()` Functions**

The `all()` function checks if all elements in a vector are true, while the `any()` function checks if any element in a vector is true. This can be illustrated with a simple example:

```python
x <- c(TRUE, TRUE, FALSE, FALSE)
any(x)  # Output: TRUE
all(x)   # Output: FALSE
```

**The `all.equal()` and `identical()` Functions**

The `all.equal()` function checks if two objects are equal, ignoring minor differences in decimal values. On the other hand, the `identical()` function checks if two objects are identical, including exact equal values. This can be demonstrated with an example:

```python
x <- c(1, 2, 3)
y <- c(1, 2, 3)
all.equal(x, y)  # Output: TRUE
identical(x, y)  # Output: TRUE

x <- c(1, 2, 3)
y <- sqrt(x^2)
identical(x, y)  # Output: FALSE
all.equal(x, y)  # Output: TRUE
```

**Real-World Example**

Suppose we have two vectors, `x` and `y`, where `y` is the square root of `x` squared. Although `x` and `y` are equal, the `identical()` function would return `FALSE` because of the slight difference in decimal values. On the other hand, the `all.equal()` function would return `TRUE` because it ignores minor differences.

**Conclusion**

In conclusion, the `all()` and `any()` functions are useful for conditional execution in R, while the `all.equal()` and `identical()` functions are useful for comparing objects. Understanding the differences between these functions can help you write more efficient and accurate code.

---

# ISTRUE-AND-ISFALSE

**Introduction**

The transcript discusses the `isTRUE` and `isFALSE` functions in R, which are used to check if a value is true or false. These functions come in handy when working with values that are not NA or null.

**isTRUE Function**

The `isTRUE` function is used to check if a value is true. It takes a single argument, which can be any R object, and returns a boolean value indicating whether the value is true or not. 

**Example**

```R
x <- 4
isTRUE(x)  # returns FALSE
x <- TRUE
isTRUE(x)  # returns TRUE
```

**isFALSE Function**

The `isFALSE` function is used to check if a value is false. It takes a single argument, which can be any R object, and returns a boolean value indicating whether the value is false or not.

**Example**

```R
x <- 4
isFALSE(x)  # returns FALSE
x <- FALSE
isFALSE(x)  # returns TRUE
```

**Use of isTRUE and isFALSE Functions**

The `isTRUE` and `isFALSE` functions are particularly useful when working with NA or null values. They can be used to check if a value is true or false, and can be used in conditional statements to make decisions.

**Example with NA Values**

```R
x <- NA
isTRUE(x)  # returns FALSE
isFALSE(x)  # returns FALSE
```

**Summary**

The `isTRUE` and `isFALSE` functions in R are used to check if a value is true or false. They can be used to make decisions in conditional statements, and are particularly useful when working with NA or null values.

---

# IF-ELSE-S

**Conditional Execution in R**

Conditional execution is a fundamental concept in programming, allowing developers to make decisions based on conditions. In R, the `if-else` statement is a powerful tool for making decisions and executing specific code blocks. This note summarizes the key points discussed in the transcript, highlighting important topics and examples.

**Introduction**

Conditional execution in R is achieved through the `if-else` statement. This statement allows developers to execute specific code blocks based on conditions. The `if-else` statement consists of a logical expression, an `if` clause, and an `else` clause.

**The `if-else` Statement**

The `if-else` statement is used to make decisions based on a logical expression. If the logical expression is true, the code block inside the `if` statement is executed. If the logical expression is false, the code block inside the `else` statement is executed.

**Example**

Consider the following code snippet:
```R
x <- 10
if (x > 0) {
  print("x is positive")
} else {
  print("x is negative")
}
```
In this example, the logical expression `x > 0` is evaluated. Since `x` is greater than 0, the code block inside the `if` statement is executed, printing "x is positive".

**Nested `if-else` Statements**

Nested `if-else` statements allow developers to create complex decision-making logic. This is achieved by nesting `if-else` statements inside another `if-else` statement.

**Example**

Consider the following code snippet:
```R
x <- 0
if (x > 0) {
  print("x is positive")
} else if (x < 0) {
  print("x is negative")
} else {
  print("x is zero")
}
```
In this example, the logical expression `x > 0` is evaluated. Since `x` is not greater than 0, the `else if` clause is evaluated. Since `x` is not less than 0, the `else` clause is executed, printing "x is zero".

**Vectorized `if-else` Statements**

Vectorized `if-else` statements allow developers to apply conditional logic to entire vectors or matrices. This is achieved using the `ifelse()` function.

**Example**

Consider the following code snippet:
```R
x <- c(1, 2, 3, 4, 5)
y <- ifelse(x > 3, "greater", "less")
print(y)
```
In this example, the `ifelse()` function is used to apply the conditional logic to the vector `x`. The result is a vector `y` containing the strings "greater" or "less" based on whether each element in `x` is greater than 3.

**Switch Statement**

The `switch()` function is another way to make decisions in R. It takes an expression and a list of cases. The expression is evaluated, and the corresponding case is executed.

**Example**

Consider the following code snippet:
```R
x <- 2
print(switch(x,
             1, "one",
             2, "two",
             3, "three",
             "default"))
```
In this example, the `switch()` function is used to evaluate the expression `x`. Since `x` is 2, the corresponding case is executed, printing "two".

**Summary**

In conclusion, conditional execution in R is achieved through the `if-else` statement and the `switch()` function. The `if-else` statement allows developers to make decisions based on conditions, while the `switch()` function provides a concise way to evaluate expressions and execute specific code blocks. Vectorized `if-else` statements allow developers to apply conditional logic to entire vectors or matrices.

---

# SANITY-CHECKS

**Notes on Sanity Checks in R**

**Introduction**

Sanity checks are an essential part of programming, ensuring that the input data is valid and meets specific criteria. In R, sanity checks can be implemented using if-else statements and functions such as `stop()` and `warning()`. This note will cover the basics of sanity checks in R, including examples and code snippets.

**Sanity Checks with if-else Statements**

Sanity checks can be implemented using if-else statements to verify that input data meets specific criteria. For example, the following code snippet checks if a value is numeric and has at least 5 elements:
```python
if (is.numeric(x) && length(x) >= 5) {
  # code to execute if condition is true
} else {
  stop("Invalid input")
}
```
**Implementing Sanity Checks with stop() and warning()**

The `stop()` function can be used to terminate the execution of a function if a specific condition is not met. The `warning()` function can be used to display a warning message if a condition is not met.

For example, the following code snippet checks if a value is positive and stops the execution if it is not:
```python
if (x <= 0) {
  stop("Value must be positive")
}
```
**Short Form Operators**

The long form of if-else statements can be condensed using short form operators. For example, the following code snippet checks if a value is numeric, has at least 5 elements, and is positive:
```python
if (!is.numeric(x) || length(x) < 5 || x <= 0) {
  stop("Invalid input")
}
```
**Examples and Code Snippets**

The following example demonstrates how to implement a sanity check function:
```python
sanity_check <- function(x) {
  if (!is.numeric(x) || length(x) < 5 || x <= 0) {
    stop("Invalid input")
  }
  return(TRUE)
}
```
This function checks if the input `x` is numeric, has at least 5 elements, and is positive. If any of these conditions are not met, the function terminates with an error message.

**Conclusion**

Sanity checks are an essential part of programming in R, ensuring that input data is valid and meets specific criteria. This note has covered the basics of sanity checks in R, including examples and code snippets. By implementing sanity checks using if-else statements, `stop()`, and `warning()`, developers can ensure that their code is robust and reliable.

---

# SOME-ADDITIONAL-FUNCTIONS

**Introduction**

The transcript discusses various R functions that are useful when working with conditional equations and reading files directly. The functions include stopifnot, inherits, match.arg, file.exists, and directory.exists. These functions can be used to simplify code and make it more efficient.

**Stopifnot Function**

The stopifnot function is used to stop the execution of a program if a condition is not met. It is a short form of writing a detailed if statement. An example of using the stopifnot function is provided:
```
stopifnot(x > 0)
```
This function will stop the execution of the program if the condition x > 0 is not met.

**Inherits Function**

The inherits function is used to check if an object is of a particular class. An example of using the inherits function is provided:
```
inherits(x, "numeric")
```
This function will return TRUE if the object x is of class "numeric".

**Match.arg Function**

The match.arg function is used to check if an argument is one of the valid arguments. An example of using the match.arg function is provided:
```
match.arg(x, c("male", "female"))
```
This function will return the argument that matches the vector "male" or "female".

**File.exists and Directory.exists Functions**

The file.exists and directory.exists functions are used to check if a file or directory exists. An example of using the file.exists function is provided:
```
file.exists("file.txt")
```
This function will return TRUE if the file "file.txt" exists.

**BMI Calculation Function**

The transcript also discusses a function to calculate BMI (Body Mass Index) and includes a sanity check to ensure that the input values are valid.

**Conclusion**

The transcript discusses various R functions that can be used to simplify code and make it more efficient. The functions include stopifnot, inherits, match.arg, file.exists, and directory.exists. The transcript also discusses a function to calculate BMI and includes a sanity check to ensure that the input values are valid.

---

