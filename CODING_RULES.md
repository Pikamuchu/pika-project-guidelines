
# Coding Rules

## Follow the Style Guide
* The code style check must be included in the build process. The project readme must explain how to run these checks.

    _why_
    > Every programming language has a style guide that tells you in great detail how to indent your code, where to put spaces and braces, how to name stuff, how to comment—all the good and bad practices.


## Choose meaningful names
* Use long descriptive names. Think long and hard before you name something.
* Names have to reflect what a variable, field, property stands for.
* Names must describe side effects. 
* The only exceptions to this rule are:
    * local variables.
    * loop index.
* Naming conventions:
    * Class and variable names should be nouns. 
    * Methods names should contain a verb. The name must describe what the method does.

    _why_
    > To help yourself, now and in the future, as well as your colleagues to understand what the code does. 

## Class design rules 
* **Single Responsibility Principle (SRP)**: A class should have one, and only one, reason to change.
* **Open Closed Principle (OCP)**: You should be able to extend a classes behaviour without modifying it.
* **Liskov Substitution Principle (LSP)**: Derived classes must be substitutable for their base classes.
* **Interface Segregation Principle (ISP)**: Make fine grained interfaces that are client-specific.
* **Dependency Inversion Principle (DIP)**: Depend on abstractions, not on concretions.
* Classes should be Small
* Classes should either do stuff (algorithm, read data, write data, …) or orchestrate other classes.

    _why_
    >


## Method design rules
* Methods should do one thing.

    _why_
    > 

* Try to keep the methods pure (functional programming). 

    _why_
    > Pure functions are easy to test. It's a way to minimize bugs and side effects.

* Avoid Method with Too Many Arguments.

    _why_
    > I's cleaner to use as parameter a dedicated class that holds the information in fields.

* Avoid methods with Flag Arguments.

    _why_
    > It's cleaner to split method into several independent methods that can be called from the client without the flag.


* **Don't Repeat Yourself (DRY)**: 
    * Never copy-and-paste code. 
    * Abstract the common parts into another method, and use it with appropriate parameters.

    _why_
    > 


* **Law of Demeter**: The method of the given object may refer to:
    * the same object.
    * any parameter passed to this method.
    * any object created by this method.

    _why_
    > Following this rules may reduce the coupling. This way, changes in the structure of the given object do not invoke the need to introduce any changes in the client that uses this object.


## Check for Errors and Respond to Them
* Check nullpointers.
* Try catch exceptions when the error can be properly handled.

    _why_
    > Yes, good error-handling is hard to write, and it makes the code longer and less readable. But ignoring errors and exceptions simply sweeps the problem under the carpet, where an unsuspecting end user will inevitably find it one day.


## Keep it Simple, Stupid (KISS)
* Simpler is always better. Reduce complexity as much as possible.

    _why_
    >

## Boy Scout Rule 
* Leave the campground cleaner than you found it

    _why_
    >

## Comment your code
* Try to make comments as clear as possible what you are intending with each major section.
* Start every routine you write (function or method) with a comment outlining what the routine does, its parameters, and what it returns, as well as possible errors and exceptions.
* Summarize in a comment the role of each file and class, the contents of each class field, and the major steps of complex code. 
* Write the comments as you develop the code
* Don't use comments as an excuse for a bad code. Keep your code clean.
* Don't use clean code as an excuse to not comment at all.
* Always comment and keep them relevant as code changes. Remove commented blocks of code.

    _why_
    > 