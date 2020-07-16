# Software Engineering Practices

References:

- [AWS ML Program](https://www.udacity.com/scholarships/aws-machine-learning-scholarship-program)

***

## Clean and Modular Code

- **PRODUCTION CODE**: software running on production servers to handle live users and data of the intended audience. Note this is different from production quality code, which describes code that meets expectations in reliability, efficiency, etc., for production. Ideally, all code in production meets these expectations, but this is not always the case.
- **CLEAN**: readable, simple, and concise. A characteristic of production quality code that is crucial for collaboration and maintainability in software development.
- **MODULAR**: logically broken up into functions and modules. Also an important characteristic of production quality code that makes your code more organized, efficient, and reusable.
- **MODULE**: a file. Modules allow code to be reused by encapsulating them into files that can be imported into other files.

<p align="center">
  <img width="460" height="300" src="https://user-images.githubusercontent.com/7588716/87248661-53d7e980-c478-11ea-8c9d-3e57ff6fcad5.png">
</p>

***

## Refactoring Code

**REFACTORING**: Restructuring your code to improve its internal structure, without changing its external functionality.

- This gives you a chance to clean and modularize your program after you've got it working.
- Since it isn't easy to write your best code while you're still trying to just get it working, allocating time to do this is essential to producing high quality code.
- Despite the initial time and effort required, this really pays off by speeding up your development time in the long run.
- You become a much stronger programmer when you're constantly looking to improve your code.
- The more you refactor, the easier it will be to structure and write good code the first time.

Example Notebook: [Refactor Wine Quality](Resources/refactor_wine_quality.ipynb)
***

## Writing Clean Code: Meaningful Names

Tip: Use meaningful names

- **Be descriptive and imply type**:
  - E.g. for booleans, you can prefix with ```is_``` or ```has_``` to make it clear it is a condition.
  - You can also use part of speech to imply types, like verbs for functions and nouns for variables.
  - Be consistent but clearly differentiate - E.g. ```age_list``` and ```age``` is easier to differentiate than ages and age.
  - Avoid abbreviations and especially single letters - (Exception: counters and common math variables) Choosing when these exceptions can be made can be determined based on the audience for your code.
  - If you work with other data scientists, certain variables may be common knowledge. While if you work with full stack engineers, it might be necessary to provide more descriptive names in these cases as well.
  - ```Long names != descriptive names``` - You should be descriptive, but only with relevant information.
    - E.g. good functions names describe what they do well without including details about implementation or highly specific uses.
  - Try testing how effective your names are by asking a fellow programmer to guess the purpose of a function or variable based on its name, without looking at your code. Coming up with meaningful names often requires effort to get right.

EXAMPLES WITH NORMAL & IMPROVED CODE:

***

Normal Code:

```python
s = [99, 78, 82, 56, 76] # student test scores
print(sum(s)/len(s)) # print mean of test scores
```

Improved Code:

```python
import numpy as np
test_scores = [99, 78, 82, 56, 76]
print(np.mean(test_scores))
```

***

Normal Code:

```python
def count_unique_values_of_names_list_with_set(names_list):
  return len(set(names_list))
```

Improved Code:

```python
def count_unique_values(arr):
  return len(set(arr))
```

***

## Writing Clean Code: Nice Whitespace

Tip: Use whitespace properly

- **Organize your code with consistent indentation**
  - the standard is to use 4 spaces for each indent. You can make this a default in your text editor.
  - Separate sections with blank lines to keep your code well organized and readable.
  - Try to limit your lines to around 79 characters, which is the guideline given in the [PEP 8 style guide](https://www.python.org/dev/peps/pep-0008/?#code-lay-out). In many good text editors, there is a setting to display a subtle line that indicates where the 79 character limit is.

***

## Writing Modular Code

- **DRY (Don't Repeat Yourself)**: Modularization allows you to reuse parts of your code. Generalize and consolidate repeated code in functions or loops.

- **Abstract out logic to improve readability**: Abstracting out code into a function not only makes it less repetitive, but also improves readability with descriptive function names. Although your code can become more readable when you abstract out logic into functions, it is possible to over-engineer this and have way too many modules, so use your judgement.
- **Minimize the number of entities (functions, classes, modules, etc.)**: There are tradeoffs to having function calls instead of inline logic. If you have broken up your code into an unnecessary amount of functions and modules, you'll have to jump around everywhere if you want to view the implementation details for something that may be too small to be worth it. Creating more modules doesn't necessarily result in effective modularization.
- **Functions should do one thing**: Each function you write should be focused on doing one thing. If a function is doing multiple things, it becomes more difficult to generalize and reuse. Generally, if there's an "and" in your function name, consider refactoring.
- **Arbitrary variable names can be more effective in certain functions**: Arbitrary variable names in general functions can actually make the code more readable.
- **Try to use fewer than three arguments per function**: Try to use no more than three arguments when possible. This is not a hard rule and there are times it is more appropriate to use many parameters. But in many cases, it's more effective to use fewer arguments. Remember we are modularizing to simplify our code and make it more efficient to work with. If your function has a lot of parameters, you may want to rethink how you are splitting this up.

***

## Efficient Code

Knowing how to write code that runs efficiently is another essential skill in software development. Optimizing code to be more efficient can mean making it:

- Execute faster
- Take up less space in memory/storage

The project you're working on would determine which of these is more important to optimize for your company or product. When we are performing lots of different transformations on large amounts of data, this can make orders of magnitudes of difference in performance.

Example Notebook: [Optimizing Common Books Code](Resources/optimizing_code_common_books.ipynb)

***

## Documentation

**DOCUMENTATION**: additional text or illustrated information that comes with or is embedded in the code of software.
Helpful for clarifying complex parts of code, making your code easier to navigate, and quickly conveying how and why different components of your program are used.

Several types of documentation can be added at different levels of your program:

- In-line Comments - line level

  ```python
  text = "Hello" # This is an inline comment
  ```

- Docstrings - module and function level
  - Docstring, or documentation strings, are valuable pieces of documentation that explain the functionality of any function or module in your code. Ideally, each of your functions should always have a docstring.

  - Docstrings are surrounded by triple quotes. The first line of the docstring is a brief explanation of the function's purpose.
  
  One line docstring

  ```python
  def get_full_name(first_name, last_name):
      """Returns full name of a user"""
      return "%s %s".format(first_name, last_name)
  ```

  Multi line docstring

  ```python
  def get_full_name(first_name, last_name):
    """Return full name of a user.

    Args:
    first_name: str. User first name
    last_name: str. User last name

    Returns:
    full_name: first_name + last_name. Full name of a user.

    """
    return "%s %s".format(first_name, last_name)
  ```

  Resources: [PEP 257 - Docstring Conventions](https://www.python.org/dev/peps/pep-0257/)

- Project Documentation - project level

  - Project documentation is essential for getting others to understand why and how your code is relevant to them, whether they are potentials users of your project or developers who may contribute to your code. A great first step in project documentation is your README file. It will often be the first interaction most users will have with your project.
  
  Resources: [Udacity course on this topic](https://classroom.udacity.com/courses/ud777) | [scikit-learn readme](https://github.com/scikit-learn/scikit-learn)

***

## Testing

- Testing your code is essential before deployment. It helps you catch errors and faulty conclusions before they make any major impact.
- To catch these errors, you have to check for the quality and accuracy of your analysis in addition to the quality of your code.
- Proper testing is necessary to avoid unexpected surprises and have confidence in your results.

  - **TEST DRIVEN DEVELOPMENT**: a development process where you write tests for tasks before you even write the code to implement those tasks.
  - **UNIT TEST**: a type of test that covers a “unit” of code, usually a single function, independently from the rest of the program.

  Resources: [Getting Started Testing - PyCon 2014](http://bit.ly/pytest0) | [TDD with PyTest](https://stackabuse.com/test-driven-development-with-pytest/) | [TTD with Python By Harry Percival](https://amzn.to/2ZnjHri)
