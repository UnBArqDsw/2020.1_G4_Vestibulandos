- IQuestaoSubject
```
public interface IQuestaoSubject
{
    void Attach(IMonitorObserver observer);
    void Detach(IMonitorObserver observer);
    void Notify();
}
```

- Questao
```
public class Questao : IQuestaoSubject
{
    private List<IMonitorObserver> _monitorObservers = new List<IMonitorObserver>();

    public void Attach(IMonitorObserver observer)
    {
        Console.WriteLine("Subject: Attached an observer.");
        _monitorObservers.Add(observer);
    }

    public void Detach(IMonitorObserver observer)
    {
        _monitorObservers.Remove(observer);
        Console.WriteLine("Subject: Detached an observer.");
    }

    public void Notify()
    {
        Console.WriteLine("Subject: Notifying observers...");

        foreach (var observer in _monitorObservers)
        {
            observer.Update(this);
        }
    }
    public void SomeBusinessLogic()
    {
        Console.WriteLine("\nSubject: I'm doing something important.");

        Console.WriteLine("Subject: My state has just changed to: " + new Random().Next(0, 10));
        Notify();
    }
}
```

- IMonitorObserver
```
public interface IMonitorObserver
{
    void Update(IQuestaoSubject subject);
}
```

- Monitor
```
public class Monitor : Usuario, IMonitorObserver
{
    public Monitor(string login, string senha, string email, int tipoUsuario) : base(login, senha, email, tipoUsuario)
    {

    }
    
    public void Update(IQuestaoSubject subject)
    {
        Console.WriteLine("Monitor: Reacted to the event.");
    }
}
```