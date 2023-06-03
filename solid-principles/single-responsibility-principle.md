# Single Responsibility Principle

> #### A class should only one reason to change

If a class has many responsibility it increase the possibility of bug. Because making changes to one of its responsibility could affect the other ones without you know

Code being broken apart with each class (small pieces) having a single purpose makes code easier to maintain.

Unit testing code suddenly becomes easier when a class is trying to only one do one thing.

Gather together the things that change for the same reason, separate those thing that change for different reason

{% code title="Bad Approach" lineNumbers="true" %}
```csharp
    public class EmailService
    {
        public void SendEmail(string email, string message)
        {
            if (!email.Contains("@") || !email.Contains("."))
            {
                throw new Exception("Email is not valid!!");
            }

            //client.Send(new MailMessage("test@email.com", email) { Subject = "Test!" });
        }
    }
```
{% endcode %}

{% code title="Nice Approach" lineNumbers="true" %}
```csharp
    public class EmailService
    {
        public void SendEmail(string email, string message)
        {
            ValidateEmail(email);
            //client.Send(new MailMessage("test@email.com", email) { Subject = "Test!" });
        }
        
        public void ValidateEmail(string email)
        {
            if (!email.Contains("@") || !email.Contains("."))
            {
                throw new Exception("Email is not valid!!");
            }
        }
    }   
```
{% endcode %}
