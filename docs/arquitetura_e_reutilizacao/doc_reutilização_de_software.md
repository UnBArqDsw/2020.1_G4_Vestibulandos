# Reutilização de Software

## Histórico de Versões

|   Data   | Versão |           Descrição           |             Autor(es)              |
|:--------:|:------:|:-----------------------------:|:----------------------------------:|
| 19/11/2020 | 0.1 | Criado o documento | Lucas Gomes |
| 19/11/2020 | 0.2 | Adicionado Introdução e Referências ao documento | Lucas Gomes |
| 19/11/2020 | 0.3 | Adicionado informações sobre o ServerFramework e Core ao documento | Lucas Gomes |
| 20/11/2020 | 0.4 | Adicionado informações sobre o MessagePack | Julio Litwin |
| 20/11/2020 | 0.5 | Adicionado informações sobre o Logging | Julio Litwin |

## Introdução
A reutilização de sofware é o uso de um sofware pré-elaboradas para a criação de um novo sofware, com o intuíto de melhorar a qualidade do sofware e diminuir o tempo de desenvolvimento. Este software pré-elaborado pode ser conceitos, módulos de um projeto, arquitetura e código fonte.  

Então, basicamente, reutilização de software é a reaplicação de informações e artefatos de uma aplicação já criada anteriormente em uma aplicação que usa conceitos semelhantes.

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

## Referências
- Vídeo-aula da disciplina Arquitetura e Desenho de Software. 16 - Vídeo-Aula - ARQ - Reutilização de Software & Framework. Professora Milene Serrano. Universidade de Brasília.

- Slides do módulo Reutilização de Software (Framework) da disciplina Arquitetura e Desenho de Software. Professora Milene Serrano. Universidade de Brasília. 

- Reutilização de Sofware. DevMedia. Disponível em: https://www.devmedia.com.br/reutilizacao-de-software-revista-engenharia-de-software-magazine-39/21956. Acesso em: 19 de novembro. 2020.

