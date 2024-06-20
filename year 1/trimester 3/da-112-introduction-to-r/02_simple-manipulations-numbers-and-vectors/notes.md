# OBJECTS-IN-R

Certainly! Here are comprehensive notes based on the provided transcript about vectors in R:

---

**Introduction to Vectors in R**

- **Objects in R:**
  - R is an object-oriented programming language, built on C.
  - Everything in R is treated as an object, including variables, functions, and data structures like vectors, matrices, and data frames.

- **Vectors:**
  - **Definition:** Vectors in R are one-dimensional arrays that can hold elements of the same data type.
  - **Types:** They can be atomic vectors (holding one type of data) or lists (holding different types).
  - **Example:** Creating a numeric vector in R:
    ```r
    numeric_vector <- c(1, 2, 3, 4, 5)
    ```

**Topics Covered:**

1. **Atomic Vectors:**
   - **Definition:** Vectors containing elements of the same type (numeric, logical, character, etc.).
   - **Example:** Creating a character vector:
     ```r
     char_vector <- c("apple", "banana", "cherry")
     ```

2. **Creating Vectors:**
   - **Methods:** Vectors can be created using functions like `c()` or sequences like `seq()` and `rep()`.
   - **Example:** Creating a sequence vector:
     ```r
     sequence_vector <- seq(1, 10, by = 2)
     ```

3. **Mixing Objects:**
   - **Combining Types:** Vectors can hold different types of objects but will coerce them to a single type if necessary.
   - **Example:** Mixing numeric and character vectors:
     ```r
     mixed_vector <- c(1, 2, "three", 4)
     ```

4. **Operations on Vectors:**
   - **Vectorized Operations:** Operations in R are often vectorized, meaning they apply element-wise.
   - **Example:** Adding two vectors:
     ```r
     result_vector <- numeric_vector + sequence_vector
     ```

5. **Vector Attributes:**
   - **Metadata:** Vectors can have attributes like names and dimensions, enhancing their utility.
   - **Example:** Adding names to a vector:
     ```r
     names(numeric_vector) <- c("A", "B", "C", "D", "E")
     ```

6. **Subsetting Vectors:**
   - **Accessing Elements:** Subsetting allows extracting specific elements or subsets of a vector.
   - **Example:** Accessing elements by index:
     ```r
     subset_vector <- numeric_vector[c(1, 3, 5)]
     ```

7. **Vector Functions:**
   - **Utility Functions:** R provides numerous built-in functions for manipulating vectors.
   - **Example:** Finding the length of a vector:
     ```r
     vector_length <- length(numeric_vector)
     ```

8. **Plotting Vectors:**
   - **Visualization:** Vectors can be plotted directly or used in data visualization packages like ggplot2.
   - **Example:** Creating a simple plot of a vector:
     ```r
     plot(numeric_vector)
     ```

**Summary:**

- **Key Points Covered:**
  - Understanding objects in R and their types.
  - Exploring atomic vectors and their creation.
  - Mixing objects within vectors and performing operations.
  - Handling vector attributes and subsetting for data extraction.
  - Utilizing vector functions and visualizing data using vectors in R.

- **Conclusion:**
  - Vectors are fundamental in R, offering flexibility and efficiency in data manipulation and analysis. Understanding their properties and operations is crucial for proficient use in programming and data science tasks.

---

# ATOMIC-VECTORS

### Notes on Atomic Vectors in R

#### Introduction to Atomic Vectors

- **Definition**: Atomic vectors are one-dimensional arrays in R that can hold data of a single data type (class).
- **Basic Data Structure**: They are fundamental units for storing data and must contain elements of the same class.

#### Types of Atomic Vectors

1. **Logical Vectors**
   - Contains `TRUE` or `FALSE` values.
   - Example: `c(TRUE, FALSE, TRUE)`

2. **Integer Vectors**
   - Stores whole numbers.
   - Example: `c(1, 2, 3)`

3. **Double Vectors**
   - Stores floating-point numbers with double precision.
   - Example: `c(1.5, 2.7, 3.0)`

4. **Character Vectors**
   - Stores text strings.
   - Example: `c("apple", "banana", "cherry")`

5. **Complex Vectors**
   - Stores complex numbers of the form `a + bi`.
   - Example: `c(1 + 2i, 3 - 4i)`

6. **Raw Vectors**
   - Stores raw byte values.
   - Example: `as.raw(c(0x48, 0x65, 0x6c, 0x6c, 0x6f))` (represents "Hello")

#### Creating Atomic Vectors

- **Using `c()` Function**: Combines elements into a vector.
  - Example: `x <- c(3.5)`
  - Example: `y <- c(1, 2, 3, 4, 5)`

