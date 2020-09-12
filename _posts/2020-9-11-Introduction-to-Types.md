---
layout: post
tags: notes
title: Introduction to Types (Reading)
---

- High quality software is *correct, comprehensible and changeable*.

- **Type:** A way to describe a data item precisely
  1. **Set of values** that the item can take
  2. **Operations** that are permitted on the item

- **Primitive type:**  Form of data that the language directly supports, can be used to tell hardware about operations on the data
  - e.g. `int` in C

- `int` in Java: 4 byte of memory, range of [-2<sup>31</sup>, 2<sup>31</sup> - 1]

### In C
- Can use `struct` to group integers
````C
struct Date { // declaring a struct with tag Date
      int dd;
      int mm;
      int yyyy;
}
// declare variables of type Date
struct Date startDate;
// setting day of month to 1st
startDate.dd = 1;
````
- However, C does not provide ability to clearly define valid operations on user-defined types

### In Java
- Can group both values (declarations) and operations (methods) together using `class`
````Java
public class Date { // in file Data.java
      private int dd;
      ...

      // constructor: initializes an object
      public Date(int d, int m, int y) {
          dd = d;
          ...
      }

      // methods
      public int getMonth() { ... }
      public Date getNextDate() { ... }
}
````
- A `Date` object can be called created or **constructed** using the operation `Date date = new Date(d, m, y)`

  - Compiler will use the constructor from `Date` class to create the object

  - `.` allows us to interact with objects with operations

- `Date` is a **class**, instances of `Date` are **objects**
````Java
// In Java, all functions have to be in a class
public class Main {
    // always need this!
    public static void main(String[] args) {

        // define a reference to a Date object
        Date jan_1_2018;

        // create a Date using constructor and keyword "new"
        jan_1_2018 = new Date(1, 1, 2018);

        // using methods
        Date jan_2_2018 = jan_1_2018.nextDate();
    }
}
````

### Realizing Types in Programming Languages
- **User-defined types** allow us to better express intention

  - Rely on primitive types or other user-defined types to represent its valid values

  - Only defined operations for that type can interact with values of the type

- `private`: restrict access to internal representation of a type

  - i.e. Only the methods in the `Date` class can directly access it


- *Developer* develops a type
  - Provides a meaningful type with useful operations
  - Understands how the type is represented internally

- *User* uses the type to build more sophisticated things
  - Only interested in manipulating values of types with operations
  - Does not care how types are internally represented



- **Defensive programming**: Developers should  prevent accidental or malicious modifications to internal representations of a type!
  - e.g. `private` as a modifier is such a mechanism


### Type Safety
- Why do types help us write better software?
  - **Type safety**: a language's support for *detecting type errors*



- **Static analysis**: analysis performed during compilation (or before program is executed)
  - Languages with *stronger static analyses = stronger correctness*


- **Dynamic analysis**: runtime analysis

- Java is strongly typed (very safe!): can detect problems from type mismatch

  - Supports user-defined type + Strong type checking
