- IPartidaFactory
```
public interface IPartidaFactory
{

}
```

- PartidaFactory
```
public class PartidaFactory
{
    public IPartidaFactory GetPartida(TipoPartidaCode tipoPartidaCode)
    {
        switch (tipoPartidaCode)
        {
            case TipoPartidaCode.Treino: return new Treino();
            case TipoPartidaCode.Ranqueada: return new Ranqueada();
            default:throw new ArgumentOutOfRangeException();
        }
    }
        
}
```

- Partida
```
public class Partida : IPartidaFactory
{
    public int Id { get; set; }
    public TipoPartida TipoPartida { get; set; }
    public DateTime DataCriado { get; set; }
    public DateTime DataFinalizado { get; set; }
    public int Dificuldade { get; set; }
    public AreaConhecimento AreaConhecimento { get; set; }
    public int QuantidadeQuestao { get; set; }
    public bool Revisao { get; set; }

    private Dictionary<int, Jogador> _jogadores = new Dictionary<int, Jogador>();

}
```

- Treino
```
public class Treino : Partida
{
    public int Acerto { get; set; }
    public int Erro { get; set; }

    public void AtualizarAcerto(){ }

    public void AtualizarErro(){ }

}
```

- Ranqueada
```
public class Ranqueada : Partida
{
    public int[] IdJogadores { get; set; }
    public int[] AcertoJogador { get; set; }
    public int[] ErroJogador { get; set; }

    public bool InserirJogadores(int[] idJogadores)
    {
        return true;
    }

    public bool AtualizarAcerto(int[] idJogadores)
    {
        return true;
    }

    public bool AtualizarErro(int[] idJogadores)
    {
        return true;
    }

}
```