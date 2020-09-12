# Plano de Análise de Riscos, Custos e Tempo

## Histórico de versão
| Data | Versão | Descrição | Autor(es) |
| :--: | :----: | :-------: | :-------: |
| 10/09/2020| 0.1 | Criação do documento | Guilherme Leal |
| 10/09/2020| 0.2 | Complemento do plano de análise | Guilherme Leal, Lucas Gomes |
| 11/09/2020| 0.3 | Edição dos tópicos sobre os riscos, probabilidade, impacto e prioridade | Lucas Gomes |
| 11/09/2020| 1.0 | Revisão das informações presentes no documento | Lucas Gomes |

## 1. Introdução
<p align="justify">A Análise de risco é o processo de decidir como abordar e planejar atividades de risco para o projeto. O plano descreve como identificar os riscos, análise qualitativa e quantitativa, plano de respostas, monitoramento e controle durante o ciclo de vida do projeto, sendo assim diminuir os impactos de riscos e otimizar o projeto.</p>

## 2. Processo de Gerenciamento de Riscos

<p align="justify">O processo de gerenciamento de riscos dá a visão do que será realizado com relação aos riscos.</p>

<ul>
    <li><b>Identificar riscos:</b> Elicitar e listar os riscos que podem afetar o desenvolvimento do projeto.</li>
    <li><b>Analisar qualitativamente:</b> Avaliar os riscos utlizando métricas, probabilidade e impacto, com o objetivo de priorizar aqueles que tem mais risco de acontecer.</li>  
    <li><b>Analisar quantitativamente:</b> Analisar de forma numérica as métricas definidas na análise qualitativa. Assim, é possível definir a prioridade para cada risco.
    <li><b>Planejar respostas aos riscos:</b> Planejar ações aos riscos elicitados levando em consideração a análise realizada anteriormente.</li>
    <li><b>Monitorar:</b> Monitorar os riscos durante o desenvolvimento do projeto, observando o que está causando-as e aplicando as ações para cada tipo de risco.</li>
</ul>

## 3. Categoria dos Riscos
<ul>
    <li>Técnico: Requisitos, Tecnologia, Confiabilidade, Usabilidade.</li>
    <li>Externo: Acessibilidade, Infraestrutura.</li>
    <li>Gerencial: Planejamento, Controle.</li>
</ul>

## 4. Definições de Probabilidade, Impacto dos Riscos e Matriz de Probabilidade e Impacto

<p align="justify">Para qualificar os riscos elicitados é necessário definir pesos para os intervalos da probabilidade e das opções de impacto. Definido a probabilidade e impacto de cada risco, é possível definir a prioridade de cada risco.</p>

<p align="justify"><b> Probabilidade:</b></p>

| Probabilidade (P) | Intervalo | Peso | 
| :--: | :----: | :-------: | 
| Nulo |	0% | 0 |
| Muito Baixa |	1% a 20%| 1 |
| Baixa |	21% a 40%| 2 |
| Moderada |	41% a 60%| 3 |
| Alta |	61% a 80%| 4 |
| Muito Alta |	81% a 100%| 5 |

<p align="justify"><b> Impacto:</b></p>

| Impacto (I) | Descrição | Peso | 
| :--: | :----: | :-------: | 
|Muito Baixo|	Quase imperceptível ao projeto|	1|
|Baixo|	Pouco impacto no projeto	|2|
|Moderado|	Perceptível no projeto, mas sem grandes consequências	|3|
|Alto|	Dificulta o desenvolvimento do projeto	|4|
|Muito Alto|	Impossibilita prosseguir com projeto	|5|


<p align="justify"><b> Matriz Probabilidade e Impacto:</b></p>
Os valores da matriz é definido pela multiplicação da probabilidade pelo impacto. 

|P \ I|	Muito Baixo|	Baixo|	Moderado|	Alto|	Muito Alto|
| :--:|:------:|:---:|:---:|:---:|:---:|
|Muito Baixa|	1|	2|	3|	4|	5|
|Baixa|	2|	4|	6|	8|	10|
|Moderada|	3|	6|	9|	12|	15|
|Alta|	4|	8|	12|	16|	20|
|Muito Alta|	5|	10|	15|	20|	25|

<p align="justify"><b> Prioridade:</b></p>
O intervalo é retirada da matriz de probabilidade e impacto, assim é possível definir o nível de prioridade para cada risco.

| Prioridade| Intervalo |  
| :--: | :----: | 
|Baixa|	1 - 5|
|Média|	6 - 15|
|Alta|	16 - 25|

## 5. Riscos:

