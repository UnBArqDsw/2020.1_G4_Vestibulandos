# Reutilização de Software

## Histórico de Versões

|   Data   | Versão |           Descrição           |             Autor(es)              |
|:--------:|:------:|:-----------------------------:|:----------------------------------:|
| 19/11/2020 | 0.1 | Criado o documento | Lucas Gomes |
| 19/11/2020 | 0.2 | Adicionado Introdução e Referências ao documento | Lucas Gomes |
| 19/11/2020 | 0.3 | Adicionado informações sobre o ServerFramework e Core ao documento | Lucas Gomes |
| 20/11/2020 | 0.4 | Adicionado informações sobre o MessagePack | Julio Litwin |
| 20/11/2020 | 0.5 | Adicionado informações sobre o Logging | Julio Litwin |
| 20/11/2020 | 0.6 | Adicionado informações sobre o Security | Julio Litwin |
| 20/11/2020 | 0.7 | Adicionado as vantagens na reutilização | Julio Litwin |

## Introdução
A reutilização de sofware é o uso de um sofware pré-elaboradas para a criação de um novo sofware, com o intuíto de melhorar a qualidade do sofware e diminuir o tempo de desenvolvimento. Este software pré-elaborado pode ser conceitos, módulos de um projeto, arquitetura e código fonte.  

Então, basicamente, reutilização de software é a reaplicação de informações e artefatos de uma aplicação já criada anteriormente em uma aplicação que usa conceitos semelhantes.

#### Vantagens e benefícios da reutilização

A reutilização otimiza as quatro variáveis que determinam o sucesso dos projetos de software: qualidade, custo, tempo e produtividade.

A prática da reutilização resulta na retenção do conhecimento na empresa e a coloca numa posição de maior competitividade na medida em que ela passa a conseguir desenvolver projetos de qualidade, no tempo acordado e com menores custos.

Um software que incorpora componentes reutilizados apresenta uma estrutura mais flexível o que facilita a manutenção e a evolução.

Os principais benefícios da reutilização, aceita pela maioria dos autores, são citados a seguir:

- Aumento da produção com a redução no esforço do desenvolvimento. 
- Redução dos custos e do prazo de entrega, pois se o esforço de desenvolvimento diminui logo o tempo de entrega também diminui e a quantidade de homens hora necessária a ser paga também.
- Como as soluções aplicadas foram anteriormente testadas e validadas, a probabilidade de que esteja correta é ainda maior, portanto temos um aumento da qualidade do produto final.
- Padronização dos produtos desenvolvidos pela empresa, pois como as soluções reusáveis foram desenvolvidas segundo uma padronização pré-definida, o reuso em um sistema provoca consequente padronização e agilidade na manutenção das aplicações devido a esta padronização da arquitetura. 


## Reutilizações de Software no Vestibulandos
Foi utilizado códigos já desenvolvidos em projetos pessoais e que se encaixam no contexto de desenvolvimento do Vestibulandos. Assim, essa reutilização aumentou reduziu significamente o tempo de desenvolvimento de alguns recursos da aplicação.

### 1. <a href="https://github.com/UnBArqDsw/2020.1_G4_Vestibulandos_Backend/tree/master/Libs/ServerFramework"> ServerFramework </a>

Esse framework é utilizado para a criação da arquitetura do servidor, além do gerenciamento dos workers das threads, do banco de dados e dos loggings. Como esse framework não terá nenhuma alteração, ele foi construído utilizando a idéia de Caixa Preta e, posteriormente, foi empacotado para ser utilizado na aplicação.

Utilizado apenas no Backend.

### 2. <a href="https://github.com/UnBArqDsw/2020.1_G4_Vestibulandos_Backend/tree/master/Libs/Core"> Core </a>

Sendo um framework muito importante na aplicação por possuir diversas funcionalidades importantes para o funcionamento da aplicação, várias classes utilizam de artefatos presentes neste framework além de herdar funcionalidades de algumas classes. Como possui herança e alguns métodos são alterados de acordo com o contexto que é utilizado, este framework se tornou um framework do tipo Caixa Branca. 

Algumas funcionalidades presentes neste framework:
- É usado na parte de networking, onde auxilia na criação de socket e gerenciamento de conexão;
- Possui uma classe para leitura de arquivos de configurações;
- Gerenciamento de banco de dados;
- Possui classes auxiliadoras, tais como classes extensoras de collections, random e singleton, por exemplo.

Utilizado apenas no Backend.

### 3. <a href="https://github.com/neuecc/MessagePack-CSharp"> MessagePack </a>

No Vestibulandos, é utilizado o MessagePack para serialização de pacotes, nas quais são trocados envios e recebimentos de buffer/data entre clientes e servidores. Nisto, foi escolhido o MessagePack para fazer a serialização e desserialização dos dados. MessagePack é um framework do tipo Caixa Branca.

Utilizado no Frontend e no Backend.

### 4. <a href="https://github.com/UnBArqDsw/2020.1_G4_Vestibulandos_Backend/tree/master/Libs/Logging"> Logging </a>

Logging é um pacote relacionado a log's dentro do projeto. A visão do pacote é facilitar toda a configuração, instanciamento e dentre outros relacionado ao log, na qual apenas a preocupação será apenas chamar as funções de logs a serem impressos e/ou salvos dentro do projeto. É um frameowrk do tipo Caixa Branca.

Utilizado apenas no Backend.

### 5. <a href="https://github.com/UnBArqDsw/2020.1_G4_Vestibulandos_Backend/tree/master/Libs/Security"> Security </a>

Security é um pacote relacionado a segurança de pacotes entre troca de dados pelos sockets. A ideia é que após a serialização pelo MessagePack, é adicionado mais uma camada de segurança, para dificultar a interceptação/recepção dos dados, terem alteração ou qualquer outra má intenção.

Utilizado no Frontend e no Backend.

## Referências
- Vídeo-aula da disciplina Arquitetura e Desenho de Software. 16 - Vídeo-Aula - ARQ - Reutilização de Software & Framework. Professora Milene Serrano. Universidade de Brasília.

- Slides do módulo Reutilização de Software (Framework) da disciplina Arquitetura e Desenho de Software. Professora Milene Serrano. Universidade de Brasília. 

- Reutilização de Sofware. DevMedia. Disponível em: https://www.devmedia.com.br/reutilizacao-de-software-revista-engenharia-de-software-magazine-39/21956. Acesso em: 19 de novembro. 2020.

