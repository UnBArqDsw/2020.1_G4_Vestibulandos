- IUsuarioFactory
```
public interface IUsuarioFactory
{

}
```

- UsuarioFactory
```
public class UsuarioFactory
{
    public IUsuarioFactory GetUsuario(TipoUsuarioCode tipoUsuarioCode)
    {
        switch (tipoUsuarioCode)
        {
            case TipoUsuarioCode.Jogador: return new Jogador("login", "senha", "email", "apelido", 1);
            case TipoUsuarioCode.Monitor: return new Monitor("login", "senha", "email", 1);
            case TipoUsuarioCode.Administrador: return new Administrador("login", "senha", "email", 1);
            default: throw new ArgumentOutOfRangeException();
        }
    }
}
```

- Usuario
```
public class Usuario : IUsuarioFactory
{
    public int Id { get; set; }
    public int TipoUsuario { get; set; }
    public string Login { get; set; }
    public string Senha { get; set; }
    public string Email { get; set; }

    public Usuario(string login, string senha, string email, int tipoUsuario)
    {
        Login = login;
        Senha = senha;
        Email = email;
        TipoUsuario = tipoUsuario;
    }
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
}
```

- Monitor
```
public class Monitor : Usuario
{
    public Monitor(string login, string senha, string email, int tipoUsuario) : base(login, senha, email, tipoUsuario)
    {

    }
}
```

- Administrador
```
public class Administrador : Monitor
{
    public Administrador(string login, string senha, string email, int tipoUsuario) : base(login, senha, email, tipoUsuario)
    {

    }
}
```