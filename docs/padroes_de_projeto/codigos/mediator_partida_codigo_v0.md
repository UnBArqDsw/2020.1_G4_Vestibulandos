- IPartidaMediator
```
public interface IPartidaMediator
{
    void RegistrarJogador(Jogador jogador);

    void Notify();
}
```

- Partida
```
public abstract class Partida : IPartidaMediator, IPartidaFactory
{
    private Dictionary<int, Jogador> _jogadores = new Dictionary<int, Jogador>();

    public void RegistrarJogador(Jogador jogador)
    {
        Console.WriteLine("Partida: player registered.");
        if (!_jogadores.ContainsValue(jogador))
        {
            _jogadores[jogador.Id] = jogador;
        }

        jogador.Partida = this;
    }

    public void Notify()
    {
        Console.WriteLine("Mediator: Notifying all players...");

        foreach (var id in _jogadores.Keys)
        {
            _jogadores[id].ReactNotify();
        }
    }

}
```

- IJogador
```
public interface IJogador
{
    bool Ação(int id);
    void ReactNotify();
}
```

- Jogador
```
public class Jogador : Usuario, IJogador
{
    public string Apelido { get; set; }
    public int Nivel { get; set; } = 0;
    public int Experiencia { get; set; } = 0;
    public int Vitoria { get; set; } = 0;
    public int Derrota { get; set; } = 0;
    public int AcertoQuestao { get; set; } = 0;
    public int ErroQuestao { get; set; } = 0;
    public IPartidaMediator Partida { get; set; }

    public Jogador(string login, string senha, string email, string apelido, int tipoUsuario) : base(login, senha, email, tipoUsuario)
    {
        Apelido = apelido;
    }

    public void ReactNotify()
    {
        Console.WriteLine($"Player {Id}: Reacted to the event.");
    }

    public bool Ação(int id)
    {
        Console.WriteLine($"Ação do jogador {id}");
        Partida.Notify();

        return true;
    }

}
```