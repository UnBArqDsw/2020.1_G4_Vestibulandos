# GOF's Criacionais

## Histórico de Versões

|   Data   | Versão |           Descrição           |             Autor(es)              |
|:--------:|:------:|:-----------------------------:|:----------------------------------:|
| 24/10/2020 | 0.1 | Adicionado o documento | Julio Litwin |
| 25/10/2020 | 0.2 | Adicionado Factory Method de Partida | Lucas Gomes, Julio Litwin |
| 25/10/2020 | 0.3 | Correção da seta de Treino e Raqueada no diagrama | Lucas Gomes |
| 25/10/2020 | 0.4 | Adicionado Factory Method de Usuário | Lucas Gomes, Julio Litwin |
| 26/10/2020 | 0.5 | Adicionado Singleton | Julio Litwin |
| 26/10/2020 | 0.6 | Refatorando documento | João Pedro |

## Introdução

Padrões de Criação se preocupam com a maneira como os objetos são criados. Eles reduzem as complexidades e a instabilidade criando objetos de maneira controlada.

O novo operador é frequentemente considerado prejudicial, pois espalha objetos por todo o aplicativo. Com o tempo, pode se tornar um desafio alterar uma implementação porque as classes se tornam fortemente acopladas.

Os Padrões de Criação tratam desse problema separando inteiramente o cliente do processo de inicialização real.

Fazendo um paralelo com o mundo real, uma empresa automobilística quando precisa de amortecedores, ela terceiriza (solicita-os) e então os instala em seus carros, sem se preocupar com o todo envolvido na criação desse componente.

## Factory Method
É um padrão criacional que permite a superclasse "adiar" a criação de objetos para suas subclasses, assim dando a possibilidade das subclasses alterarem o tipo de objeto a ser criado. Isso é feito instanciando um objeto da superclasse e chamando o método que retorna um objeto de determinada classe solicitada no parâmetro do método. 

Foi utilizado esse método pela facilidade de criação de novas subclasses sem quebrar o código já em produção além de facilitar a manutenção do código já que cada classe tem responsabilidades únicas.

**Problema:** Acoplamento forte em classes com código de criação de instância além da lógica de negócio própria.

**Solução:** Adicionar uma interface para a criação de grupos de objetos correlatos/dependentes, uma forma de desenvolver objetos que são responsáveis pela criação de outros objetos.


### Factory method para Partida
#### Diagrama representando o padrão no projeto
- Versão 0

![FactoryPartidaDiagrama](../img/diagramas/factory_method_partida_v0.png)

> [Implementação em código - Versão 0](./codigos/factory_partida_codigo_v0.md)

