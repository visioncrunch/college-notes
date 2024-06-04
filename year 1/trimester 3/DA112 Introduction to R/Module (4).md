Lecture Notes on Functions in R

**Introduction**

- **Functions:** Self-contained blocks of code that perform specific tasks.
- **Philosophy:** "Don't Repeat Yourself" (DRY) principle, write code once and reuse it.
- **Benefits:** Avoid repetition, decompose complex problems, improve code structure, facilitate testing and debugging.

**R Functions**

- **Types:**
    - Built-in: Predefined functions in R (e.g., `mean`, `sum`, `sd`).
    - User-defined: Functions you create yourself.
- **Syntax:**
    
    Code snippet
    
    ```
    function_name <- function(arg1, arg2, ...) {
        # Function body
        return(value) 
    }
    ```
    
    - `function_name`: The name you give your function.
    - `arg1`, `arg2`, etc.: Arguments (inputs) passed to the function.
    - `# Function body`: The code that performs the task.
    - `return(value)`: Optional statement to explicitly return a value.

**When to Use Functions**

- To avoid repeating code.
- To break down complex problems.
- To improve code organization.
- To promote code reusability and testing.

**Example: Standard Deviation Function**

- **Formula:**
    
    ```
    σ = √(Σ(x_i - x̄)² / (n - 1))
    ```
    
- **Manual Calculation:** Possible with a one-liner in R, but prone to errors.
- **Function Definition:**
    
    Code snippet
    
    ```
    standard_deviation <- function(x) {
        result <- sqrt(sum((x - mean(x))^2) / (length(x) - 1))
        return(result)
    }
    ```
    
- **Function Call:**
    
    Code snippet
    
    ```
    data <- c(1, 2, 3, 4, 5)
    result <- standard_deviation(data)
    print(result) 
    ```
    

**Key Points**

- Functions are essential for efficient and organized R programming.
- User-defined functions allow you to customize your code.
- Functions improve code readability and maintainability.
- The standard deviation example demonstrates the power of functions in simplifying complex calculations.

Lecture Notes on Functions in R (Continued)

**Naming Functions**

- **Good Practices:**
    - Use meaningful and descriptive names.
    - Avoid single-letter or generic names (e.g., "for").
    - Use unique names that don't conflict with existing objects or functions.
    - Use lowercase letters and separate words with underscores (e.g., `standard_deviation`).
- **Bad Practices:**
    - All capital letters (e.g., `STANDARD`).
    - Mixed case without underscores (e.g., `standardDeviation`).

**Declaring Functions**

- **Syntax:**
    
    Code snippet
    
    ```
    function_name <- function(arg1, arg2, ...) {
        # Function body
    }
    ```
    
- **Example:**
    
    Code snippet
    
    ```
    multiply_by_2 <- function(A) {
        result <- A * 2
        return(result)
    }
    ```
    
- **Key Points:**
    - Use the `function` keyword.
    - Functions are objects in R, can be assigned to variables, and passed as arguments.

**Calling Functions**

- **Syntax:**
    
    Code snippet
    
    ```
    function_name(arg1, arg2, ...)
    ```
    
- **Example:**
    
    Code snippet
    
    ```
    result <- multiply_by_2(5)  # Returns 10
    ```
    

**Returning Values**

- **Default Behavior:**
    - If no explicit `return` statement is used, the last expression in the function body is returned.
    - If the function body is empty or only contains a `print` statement, the function returns `NULL`.
- **Explicit Return:**
    - Use the `return()` statement to explicitly specify the value to be returned.
- **NULL Value:**
    - A special value in R representing the absence of a value.
    - Different from `NA` (Not Available) or `NaN` (Not a Number).

**Additional Notes**

- You can check the class of a function using `class(function_name)`.
- Experiment with functions like `typeof()`, `length()`, and `attributes()` on functions to see their outputs.

Let me know if you'd like me to continue with the rest of the lecture transcript.

