# OOMDHW4

Object-oriented Modeling & Design, Assignment IV.

*Gang of Four (GoF) design patterns etc.*

### Answers to the question (a)

##### Calculating GPA should not be done by `Student`.

From the behavioral aspect, *GPA* and *student* are different kinds.
A *student* does not have to have a *GPA*, at all.
For instance, a student might be enrolled to a course without a grading system.
Hence, the contract cannot be provided by all possible concrete implementations of an abstract *student* implementation containing abstract method(s) for calculating GPA.

The solution for the problem could be implementing a grading calculation strategy, which is contained by a `Student` object.
In overall, we prefer **composition** over **inheritance**, since the calculation of GPA should be seperated from the logic of `Student` class' itself.

##### If there is a GPA to be calculated, how to calculate it must be decided during creation of the `Student` object.

A factory class for creating `GpaStrategy` objects can be implemented.
The new factory class can implement a factory method with a year parameter to provide objects to various `Student`s.
The system is highly cohesive, since the responsibility of creating strategy objects is now at factory class.

##### Instead of implementing new class for each GPA calculation method, we could implement a parametric class which makes a general implementation.

The `Grade` object may contain score and weight properties to supply enough information to the GPA calculator algorithm.
Most of the time, GPAs will be calculated with a `Grade` object.
One could implement such class, who is responsible for calculating GPA, with parameters of minimum and maximum boundaries of the grading system.

For example, instead of having classes for each GPA calculation method, we could parameterize the function.

### Suggested UML class diagram

![UML Class Diagram]

[UML Class Diagram]: uml.png

### License

MIT
