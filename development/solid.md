---
cover: >-
  https://images.unsplash.com/photo-1519389950473-47ba0277781c?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=2970&q=80
coverY: 0
---

# SOLID

### Single Responsibility Principle (SRP)

> A class should only one reason to change

If a class has many responsibility it increase the possibility of bug. Because making changes to one of its responsibility could affect the other ones without you know

Code being broken apart with each class (small pieces) having a single purpose makes code easier to maintain.

Unit testing code suddenly becomes easier when a class is trying to only one do one thing.

Gather together the things that change for the same reason, separate those thing that change for different reason

### Open Closed Principle (OCP)

> You should be able to extend a classes behavior, without modifying it

> Software entities(classes, modules,functions) should be open for extension, but changed for modification\*

Can I extend this code and add more functionality without modify the original code in any way

### Liskov Substitution Principle (LSP)

> Types can be replaced by their subtypes without breaking application

The child class should be able to everything the parent class can do if cannot perform the same actions as it parent class, this can cause bugs.

Parent class deliver coffee, it is acceptable for the class to deliver cappuccino. Because it is specific type of Coffee but it is not acceptable to deliver water.

Enforced consistency so that the parent class or its child class can be used in the same way without any errors

The overridden method shouldn’t remain empty\
The overridden method shouldn’t throw an error\
Base class or interface behavior should not go for modification (rework) as because of derived class behaviors.\\

### Interface Segregation Principle(ISP)

> Clients shouldn't be forced to depend on methods that they dont use\*

Keep interfaces focused. Use multiple interfaces which does not force clients implement they dont used

Use multiple interfaces that don't force clients to implement what they're not used

### Dependency Inversible Principle (DIP)

> High level modules shouldn't depend on low level module. Both should depend on abstraction\*

> Abstractions shouldn't depend on details. Details should depend on abstractions\*

We call repository but we are not interested in how that get Power socket plug doesn't care which type of wire it, just needs that to forward electricity.

Constructor injection Property injection -> (optional dependency) Method injection-> CalculateFee(Guid userId,IContext context)