Lecture Notes on Functions in R (Continued)

**Cat and Paste Functions**

- **Purpose:**
    - `cat`: Concatenates elements and displays the result directly on the console. Returns NULL.
    - `paste`: Concatenates elements into a character string. Returns a character vector.

**Cat Function**

- **Usage:**
    
    Code snippet
    
    ```
    cat("Hello", "World", sep = ", ")  # Output: Hello, World
    ```
    
- **Line Breaks:**
    - Automatically inserts a line break at the end of the output.
    - Use `\n` to explicitly insert line breaks within the output.

**Example with Named Vector:**

Code snippet

```
housecat <- c(height = 46, weight = 4.5)
cat("The average housecat is", housecat["height"], "centimeters tall\n",
    "and weights", housecat["weight"], "kilograms\n")
```

**Output:**

```
The average housecat is 46 centimeters tall 
 and weights 4.5 kilograms
```

**Paste Function**

- **Usage:**
    
    Code snippet
    
    ```
    result <- paste("Hello", "World", sep = ", ")
    print(result)  # Output: Hello, World
    ```
    

**Cat vs. Paste**

|Feature|`cat`|`paste`|
|---|---|---|
|Purpose|Display output on console|Concatenate elements into a character string|
|Return Value|NULL|Character vector|
|Line Breaks|Automatic at the end, use `\n` for explicit breaks|No automatic line breaks|

**Additional Functions to Explore**

- `paste0`: Similar to `paste`, but with no default separator.
- `format`: Formats numbers and strings.
- `sprintf`: Creates formatted strings using C-style formatting.

Let me know if you'd like me to continue with the rest of the lecture transcript.

Lecture Notes on Functions in R (Continued)

**Basic Function Types in R**

- **Type A:** No arguments, no explicit return value, output to console.
    
    Code snippet
    
    ```
    hello_world <- function() {
        cat("Hello, world!\n")
    }
    ```
    
- **Type B:** One argument, no explicit return value, output to console.
    
    Code snippet
    
    ```
    greet <- function(name) {
        cat("Hello,", name, "\n")
    }
    ```
    
- **Type C:** One argument, explicit return value.
    
    Code snippet
    
    ```
    square <- function(x) {
        return(x^2)
    }
    ```
    

**The `invisible` Function**

- **Purpose:** Returns a value from a function without displaying it on the console.
- **Example:**
    
    Code snippet
    
    ```
    square_invisible <- function(x) {
        invisible(x^2)
    }
    ```
    

**One-Liner Function Definitions**

- **Syntax:**
    
    Code snippet
    
    ```
    function_name <- function(arg1, arg2, ...) expression
    ```
    
- **Example:**
    
    Code snippet
    
    ```
    square <- function(x) x^2
    ```
    

**Multiple Arguments**

- **Syntax:** Separate arguments with commas in the function definition.
- **Example:**
    
    Code snippet
    
    ```
    add <- function(a, b) {
        return(a + b)
    }
    ```
    

**Missing Arguments**

- **Behavior:**
    - If a function is called with missing arguments, R will replace them with `NA` (Not Available).
    - If the missing argument is not used in the function body, no error is thrown.
    - If the missing argument is used, an error is thrown.

**Named Arguments**

- **Advantage:** Allows you to specify arguments in any order by explicitly naming them in the function call.
- **Example:**
    
    Code snippet
    
    ```
    greet_person <- function(name, greeting = "Hello") {
        cat(greeting, ", ", name, "\n")
    }
    
    greet_person(name = "Alice", greeting = "Hi")  # Output: Hi, Alice
    ```
    

**Default Argument Values**

- **Advantage:** Provides a default value for an argument if it is not explicitly specified in the function call.
- **Example:**
    
    Code snippet
    
    ```
    greet_person("Alice")  # Output: Hello, Alice (since greeting defaults to "Hello")
    ```
    
