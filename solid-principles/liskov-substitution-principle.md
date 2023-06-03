# Liskov Substitution Principle

> Types can be replaced by their subtypes without breaking application

The child class should be able to everything the parent class can do if cannot perform the same actions as it parent class, this can cause bugs.

Parent class deliver coffee, it is acceptable for the class to deliver cappuccino. Because it is specific type of Coffee but it is not acceptable to deliver water.

Enforced consistency so that the parent class or its child class can be used in the same way without any errors

The overridden method shouldn’t remain empty\
The overridden method shouldn’t throw an error\
Base class or interface behavior should not go for modification (rework) as because of derived class behaviors.\


{% code title="Bad Approach" %}
```csharp
    public class Plane
    {
        public virtual void StartEngine()
        {
        }
    }

    public class FighterJet : Plane
    {
    }

    public class PaperPlane : Plane
    {
        public override void StartEngine()
        {
            throw new InvalidOperationException("A Paper Plane doesn't have an engine.");
        }
    }
```
{% endcode %}



{% code title="Nice Approach" %}
```csharp
    public class Plane
    {
        public string Name { get; set; }
    }

    public class RealPlane
    {
        public void startEngine()
        {
        }
    }

    public class FighterJet : RealPlane
    {
    }

    public class PaperPlane : Plane
    {
    }
```
{% endcode %}