#### Checking Vector Properties

- **Type Checking Functions**:
  - `is.numeric()`, `is.logical()`, `is.integer()`, `is.double()`, `is.character()`, `is.complex()`
  - Example: `is.numeric(1.5)` returns `TRUE`
  - Example: `is.character("a")` returns `TRUE`

#### Handling Missing and Undefined Values

- **`NA` (Not Applicable)**:
  - Represents missing values.
  - Example: `z <- c(1, NA, 3)` where `NA` denotes a missing value.

- **`NaN` (Not a Number)**:
  - Represents undefined or unrepresentable values in floating-point calculations.
  - Example: `w <- 0/0` results in `NaN`.
	 
#### Useful Functions

- **`length()`**: Determines the number of elements in a vector.
  - Example: `length(y)` returns `5`.

- **`typeof()` vs `class()`**:
  - `typeof()` returns the basic type of the object.
  - `class()` returns the class of the object.
  - Example: `typeof(3.5)` returns `"double"`.

- **`attributes()`**: Retrieves additional metadata associated with an object.

#### Conclusion

Atomic vectors in R are versatile and essential for storing homogeneous data types efficiently. They are the building blocks for more complex data structures and operations in R programming. Understanding their types, creation methods, and handling of special values like `NA` and `NaN` is crucial for effective data manipulation and analysis.

These notes provide a foundational understanding of atomic vectors, preparing you to utilize them effectively in data-centric tasks in R.

---

# CREATING-VECTORS

**Creating Vectors in R**

In R, vectors are the fundamental data structure for storing and manipulating data. There are several ways to create vectors in R, including using the `c()` function, `vector()`, and `sequence()` functions.

**Creating Vectors using the `c()` Function**

The `c()` function is used to combine multiple values into a single vector. For example:
```python
x <- c(1, 2, 3, 4, 5)
```
This creates a numeric vector with the values 1 through 5.

**Creating Vectors using the `vector()` Function**

The `vector()` function is used to create a vector with a specified type and length. For example:
```python
x <- vector("numeric", 5)
```
This creates a numeric vector with 5 elements, all set to 0.

**Creating Vectors using the `sequence()` Function**

The `sequence()` function is used to create a sequence of numbers. For example:
```python
x <- seq(1, 10, by = 2)
```
This creates a numeric vector with the values 1, 3, 5, 7, and 9.

**Creating Vectors using the `rep()` Function**

The `rep()` function is used to replicate elements of a vector. For example:
```python
x <- rep(c("Varanasi", "Guwahati", "Delhi"), times = 2)
```
This creates a character vector with the values "Varanasi", "Guwahati", "Delhi", "Varanasi", "Guwahati", and "Delhi".

**Main Topics**

1. Creating Vectors using the `c()` Function
2. Creating Vectors using the `vector()` Function
3. Creating Vectors using the `sequence()` Function
4. Creating Vectors using the `rep()` Function

**Summary**

In this section, we have discussed the different ways to create vectors in R using the `c()` function, `vector()` function, `sequence()` function, and `rep()` function. We have also discussed the different types of vectors that can be created, including numeric, character, and logical vectors.

---

# MIXING-OBJECTS

**Mixing Objects in R**

**Introduction**

In R, objects of different classes can be mixed in a vector, and R will coerce the elements to be of the same class. This is called coercion. There are two types of coercion in R: implicit coercion and explicit coercion.

**Implicit Coercion**

Implicit coercion is a type of coercion that occurs automatically when mixing objects of different classes in a vector. For example, when creating a vector with numeric and character values, R will coerce the numeric values to characters.

**Example 1: Coercion of Numeric and Character Values**

```r
x <- c(1, 2, "a", "b")
print(x)
```

In this example, the numeric values 1 and 2 are coerced to characters, and the character values "a" and "b" remain unchanged.

**Example 2: Coercion of Numeric and Logical Values**

```r
x <- c(1, 2, TRUE, FALSE)
print(x)
```

In this example, the logical values TRUE and FALSE are coerced to numeric values 1 and 0, respectively.

**Explicit Coercion**

Explicit coercion is a type of coercion that can be forced using the `as.*` function. For example, to convert a vector of numeric values to characters, you can use the `as.character()` function.

**Example: Conversion of Numeric to Character**

```r
y <- as.character(1:4)
print(y)
```

In this example, the numeric values 1, 2, 3, and 4 are coerced to character values.

**Restrictions on Coercion**

Not all coercions are possible. For example, attempting to convert a character vector to a numeric vector will result in a warning and the creation of NA values.

