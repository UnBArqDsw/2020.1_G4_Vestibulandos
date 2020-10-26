# Padrões GRASP's

## Histórico de Versões

|   Data   | Versão |           Descrição           |             Autor(es)              |
|:--------:|:------:|:-----------------------------:|:----------------------------------:|
| 26/10/2020 | 0.1 | Adicionado o documento | Ricardo Lima Canela |
| 26/10/2020 | 0.2 | Adicionado Criador | Ricardo Lima Canela e Julio Litwin |
| 26/10/2020 | 0.3 | Adicionado Especialista | Ricardo Lima Canela |
| 26/10/2020 | 0.4 | Adicionado Alta Coesão e Baixo Acoplamento | Ricardo Lima Canela |

### Introdução

Para explicar o que são os Padrões GRASPs vamos primeiro entender o que são Padrões de Projeto. No contexto de desenvolvimento de software, é comum nos depararmos com problemas que já foram enfrentados por outros programadores anteriormente e que geraram soluções validadas, funcionais e que se tornaram padrões para desenvolvimento.

Os Padrões GRASP's (General Responsibility Assignment Software Patterns) consistem em uma série de princípios, práticas e soluções baseados em conceitos para atribuição de responsabilidades a classes e objetos na construção de softwares usando programação orientada a objetos.

Para realizar a proposta dos Padrões GRASP's de correta atribuição de responsabilidades, foram divididos padrões que solucionam problemas e aumentam a qualidade e a manutenibilidade do código. A seguir será apresentado a explicação de cada um e a utilização no projeto Vestibulandos.

### Criador

Problema: Quem deve ser responsável por criar uma nova instância de uma classe?
Solução: Atribua à classe B a responsabilidade de criar uma instância de A se pelo menos um desses for verdadeiro (quanto mais melhor):
• B contém ou agrega A
• B registra a existência de A
• B usa A
• B tem os dados necessários para a inicialização de A que serão passados ao construtor de A

No projeto Vestibulando podemos destacar:

- Jogador(TODO) é responsável pela criação das Partidas(PARTES)  
- Partida(TODO) é responsável pela criação das Questões(PARTES)  
- Questão(TODO) é responsável pela criação das Alternativa(PARTES)  

#### Detalhamento do Padrão no nível de Modelagem

![ModelagemCriador](../img/diagramas/diagrama_grasp_criador.png)


#### Detalhamento do Padrão no nível de Implementação
ex: trecho de código correspondente

### Especialista

A diferença entre criador e especialista é que o especialista não só é o melhor para criar a instância do objeto da outra classe como também é o melhor em desempenhar uma função específica do sistema (Quem é a melhor entidade para calcular algo? Quem é a melhor entidade para ordenar algo? Quem é a melhor entidade para cadastrar algo?)

Por isso, A relação das entidades Partida, Questão e Alternativa é dada como especialistas pois cada uma desempenha uma função específica no sistema. Partida é especialista em gerenciar os dados de pontuação. Questão gerencia as informações relacionadas a pergunta a ser respondida. Alternativa da a descrição de cada alternativa. Cada um tem sua responsabilidade. Seria possível porém menos elegante se partida gerenciasse sozinha as questões e as alternativas.


#### Detalhamento do Padrão no nível de Modelagem

![ModelagemEspecialista](../img/diagramas/diagrama_grasp_especialista.png)

#### Detalhamento do Padrão no nível de Implementação
ex: trecho de código correspondente

### Alta Coesão

Alta coesão é atribuir de forma coerente as responsabilidades da classe. Existe uma alta coesão para as classes Partida, Questão e Alternativa já que cada uma tem sua responsabilidade bem definida conforme evidenciado na explicação do GRASP Especialista, que ao ser implementado garantiu ao sistema uma alta coesão nas classes citadas. Nesse caso, os GRASPs Especialista e Alta Coesão foram satisfeitos ao declarar responsabilidades específicas para cada uma das classes citadas (Partida, Questão e Alternativa).

O detalhamento a nível de Modelagem e de Implementação são os mesmos do Padrão Especialista

### Baixo Acoplamento

O Baixo Acoplamento se dá quando uma classe está coesa e possui baixa conexão ou dependência com outras classes. Um caso de alto acoplamento seria fazer com que Partida tivesse que interagir com Questão e Alternativa. Para manter um baixo acoplamento, Partida conversa apenas com Questão, que por sua vez conversa com Alternativa. Baixo Acoplamento anda de mãos dadas com Alta Coesão.

O detalhamento a nível de Modelagem e de Implementação são os mesmos do Padrão Especialista

### Polimorfismo

#### Detalhamento do Padrão no nível de Modelagem
ex: modelo de classes correspondente
#### Detalhamento do Padrão no nível de Implementação
ex: trecho de código correspondente
#### Rastreamento
rastro para código
rastro para as decisões da equipe
rastros para outros artefatos

#### Reflexões acerca do Padrão
justificativas, prós e contras, pertinência e outras reflexões

### Controlador

#### Detalhamento do Padrão no nível de Modelagem
ex: modelo de classes correspondente
#### Detalhamento do Padrão no nível de Implementação
ex: trecho de código correspondente
#### Rastreamento
rastro para código
rastro para as decisões da equipe
rastros para outros artefatos

#### Reflexões acerca do Padrão
justificativas, prós e contras, pertinência e outras reflexões

### Fabricação ou Invenção Pura

#### Detalhamento do Padrão no nível de Modelagem
ex: modelo de classes correspondente
#### Detalhamento do Padrão no nível de Implementação
ex: trecho de código correspondente
#### Rastreamento
rastro para código
rastro para as decisões da equipe
rastros para outros artefatos

#### Reflexões acerca do Padrão
justificativas, prós e contras, pertinência e outras reflexões

### Referências

