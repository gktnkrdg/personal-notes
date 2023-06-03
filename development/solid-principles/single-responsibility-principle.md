# Single Responsibility Principle

### Single Responsibility Principle (SRP)

> A class should only one reason to change

If a class has many responsibility it increase the possibility of bug. Because making changes to one of its responsibility could affect the other ones without you know

Code being broken apart with each class (small pieces) having a single purpose makes code easier to maintain.

Unit testing code suddenly becomes easier when a class is trying to only one do one thing.

Gather together the things that change for the same reason, separate those thing that change for different reason



{% code title="Bad Approach" %}
```csharp
public class BadApproach
{
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
}
```
{% endcode %}



<pre class="language-csharp" data-title="Nice Approach"><code class="lang-csharp"><strong> public class PostService
</strong>    {
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
</code></pre>