**Summary**

In R, mixing objects of different classes in a vector can be done using coercion. There are two types of coercion: implicit coercion, which occurs automatically, and explicit coercion, which can be forced using the `as.*` function. Understanding coercion is important for working with different data types in R.

---

# MATHEMATICAL-OPERATIONS

Transcript not available.

**Introduction**

Operations in R are fundamental to performing any computations. In this topic, we will discuss the different types of operations available in R, including mathematical, relational, and logical operations.

**Mathematical Operations**

Mathematical operations in R include addition, subtraction, multiplication, division, exponentiation, and modulo. These operations can be performed on vectors and can be used to manipulate and analyze data.

* Addition: `x + y` can be used to add two vectors element-wise.
* Subtraction: `x - y` can be used to subtract one vector from another element-wise.
* Multiplication: `x * y` can be used to multiply two vectors element-wise.
* Division: `x / y` can be used to divide one vector by another element-wise.
* Exponentiation: `x ^ y` can be used to raise one vector to the power of another element-wise.
* Modulo: `%` can be used to find the remainder of dividing one vector by another element-wise.

**Relational Operations**

Relational operations in R include equal to, not equal to, less than, less than or equal to, greater than, and greater than or equal to. These operations can be used to compare vectors and can be used to manipulate and analyze data.

* Equal to: `x == y` can be used to compare two vectors element-wise.
* Not equal to: `x != y` can be used to compare two vectors element-wise and return a logical vector indicating whether the elements are equal or not.
* Less than: `x < y` can be used to compare two vectors element-wise and return a logical vector indicating whether the elements of the first vector are less than the elements of the second vector.
* Less than or equal to: `x <= y` can be used to compare two vectors element-wise and return a logical vector indicating whether the elements of the first vector are less than or equal to the elements of the second vector.
* Greater than: `x > y` can be used to compare two vectors element-wise and return a logical vector indicating whether the elements of the first vector are greater than the elements of the second vector.
* Greater than or equal to: `x >= y` can be used to compare two vectors element-wise and return a logical vector indicating whether the elements of the first vector are greater than or equal to the elements of the second vector.

**Logical Operations**

Logical operations in R include negation, AND, and XOR. These operations can be used to manipulate and analyze data.

* Negation: `!x` can be used to negate a logical vector.
* AND: `x & y` can be used to perform a logical AND operation on two vectors.
* XOR: `x ^ y` can be used to perform a logical XOR operation on two vectors.
* OR: `x || y` can be used to perform a logical OR operation on two vectors.

**Matching Operator**

The matching operator `%in%` can be used to check if an element is present in a vector.

* Example: `x %in% c(1, 2, 3)` can be used to check if the element 2 is present in the vector `x`.

**Vector Operations**

Vector operations in R include addition and multiplication.

* Addition: `x + y` can be used to add two vectors element-wise.
* Multiplication: `x * y` can be used to multiply two vectors element-wise.

**Logical Vectors**

Logical vectors in R can be used to manipulate and analyze data.

* Example: `x + y` can be used to add two logical vectors element-wise.

**NA Values**

NA values in R can be used to represent missing or unknown values.

* Example: `x * 2` can be used to multiply a vector containing NA values by 2.

**Conclusion**

In this topic, we have discussed the different types of operations available in R, including mathematical, relational, and logical operations. We have also discussed how to use these operations to manipulate and analyze data.

---

# VECTOR-ATTRIBUTES

**Vector Attributes in R**

Vector attributes in R refer to the metadata associated with an object, which stores additional information about the object. These attributes can be used to store information such as the name of the elements in a vector, the dimension of the object, and the class of the object.

**Types of Vector Attributes**

Some common attributes include:

* Names: These are the names of the elements in a vector. For example, in the code snippet below, `x` is a vector with names `age`, `height`, and `weight`.

```python
x <- c(age = 25, height = 5.8, weight = 70)
```

* Dimension: This refers to the number of dimensions in an object, such as a matrix or array.
* Class: Every object in R must have a class, which defines the type of object it is.

**Setting Attributes**

Attributes can be set manually using the `attributes` function. For example, the following code sets the names of a vector:

```python
x <- c(25, 5.8, 70)
names(x) <- c("age", "height", "weight")
```

**Getting Attributes**

Attributes can be retrieved using the `attributes` function. For example, the following code retrieves the names of a vector:

```python
x <- c(age = 25, height = 5.8, weight = 70)
attributes(x)
```

**Changing Attributes**

Attributes can also be changed using the `attributes` function. For example, the following code changes the names of a vector:

```python
x <- c(age = 25, height = 5.8, weight = 70)
names(x) <- c("a", "b", "c")
```

