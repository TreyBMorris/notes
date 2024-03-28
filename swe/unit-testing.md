# Unit Testing and JUnit
[Back](./swe.md)

#### Jump to a Section
- [What is White Box Testing?](#what-is-white-box-testing)
- [What is Unit Testing?](#what-is-unit-testing)
- [What is JUnit?](#what-is-junit)
- [The AAA Pattern](#the-aaa-pattern)
- [Example 1](#example-1)


# What is White Box Testing?
White box testing, also commonly referred to as clear box testing, code-based testing, is a testing method in software where we directly look at the internal implementation of a software. To put it simply, white box testing is testing paths and methods within a system. Examples of white box testing include integration and system testing. Unit tests are also considered a white box testing method, and that is the main topic of this page.

# What is Unit Testing?
Unit testing is a part of software testing where individual parts of software are tested. This is so that we can assure that our code works the way that it should. A "unit" is a small testable part of software. In Object Oriented programming, a unit would be something like a method that belongs to a base class, or child class, like a module of a larger product. Unit tests are also performed by white box testing methods. 

# What is JUnit?
JUnit is a popular test framework for the Java language. JUnit is used for unit testing where we can write and execute tests for our code. For this article, we will be using JUnit for our example of unit testing.

# The AAA Pattern
Before we show an example of unit testing with JUnit, we need to cover a common testing pattern for unit testing. The pattern is described in three sections, Arrange, Act, and Assert, or AAA for short. 
- Arrange: Setting up the test objects and any other things we need to test.
- Act: This is where we will actually run the test
- Assert: Verifying our result, does the test return what we expect?


# Example 1
Below is an example of unit testing using JUnit. 
Here we have our class to test, that we will call "Calculator". For this example, we will test the two basic methods, add and subtract.
```Java
public class Calculator
{
    public static double add(double firstNumber, double secondNumber)
    {
        return firstNumber + secondNumber;
    }
    public static double subtract(double firstNumber, double secondNumber)
    {
        return firstNumber - secondNumber;
    }
}
```
Then, we will write our unit tests.
```Java
//Make sure that we import JUnit into our project.
import org.junit.jupiter.api.Test;

public class CalculatorTests
{
    @Test //We add this notation to our code to denote a method is a test method.
    //This is a good test naming convnetion where we list the class we are testing and what we expect the test to do.
    public void Calculator_AddTwoFloatingPoints_ReturnsSum() 
    {
        //Arrange
        Calculator calculator = new Calculator();
        double firstNumber = 3.0;
        double secondNumber = 2.5;
        double expectedResult = 5.5;

        //Act
        double actualResult = calculator.add(double firstNumber, double secondNumber);

        //Assert
        //This is comparing the expectedResult and the actualResult. If they are equal to each other, then the test will pass, otherwise the test will fail.
        assertEquals(expectedResult, actualResult);
    }
    //Test for subtracting two floating points.
    @Test
    public void Calculator_SubtractTwoFloatingPoints_ReturnsDifference() 
    {
        //Arrange
        Calculator calculator = new Calculator();
        double firstNumber = 3.0;
        double secondNumber = 2.5;
        double expectedResult = 0.5;

        //Act
        double actualResult = calculator.subtract(double firstNumber, double secondNumber);

        //Assert
        assertEquals(expectedResult, actualResult);
    }
}
```
