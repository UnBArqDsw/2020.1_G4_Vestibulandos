# First Things First

## Histórico de Versões

|   Data   | Versão |           Descrição           |             Autor(es)              |
|:--------:|:------:|:-----------------------------:|:----------------------------------:|
| 28/09/2020 | 0.1 | Adicionado o documento | João Pedro |

## Introdução
"First Things First" uma ferramenta que pode ajudar a tomar decisões de troca de requisitos, quando se avaliam novas necessidades. Estimando a prioridade usando o modelo já preenchido para o projeto, podemos verificar como as novas necessidades se comportam em relação aos requisitos existentes. Com isso, podemos escolher a sequência de implementação apropriada.

## Cálculo
Os atributos relativos foram pontuados de 1 a 9, sendo os pesos atribuídos para efeitos de cálculo das porcentagens e prioridade representados na tabela a seguir.

Atributo | Peso
|--------| --|
|Benefício relativo| 2|
|Penalidade relativa| 1|
|Custo relativo| 1|
|Risco relativo| 0.5|

Cálculo do valor: benefício relativo * peso do benefício + penalidade relativa * peso da penalidade

Cálculo da prioridade: valor(%) / (custo(%) * peso do custo relativo + risco(%) * peso do risco relativo)

## Resultado
US #|Benefício relativo |Penalidade Relativa |Valor total |Valor (%) |Custo Relativo |Custo (%)|Risco relativo |Risco(%) |Prioridade|
|--|---|---|---|---|---|---|---|---|---|
|01| 9| 9| 27| 6,2068| 3| 5,8823| 3| 3,7037| 0,80251869953388543|
|02| 7| 5| 19| 4,3678| 3| 5,8823| 3| 3,7037| 0,56474208542632353|
|03| 8| 5| 21| 4,8275| 2| 3,9215| 3| 3,7037| 0,83616964154260524|
|04| 9| 8| 26| 5,9770| 5| 9,8039| 7| 8,6419| 0,42315493615861407|
|05| 8| 7| 23| 5,2873| 2| 3,9215| 4| 4,9382| 0,82735580383688542|
|06| 9| 8| 26| 5,9770| 3| 5,8823| 4| 4,9382| 0,71568838757573580|
|07| 5| 4| 14| 3,2183| 2| 3,9215| 3| 3,7037| 0,55744065403968233|
|08| 5| 3| 13| 2,9885| 2| 3,9215| 3| 3,7037| 0,51763707379597633|
|09| 2| 2| 6 | 1,3793| 2| 3,9215| 2| 2,4691| 0,26751098224415977|
|10| 7| 4| 18| 4,1379| 1| 1,9607| 3| 3,7037| 1,08533658574969508|
|11| 7| 5| 19| 4,3678| 2| 3,9215| 3| 3,7037| 0,75654516008902976|
|12| 8| 6| 22| 5,0574| 3| 5,8823| 5| 6,1728| 0,56389443286094974|
|13| 7| 5| 19| 4,3678| 2| 3,9215| 5| 6,1728| 0,62326802608484710|
|14| 7| 5| 19| 4,3678| 2| 3,9215| 5| 6,1728| 0,62326802608484710|
|15| 6| 4| 16| 3,6781| 1| 1,9607| 3| 3,7037| 0,96473488872277084|
|16| 5| 4| 14| 3,2183| 1| 1,9607| 2| 2,4691| 1,00721383303340896|
|17| 9| 7| 25| 5,7471| 2| 3,9215| 3| 3,7037| 0,99545324638208319|
|18| 9| 8| 26| 5,9770| 2| 3,9215| 4| 4,9382| 0,93527994241542265|
|19| 7| 4| 18| 4,1379| 2| 3,9215| 3| 3,7037| 0,71672425887916027|
|20| 8| 6| 22| 5,0574| 3| 5,8823| 5| 6,1728| 0,56389443286094974|
|21| 7| 6| 20| 4,5977| 4| 7,8431| 5| 6,1728| 0,42066883206002104|
|22| 8| 6| 22| 5,0574| 2| 3,9215| 3| 3,7037| 0,87599054275247473|
**Total**| 157| 121| 435| 100| 51| 100| 81| | --|

## Referências
- First Things First: Prioritizing Requirements. Karl E. Wiegers, 1999. Disponível em <https://www.processimpact.com/articles/prioritizing.pdf>. Último acesso em 28/09/2020.