**Summary**

Vector attributes in R provide a way to associate metadata with an object, which can be useful for storing additional information about the object. Attributes can be set and retrieved using the `attributes` function, and can be changed using the `names` function.

---

# SUBSETTING-VECTORS

**Introduction to Subsetting Vectors**

In R, subsetting vectors allows you to access specific elements or subsets of a vector. This can be done using various methods, including indexing, logical vectors, and names.

**Indexing**

Indexing is one way to subset vectors. In R, indexing starts from 1. You can access specific elements of a vector by specifying the index in square brackets. For example, if you have a vector `x` containing the names "Bob", "John", "Alice", and "Mary", you can access the first name, "Bob", by using `x[1]`. You can also subset multiple elements by specifying multiple indices. For example, `x[c(1, 3)]` would return the first and third elements, "Bob" and "Alice".

**Logical Vectors**

Logical vectors can also be used to subset vectors. A logical vector is a vector of boolean values (True or False). You can create a logical vector and use it to subset a vector. For example, if you have a numeric vector `edges` containing the values 15, 20, 25, 30, and 35, you can create a logical vector `edges > 18` to subset the vector to include only the values greater than 18.

**Names**

You can also subset vectors using names. If you have a vector with named elements, you can access specific elements by their names. For example, if you have a vector `x` containing the names "age", "height", and "weight", you can access the "age" element by using `x["age"]`.

**Negative Indexing**

Negative indexing allows you to subset vectors by excluding specific elements. For example, if you want to exclude the first element of a vector, you can use `x[-1]`. You can also use negative indexing to exclude multiple elements by specifying multiple indices.

**which() Function**

The `which()` function is used to find the indices of elements that meet a specific condition. For example, you can use `which(x > 3)` to find the indices of elements in vector `x` that are greater than 3.

### Using Double Square Brackets `[[ ]]` in R

**Double Square Brackets for Lists:**
- Double square brackets `[[ ]]` are used to access the elements of a list.
- They can be used to extract a single element from a list.

**Example:**
```r
x <- list(age = 25, height = 170, weight = 65)
first_element <- x[[1]]  # Extracts the first element, which is 25
```

### Using Single Square Brackets `[ ]` in R

**Single Square Brackets for Vectors:**
- Single square brackets `[ ]` are used to access elements of a vector.
- They can be used to extract one or more elements from a vector.

**Example:**
```r
x <- c("age", "height", "weight")
first_element <- x[1]  # Extracts the first element, which is "age"
```

### Explanation in Context:

- If you have a vector `x` containing the elements "age", "height", and "weight", you can use `x[1]` to extract the first element, which is "age".
- If you have a list `x` containing named elements like `age`, `height`, and `weight`, you can use `x[[1]]` to extract the first element, which would be the value associated with the first name (e.g., `age`).

### Example with Both:

```r
# Vector example
vector_x <- c("age", "height", "weight")
first_element_vector <- vector_x[1]  # "age"

# List example
list_x <- list(age = 25, height = 170, weight = 65)
first_element_list <- list_x[[1]]  # 25
```

In summary, double square brackets `[[ ]]` are primarily used for extracting elements from lists, while single square brackets `[ ]` are used for extracting elements from vectors and for subsetting.

**Summary**

In summary, subsetting vectors in R can be done using indexing, logical vectors, names, and negative indexing. The `which()` function can be used to find the indices of elements that meet a specific condition. Double square brackets can be used to extract a single element from a vector.

---

# VECTOR-FUNCTIONS

**Vector Functions in R**

**Introduction**

Vector functions in R are essential for manipulating and analyzing data. These built-in functions make it easier to perform various operations on vectors, such as calculating statistics, checking for duplicates, and reversing the order of elements.

**Statistics Functions**

R provides various statistics functions, including:

* `sum()`: calculates the sum of all elements in a vector
* `mean()`: calculates the mean of all elements in a vector
* `median()`: calculates the median of all elements in a vector
* `max()`: calculates the maximum value in a vector
* `min()`: calculates the minimum value in a vector
* `sd()`: calculates the standard deviation of all elements in a vector
* `var()`: calculates the variance of all elements in a vector

**Examples**

* Calculating the sum of a vector: `sum(c(1, 2, 3, 4, 5))` returns `15`
* Calculating the mean of a vector: `mean(c(1, 2, 3, 4, 5))` returns `3`

**Handling NA Values**

NA values can occur in vectors, especially when working with datasets. To handle NA values, you can use the `na.rm` argument in various functions, such as `sum()`, `mean()`, and `median()`. For example:
```R
x <- c(1, 2, NA, 4, 5)
sum(x, na.rm = TRUE)  # returns 12
```
**Checking for Duplicates**

