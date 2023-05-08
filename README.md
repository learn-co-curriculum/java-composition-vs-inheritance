# Composition vs. Inheritance

## Learning Goals

- Explain the difference between composition and inheritance

## Introduction

Composition and inheritance represent two types of relationships
between classes. Composition and inheritance both promote code reuse,
but in different ways.

## When to use Composition and Inheritance

**Composition** is when a class has references to other classes as members.
We can think of composition as having a "has-a" relationship:

- A library has a book.
- A house has a kitchen.
- A car has a steering wheel

Consider the following example:

```java
public class SteeringWheel {
    private double radius;
    private boolean heated;
    ...
}

public class Engine {
    private String type;
    private int cylinders;
    ...
}

public class Car {
    private SteeringWheel steeringWheel;
    private Engine engine;
    ...
}
```

This is a very simplified example, but it shows that we know
a car has a steering wheel, an engine, and possibly other parts.
We can represent this in code
by defining a `Car` class to have fields referencing a
`SteeringWheel` and an `Engine` object.

Composition differs from inheritance since inheritance is
associated with an "is-a" relationship:

- A cat is an animal.
- Football is a sport.
- A car is a vehicle.

```java
public class Sport {
    ...
}

public class Football extends Sport {
    ...
}
```

We've seen with polymorphism that inheritance promotes substitutability.
Since `Football` inherits from `Sport`, a `Football` object can be used
anywhere a `Sport` object is expected since football "is-a" sport.

When deciding on whether to use composition or inheritance, it is important to
remember the "is-a" versus "has-a" relationships as they serve different
purposes.

Why don't we just have `Car` inherit from `SteeringWheel` rather than using composition?
Because a car is not a type of steering wheel, a car "has-a" steering wheel as a part.

Why don't we just have `Football` use composition to contain a `Sport` object?  Because
football "is-a" type of sport, and we can use an instance of `Football` anywhere
a `Sport` object is needed.
