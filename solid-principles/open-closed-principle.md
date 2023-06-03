# Open Closed Principle

> #### You should be able to extend a classes behavior, without modifying it

> #### Software entities(classes, modules,functions) should be open for extension, but changed for modification\*

Can I extend this code and add more functionality without modify the original code in any way.

{% code title="Bad Approach" lineNumbers="true" %}
```csharp
    public class Rectangle
    {
        public double Width { get; set; }
        public double Height { get; set; }
    }
    
    public class Circle
    {
        public double Radius { get; set; }
    }
    
    public class CombinedAreaCalculator
    {
        public double Area(object[] shapes)
        {
            double area = 0;
            foreach (var shape in shapes)
            {
                if (shape is Rectangle)
                {
                    Rectangle rectangle = (Rectangle)shape;
                    area += rectangle.Width * rectangle.Height;
                }
                
                if (shape is Circle)
                {
                    Circle circle = (Circle)shape;
                    area += (circle.Radius * circle.Radius) * Math.PI;
                }
            }
            return area;
        }
    }
```
{% endcode %}

{% code title="Nice Approach" lineNumbers="true" %}
```csharp
    public abstract class Shape
    {
        public abstract double Area();
    }

    public class Rectangle : Shape
    {
        public double Width { get; set; }
        public double Height { get; set; }

        public override double Area()
        {
            return Width * Height;
        }
    }

    public class Circle : Shape
    {
        public double Radius { get; set; }

        public override double Area()
        {
            return Radius * Radius * Math.PI;
        }
    }

    public class CombinedAreaCalculator
    {
        public double Area(Shape[] shapes)
        {
            double area = 0;
            foreach (var shape in shapes)
            {
                area += shape.Area();
            }

            return area;
        }
    }
```
{% endcode %}
