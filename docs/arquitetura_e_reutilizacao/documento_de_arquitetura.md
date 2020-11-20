# Documento de Arquitetura de Software

## Histórico de Versões

|   Data   | Versão |           Descrição           |             Autor(es)              |
|:--------:|:------:|:-----------------------------:|:----------------------------------:|
| 19/11/2020 | 0.1 | Criado o documento | Lucas Gomes |
| 19/11/2020 | 0.2 | Adicionando introdução | João Pedro |
| 19/11/2020 | 0.2 | Adicionando representação arquitetural | João Pedro e Rodrigo Canela |


# Introdução

## Finalidade

A finalidade deste artefato é evidenciar as decisões pertinentes à arquitetura do software. Englobando desde escolhas de alto nível, tecnologias e componentes, até o nível de código. 

## Escopo
Este documento foi construído sobre a visão arquitetural utilizada na implementação do Vestibulandos. Nele serão expostas as visões de caso de uso, lógica, dados e implementação. 


# Representação Arquitetural
A arquitetura utilizada no Vestibulandos, de modo geral, segue o modelo Cliente-Servidor, sendo o responsável pela manutenção das informações (servidor) provenientes da plataforma onde ocorrem as partidas e a inserção de novas questões (cliente).


## Referências