#### Links para o código implementado
- [IPartidaFactory](https://github.com/UnBArqDsw/2020.1_G4_Vestibulandos_Backend/blob/master/GameServer/Interfaces/IPartidaFactory.cs)
- [PartidaFactory](https://github.com/UnBArqDsw/2020.1_G4_Vestibulandos_Backend/blob/master/GameServer/Patterns/PartidaFactory.cs)
- [Partida](https://github.com/UnBArqDsw/2020.1_G4_Vestibulandos_Backend/blob/master/GameServer/Entities/Partida.cs)
- [Treino](https://github.com/UnBArqDsw/2020.1_G4_Vestibulandos_Backend/blob/master/GameServer/Entities/Treino.cs)
- [Ranqueada](https://github.com/UnBArqDsw/2020.1_G4_Vestibulandos_Backend/blob/master/GameServer/Entities/Ranqueada.cs)


### Factory method para Usuário
#### Diagrama representando o padrão no projeto
- Versão 0

![FactoryPartidaDiagrama](../img/diagramas/factory_method_usuario_v0.png)

> [Implementação em código - Versão 0](./codigos/factory_usuario_codigo_v0.md)

#### Links para o código implementado
- [IUsuarioFactory](https://github.com/UnBArqDsw/2020.1_G4_Vestibulandos_Backend/blob/master/GameServer/Interfaces/IUsuarioFactory.cs)
- [UsuarioFactory](https://github.com/UnBArqDsw/2020.1_G4_Vestibulandos_Backend/blob/master/GameServer/Patterns/UsuarioFactory.cs)
- [Usuario](https://github.com/UnBArqDsw/2020.1_G4_Vestibulandos_Backend/blob/master/GameServer/Entities/Usuario.cs)
- [Jogador](https://github.com/UnBArqDsw/2020.1_G4_Vestibulandos_Backend/blob/master/GameServer/Entities/Jogador.cs)
- [Monitor](https://github.com/UnBArqDsw/2020.1_G4_Vestibulandos_Backend/blob/master/GameServer/Entities/Monitor.cs)
- [Administrador](https://github.com/UnBArqDsw/2020.1_G4_Vestibulandos_Backend/blob/master/GameServer/Entities/Administrador.cs)

## Singleton

O Singleton é um padrão de projeto criacional que permite a você garantir que uma classe tenha apenas uma instância, enquanto provê um ponto de acesso global para essa instância.

### Prós 
- Você pode ter certeza de que uma classe possui apenas uma única instância.
- Você ganha um ponto de acesso global para essa instância.
- O objeto singleton é inicializado apenas quando é solicitado pela primeira vez.

### Contras
- Viola o princípio da responsabilidade única. O padrão resolve dois problemas no momento.
- O padrão Singleton pode mascarar um projeto ruim, por exemplo, quando os componentes do programa sabem muito sobre os outros.
- O padrão requer tratamento especial em um ambiente multithread para que vários threads não criem um objeto singleton várias vezes.

### Aplicabilidade
Mesmo o Singleton sendo um padrão com mais contras do que pós, ainda é visível de o quanto ainda é usado ainda no mundo real. No Vestibulandos, será utilizado no back e no front, com todos os cuidados possíveis, principalmente com Threads, para não haver violações, tais como deadlocks. Entretando, os singletons são utilizados mais em classes internas, tais como estruturas: 

- NetworkManager(back/front)
- AudioManager(front)
- GameManager(back/front)
- ResourceManager(front)

Dentro do projeto, principalmente no Front, foi adicionado uma classe para auxiliar na criação rápida de Singleton, em seguida, é possível verificar o código.

### Código

```
public class Singleton<T> where T : new()
{
    private static T s_instance;

    public static T GetInstance()
    {
        if (s_instance == null) 
            s_instance = new T();

        return s_instance;
    }

    public static void Destroy()
    {
        s_instance = default;
    }

    public static bool IsCreated()
    {
        return (s_instance != null);
    }
}
```

#### Links para o código implementado
- [Singleton](https://github.com/UnBArqDsw/2020.1_G4_Vestibulandos_Frontend/blob/master/Vestibulandos/Assets/Scripts/Utils/Singletons/Singleton.cs)
- [MonoSingleton](https://github.com/UnBArqDsw/2020.1_G4_Vestibulandos_Frontend/blob/master/Vestibulandos/Assets/Scripts/Utils/Singletons/MonoSingleton.cs)

### Exemplo de Uso
Como exemplo, iremos utilizar um trecho de código do NetworkManager.

```
public class NetworkingManager
{
        /// <summary>
        /// Singleton.
        /// </summary>
        public static NetworkingManager Instance => Singleton<NetworkingManager>.GetInstance();
}
```

Para o acesso do Singleton, basta apenas chamar como:

```
NetworkingManager.Instance.*
```

O *** (asterisco)** é referente a qualquer acesso, tais como funções, variaveis e dentre outros.

Caso **Instance**, seja chamada pela a primeira vez, a classe será inicializada e criada, depois definida como a instância principal a ser utilizada.

## Referências

- **Baeldung**, Introduction to Creational Design Patterns. Disponível em: <https://www.baeldung.com/creational-design-patterns>. Acesso em: 24 de Outubro 2020.

- **REFACTORING . GURU**, reational Design Patterns. Disponível em: <https://refactoring.guru/design-patterns/creational-patterns>. Acesso em: 24 de Outubro 2020.

- **TreinaWeb**, Padrões de projeto: o que são e o que resolvem. Disponível em: <https://www.treinaweb.com.br/blog/padroes-de-projeto-o-que-sao-e-o-que-resolvem/>. Acesso em: 24 de Outubro 2020.

- **Wikipedia**, Padrão de projeto de software. Disponível em: <https://pt.wikipedia.org/wiki/Padr%C3%A3o_de_projeto_de_software>. Acesso em: 24 de Outubro 2020.

- Material complementar da disciplina Arquitetura e Desenho de Software. VideoAula 08a - Vídeo-Aula - DSW - GoFs - Criacionais. Professora Milene Serrano. Universidade de Brasília.