- **Overriding Defaults:** You can still override the default value by explicitly specifying the argument in the function call.

**Good Coding Practices**

- Define only the arguments that are necessary.
- Place unnamed arguments before named arguments in function calls.

Please let me know if you would like the rest of the transcript!

Lecture Notes on Functions in R (Continued)

**Lexical Scoping**

- **Definition:** A method for resolving variable names in a programming language.
- **R's Approach:** Lexical scoping, meaning the scope of a variable is determined by its location in the source code.
- **How it Works:**
    1. R first looks for a variable's value within the function where it's used.
    2. If not found, R searches in the environment where the function was defined.
    3. This continues up the hierarchy of environments until the global environment is reached.

**Example 1: Power Function**

Code snippet

```
power <- 2

power_function <- function(x) {
    result <- x^power
    print(result)
}

power_function(3)  # Output: 9 (since power is found outside the function)
```

- **Key Point:** The `power` variable is defined outside the function, but R still finds it due to lexical scoping.
- **Potential Issue:** External variables can affect function behavior, making it harder to debug.

**Example 2: Nested Functions**

Code snippet

```
x <- 10

f <- function() {
    x <- 20
    z <- function() {
        x <- 30
        cat("x in z:", x, "\n")  # Output: x in z: 30
    }
    z()
    cat("x in f:", x, "\n")      # Output: x in f: 20
}

f()
cat("x in global:", x, "\n")  # Output: x in global: 10
```

- **Explanation:**
    - `x` is defined at three levels: global, within `f`, and within `z`.
    - When `z()` is called, it prints the value of `x` defined within itself (30).
    - When `cat("x in f:", x)` is called, it prints the value of `x` defined within `f` (20).
    - The final `cat` statement prints the global value of `x` (10).

**Key Takeaways**

- Lexical scoping is powerful but can lead to unexpected behavior if not understood.
- It's generally good practice to define variables within the functions that use them.
- Nested functions can create complex scoping scenarios.
- Careful understanding of lexical scoping is crucial for debugging and maintaining R code.

Feel free to ask if you have any further questions or would like me to elaborate on any aspect!

Lecture Notes on Functions in R (Continued)

**Returning Multiple Values from R Functions**

- **Limitation:** R functions cannot directly return multiple objects (e.g., vectors) by default.
- **Workaround:** Use lists to combine multiple objects and return them as a single list object.

**Lists in R (Brief Overview)**

- **Definition:** A container that can hold multiple objects of different types (e.g., vectors, matrices, data frames).
- **Example:**
    
    Code snippet
    
    ```
    my_list <- list(numbers = c(1, 2, 3, 4), strings = c("apple", "banana", "cherry"))
    print(my_list)
    ```
    

**Example: Calculating Circle Properties**

Code snippet

```
calculate_circle_properties <- function(radius) {
    circumference <- 2 * pi * radius
    area <- pi * radius^2
    result <- list(circumference = circumference, area = area)
    return(result)
}

result <- calculate_circle_properties(5)
print(result) 
```

**Example: Calculating BMI**

Code snippet

```
calculate_BMI <- function(height, weight, height_in_cm = TRUE) {
    if (height_in_cm) {
        height <- height / 100 
    }
    BMI <- weight / height^2
    return(BMI)
}

heights <- c(180, 172, 140, 210)
weights <- c(45, 65, 82, 110)
BMIs <- calculate_BMI(heights, weights)
print(BMIs)
```

**Example: Calculating Area of a Rectangle**

Code snippet

```
calculate_area <- function(length, breadth) {
    area <- length * breadth
    return(area)
}

result <- calculate_area(10, 5)
print(result) 
```

**Key Points**

- Lists provide a convenient way to return multiple values from a function.
- Vectorization can be used to apply functions to multiple inputs efficiently.
- Default arguments can make functions more flexible and user-friendly.

Let me know if you'd like me to continue with any remaining parts of the lecture transcript!

