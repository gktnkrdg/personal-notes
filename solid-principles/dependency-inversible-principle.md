# Dependency Inversion Principle

test 

> High level modules shouldn't depend on low level module. Both should depend on abstraction\*

> Abstractions shouldn't depend on details. Details should depend on abstractions\*

We call repository but we are not interested in how that get Power socket plug doesn't care which type of wire it, just needs that to forward electricity.

Constructor injection Property injection -> (optional dependency) Method injection-> CalculateFee(Guid userId,IContext context)

{% code title="Bad Approach" %}
```csharp
    public class PostService
    {
        private FileLogger logger = new FileLogger();

        void CreatePost(string postMessage)
        {
            try
            {
                // create post
            }
            catch (Exception ex)
            {
                logger.Log(ex.ToString());
            }
        }
    }

    public class FileLogger
    {
        public bool Log(string message)
        {
            //send log 
            return true;
        }
    }
```
{% endcode %}



{% code title="Nice Approach" %}
```csharp
    public class PostService
    {
        private ILogger _logger;

        public PostService(ILogger logger)
        {
            _logger = logger;
        }

        public void CreatePost(string postMessage)
        {
            try
            {
                //create post
            }
            catch (Exception ex)
            {
                _logger.Log(ex.ToString());
            }
        }
    }

    public interface ILogger
    {
        bool Log(string message);
    }

    public class FileLogger : ILogger
    {
        public bool Log(string message)
        {
            return true;
        }
    }
```
{% endcode %}