To check for duplicates in a vector, you can use the `duplicated()` function:
```R
x <- c(1, 2, 3, 4, 5, 1, 2, 3)
duplicated(x)  # returns a logical vector indicating duplicate values
```
**Reversing the Order of Elements**

To reverse the order of elements in a vector, you can use the `reverse()` function:
```R
x <- c(1, 2, 3, 4, 5)
reverse(x)  # returns (5, 4, 3, 2, 1)
```
**Summary**

In conclusion, vector functions in R are essential for data analysis and manipulation. By using various statistics functions, handling NA values, checking for duplicates, and reversing the order of elements, you can efficiently analyze and manipulate data in R.

---

# PLOTTING-VECTORS

**Plotting Vectors in R**

The lecture covers the basics of plotting vectors in R, including the use of the `plot` function, `barplot` function, `pi` function, `histogram` function, and `boxplot` function.

**Introduction to Plotting Vectors**

Plotting vectors in R allows users to visualize the contents of a vector. This can be done using the `plot` function, which is a generic function for plotting vectors. The `plot` function can be used to create a variety of plots, including line plots, scatter plots, and histograms.

**Plot Function**

The `plot` function is used to create a line plot of a vector. The function takes two arguments: the first is the vector to be plotted, and the second is the title of the plot. The `plot` function can also be used to customize the appearance of the plot, including the x and y axis labels, the title, and the colors used.

**Example**

Suppose we have a vector `x` containing the values 1, 2, 3, 4, and 5. We can use the `plot` function to create a plot of the vector as follows:
```python
x <- c(1, 2, 3, 4, 5)
plot(x)
```
This will create a plot with the x-axis labeled as the index of the vector and the y-axis labeled as the values of the vector.

**Bar Plot Function**

The `barplot` function is used to create a bar plot of a vector. The function takes two arguments: the first is the vector to be plotted, and the second is the title of the plot. The `barplot` function can also be used to customize the appearance of the plot, including the x and y axis labels, the title, and the colors used.

**Example**

Suppose we have a vector `x` containing the votes for three candidates: A, B, and C. We can use the `barplot` function to create a bar plot of the votes as follows:
```python
x <- c(100, 150, 200)
barplot(x, main = "Vote Count")
```
This will create a bar plot with the x-axis labeled as the candidate names and the y-axis labeled as the vote counts.

**Pi Function**

The `pi` function is used to create a pie chart of a vector. The function takes two arguments: the first is the vector to be plotted, and the second is the title of the plot. The `pi` function can also be used to customize the appearance of the plot, including the x and y axis labels, the title, and the colors used.

**Example**

Suppose we have a vector `x` containing the votes for three candidates: A, B, and C. We can use the `pi` function to create a pie chart of the votes as follows:
```python
x <- c(100, 150, 200)
pie(x, main = "Vote Count")
```
This will create a pie chart with the x-axis labeled as the candidate names and the y-axis labeled as the vote counts.

**Histogram Function**

The `histogram` function is used to create a histogram of a vector. The function takes two arguments: the first is the vector to be plotted, and the second is the title of the plot. The `histogram` function can also be used to customize the appearance of the plot, including the x and y axis labels, the title, and the colors used.

**Example**

Suppose we have a vector `x` containing 1,000 random numbers from a normal distribution. We can use the `histogram` function to create a histogram of the numbers as follows:
```python
x <- rnorm(1000, mean = 0, sd = 1)
hist(x, main = "Histogram of Random Numbers")
```
This will create a histogram with the x-axis labeled as the values of the numbers and the y-axis labeled as the frequency of the values.

**Boxplot Function**

The `boxplot` function is used to create a box plot of a vector. The function takes two arguments: the first is the vector to be plotted, and the second is the title of the plot. The `boxplot` function can also be used to customize the appearance of the plot, including the x and y axis labels, the title, and the colors used.

**Example**

Suppose we have a vector `x` containing 1,000 random numbers from a normal distribution. We can use the `boxplot` function to create a box plot of the numbers as follows:
```python
x <- rnorm(1000, mean = 0, sd = 1)
boxplot(x, main = "Box Plot of Random Numbers")
```
This will create a box plot with the x-axis labeled as the values of the numbers and the y-axis labeled as the quartiles of the values.

**Summary**

In this lecture, we covered the basics of plotting vectors in R, including the use of the `plot` function, `barplot` function, `pie` function, `histogram` function, and `boxplot` function. We also discussed how to customize the appearance of the plots using various options.

---

