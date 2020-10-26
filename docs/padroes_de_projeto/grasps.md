# Padrões GRASP's

## Histórico de Versões

|   Data   | Versão |           Descrição           |             Autor(es)              |
|:--------:|:------:|:-----------------------------:|:----------------------------------:|
| 26/10/2020 | 0.1 | Adicionado o documento | Ricardo Lima Canela |


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
• B tem os dados necessários para a inicialização de A que
serão passados ao construtor de A

No projeto Vestibulando podemos destacar:

- Jogador é uma Composição de Usuário, um caso em que TODO é responsável pela criação da PARTE  
- Questão(TODO) é responsável pela criação das Alternativa(PARTES)  

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

### Especialista

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

### Alta Coesão

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

### Baixo Acoplamento

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

