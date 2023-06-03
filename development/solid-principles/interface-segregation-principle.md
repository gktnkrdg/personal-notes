# Interface Segregation Principle

### Interface Segregation Principle(ISP)

> Clients shouldn't be forced to depend on methods that they dont use\*

Keep interfaces focused. Use multiple interfaces which does not force clients implement they dont used

Use multiple interfaces that don't force clients to implement what they're not used


{% code title="Bad Approach" %}
```csharp
    public interface IPersonalComputer
    {
        void TurnOn();
        void TurnOff();
        void UnPlugBattery();
    }

    public class LaptopPC : IPersonalComputer
    {
        public void TurnOn()
        {
            // Logic to turn on
        }

        public void TurnOff()
        {
            // Logic to turn off
        }

        public void UnPlugBattery()
        {
            // Logic to turn off
        }
    }
    
    public class DesktopPC : IPersonalComputer
    {
        public void TurnOn()
        {
            // Logic to turn on
        }

        public void TurnOff()
        {
            // Logic to turn off
        }

        public void UnPlugBattery()
        {
            throw new NotImplementedException();
        }
    }
```
{% endcode %}



{% code title="Nice Approach" %}
```csharp
    public interface IPersonalComputer
    {
        void TurnOn();
        void TurnOff();
    }
    
    public interface IBattery
    {
        void UnPlugBattery();
    }
    
    public class LaptopPC : IPersonalComputer,IBattery
    {
        public void TurnOn()
        {
            // Logic to turn on
        }

        public void TurnOff()
        {
            // Logic to turn off
        }

        public void UnPlugBattery()
        {
            // Logic to turn off
        }
    }
    
    public class DesktopPC : IPersonalComputer
    {
        public void TurnOn()
        {
            // Logic to turn on
        }

        public void TurnOff()
        {
            // Logic to turn off
        }
    }
    ```
{% endcode %}