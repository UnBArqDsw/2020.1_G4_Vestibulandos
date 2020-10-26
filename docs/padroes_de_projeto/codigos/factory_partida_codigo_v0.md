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
}
```

- Treino
```
public class Treino : Partida
{

}
```

- Ranqueada
```
public class Ranqueada : Partida
{
    public int[] IdJogadores { get; set; }
    public int[] AcertoJogador { get; set; }
    public int[] ErroJogador { get; set; }
}
```