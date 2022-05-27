![image](https://user-images.githubusercontent.com/44026423/125207967-27f76b80-e266-11eb-9f03-de62c59f6699.png)

Este é um projeto de regressão.  

O conjunto de dados utilizado está disponível [neste link](https://www.kaggle.com/c/rossmann-store-sales). 

Uma apresentação em PowerPoint abordando as principais etapas do projeto está disponível [neste link](https://show.zohopublic.com/publish/8ulnq1503aa16c77f43a980e358d241332809).

[![forthebadge made-with-python](http://ForTheBadge.com/images/badges/made-with-python.svg)](https://www.python.org/)

# Entendimento do Negócio

A Rossmann é uma das maiores redes de drogarias da Europa, com cerca de 56 mil funcionários e mais de 4 mil unidades. Com o grande sucesso da marca, a empresa planeja uma reforma geral a fim de renovar e padronizar a estética de todas as suas lojas.

Para essa reforma ser possível a equipe de negócios da Rossmann precisaria contar com as previsões de vendas de todas as unidades para as próximas seis semanas, porém, atualmente a previsão de vendas é feita através de uma planilha Excel, considerando apenas a média das vendas, que em muitos casos, resulta em uma previsão muito distante do valor real. Diante disso, a empresa decidiu contratar um cientista de dados para ficar ciente de qual é a melhor solução para o problema.

Durante a reunião de negócios, o cientista de dados explicou os detalhes de uma previsão de vendas, bem como os metódos que poderiam ser utilizados. Ao final da reunião, ficou a cargo do cientista de dados montar um modelo de previsão de vendas para responder a seguinte questão:

**Quanto cada unidade venderá nas próximas seis semanas?**


# Dicionário de Dados

As seguintes suposições foram feitas sobre o problema de negócio:
- Os dados estão em formato estruturado e serão disponibilizados em arquivos "csv".
- Os dias em que as unidades estiveram fechadas serão removidos da análise.
- Apenas unidades com valores de vendas maiores que zero serão consideradas.
- Para as unidades que não possuirem a informação da distância do concorrente mais próximo (CompetitionDistance), iremos considerar um valor bem acima dos observados.

Além disso, também foi disponibilizado o dicionário de dados:

| Variáveis                        | Descrição                                                    |
| -------------------------------- | ------------------------------------------------------------ |
| Store                            | Código de identificação de cada unidade da drogaria          |                          
| DayOfWeek                        | Dia da semana do registro                                    |
| Date                             | Data do registro                                             |
| Sales                            | Total de vendas registrado no dia                            |
| Customers                        | Número de clientes no dia                                    |
| Open                             | Indica se a drogaria estava trabalhando no dia (0 = não, 1 = sim) |
| Promo                            | Indica se a drogaria estava participando da promoção "normal" |
| StateHoliday                     | Indica se a unidade trabalha durante os feriados |
| SchoolHoliday                    | Indica se a data do registro era epóca de férias escolares  |
| Assortment                       | Nível de sortimento de produtos da unidade (a, b, c) |
| CompetitionDistance              | Distância em metros da unidade do concorrente mais próximo |
| CompetitionOpenSince[Month/Year] | Ano e mês em que o concorrente mais próximo foi inaugurado |
| Promo2                           | Indica se a drogaria estava participando da promoção "estendida" (0 = não, 1 = sim) |
| Promo2Since[Week/Year]           | Semana e ano que a drogaria começou a participar da promoção estendida |
| PromoInterval                    | Descreve os intervalos que a promoção estendida é iniciada |

# Estratégia da Solução
Como estratégia para a solução dos problemas apresentados, definimos as seguintes etapas: 
- **1. Entendimento do Negócio:** nesta etapa inicial, o principal objetivo é compreender o problema de negócio e as necessidades do cliente.
- 
- **2. Entendimento dos Dados:** aqui, iremos tratar as principais inconsistências encontradas nos dados, também criaremos hipóteses de negócio e realizaremos uma análise detalhada em cada variável. 
- 
- **3. Engenharia de Atributos:** criaremos novas variáveis a fim de resumir as informações e facilitar o aprendizado dos modelos.

- **4. Pré-Processamento dos Dados:** nosso objetivo é preparar os dados para a aplicação dos modelos preditivos. Técnicas como redimensionamento e seleção das melhores variáveis serão aplicadas nessa etapa.

- **5. Modelagem Preditiva:** criaremos funções para treinar e avaliar o desempenho de três algoritmos de regressão.

- **6. Avaliação dos Modelos**: aqui, iremos comparar o desempenho dos modelos treinados. 

- **7. Conclusões Finais:** por fim, entregaremos o resultado final do projeto.

# TOP 3 Insights 

**H1. As unidades deveriam vender mais depois do dia 10 de cada mês.**  
**Verdadeiro:** as unidades vendem mais após o dia 10 de cada mês.  
![](reports/figures/H2.png)

**H4. As unidades deveriam vender mais ao longo dos anos.**  
**Falso:** vemos claramente uma queda no número de vendas ao longo dos anos. 
![](reports/figures/H9.png)

**H9. As unidades com concorrentes mais próximos deveriam vender menos.**  
**Falso:** unidades com concorrentes mais próximos vendem mais.
![](reports/figures/H11.png)