### 5.1 Riscos Negativos

| **ID** | **Risco** | **Descrição** | 
| :-----:| :-------: | :-----------: |
|**RN01**| Acessibilidade | Acesso a equipamentos e meios de conexão de internet. |
|**RN02**| Pandemia |Risco de doença, morte ou lesão de indivíduo chave.|
|**RN03**| Operacional |Perda de acesso a ativos essenciais para o sistema.|
|**RN04**| Escopo |Mudanças no escopo.|
|**RN05**| Tecnologias utilizadas |Membros não utilizaram uma ou mais tecnologias que serão utilizadas no projeto.|
|**RN06**| Comunicação da equipe | Os integrantes não possuem uma boa comunicação entre si. |
|**RN07**| Disponibilidade dos integrantes | Os horários dos integrantes não são compatíveis para realizar reuniões síncronas.|
|**RN08**| Brigas internas | Discussões entre integrantes. |



### 5.2 Riscos Positivos
| **ID** | **Risco** | **Descrição** | 
| :-----:| :-------: | :-----------: |
|**RP01**| Alta produtividade | O grupo não deixar para entregar os artefatos próximo a deadline. |
|**RP02**| Experiência com tecnologia | Algum membro do grupo ter experiência com alguma das tecnologias escolhidas.|
|**RP03**| Domínio do tema do projeto | O grupo ter domínio do tema do projeto e de todos os requisitos para o desenvolvimento dele.|


## 6. Análise e ação aos riscos
### 6.1 Riscos Negativos
| **ID** | **Probabilidade** | **Impacto** |  **Prioridade** |  **Ação** | 
| :-----:| :-------: | :-----------: | :-----------: | :-----------: |
|**RN01**| Baixa ( 2 ) | Moderado ( 3 ) | Média ( 6 ) | Prevenir - Evitar entrar nessa situação, a menos que seja causada por terceiros. |
|**RN02**| Moderada ( 3 ) | Alto ( 4 ) | Média ( 12 ) | Mitigar - Redistribuição das tarefas dadas.  |
|**RN03**| Baixa ( 2 ) | Muito alto ( 5 ) | Média ( 8 ) | Mitigar - Procurar novos ativos para dar continuidade ao projeto. |
|**RN04**| Muito baixa ( 1 ) | Muito alto ( 5 ) | Baixa ( 5 ) | Aceitar - Entender o novo escopo e atualizar artefatos criados para o antigo escopo. |
|**RN05**| Alta ( 4 ) | Muito alto ( 5 ) | Alta ( 20 ) | Mitigar - Integrantes que possuem alguma experiência auxiliar os outros integrantes ou estipular atividades simples para ganhar conhecimento sobre a tecnologia. |
|**RN06**| Moderada ( 3 ) | Alto ( 5 ) | Média ( 15 ) | Prevenir - Procurar uma maior interação de todo o grupo sem excluir integrantes e chamando para discussões integrantes "tímidos". |
|**RN07**| Baixa ( 2 ) | Alto ( 5 ) | Média ( 10 ) | Prevenir - Definir horários acessíveis para todos os integrantes. |
|**RN08**| Muito baixa ( 1 ) | Moderado ( 5 ) | Baixa ( 5 ) | Prevenir - Respeitar o espaço de cada membro e procurar ter empatia por eles. |

### 6.2 Riscos Positivos
| **ID** | **Probabilidade** | **Impacto** |  **Prioridade** |  **Ação** | 
| :-----:| :-------: | :-----------: | :-----------: | :-----------: |
|**RP01**| Moderada ( 3 ) | Muito alto ( 5 ) | Média ( 15 ) | Continuar aproveitando o tempo para realizar as entregas sem pressão. |
|**RP02**| Moderada ( 3 ) | Alto ( 4 ) | Média ( 12 ) | Ajudar o restante do grupo ensinando-os sobre a tecnologia em questão. |
|**RP03**| Muito baixa ( 1 ) | Muito alto ( 5 ) | Baixa ( 5 ) | Estudar sobre o projeto para ter conhecimento sobre o projeto.  |

## 7. Referências 

- PMI. A Guide to the Project Managent Body of Knowledge (PMBOK Guide). Pennsylvania: PMI, 2008.

- ABNT. NBR ISO 1006, Gestão da qualidade, diretrizes para a 
qualidade no gerenciamento de projetos. Rio de Janeiro: ABNT,2001.

- Wiki SpaceShooter https://github.com/DesenhoMaster2017/SpaceShooter/wiki/Plano-de-Riscos último acesso em 11/09/2020.



